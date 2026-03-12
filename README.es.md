[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

🌐 [English](README.md) | [Français](README.fr.md) | **Español**

# wshm (wishmaster)

> Los deseos de tu repositorio son órdenes.

Agente GitHub impulsado por IA para mantenedores OSS. Triaje de issues, corrección automática de bugs simples, análisis de PRs, resolución de conflictos, generación de informes. Escrito en Rust. Cero infraestructura. Un solo binario.

## Instalación

```bash
cargo install wshm
```

O compilar desde el código fuente:

```bash
git clone https://github.com/pszymkowiak/wshm.git
cd wshm
cargo build --release
```

## Inicio rápido

```bash
# 1. Iniciar sesión (GitHub + proveedor IA)
wshm login

# 2. Inicializar configuración
wshm config init

# 3. Sincronizar y triaje (simulación)
wshm sync
wshm triage

# 4. Aplicar acciones
wshm triage --apply
```

## Modo Daemon (24/7)

wshm puede ejecutarse como daemon persistente que reacciona a eventos de GitHub en tiempo real.

### Modo Webhook (recomendado)

Requiere una URL pública (IP, dominio o túnel como ngrok/cloudflare).

```bash
# Configuración
wshm login
wshm config init

# Iniciar daemon
wshm daemon --apply --secret "whsec_your_webhook_secret"
```

Luego configura un webhook de GitHub en tu repositorio:
- **URL:** `http://your-server:3000/webhook`
- **Tipo de contenido:** `application/json`
- **Secret:** igual que `--secret`
- **Eventos:** Issues, Pull requests, Comentarios de issues

### Modo Polling (sin IP pública)

Usa la API de GitHub Events — no requiere configuración de webhook.

```bash
# Iniciar daemon con polling (sin servidor HTTP)
wshm daemon --apply --poll --no-server

# O híbrido: webhook + polling de respaldo
wshm daemon --apply --poll
```

| Flag | Descripción |
|------|-------------|
| `--apply` | Ejecutar acciones (simulación por defecto) |
| `--poll` | Activar polling via API de GitHub Events |
| `--poll-interval <N>` | Intervalo de polling en segundos (defecto: 30) |
| `--no-server` | Desactivar el servidor HTTP webhook |
| `--bind <addr>` | Dirección de escucha (defecto: `0.0.0.0:3000`) |
| `--secret <s>` | Secreto HMAC del webhook |

### Lo que hace el Daemon

| Disparador | Acción |
|------------|--------|
| Nueva issue abierta | Triaje automático (clasificar, etiquetar, comentar) |
| PR nueva/actualizada | Análisis IA (tipo, riesgo, checklist de revisión) |
| Comentario `/wshm triage` | Re-triaje de la issue |
| Comentario `/wshm analyze` | Re-análisis del PR |
| Comentario `/wshm review` | Revisión de código IA inline |
| Comentario `/wshm label <nombre>` | Agregar una etiqueta |
| Comentario `/wshm unlabel <nombre>` | Eliminar una etiqueta |
| Comentario `/wshm queue` | Posición en la cola de merge |
| Comentario `/wshm health` | Chequeo de salud del PR |
| Comentario `/wshm help` | Listar comandos disponibles |
| Cada 5 min (planificador) | Sync incremental + triaje de issues sin clasificar |

### Verificación de salud

```bash
curl http://localhost:3000/health
# {"status":"ok","apply":true,"pending_events":0,"repo":"owner/repo"}
```

## Autenticación

### Inicio de sesión interactivo

```bash
wshm login              # Configurar GitHub + proveedor IA
wshm login --github     # Solo GitHub (usa gh auth login)
wshm login --ai         # Solo proveedor IA (solicita clave API)
wshm login --status     # Mostrar estado de autenticación
```

Las credenciales se almacenan en `.wshm/credentials` (chmod 600, gitignored).

### Prioridad de tokens

| Prioridad | GitHub | IA |
|-----------|--------|----|
| 1 | Variable de entorno `GITHUB_TOKEN` / `WSHM_TOKEN` | Variable de entorno `ANTHROPIC_API_KEY` |
| 2 | `gh auth token` (gh CLI) | — |
| 3 | `.wshm/credentials` (via `wshm login`) | `.wshm/credentials` |

### Proveedores IA soportados

| Proveedor | Variable de entorno | Modelos |
|-----------|---------------------|---------|
| `anthropic` (defecto) | `ANTHROPIC_API_KEY` | claude-sonnet-4-20250514, etc. |
| `openai` | `OPENAI_API_KEY` | gpt-4o, etc. |
| `google` | `GOOGLE_API_KEY` | gemini-2.5-pro, etc. |
| `mistral` | `MISTRAL_API_KEY` | mistral-large, etc. |
| `groq` | `GROQ_API_KEY` | llama-3, etc. |
| `deepseek` | `DEEPSEEK_API_KEY` | deepseek-chat, etc. |
| `xai` | `XAI_API_KEY` | grok-3, etc. |
| `ollama` | — (local) | Cualquier modelo Ollama |
| `local` | — | phi4-mini, smollm3-3b, qwen3-4b, etc. |

## Referencia CLI

| Comando | Descripción |
|---------|-------------|
| `wshm` | Mostrar estado desde caché (instantáneo) |
| `wshm sync` | Forzar sincronización completa desde GitHub |
| `wshm login` | Autenticarse con GitHub + proveedor IA |
| `wshm triage [--issue <N>]` | Clasificar issues (o una sola) |
| `wshm pr [--pr <N>]` | Analizar PRs (o uno solo) |
| `wshm queue` | Mostrar cola de merge clasificada |
| `wshm conflicts` | Detectar PRs en conflicto |
| `wshm run` | Ciclo completo: triaje + análisis + cola + conflictos |
| `wshm review [--pr <N>]` | Revisión de código IA inline en diffs de PR |
| `wshm health` | Salud de PRs: duplicados, PRs obsoletos/zombis |
| `wshm fix --issue <N>` | Generar automáticamente un PR de corrección |
| `wshm report` | Generar informe (md/html/pdf) |
| `wshm changelog` | Generar changelog desde PRs mergeados |
| `wshm dashboard` | Generar dashboard de métricas (HTML + gráficos) |
| `wshm daemon` | Iniciar daemon persistente (webhook + polling) |
| `wshm config init` | Crear template `.wshm/config.toml` |
| `wshm model list` | Listar modelos IA locales disponibles |
| `wshm model pull <nombre>` | Descargar un modelo para inferencia local |

### Flags globales

| Flag | Descripción |
|------|-------------|
| `--apply` | Ejecutar acciones (simulación por defecto) |
| `--offline` | Omitir sync de GitHub, usar solo caché |
| `--verbose` / `-v` | Salida detallada |
| `--json` | Salida JSON para scripting |
| `--repo <owner/repo>` | Forzar repositorio objetivo |

## Personalización

Personaliza la identidad del bot para tu organización.

```toml
# .wshm/config.toml
[branding]
name = "jarvis"                                # Nombre del bot en comentarios
url = "https://acme.com/jarvis"                # Enlace en pies de página
avatar_url = "https://acme.com/logo.png"       # Logo en encabezados
tagline = "Tu asistente IA para repositorios"  # Subtítulo en encabezados
command_prefix = "/jarvis"                     # Prefijo de comandos slash
footer_template = "*{action} por [{name}]({url})*"  # Pie de página personalizado
```

## Auto-Fix con Sandbox Podman

wshm puede generar automáticamente PRs de corrección a partir de issues usando Claude Code o Codex, opcionalmente dentro de un contenedor Podman rootless.

```bash
# Construir la imagen sandbox
podman build -f Dockerfile.sandbox -t wshm-sandbox:latest .

# Simulación (muestra lo que ocurriría)
wshm fix --issue 42 --docker

# Ejecutar Claude Code en sandbox Podman
wshm fix --issue 42 --docker --apply

# Usar Codex en su lugar
wshm fix --issue 42 --docker --tool codex --apply
```

### Inyección de credenciales (orden de prioridad)

| Prioridad | Fuente | Cómo | Contexto |
|-----------|--------|------|----------|
| 1 | `CLAUDE_CREDENTIALS_JSON` | Secret GitHub -> archivo temp -> montaje volumen | CI |
| 2 | `~/.claude/.credentials.json` | Montaje volumen (`-v ~/.claude:....:ro`) | Local (Max/Pro) |
| 3 | `ANTHROPIC_API_KEY` | Variable de entorno (`-e`) | Clave API de respaldo |

**Seguridad** (Podman rootless, como OpenClaw):
- `--userns=keep-id` (sin root)
- `--cap-drop ALL`
- `--pids-limit 256`
- Credenciales montadas en solo lectura

## Informes

```bash
# Informe Markdown
wshm report --format md

# Informe HTML (métricas SLA, salud de PRs, duplicados)
wshm report --format html --output report.html

# Informe PDF
wshm report --format pdf --output report.pdf

# Ciclo completo y luego informe
wshm run --apply
wshm report --format html
```

Los informes incluyen: triaje de issues, análisis de PRs, clasificación de cola de merge, seguimiento SLA, salud de PRs (duplicados, obsoletos/zombis).

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

## Despliegue en una VM

```bash
# 1. Clonar tu repositorio
git clone git@github.com:owner/repo.git && cd repo

# 2. Instalar wshm
cargo install wshm

# 3. Iniciar sesión
wshm login

# 4. Inicializar config
wshm config init

# 5. Iniciar daemon (ejecuta 24/7)
wshm daemon --apply --poll

# O con webhook + systemd
wshm daemon --apply --secret "$WSHM_WEBHOOK_SECRET"
```

### Servicio Systemd

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

## Arquitectura

Ver [CLAUDE.md](CLAUDE.md) para el documento de arquitectura completo, incluyendo:

- Estrategia de caché SQLite y reglas de sincronización
- Los 4 pipelines (triaje, análisis PR, cola de merge, resolución de conflictos)
- Referencia de configuración
- Estructura del proyecto
- Patrones de integración IA
- Principios de seguridad

## Licencia

[MIT](LICENSE)
