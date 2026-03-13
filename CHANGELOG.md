# Changelog

## 0.1.0 (2026-03-13)


### Features

* add 15 AI providers (Anthropic, OpenAI, Gemini, Mistral, Groq, DeepSeek, xAI, Together, Fireworks, Perplexity, Cohere, OpenRouter, Ollama, Azure, custom) ([a0d8e2e](https://github.com/pszymkowiak/wshm/commit/a0d8e2eb00c4c99d565c036c87297838f4ffbf5f))
* add CI/CD workflows and systemd install/uninstall ([#1](https://github.com/pszymkowiak/wshm/issues/1)) ([53b43c4](https://github.com/pszymkowiak/wshm/commit/53b43c46cf9350f3044822a93c89dd0e537f0317))
* add Claude OAuth login (Max/Pro/Team subscription support) ([0f80031](https://github.com/pszymkowiak/wshm/commit/0f80031e7d454e1e3d775e90bee074d6123c2475))
* add security audit + command injection scan + smoke test to CI ([3dd8b87](https://github.com/pszymkowiak/wshm/commit/3dd8b87b8b0d8ef49347b0d6657061206e915189))
* auto-fix security hardening ([#7](https://github.com/pszymkowiak/wshm/issues/7)) ([50ae379](https://github.com/pszymkowiak/wshm/commit/50ae379c7e2f847767cec951add93d98909c7dc5))
* auto-fix trigger from triage pipeline ([#6](https://github.com/pszymkowiak/wshm/issues/6)) ([bee1057](https://github.com/pszymkowiak/wshm/commit/bee10573c9ce38c634d1e9c643815e8e5426b2e2))
* bot-style comments with emojis and automated banner ([#5](https://github.com/pszymkowiak/wshm/issues/5)) ([5d51d6c](https://github.com/pszymkowiak/wshm/commit/5d51d6ce5ecdc17e2807c2d1dc8bd64488ad1e76))
* check for updates on daemon startup ([#9](https://github.com/pszymkowiak/wshm/issues/9)) ([ef68fc1](https://github.com/pszymkowiak/wshm/commit/ef68fc1bc2df4ec61deb568f722229c9f16de9ff))
* daemon mode, login, polling, slash commands, branding ([b79b42b](https://github.com/pszymkowiak/wshm/commit/b79b42bf1806c17a99a9cc993262e23ef1ad3eae))
* export system, enhanced code review, source-available license ([beacbb1](https://github.com/pszymkowiak/wshm/commit/beacbb1e5191835ea41b2c817dd7aff1cf9e35bd))
* extend auto-fix to feature issues + detect claude CLI as auth fallback ([f69b089](https://github.com/pszymkowiak/wshm/commit/f69b089b2ee8e7fb8b7fb3d077ad78b3e73386c9))
* initial project scaffold — CLI, DB, GitHub sync, AI pipelines ([f5263ee](https://github.com/pszymkowiak/wshm/commit/f5263ee6e440a563cee562ebef1d54212644dceb))
* integrate ICM as shared memory layer across all pipelines ([#29](https://github.com/pszymkowiak/wshm/issues/29)) ([b842ab3](https://github.com/pszymkowiak/wshm/commit/b842ab388e9a45cd44cfbdf535217d6ad2635f1c))
* per-pipeline AI model override ([#30](https://github.com/pszymkowiak/wshm/issues/30)) ([44d74df](https://github.com/pszymkowiak/wshm/commit/44d74df03bdd410bb31d5b1d9cbe298a98a09f9a))
* per-release checksums + binary integrity check at startup ([91288d0](https://github.com/pszymkowiak/wshm/commit/91288d0f25f4adae9b3462bd4080e6239bd70ffe))
* secure auto-update with SHA256 checksum verification ([#2](https://github.com/pszymkowiak/wshm/issues/2)) ([183e605](https://github.com/pszymkowiak/wshm/commit/183e605fa5a25a956b6cc4404b2e5bf052888a2d))
* support [@wshm](https://github.com/wshm) prefix in addition to /wshm for slash commands ([c1378b3](https://github.com/pszymkowiak/wshm/commit/c1378b3af34afd16bb7f561bc339450a3a5d6272))
* wire /wshm fix slash command to actually run auto-fix pipeline ([99ba95d](https://github.com/pszymkowiak/wshm/commit/99ba95d6b6ed4df175f731bc81668816dcc49e36))
* wshm — full initial implementation ([be69681](https://github.com/pszymkowiak/wshm/commit/be6968162d1281ad3e09f1bfa71819b0340bcc56))


### Bug Fixes

* add .fastembed_cache to gitignore ([721dc20](https://github.com/pszymkowiak/wshm/commit/721dc203d6adbea3d3edf9b846feccce08bd4ab6))
* add logging to claude -p, exclude .fastembed_cache from commits ([6c2e856](https://github.com/pszymkowiak/wshm/commit/6c2e8561469029174750ed08052cbc6db754a4b6))
* add pagination for issues/PRs and gh auth token fallback ([465fbf4](https://github.com/pszymkowiak/wshm/commit/465fbf4ac01aba2ffb491640af611c0ed8d0bf86))
* auto-fix for issue [#15](https://github.com/pszymkowiak/wshm/issues/15) [wshm] ([#16](https://github.com/pszymkowiak/wshm/issues/16)) ([430294a](https://github.com/pszymkowiak/wshm/commit/430294a01a52a4adbf2c50d874745d622494403a))
* auto-fix for issue [#38](https://github.com/pszymkowiak/wshm/issues/38) [wshm] ([#39](https://github.com/pszymkowiak/wshm/issues/39)) ([2c70a25](https://github.com/pszymkowiak/wshm/commit/2c70a254d69955f56219ad43984da5ab124733ca))
* bump version to 0.5.0 and fix auto-update restart ([#28](https://github.com/pszymkowiak/wshm/issues/28)) ([1b2650d](https://github.com/pszymkowiak/wshm/commit/1b2650d60aac9f8c9273e4be931d1c188e7b5ac5))
* cargo fmt ([c2f6f72](https://github.com/pszymkowiak/wshm/commit/c2f6f72a34fee2fd5ac21d10be91ef75167d6652))
* don't skip release upload when some build targets fail ([93bea25](https://github.com/pszymkowiak/wshm/commit/93bea2587e58fbe3f83e882a7202f50dff92356f))
* ensure auto-fix starts from clean base branch ([43586f4](https://github.com/pszymkowiak/wshm/commit/43586f4478d3e7c1d30ce0cbcfd66000ddb37a34))
* force sync on event instead of throttled incremental sync ([a91280e](https://github.com/pszymkowiak/wshm/commit/a91280ed89ae4329bf558b95547fa478f3241792))
* gitignore credentials and sqlite WAL files ([1e8b62d](https://github.com/pszymkowiak/wshm/commit/1e8b62d5c00302eeb4590a2c94017e5955b2a5a0))
* reduce false positives in diff security scanner (nc pattern too broad) ([6c2cbc7](https://github.com/pszymkowiak/wshm/commit/6c2cbc778cae136922f3d99d62e674b0a4bfe63e))
* remove reports, config and sensitive files from repo ([bf49293](https://github.com/pszymkowiak/wshm/commit/bf492937cce9817ce9830661a89a5cf6ac652012))
* **security:** patch 6 vulnerabilities found in audit ([c6a1ff8](https://github.com/pszymkowiak/wshm/commit/c6a1ff8ce98e562b0da0d39104c40c4eb9992bda))
* triage comment announces auto-fix when it will be attempted ([a125327](https://github.com/pszymkowiak/wshm/commit/a125327880f147cb45c337f175af6e41b9a176b1))
* use --dangerously-skip-permissions instead of --yes for claude CLI ([8a27b83](https://github.com/pszymkowiak/wshm/commit/8a27b832fc5b96acc20897723841a740f3d79a0e))
* use `claude -p` for OAuth/Max/Pro instead of API direct call ([#4](https://github.com/pszymkowiak/wshm/issues/4)) ([9913b21](https://github.com/pszymkowiak/wshm/commit/9913b21557e1fad0af57ab3adcbf64eb35d24926))
* use git add -A with exclusion list for auto-fix ([035eb59](https://github.com/pszymkowiak/wshm/commit/035eb59e02712f8339c79ffded750ca38fc3f32a))
* use git add -u instead of -A to avoid committing secrets ([126b52d](https://github.com/pszymkowiak/wshm/commit/126b52dcbb8abcf7f246889e4e8d8055c2f0b35f))
* use process exit instead of systemctl for auto-update restart ([bbf11a9](https://github.com/pszymkowiak/wshm/commit/bbf11a9c11948a09b79cf0ae9cbec04cc54187d8))


### Performance Improvements

* lazy regex compilation + pre-allocated vectors ([46a465b](https://github.com/pszymkowiak/wshm/commit/46a465b9ebb82dd4ab3092ef553cecec8ee1bc5d))

## [0.8.0](https://github.com/pszymkowiak/wshm/compare/v0.7.0...v0.8.0) (2026-03-13)


### Features

* add security audit + command injection scan + smoke test to CI ([8cfb444](https://github.com/pszymkowiak/wshm/commit/8cfb444fb3deff4ee7084fcf84d366d06009c2c4))
* extend auto-fix to feature issues + detect claude CLI as auth fallback ([2cd940c](https://github.com/pszymkowiak/wshm/commit/2cd940c1a0979ce8528c7ee0da769598a6568b26))


### Bug Fixes

* add .fastembed_cache to gitignore ([3d2f783](https://github.com/pszymkowiak/wshm/commit/3d2f7832f1bd409cc39755b101e43f58b5cc35a0))
* add logging to claude -p, exclude .fastembed_cache from commits ([ecdde2e](https://github.com/pszymkowiak/wshm/commit/ecdde2e3bc894564d806136ce5365f078c54d642))
* auto-fix for issue [#38](https://github.com/pszymkowiak/wshm/issues/38) [wshm] ([#39](https://github.com/pszymkowiak/wshm/issues/39)) ([a5d3b51](https://github.com/pszymkowiak/wshm/commit/a5d3b516679da7b0a750240cc72eed417ab827ae))
* cargo fmt ([b322ea2](https://github.com/pszymkowiak/wshm/commit/b322ea2846cfba5c564d6df0759980c919654bdb))

## [0.7.0](https://github.com/pszymkowiak/wshm/compare/v0.6.0...v0.7.0) (2026-03-12)


### Features

* per-pipeline AI model override ([#30](https://github.com/pszymkowiak/wshm/issues/30)) ([19a2861](https://github.com/pszymkowiak/wshm/commit/19a28611a7f2592480a1abbe4501983a4bb26a0a))

## [0.3.1](https://github.com/pszymkowiak/wshm/compare/v0.3.0...v0.3.1) (2026-03-12)


### Bug Fixes

* don't skip release upload when some build targets fail ([5332dd1](https://github.com/pszymkowiak/wshm/commit/5332dd1d1f6fc4f4604731476a4a2e0a9e887681))
* ensure auto-fix starts from clean base branch ([9c3f0ce](https://github.com/pszymkowiak/wshm/commit/9c3f0ce82aaabdd76a33c90770727e3e8be88a9f))
* use git add -A with exclusion list for auto-fix ([7918788](https://github.com/pszymkowiak/wshm/commit/7918788421252dce2d4a93cb9c2caa3ccb2ef329))

## [0.3.0](https://github.com/pszymkowiak/wshm/compare/v0.2.0...v0.3.0) (2026-03-12)


### Features

* wire /wshm fix slash command to actually run auto-fix pipeline ([a5c7096](https://github.com/pszymkowiak/wshm/commit/a5c7096f301c6fd86cff63dea1388aee1340863c))


### Bug Fixes

* reduce false positives in diff security scanner (nc pattern too broad) ([fffea93](https://github.com/pszymkowiak/wshm/commit/fffea93f9630fc1aa9d965719175043359c82118))

## [0.2.0](https://github.com/pszymkowiak/wshm/compare/v0.1.0...v0.2.0) (2026-03-12)


### Features

* check for updates on daemon startup ([#9](https://github.com/pszymkowiak/wshm/issues/9)) ([ea699ce](https://github.com/pszymkowiak/wshm/commit/ea699ceadb49a1ca3108bc7e2cc6a421aa4fd6a2))
* support [@wshm](https://github.com/wshm) prefix in addition to /wshm for slash commands ([7f4d38d](https://github.com/pszymkowiak/wshm/commit/7f4d38df6ba649028a24944aa742da487a2458cc))


### Bug Fixes

* auto-fix for issue [#15](https://github.com/pszymkowiak/wshm/issues/15) [wshm] ([#16](https://github.com/pszymkowiak/wshm/issues/16)) ([6ad8b7a](https://github.com/pszymkowiak/wshm/commit/6ad8b7af6f0f03a413b7afb8dc37bb1e803f076c))
* force sync on event instead of throttled incremental sync ([8a2c708](https://github.com/pszymkowiak/wshm/commit/8a2c708e52f4a94cfca5ee46a76a19de99536648))
* gitignore credentials and sqlite WAL files ([edc8c18](https://github.com/pszymkowiak/wshm/commit/edc8c18f1c9e8cc89221be25ec27987bd2778b1f))
* triage comment announces auto-fix when it will be attempted ([39f4783](https://github.com/pszymkowiak/wshm/commit/39f47831dc5ed91b3c5d97b4a2fa42371ebef673))
* use --dangerously-skip-permissions instead of --yes for claude CLI ([b6f0d0a](https://github.com/pszymkowiak/wshm/commit/b6f0d0a40afcdd115c0e7ca428860b0088c1df57))
* use git add -u instead of -A to avoid committing secrets ([b89d976](https://github.com/pszymkowiak/wshm/commit/b89d976c239f3eb0225c44eb593c44a3579115c4))

## 0.1.0 (2026-03-12)


### Features

* add 15 AI providers (Anthropic, OpenAI, Gemini, Mistral, Groq, DeepSeek, xAI, Together, Fireworks, Perplexity, Cohere, OpenRouter, Ollama, Azure, custom) ([a0d8e2e](https://github.com/pszymkowiak/wshm/commit/a0d8e2eb00c4c99d565c036c87297838f4ffbf5f))
* add CI/CD workflows and systemd install/uninstall ([#1](https://github.com/pszymkowiak/wshm/issues/1)) ([d8adef9](https://github.com/pszymkowiak/wshm/commit/d8adef90c364d39ee0da5793b7c709fd4b062d35))
* add Claude OAuth login (Max/Pro/Team subscription support) ([0f80031](https://github.com/pszymkowiak/wshm/commit/0f80031e7d454e1e3d775e90bee074d6123c2475))
* auto-fix security hardening ([#7](https://github.com/pszymkowiak/wshm/issues/7)) ([be3212c](https://github.com/pszymkowiak/wshm/commit/be3212c4962d8c7e6633349d24ec3bbfed9e9864))
* auto-fix trigger from triage pipeline ([#6](https://github.com/pszymkowiak/wshm/issues/6)) ([b5589c6](https://github.com/pszymkowiak/wshm/commit/b5589c64ef7811b9f191c24efc818352181a8caf))
* bot-style comments with emojis and automated banner ([#5](https://github.com/pszymkowiak/wshm/issues/5)) ([2b379b2](https://github.com/pszymkowiak/wshm/commit/2b379b222d11b214a7e4abcfae037090a6c07d00))
* daemon mode, login, polling, slash commands, branding ([b79b42b](https://github.com/pszymkowiak/wshm/commit/b79b42bf1806c17a99a9cc993262e23ef1ad3eae))
* initial project scaffold — CLI, DB, GitHub sync, AI pipelines ([f5263ee](https://github.com/pszymkowiak/wshm/commit/f5263ee6e440a563cee562ebef1d54212644dceb))
* secure auto-update with SHA256 checksum verification ([#2](https://github.com/pszymkowiak/wshm/issues/2)) ([eccca1a](https://github.com/pszymkowiak/wshm/commit/eccca1a4b0345c78f40070d78c42c5c3bde5586c))
* wshm — full initial implementation ([be69681](https://github.com/pszymkowiak/wshm/commit/be6968162d1281ad3e09f1bfa71819b0340bcc56))


### Bug Fixes

* add pagination for issues/PRs and gh auth token fallback ([465fbf4](https://github.com/pszymkowiak/wshm/commit/465fbf4ac01aba2ffb491640af611c0ed8d0bf86))
* use `claude -p` for OAuth/Max/Pro instead of API direct call ([#4](https://github.com/pszymkowiak/wshm/issues/4)) ([4595b43](https://github.com/pszymkowiak/wshm/commit/4595b43e6f05d3c973959267a1e59ee17d24d996))
