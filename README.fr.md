[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

🌐 [English](README.md) | **Français** | [Español](README.es.md)

# wshm (wishmaster)

> Les souhaits de votre dépôt sont des ordres.

Agent GitHub propulsé par l'IA pour les mainteneurs OSS. Triage des issues, correction automatique des bugs simples, analyse des PRs, résolution de conflits, génération de rapports. Écrit en Rust. Zéro infra. Un seul binaire.

## Installation

```bash
cargo install wshm
```

Ou compiler depuis les sources :

```bash
git clone https://github.com/pszymkowiak/wshm.git
cd wshm
cargo build --release
```

## Démarrage rapide

```bash
# 1. Connexion (GitHub + fournisseur IA)
wshm login

# 2. Initialiser la configuration
wshm config init

# 3. Sync & triage (simulation)
wshm sync
wshm triage

# 4. Appliquer les actions
wshm triage --apply
```

## Mode Daemon (H24)

wshm peut fonctionner en daemon persistant qui réagit aux événements GitHub en temps réel.

### Mode Webhook (recommandé)

Nécessite une URL publique (IP, domaine, ou tunnel type ngrok/cloudflare).

```bash
# Configuration
wshm login
wshm config init

# Démarrer le daemon
wshm daemon --apply --secret "whsec_your_webhook_secret"
```

Configurez ensuite un webhook GitHub sur votre dépôt :
- **URL :** `http://your-server:3000/webhook`
- **Type de contenu :** `application/json`
- **Secret :** identique à `--secret`
- **Événements :** Issues, Pull requests, Commentaires d'issues

### Mode Polling (pas besoin d'IP publique)

Utilise l'API GitHub Events — aucune configuration webhook requise.

```bash
# Démarrer le daemon en polling (pas de serveur HTTP)
wshm daemon --apply --poll --no-server

# Ou hybride : webhook + polling en secours
wshm daemon --apply --poll
```

| Flag | Description |
|------|-------------|
| `--apply` | Exécuter les actions (simulation par défaut) |
| `--poll` | Activer le polling via l'API GitHub Events |
| `--poll-interval <N>` | Intervalle de polling en secondes (défaut : 30) |
| `--no-server` | Désactiver le serveur HTTP webhook |
| `--bind <addr>` | Adresse d'écoute (défaut : `0.0.0.0:3000`) |
| `--secret <s>` | Secret HMAC du webhook |

### Ce que fait le Daemon

| Déclencheur | Action |
|-------------|--------|
| Nouvelle issue ouverte | Triage automatique (classifier, labelliser, commenter) |
| PR nouvelle/mise à jour | Analyse IA (type, risque, checklist de revue) |
| Commentaire `/wshm triage` | Re-triage de l'issue |
| Commentaire `/wshm analyze` | Re-analyse de la PR |
| Commentaire `/wshm review` | Revue de code IA inline |
| Commentaire `/wshm label <nom>` | Ajouter un label |
| Commentaire `/wshm unlabel <nom>` | Supprimer un label |
| Commentaire `/wshm queue` | Position dans la file de merge |
| Commentaire `/wshm health` | Bilan de santé de la PR |
| Commentaire `/wshm help` | Lister les commandes disponibles |
| Toutes les 5 min (planificateur) | Sync incrémentale + triage des issues non triées |

### Vérification de santé

```bash
curl http://localhost:3000/health
# {"status":"ok","apply":true,"pending_events":0,"repo":"owner/repo"}
```

## Authentification

### Connexion interactive

```bash
wshm login              # Configurer GitHub + fournisseur IA
wshm login --github     # GitHub uniquement (utilise gh auth login)
wshm login --ai         # Fournisseur IA uniquement (demande la clé API)
wshm login --status     # Afficher le statut d'authentification
```

Les identifiants sont stockés dans `.wshm/credentials` (chmod 600, gitignored).

### Priorité des tokens

| Priorité | GitHub | IA |
|----------|--------|----|
| 1 | Variable d'env `GITHUB_TOKEN` / `WSHM_TOKEN` | Variable d'env `ANTHROPIC_API_KEY` |
| 2 | `gh auth token` (gh CLI) | — |
| 3 | `.wshm/credentials` (via `wshm login`) | `.wshm/credentials` |

### Fournisseurs IA supportés

| Fournisseur | Variable d'env | Modèles |
|-------------|----------------|---------|
| `anthropic` (défaut) | `ANTHROPIC_API_KEY` | claude-sonnet-4-20250514, etc. |
| `openai` | `OPENAI_API_KEY` | gpt-4o, etc. |
| `google` | `GOOGLE_API_KEY` | gemini-2.5-pro, etc. |
| `mistral` | `MISTRAL_API_KEY` | mistral-large, etc. |
| `groq` | `GROQ_API_KEY` | llama-3, etc. |
| `deepseek` | `DEEPSEEK_API_KEY` | deepseek-chat, etc. |
| `xai` | `XAI_API_KEY` | grok-3, etc. |
| `ollama` | — (local) | Tout modèle Ollama |
| `local` | — | phi4-mini, smollm3-3b, qwen3-4b, etc. |

## Référence CLI

| Commande | Description |
|----------|-------------|
| `wshm` | Afficher le statut depuis le cache (instantané) |
| `wshm sync` | Forcer une synchronisation complète depuis GitHub |
| `wshm login` | S'authentifier auprès de GitHub + fournisseur IA |
| `wshm triage [--issue <N>]` | Classifier les issues (ou une seule) |
| `wshm pr [--pr <N>]` | Analyser les PRs (ou une seule) |
| `wshm queue` | Afficher la file de merge classée |
| `wshm conflicts` | Détecter les PRs en conflit |
| `wshm run` | Cycle complet : triage + analyse + file + conflits |
| `wshm review [--pr <N>]` | Revue de code IA inline sur les diffs de PR |
| `wshm health` | Santé des PRs : doublons, PRs obsolètes/zombies |
| `wshm fix --issue <N>` | Générer automatiquement une PR de correction |
| `wshm report` | Générer un rapport (md/html/pdf) |
| `wshm changelog` | Générer un changelog depuis les PRs mergées |
| `wshm dashboard` | Générer un tableau de bord métriques (HTML + graphiques) |
| `wshm daemon` | Démarrer le daemon persistant (webhook + polling) |
| `wshm config init` | Créer le template `.wshm/config.toml` |
| `wshm model list` | Lister les modèles IA locaux disponibles |
| `wshm model pull <nom>` | Télécharger un modèle pour l'inférence locale |

### Flags globaux

| Flag | Description |
|------|-------------|
| `--apply` | Exécuter les actions (simulation par défaut) |
| `--offline` | Ignorer la sync GitHub, utiliser le cache uniquement |
| `--verbose` / `-v` | Sortie détaillée |
| `--json` | Sortie JSON pour le scripting |
| `--repo <owner/repo>` | Forcer le dépôt cible |

## Personnalisation

Personnalisez l'identité du bot pour votre organisation.

```toml
# .wshm/config.toml
[branding]
name = "jarvis"                                # Nom du bot dans les commentaires
url = "https://acme.com/jarvis"                # Lien dans les pieds de page
avatar_url = "https://acme.com/logo.png"       # Logo dans les en-têtes
tagline = "Votre assistant IA pour dépôts"     # Sous-titre dans les en-têtes
command_prefix = "/jarvis"                     # Préfixe des commandes slash
footer_template = "*{action} par [{name}]({url})*"  # Pied de page personnalisé
```

## Auto-Fix avec Sandbox Podman

wshm peut générer automatiquement des PRs de correction à partir d'issues en utilisant Claude Code ou Codex, optionnellement dans un conteneur Podman rootless.

```bash
# Construire l'image sandbox
podman build -f Dockerfile.sandbox -t wshm-sandbox:latest .

# Simulation (montre ce qui se passerait)
wshm fix --issue 42 --docker

# Exécuter Claude Code dans le sandbox Podman
wshm fix --issue 42 --docker --apply

# Utiliser Codex à la place
wshm fix --issue 42 --docker --tool codex --apply
```

### Injection des identifiants (ordre de priorité)

| Priorité | Source | Comment | Contexte |
|----------|--------|---------|----------|
| 1 | `CLAUDE_CREDENTIALS_JSON` | Secret GitHub -> fichier temp -> montage volume | CI |
| 2 | `~/.claude/.credentials.json` | Montage volume (`-v ~/.claude:....:ro`) | Local (Max/Pro) |
| 3 | `ANTHROPIC_API_KEY` | Variable d'env (`-e`) | Clé API de secours |

**Sécurité** (Podman rootless, comme OpenClaw) :
- `--userns=keep-id` (pas de root)
- `--cap-drop ALL`
- `--pids-limit 256`
- Identifiants montés en lecture seule

## Rapports

```bash
# Rapport Markdown
wshm report --format md

# Rapport HTML (métriques SLA, santé des PRs, doublons)
wshm report --format html --output report.html

# Rapport PDF
wshm report --format pdf --output report.pdf

# Cycle complet puis rapport
wshm run --apply
wshm report --format html
```

Les rapports incluent : triage des issues, analyse des PRs, classement de la file de merge, suivi SLA, santé des PRs (doublons, obsolètes/zombies).

## GitHub Action

```yaml
name: wshm
on:
  issues:
    types: [opened]
  pull_request:
    types: [opened, synchronize]
  issue_comment:
    types: [created]
  schedule:
    - cron: '0 */6 * * *'

jobs:
  wshm:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: pszymkowiak/wshm@main
        with:
          github-token: ${{ secrets.GITHUB_TOKEN }}
          ai-api-key: ${{ secrets.ANTHROPIC_API_KEY }}
          claude-credentials-json: ${{ secrets.CLAUDE_CREDENTIALS_JSON }}
```

## Déploiement sur une VM

```bash
# 1. Cloner votre dépôt
git clone git@github.com:owner/repo.git && cd repo

# 2. Installer wshm
cargo install wshm

# 3. Connexion
wshm login

# 4. Initialiser la config
wshm config init

# 5. Démarrer le daemon (tourne 24/7)
wshm daemon --apply --poll

# Ou avec webhook + systemd
wshm daemon --apply --secret "$WSHM_WEBHOOK_SECRET"
```

### Service Systemd

```ini
# /etc/systemd/system/wshm.service
[Unit]
Description=wshm daemon
After=network.target

[Service]
Type=simple
User=deploy
WorkingDirectory=/home/deploy/repo
ExecStart=/home/deploy/.cargo/bin/wshm daemon --apply --poll
Restart=always
RestartSec=10
Environment=RUST_LOG=info

[Install]
WantedBy=multi-user.target
```

```bash
sudo systemctl enable --now wshm
journalctl -u wshm -f
```

## Architecture

Voir [CLAUDE.md](CLAUDE.md) pour le document d'architecture complet, incluant :

- Stratégie de cache SQLite et règles de synchronisation
- Les 4 pipelines (triage, analyse PR, file de merge, résolution de conflits)
- Référence de configuration
- Structure du projet
- Patterns d'intégration IA
- Principes de sécurité

## Licence

[MIT](LICENSE)
