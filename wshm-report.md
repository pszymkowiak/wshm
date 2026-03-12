# wshm Report — rtk-ai/rtk

Generated: 2026-03-11 22:03 UTC

## Overview

| Metric | Count |
|--------|-------|
| Open issues | 111 |
| Untriaged | 0 |
| Open PRs | 90 |
| Unanalyzed PRs | 90 |
| Conflicts | 31 |

## SLA Tracking

| Metric | Value |
|--------|-------|
| Avg PR age | 7.9 days |
| Oldest PR | #138 (23 days) |
| PRs > 7 days | 34 |
| PRs > 30 days | 0 |
| Avg issue age | 10.3 days |
| Oldest issue | #87 (27 days) |
| Issues > 7 days | 53 |
| Issues > 30 days | 0 |

## Linked Issues & PRs

### Issue #500 — bug: test-all.sh aborts on Graphite section when gt is not installed

- **Category:** bug | **Priority:** high | **Confidence:** 100% | **Activity:** today
- **Summary:** The `test-all.sh` script aborts prematurely when `gt` is not installed due to calling `skip` instead of `skip_test`, preventing subsequent test sections from running.
- **PR #501 (fixes):** fix: test-all.sh aborts when gt is not installed | Mergeable: **yes** | Score: 2 `mergeable:+2`

### Issue #87 — feat: add support or template support for additional compilers

- **Category:** feature | **Priority:** medium | **Confidence:** 98% | **Activity:** 3d ago
- **Summary:** Request to add support for additional compilers (e.g., gcc, swift, go, zig) and explore a generic template for easier integration of new tools.
- **PR #153 (closes):** feat: add rtk scaffold command for contributor boilerplate | Mergeable: **conflict** | Score: 0 `conflict:-10 age:+10`

### Issue #212 — bug: RTK can't resolve .CMD/.BAT wrappers on Windows (PATHEXT not honored)

- **Category:** bug | **Priority:** high | **Confidence:** 98% | **Activity:** 3d ago
- **Summary:** RTK on Windows fails to resolve and spawn Node.js tools (e.g., vitest, eslint, pnpm) due to not honoring PATHEXT for script wrappers. A fix using the `which` crate is recommended.
- **PR #269 (closes):** fix windows PATHEXT resolution for .cmd/.bat wrappers | Mergeable: **conflict** | Score: 0 `conflict:-10 age:+10`

### Issue #285 — Feature request: add rtk rewrite for `python3`

- **Category:** feature | **Priority:** high | **Confidence:** 98% | **Activity:** 11d ago
- **Summary:** Feature request to add an RTK rewrite/filter for `python3` commands to reduce verbose output, as it is a frequently unhandled command.
- **PR #429 (fixes):** Add rtk python3 command with module routing and traceback filtering | Mergeable: **unknown** | Score: 2 `age:+2`

### Issue #376 — Feature Request: Add support for `xcodebuild` and subcommands

- **Category:** feature | **Priority:** medium | **Confidence:** 98% | **Activity:** 4d ago
- **Summary:** Request to add support for `xcodebuild` and its various subcommands to enable RTK's token-optimized filtering for verbose output.
- **PR #394 (closes):** feat(xcodebuild): add support | Mergeable: **unknown** | Score: 4 `age:+4`

### Issue #407 — tail -N fails when rewritten to rtk read (+1: 1)

- **Category:** bug | **Priority:** high | **Confidence:** 98% | **Activity:** 3d ago
- **Summary:** `rtk read` fails to correctly handle `tail -N` arguments when `tail` commands are rewritten, causing an error. The issue requires `rtk read` to either translate `tail -N` arguments or fall back to the native `tail` command.
- **PR #412 (closes):** fix: handle tail rewrites with read tail-lines | Mergeable: **unknown** | Score: 3 `age:+3`

### Issue #482 — fix: rtk ls summary line inflates pipe count

- **Category:** bug | **Priority:** medium | **Confidence:** 98% | **Activity:** 1d ago
- **Summary:** The `rtk ls` command incorrectly prints a summary line to stdout even when piped, inflating line counts and breaking scripts. The fix involves suppressing the summary when stdout is not a TTY.
- **PR #503 (fixes):** fix(ls): suppress summary line when stdout is piped | Mergeable: **unknown** | Score: 0 ``

### Issue #117 — add support/installation for OpenCode (+1: 38)

- **Category:** feature | **Priority:** medium | **Confidence:** 95% | **Activity:** 6d ago
- **Summary:** Request to add support and installation for OpenCode, a code system similar to Claude Code, citing its active development and potential benefits.
- **PR #300 (closes):** feat: add OpenCode plugin support | Mergeable: **conflict** | Score: -1 `conflict:-10 age:+9`

### Issue #163 — bug: rtk git -C <path> ... is rejected (works only via separator form) (+1: 5)

- **Category:** bug | **Priority:** high | **Confidence:** 95% | **Activity:** 2d ago
- **Summary:** `rtk git` fails to correctly parse the `-C <path>` argument, leading to an "unexpected argument" error. This requires users to use the `--` separator, which is inconsistent with native `git` behavior and should be fixed for better CLI parity.
- **PR #518 (closes):** fix: discover absolute paths + git global options (#485, #163) | Mergeable: **unknown** | Score: 0 ``

### Issue #213 — feat: add support for cursor (+1: 16)

- **Category:** feature | **Priority:** medium | **Confidence:** 95% | **Activity:** 1d ago
- **Summary:** Feature request to add support for a cursor, likely for navigation or selection within the application.
- **PR #254 (closes):** feat(init): add Cursor support (`rtk init --cursor`) | Mergeable: **yes** | Score: 12 `mergeable:+2 age:+10`

### Issue #372 — fix: extra blank lines in gradle output

- **Category:** bug | **Priority:** medium | **Confidence:** 95% | **Activity:** 5d ago
- **Summary:** Fix extra blank lines appearing in `rtk gradle` command output, specifically leading lines and an extra newline when stderr is empty.
- **PR #381 (closes):** feat(gradle): add Gradle/Gradlew support with compact output (80-90% token reduction) | Mergeable: **unknown** | Score: 5 `age:+5`

### Issue #416 — Issue accepting arguments for `gh run`

- **Category:** bug | **Priority:** medium | **Confidence:** 95% | **Activity:** 3d ago
- **Summary:** The `rtk gh run view` command fails to correctly parse arguments like `--job`, reporting 'flag needs an argument'.
- **PR #419 (fixes):** fix: preserve gh run view passthrough args | Mergeable: **yes** | Score: 5 `mergeable:+2 age:+3`

### Issue #461 — `rtk git log --oneline` silently truncates the log to 10 entries.

- **Category:** bug | **Priority:** high | **Confidence:** 95% | **Activity:** 1d ago
- **Summary:** `rtk git log --oneline` silently truncates output to 10 entries, hindering AI agent's git operations.
- **PR #505 (fixes):** fix: respect user-specified git log limits (#461) | Mergeable: **unknown** | Score: 0 ``

### Issue #484 — feat: add xcodebuild test filter (TOML)

- **Category:** feature | **Priority:** medium | **Confidence:** 95% | **Activity:** 1d ago
- **Summary:** Add a TOML filter for `xcodebuild test` command output to reduce verbosity and save tokens, similar to the `cargo test` filter.
- **PR #499 (closes):** chore: merge develop into master | Mergeable: **yes** | Score: 2 `mergeable:+2`

### Issue #485 — fix: discover doesn't match /usr/bin/grep as rtk grep equivalent

- **Category:** bug | **Priority:** medium | **Confidence:** 95% | **Activity:** today
- **Summary:** `rtk discover` fails to identify commands invoked with absolute paths (e.g., `/usr/bin/grep`) as `rtk` equivalents, leading to missed savings. The fix involves normalizing command paths before classification.
- **PR #518 (closes):** fix: discover absolute paths + git global options (#485, #163) | Mergeable: **unknown** | Score: 0 ``

### Issue #496 — cargo clippy -- -D warnings fails: args after -- treated as filenames

- **Category:** bug | **Priority:** high | **Confidence:** 95% | **Activity:** today
- **Summary:** The `rtk cargo clippy` command incorrectly parses arguments after `--`, treating them as filenames instead of compiler flags, leading to compilation errors.
- **PR #519 (fixes):** fix: prevent double -- separator in cargo clippy with -p flags (#496) | Mergeable: **yes** | Score: 2 `mergeable:+2`

### Issue #259 — `pnpm --filter` command results in rtk usage output

- **Category:** bug | **Priority:** high | **Confidence:** 92% | **Activity:** 16d ago
- **Summary:** `rtk pnpm` command fails with an 'unexpected argument' error when `--filter` is used, contrary to the expected behavior of passing unknown arguments to the target command.
- **PR #520 (fixes):** fix: handle pnpm --filter/-F flag (#259) | Mergeable: **yes** | Score: 2 `mergeable:+2`

### Issue #387 — Basic Claude Issues / Grep, Read, Glob not being rewritten as they're not Bash commands (+1: 1)

- **Category:** bug | **Priority:** high | **Confidence:** 92% | **Activity:** 4d ago
- **Summary:** Commands like `grep`, `read`, and `glob` are not being rewritten by RTK, leading to a significant number of raw command executions and confusion based on documentation. This impacts expected efficiency gains.
- **PR #413 (fixes):** docs: clarify Bash-only auto-rewrite scope | Mergeable: **conflict** | Score: -7 `conflict:-10 age:+3`

### Issue #388 — Claude fails to use `rtk proxy` because of quotes (+1: 1)

- **Category:** feature | **Priority:** medium | **Confidence:** 90% | **Activity:** 4d ago
- **Summary:** Enhance `rtk proxy` to correctly parse commands wrapped in single quotes, especially when generated by AI tools like Claude, to prevent 'No such file or directory' errors.
- **PR #411 (fixes):** fix: split single-string proxy invocations | Mergeable: **yes** | Score: 5 `mergeable:+2 age:+3`

## Issues (no linked PR)

| # | Title | Category | Confidence | Priority | +1 | Activity | Summary |
|---|-------|----------|-----------|----------|-----|----------|--------|
| #276 | Feature request: add rtk rewrite for `docker compose` | feature | 100% | high | 3 | 11d ago | Feature request to add RTK rewrite/filter support for `docker compose` subcommands, as it's a highly used unhandled command. |
| #278 | Feature request: add rtk rewrite for `psql` | feature | 100% | high | - | 11d ago | Request to add an RTK rewrite/filter for `psql` command output to reduce verbosity and token usage, as it's a frequently used unhandled command. |
| #441 | [Feature]: diffsitter instead of diff | feature | 100% | medium | - | 2d ago | Request to integrate `diffsitter` to provide semantically reduced diff output, optimizing token consumption for AI agents. |
| #103 | feat: Add support for dotnet CLI commands | feature | 98% | high | 1 | 22d ago | Add native support for filtering verbose `dotnet` CLI command output (e.g., `build`, `test`, `restore`) to reduce LLM context usage. |
| #142 | feat: integrate session summary hook for end-of-session analytics | feature | 98% | high | - | 23d ago | Integrate a session summary hook or native functionality to automatically display RTK token savings and other analytics at the end of Claude Code sessions, addressing a common user request for visibility. |
| #146 | Feature Request: Add sudo prefix support for command rewriting | feature | 98% | medium | - | 22d ago | Add support for `sudo` prefix in the RTK command rewriting hook to ensure commands like `sudo docker ps` are correctly rewritten to `sudo rtk docker ps`, improving token savings. |
| #147 | Feature Request: Add Support for Java/Kotlin, Spring Boot, and Maven Environment Workflows | feature | 98% | medium | 2 | 18d ago | Feature request to add comprehensive support for Java/Kotlin development workflows, including Maven, Spring Boot, environment variable handling, and test output filtering. |
| #181 | Feature request: kubectl filter support | feature | 98% | medium | - | 21d ago | Request to add first-class filter support for `kubectl` commands to reduce token usage by stripping metadata, compacting output, and truncating logs. |
| #182 | Feature request: helm filter support (show, template) | feature | 98% | medium | - | 21d ago | Feature request to add RTK filtering support for `helm show` and `helm template` commands to reduce verbose YAML output. |
| #190 | How to upgrade ? | question | 98% | low | - | 6d ago | User is asking for instructions on how to upgrade the `rtk` package, as `brew upgrade rtk` is not working. |
| #191 | Feature: Add dotnet / MSBuild command filters | feature | 98% | medium | 1 | 3d ago | Request to add command output filtering for the .NET/MSBuild toolchain, including `dotnet restore`, `dotnet build`, `MSBuild.exe`, `dotnet test`, and `dotnet format`, to reduce verbosity for AI agents. |
| #195 | Support for Oxlint and Oxfmt in RTK | feature | 98% | medium | 3 | 3d ago | Request to add support for Oxlint and Oxfmt to RTK to improve performance in TypeScript projects. |
| #205 | feat: add support for awscli | feature | 98% | medium | 1 | 3d ago | Request to add native support for AWS CLI commands in RTK to provide compact summaries, reduce LLM context usage, and integrate with existing rewrite/discover mechanisms. |
| #243 | Support exclude_commands config for auto-rewrite hook | feature | 98% | medium | 3 | 17d ago | Request to add a configuration option to exclude specific commands from being rewritten by the auto-rewrite hook. |
| #260 | Security: PreToolUse hook bypasses Claude Code deny rules via permissionDecision: allow | bug | 98% | high | 9 | 2d ago | The PreToolUse hook in RTK bypasses Claude Code's permission deny rules by explicitly setting `permissionDecision: "allow"`, leading to a security vulnerability where dangerous commands can be executed without user confirmation. A fix is proposed to dynamically check deny rules before allowing execution. |
| #271 | Feature request: Add Jujutsu (jj) support | feature | 98% | medium | 3 | 7d ago | Feature request to add support for Jujutsu (jj) VCS, leveraging existing Git output compression logic due to similar output formats. |
| #275 | Feature request: add rtk rewrite for `docker exec` | feature | 98% | high | - | 11d ago | Feature request to add an RTK rewrite/filter for `docker exec` command output to reduce token usage, as it's the #1 unhandled command. |
| #279 | Feature request: add rtk rewrite for `docker inspect` | feature | 98% | high | - | 11d ago | Request to add an RTK rewrite/filter for `docker inspect` to reduce its verbose JSON output, identified as a frequently used unhandled command. |
| #304 | Feature request : add command for grepai | feature | 98% | high | - | 9d ago | Feature request to add an `rtk grepai` command to filter `grepai` output, significantly reducing token usage for LLMs in Claude Code workflows. |
| #315 | discover: cat > (file writes) incorrectly counted as cat (file reads), inflating savings estimates | bug | 98% | high | - | 7d ago | The `rtk discover` command incorrectly counts `cat > file.txt` (file write operations) as savable `cat` commands, leading to inflated token savings estimates. A regex fix is proposed. |
| #322 | Telemetry data | question | 98% | high | - | 6d ago | User asks for disclosure regarding telemetry data collection in the CLI following the RTK cloud announcement. This requires a clear statement on data collection practices. |
| #330 | Add hooks support for Windows | duplicate | 98% | high | - | 4d ago | This issue is a duplicate of #502, requesting support for hook-based mode on Windows. |
| #331 | feat(init): interactive config wizard for rtk init | feature | 98% | medium | - | 6d ago | Implement an optional interactive configuration wizard for `rtk init` to improve user experience, while retaining non-interactive options for scripting and adding a `--dev-hooks` mode. |
| #333 | Feature Request rtk ssh subcommand — remote command output filtering | feature | 98% | high | - | 6d ago | Request for a new `rtk ssh` subcommand to execute remote commands and filter their stdout using existing `rtk` filters, addressing a significant unhandled savings opportunity. |
| #348 | feat: Automated Issue & PR triage system (templates, labeling, classification) | feature | 98% | high | - | 6d ago | Implement an automated issue and PR triage system using GitHub Actions, templates, and classification logic to improve maintainer efficiency and reduce manual triage time. |
| #354 | gh PR comments/reviews and git diff output still truncated, causing repeated fetch attempts by AI agents | bug | 98% | high | 1 | 3d ago | Output from `gh` CLI (PR comments, review data) and `git diff` is truncated by rtk, causing AI agents to repeatedly fetch data and significantly slowing down workflows. |
| #361 | 5 hook bugs on master — routing, streaming, extensibility (fixed in PR #156) | bug | 98% | critical | - | today | Multiple critical and high-priority bugs in the current shell hook on master, including lack of streaming, extensibility, and incorrect command routing, are addressed by PR #156. |
| #383 | Windows: add winget package support | feature | 98% | medium | - | 4d ago | Add support for installing RTK via the Winget package manager on Windows, including CI automation for manifest updates. |
| #442 | [Feature]: use HEDL instead of JSON, XML, YAML, CSV | feature | 98% | medium | - | 2d ago | Request to add automatic conversion of JSON, XML, YAML, and CSV outputs to HEDL format to optimize token usage. |
| #448 | [Feature] add ty type checker | feature | 98% | medium | - | 2d ago | Feature request to integrate the `ty` type checker for Python to help reduce token usage. |
| #449 | [Feature]: add basedpyright | feature | 98% | medium | - | 2d ago | Request to add support for the basedpyright Python type checker to benefit from reduced token usage. |
| #464 | bug: `rtk read` corrupts `package.json` when JSON strings contain `/*` or `*/` | bug | 98% | high | - | 1d ago | `rtk read` corrupts `package.json` by misinterpreting `/*` and `*/` within JSON string values as comments, leading to structural data loss. |
| #474 | Branch naming guidelines in CONTRIBUTING.md are illegal | docs | 98% | medium | - | 1d ago | The branch naming guidelines in CONTRIBUTING.md suggest using colons and spaces, which are illegal in Git branch names and need to be corrected. |
| #476 | CI: validate-docs.sh breaks on every release (version mismatch) | bug | 98% | high | - | 1d ago | The `validate-docs.sh` CI script fails after every release due to a version mismatch between `Cargo.toml` and documentation files, requiring manual updates. |
| #481 | feat: rtk discover --share / --issue — Community filter prioritization | feature | 98% | high | - | today | Implement `rtk discover --share` and `--issue` for community data collection, a backend for aggregation, and an agent-assisted pipeline (`rtk analyze`, `/create-filter`, `rtk discover --suggest`) to streamline filter creation based on this data. |
| #483 | feat: add jq filter (TOML) | feature | 98% | high | - | 1d ago | Add a TOML filter for `jq` commands to intelligently truncate large JSON outputs, improving token efficiency for `rtk discover`. |
| #486 | feat: rtk context — Show Claude Code context token budget | feature | 98% | high | - | today | Implement a new `rtk context` command to display the estimated token budget for various Claude Code components like CLAUDE.md, skills, and commands. |
| #487 | feat: rtk session — Show RTK adoption across Claude Code sessions | feature | 98% | medium | - | today | Implement a new `rtk session` command to display RTK adoption statistics across Claude Code sessions, showing usage ratio and output size for recent sessions. |
| #488 | Feature Request: Configurable context reduction profiles (heavy, normal, soft, light) | feature | 98% | high | 1 | today | Request to add configurable context reduction profiles (heavy, normal, soft, light) via CLI flag or config to allow users to control token-saving aggressiveness, especially for debugging. |
| #512 | feat: pnpm workspace filter support (--filter/-F) | feature | 98% | high | - | today | Implement support for pnpm workspace filter (`--filter`/`-F`) commands by normalizing the command in the rewrite layer and propagating the filter to tool modules, enabling token savings for pnpm monorepo users. |
| #513 | feat(registry): rewrite-layer normalization for pnpm --filter | feature | 98% | medium | - | today | Implement rewrite-layer normalization for pnpm --filter commands in `src/discover/registry.rs` to enable pnpm workspace filter support. |
| #514 | feat(main): --pnpm-filter global Clap arg + dispatch updates | feature | 98% | medium | - | today | Implement the hidden global `--pnpm-filter` argument in `src/main.rs` and propagate it to all affected command dispatch calls. |
| #515 | feat(utils): add package_manager_filtered_exec() for pnpm workspace support | feature | 98% | medium | - | today | Add a new utility function `package_manager_filtered_exec` in `src/utils.rs` to support pnpm workspace filtering. |
| #516 | feat(tool-modules): propagate pnpm_filter to all affected run() functions | feature | 98% | medium | - | today | Implement pnpm workspace filter propagation by updating `run()` signatures and command construction in various tool modules. |
| #115 | Optional feature for safely remapping commands? (Eg rm -> trash) | feature | 95% | medium | - | 21d ago | Request for an optional feature to safely remap dangerous commands (e.g., `rm` to `trash`, `git reset` to `git stash` then reset) to prevent accidental data loss. |
| #139 | plugin system so people can integrate their own | feature | 95% | medium | 9 | 19d ago | Request for a plugin system to allow users to integrate and manage their own tools, reducing the need for direct support of every tool in the core project. |
| #140 | Support running pytest with uv run python/python -m | feature | 95% | medium | - | 22d ago | Request to add support for `uv run python -m pytest` and `python -m pytest` command patterns. |
| #154 | refactor: migrate rtk-rewrite.sh hook from shell to Rust subcommand | feature | 95% | high | - | 23d ago | Migrate the `rtk-rewrite.sh` hook from a Bash script to a native Rust subcommand (`rtk hook-rewrite`) to improve performance, maintainability, and remove external dependencies. |
| #165 | Using rtk in Zed editor with Claude Code ACP | question | 95% | low | 1 | 17d ago | User is asking for advice on how to configure rtk to work correctly within the Zed editor, as commands are being missed. |
| #169 | Add support/installation for Codex | feature | 95% | medium | 69 | 1d ago | Request to add native support and installation for the Codex agentic CLI. |
| #183 | Feature request: gcloud CLI filter support | feature | 95% | medium | - | 21d ago | Request to add filtering capabilities for `gcloud` CLI command outputs to reduce verbosity and focus on relevant data, including compact tables and stripping metadata. |
| #184 | Feature request: pre-commit / linter output filter support | feature | 95% | medium | 1 | 21d ago | Request to add output filtering for verbose linters like pre-commit and checkov to reduce noise and improve LLM context. |
| #189 | Release pipeline should skip binary builds for non-code changes | feature | 95% | high | - | 21d ago | Optimize the release pipeline to skip binary builds when only non-code files change, by adding a step to detect Rust source code modifications. |
| #197 | Handle supported commands through the bunx / bun x / pnpx / pnpm dlx / npx | feature | 95% | medium | 2 | 3d ago | Request to extend RTK's command handling to include commands executed via package manager wrappers like `bunx`, `npx`, and `pnpm dlx`. |
| #208 | benchmark.sh: add missing commands for pre-release pipeline | feature | 95% | high | - | 21d ago | Enhance `benchmark.sh` to include all missing testable RTK commands and correct existing benchmarking methods to prevent regressions in the pre-release pipeline. |
| #218 | Add timeout to hook | feature | 95% | high | - | 3d ago | Add a configurable timeout to the RTK hook to prevent indefinite stalling if the hook hangs. |
| #220 | `vitest run --coverage` is not supported | bug | 95% | high | - | 20d ago | Bug: The `vitest run --coverage` command's output, specifically coverage data, is not correctly captured or propagated. |
| #222 | bug: rtk proxy does not stream long-running command output progressively | bug | 95% | high | - | 2d ago | The `rtk proxy` command does not progressively stream output from long-running commands, causing a 'silent hang' UX until the command completes. |
| #236 | Hook: find/grep rewrite breaks on native flags — workaround with smart translation | bug | 95% | high | 1 | 4d ago | The `rtk` hook's blind prefixing of `find` and `grep` commands leads to argument parsing errors and syntax mismatches, requiring a smart translation layer in the hook. This issue details the problems and proposes solutions for `rtk`'s CLI argument handling and documentation. |
| #237 | Integrate rtk with framework | question | 95% | low | - | 18d ago | User is asking for advice on the best way to integrate rtk with their Kubernetes-based framework and inquiring about future support for other coding agents. |
| #266 | Hook rewrites git commit --amend but rtk git commit doesn't support it | bug | 95% | medium | 1 | 13d ago | The `rtk` rewrite hook incorrectly intercepts `git commit --amend` and other variants, causing `rtk git commit` to fail due to unsupported arguments. |
| #283 | Feature request: add rtk rewrite for `stat` | feature | 95% | medium | - | 2d ago | Request to add an RTK rewrite/filter for the `stat` command to provide more concise output, as it is a frequently used unhandled command. |
| #294 | Hook rewrite: add coverage for uv run, pnpm exec, Python path variants, and more | feature | 95% | medium | 3 | 10d ago | Enhancement to the `rtk-rewrite.sh` hook script to intercept a wider range of commands, including `uv run`, `pnpm exec`, and various Python path variants, significantly improving command coverage. |
| #307 | Add support for MS Copilot | feature | 95% | medium | 17 | today | Request to add native support for Microsoft Copilot integration. |
| #316 | Support Biome for lint command | feature | 95% | medium | 2 | 6d ago | Request to add support for Biome as an alternative linting tool, detectable via package.json scripts or biome.json. |
| #384 | Windows: rtk init --uninstall does not work | bug | 95% | high | - | 4d ago | The `rtk init --uninstall` command fails on Windows due to Unix-specific assumptions, preventing proper cleanup of RTK files and configurations. |
| #401 | Pi support | feature | 95% | medium | - | 1d ago | Request to add integration with the pi-coding-agent. |
| #428 | Add skopeo support | feature | 95% | medium | 1 | 2d ago | Request to add `skopeo` command support to `rtk` with token-saving output filtering for `list-tags` and `inspect` commands. |
| #444 | Add `pnpm nx` command patterns for Nx monorepos | feature | 95% | high | 1 | 2d ago | Add rewrite/compression patterns for `pnpm nx` commands to reduce uncompressed output in Nx monorepos. |
| #445 | Add coverage for git subcommands: restore, reset, rm, ls-files, rev-parse | feature | 95% | high | - | 2d ago | Request to add compression patterns for `git restore`, `git reset`, `git rm`, `git ls-files`, and `git rev-parse` to reduce uncompressed output for AI agents. |
| #446 | Add `gh search` subcommand support | feature | 95% | medium | - | 2d ago | Add compression patterns for `gh search` subcommands (`repos`, `issues`, `prs`) to reduce verbose output and passthrough invocations. |
| #457 | Would you accept a nix config? | feature | 95% | medium | 1 | 1d ago | Request to incorporate a Nix configuration (flake.nix) into the project, with an offer for maintenance and CI integration. |
| #502 | Support hook-based mode on Windows (rtk init --global) | bug | 95% | medium | - | today | `rtk init --global` on Windows incorrectly falls back to `--claude-md` mode, despite hook-based mode being functional via Git Bash. |
| #508 | warn: detect and report RTK_DISABLED=1 overuse in sessions | feature | 95% | high | - | today | Implement warnings and detection for excessive `RTK_DISABLED=1` usage in sessions to recover lost token savings due to AI agent over-generalization. |
| #509 | fix: hook_check should warn when no hook is installed, not just when outdated | bug | 95% | high | - | today | The `hook_check` mechanism fails to warn users when the RTK hook is not installed, leading to missed token savings without notification. The system should warn users and surface this in `rtk gain` output. |
| #122 | Support for pnpm and glab cli | feature | 92% | medium | 1 | 22d ago | Request to add support for `pnpm` and `glab` CLI commands to improve token savings, as indicated by high usage in unhandled commands. |
| #149 | Other (catchall) doesn't allow user made scripts | feature | 92% | medium | 1 | 20d ago | The `rtk` CLI should support executing user-defined scripts directly, treating them as external commands rather than unrecognized subcommands. |
| #173 | Claude.md french preference | feature | 92% | medium | 1 | 22d ago | Request to change the default language preference in `claude.md` from French to English to improve contribution friendliness. |
| #187 | bug: rtk proxy bun run lint reorders output line vs raw command | bug | 92% | medium | - | 1d ago | The `rtk proxy` command reorders output lines from `bun run lint`, specifically moving a Bun metadata line, breaking strict output fidelity. |
| #219 | feat: config for curl filter bypass | feature | 92% | medium | 3 | 3d ago | Request for a configuration option to bypass the `curl` filter's automatic JSON-to-schema conversion, allowing LLMs to receive raw JSON data. |
| #229 | grep: unexpecter argument | bug | 92% | high | 1 | 2d ago | rtk's proxy for `grep` fails to correctly parse or pass the `-E` argument, leading to an 'unexpected argument' error. |
| #257 | rtk rg command fails — ripgrep not supported or not forwarded correctly (codex) | bug | 92% | medium | 1 | 16d ago | The `rtk rg` command fails to correctly proxy to `ripgrep`, requiring users to execute `rg` directly. This needs to be fixed or documented. |
| #320 | rtk gain not tracking commands when sandbox blocks writes to ~/.local/share/rtk/ | bug | 92% | medium | - | 6d ago | RTK gain stats fail silently in Claude Code sandbox due to blocked write access to history.db, requiring a warning or automatic sandbox configuration. |
| #427 | The rtk proxy is summarizing the diff. Let me get the raw content   differently. | feature | 92% | high | 1 | 2d ago | Request to add a configuration option to disable `rtk proxy`'s summarization of `git diff` output and use the native `git diff` instead, to provide raw content for AI agents. |
| #450 | Failed to get latest version | bug | 92% | high | 1 | 1d ago | The `rtk` installation fails with a 403 Forbidden error when attempting to fetch the latest version, preventing successful installation. |
| #467 | git log filter strips commit bodies that agents need for context | feature | 92% | high | - | 1d ago | The `rtk git log` command currently strips commit bodies, removing critical context needed by AI agents. This issue proposes preserving commit bodies by default or via an explicit flag to improve agent decision-making. |
| #470 | npm run is broken | bug | 92% | medium | 1 | 1d ago | The `rtk npm run <script>` command is broken, returning an error instead of executing the npm script, despite `rtk init` suggesting its use in `CLAUDE.md`. |
| #511 | cleanup: remove emojis from CLI output — use plain text indicators | feature | 92% | medium | 1 | today | Remove emojis from CLI output and replace them with plain text indicators to improve terminal compatibility, professionalism, and text processing. |
| #273 | How to use on roo/cline/kilo? | question | 90% | medium | 1 | 11d ago | A user is asking for guidance on how to use the tool on 'roo/cline/kilo' environments. This is a question about usage. |
| #396 | Cost more after using rtk | bug | 90% | medium | 1 | 3d ago | Using rtk increases 'cache write token' cost compared to not using it, as shown by provided screenshots. |
| #403 | Why CLAUDE.md? | docs | 90% | low | - | 3d ago | The user is questioning the purpose and usefulness of the content linked from CLAUDE.md to RTK.md, suggesting the documentation might need clarification or improvement. |
| #439 | Trouble running xargs as second bash command. | bug | 85% | high | - | today | rtk appears to interfere with `xargs` when used in a pipeline (e.g., `find \| xargs grep`), causing `grep` to fail on incorrect paths. More information is needed to diagnose. |

## Merge Queue

| # | Title | Score | Breakdown | CI | Mergeable | Last Activity |
|---|-------|-------|-----------|----|-----------|--------------|
| #520 | fix: handle pnpm --filter/-F flag (#259) | 2 | `mergeable:+2` | unknown | yes | today |
| #519 | fix: prevent double -- separator in cargo clippy with -p flags (#496) | 2 | `mergeable:+2` | unknown | yes | today |
| #518 | fix: discover absolute paths + git global options (#485, #163) | 0 | `` | unknown | unknown | today |
| #505 | fix: respect user-specified git log limits (#461) | 0 | `` | unknown | unknown | today |
| #503 | fix(ls): suppress summary line when stdout is piped | 0 | `` | unknown | unknown | today |
| #501 | fix: test-all.sh aborts when gt is not installed | 2 | `mergeable:+2` | unknown | yes | today |
| #499 | chore: merge develop into master | 2 | `mergeable:+2` | unknown | yes | today |
| #495 | Add opencode init lifecycle support | -10 | `conflict:-10` | unknown | conflict | today |
| #494 | feat(config): configurable auto_approve and claude dir | 0 | `` | unknown | unknown | today |
| #491 | feat: Claude Code tooling — 2 agents, 7 commands, 2 rules, 4 skills | 0 | `` | unknown | unknown | today |
| #463 | fix(ls): force LC_ALL=C for predictable parsing | 3 | `mergeable:+2 age:+1` | unknown | yes | 1d ago |
| #456 | Added German Translation  | 1 | `age:+1` | unknown | unknown | today |
| #455 | feat(init): add --opencode flag for OpenCode plugin install | 3 | `mergeable:+2 age:+1` | unknown | yes | 1d ago |
| #453 | feat(bun): add bun pm | 3 | `mergeable:+2 age:+1` | unknown | yes | 1d ago |
| #452 | feat: add Windows hook support for rtk init --global | 3 | `mergeable:+2 age:+1` | unknown | yes | 1d ago |
| #451 | feat(config): support CLAUDE_CONFIG_DIR environment variable | 1 | `age:+1` | unknown | unknown | 1d ago |
| #447 | Add documentation for RTK CLI proxy | 4 | `mergeable:+2 age:+2` | unknown | yes | 1d ago |
| #443 | feat(npm): structured NpmCommands sub-enum with smart script routing | 4 | `mergeable:+2 age:+2` | unknown | yes | 1d ago |
| #436 | feat(chezmoi): add chezmoi dotfile manager support (80-90% token savings) | 2 | `age:+2` | unknown | unknown | 1d ago |
| #431 | feat(init): add --project and --local scope flags | -8 | `conflict:-10 age:+2` | unknown | conflict | 2d ago |
| #429 | Add rtk python3 command with module routing and traceback filtering | 2 | `age:+2` | unknown | unknown | 1d ago |
| #426 | feat(kubectl): support global context and identity flags | 4 | `mergeable:+2 age:+2` | unknown | yes | 2d ago |
| #424 | [feat] Add shim to make rtk work with Codex | -8 | `conflict:-10 age:+2` | unknown | conflict | 1d ago |
| #423 | chore: sort help | -8 | `conflict:-10 age:+2` | unknown | conflict | 2d ago |
| #422 | chore: cleanup dead code | 5 | `mergeable:+2 age:+3` | unknown | yes | 2d ago |
| #421 | docs: reposition RTK as agent-agnostic | -7 | `conflict:-10 age:+3` | unknown | conflict | today |
| #420 | security: comprehensive OWASP security review and fixes | 5 | `mergeable:+2 age:+3` | unknown | yes | 3d ago |
| #419 | fix: preserve gh run view passthrough args | 5 | `mergeable:+2 age:+3` | unknown | yes | 1d ago |
| #417 | Add OpenCode provider support for discover | 5 | `mergeable:+2 age:+3` | unknown | yes | today |
| #413 | docs: clarify Bash-only auto-rewrite scope | -7 | `conflict:-10 age:+3` | unknown | conflict | 1d ago |
| #412 | fix: handle tail rewrites with read tail-lines | 3 | `age:+3` | unknown | unknown | 3d ago |
| #411 | fix: split single-string proxy invocations | 5 | `mergeable:+2 age:+3` | unknown | yes | 1d ago |
| #408 | feat: add arabic readme | 3 | `age:+3` | unknown | unknown | 1d ago |
| #406 | feat: add codex review support | 6 | `mergeable:+2 age:+4` | unknown | yes | 4d ago |
| #402 | feat: add rtk cdk diff/synth/deploy filters | 4 | `age:+4` | unknown | unknown | 1d ago |
| #399 | feat(docs): add Indonesian README translation | 4 | `age:+4` | unknown | unknown | today |
| #398 | fix(windows): use script_cmd() for all Node.js tool spawning | 4 | `age:+4` | unknown | unknown | 1d ago |
| #395 | feat: `rtk mysql` — MySQL client output compression | 4 | `age:+4` | unknown | unknown | 1d ago |
| #394 | feat(xcodebuild): add support | 4 | `age:+4` | unknown | unknown | 1d ago |
| #392 | fix(init-uninstall): uninstall removes --claude-md artifacts on Windows | 4 | `age:+4` | unknown | unknown | 1d ago |
| #390 | fix: normalize venv/path-prefixed commands in rewrite hook | 7 | `mergeable:+2 age:+5` | unknown | yes | 5d ago |
| #385 | fix(windows): improve native build support and Git Bash integration | 7 | `mergeable:+2 age:+5` | unknown | yes | 1d ago |
| #381 | feat(gradle): add Gradle/Gradlew support with compact output (80-90% token reduction) | 5 | `age:+5` | unknown | unknown | 1d ago |
| #379 | feat: add Bundle and Rails CLI support (TOML DSL + Rust hybrid) | -5 | `conflict:-10 age:+5` | unknown | conflict | 1d ago |
| #377 |  feat(init): add Codex CLI support via AGENTS.md + RTK.md workflow | -5 | `conflict:-10 age:+5` | unknown | conflict | 1d ago |
| #368 | feat: add Maven (mvn) command support with 7 subcommands | -5 | `conflict:-10 age:+5` | unknown | conflict | today |
| #367 | Add support for CLAUDE_CONFIG_DIR | -5 | `conflict:-10 age:+5` | unknown | conflict | 5d ago |
| #364 | feat: add worktree slash commands for isolated Rust development | -5 | `conflict:-10 age:+5` | unknown | conflict | 5d ago |
| #358 | feat: OpenClaw plugin for transparent exec rewriting | 7 | `mergeable:+2 age:+5` | unknown | yes | 5d ago |
| #357 | feat: add Codex CLI integration via skill | 7 | `mergeable:+2 age:+5` | unknown | yes | 5d ago |
| #356 | feat: add Warp (Oz) integration via skill | 7 | `mergeable:+2 age:+5` | unknown | yes | 5d ago |
| #355 | feat(discover): handle more npm/npx/pnpm/pnpx patterns | 7 | `mergeable:+2 age:+5` | unknown | yes | 2d ago |
| #341 | Add az CLI provider with compact Azure DevOps/Monitor/WebApp output | 8 | `mergeable:+2 age:+6` | unknown | yes | 4d ago |
| #339 | feat: add OpenCode integration (plugin + setup) | 8 | `mergeable:+2 age:+6` | unknown | yes | 6d ago |
| #317 | feat: add rtk yarn command with smart filter routing | -4 | `conflict:-10 age:+6` | unknown | conflict | 6d ago |
| #314 | feat(glab): add GitLab CLI (glab) command support | 9 | `mergeable:+2 age:+7` | unknown | yes | 5d ago |
| #312 | feat(gradlew): Gradle support for Android/Kotlin developers | -2 | `conflict:-10 age:+8` | unknown | conflict | 1d ago |
| #308 | feat: add bazel support | 10 | `mergeable:+2 age:+8` | unknown | yes | 2d ago |
| #306 | Replace lazy_static with std::sync::LazyLock | -1 | `conflict:-10 age:+9` | unknown | conflict | 1d ago |
| #305 | feat: add grepai command with search and trace filters | 9 | `age:+9` | unknown | unknown | 1d ago |
| #303 | Add OpenCode plugin for RTK auto-rewrite | 11 | `mergeable:+2 age:+9` | unknown | yes | 2d ago |
| #301 | chore: Update dependencies | -1 | `conflict:-10 age:+9` | unknown | conflict | 6d ago |
| #300 | feat: add OpenCode plugin support | -1 | `conflict:-10 age:+9` | unknown | conflict | 2d ago |
| #295 | feat: add PowerShell installer for Windows | 12 | `mergeable:+2 age:+10` | unknown | yes | 1d ago |
| #293 | feat(kubectl): add global flags --context, --kubeconfig, -n, -l, --as | 0 | `conflict:-10 age:+10` | unknown | conflict | 5d ago |
| #292 | feat: add Ruby CLI support (rspec, rubocop) | 0 | `conflict:-10 age:+10` | unknown | conflict | 5d ago |
| #272 | feat: add support for `yarn test` (Vitest) | 0 | `conflict:-10 age:+10` | unknown | conflict | 5d ago |
| #270 | feat(pnpm): Add filter argument support | 0 | `conflict:-10 age:+10` | unknown | conflict | 1d ago |
| #269 | fix windows PATHEXT resolution for .cmd/.bat wrappers | 0 | `conflict:-10 age:+10` | unknown | conflict | today |
| #261 | feat: add cache compounding savings to rtk gain | 12 | `mergeable:+2 age:+10` | unknown | yes | 4d ago |
| #256 | fix: include command name in err/test tracking labels | 12 | `mergeable:+2 age:+10` | unknown | yes | 1d ago |
| #255 | feat: multi-provider session scanning for discover and learn | 12 | `mergeable:+2 age:+10` | unknown | yes | 1d ago |
| #254 | feat(init): add Cursor support (`rtk init --cursor`) | 12 | `mergeable:+2 age:+10` | unknown | yes | 1d ago |
| #253 | feat: add rtk sqlfluff lint with JSON filter (~75% token reduction) | 12 | `mergeable:+2 age:+10` | unknown | yes | 5d ago |
| #235 | fix(gh): show fallback note for filtered body; fix api truncation message | 0 | `conflict:-10 age:+10` | unknown | conflict | 6d ago |
| #232 | feat(pnpm): add `rtk pnpm [run] <script>` with smart filter routing | 12 | `mergeable:+2 age:+10` | unknown | yes | 6d ago |
| #226 | feat: add yarn workspace command with smart filter routing | 0 | `conflict:-10 age:+10` | unknown | conflict | 6d ago |
| #225 | Feature/opencode integration | 0 | `conflict:-10 age:+10` | unknown | conflict | 6d ago |
| #217 | fix: gh pr/issue/run view drops flags when no identifier given | 0 | `conflict:-10 age:+10` | unknown | conflict | 6d ago |
| #198 | feat(rspec): add RSpec test runner with compact output (Rails/Ruby) | 12 | `mergeable:+2 age:+10` | unknown | yes | 1d ago |
| #176 | Add first-class uv command dispatch and hook rewrite | 12 | `mergeable:+2 age:+10` | unknown | yes | 1d ago |
| #174 | feat: add Gemini CLI support via rtk init --gemini | 12 | `mergeable:+2 age:+10` | unknown | yes | today |
| #172 | Add structured rtk dotnet support (build/test/restore) with binlog/TRX parsing, robust argument forwarding, and locale-stable fallback behavior | 10 | `age:+10` | unknown | unknown | 3d ago |
| #160 | feat: add multi agent | 0 | `conflict:-10 age:+10` | unknown | conflict | 6d ago |
| #158 | Gemini CLI Hook Support (PR #131 Part 3) | 0 | `conflict:-10 age:+10` | unknown | conflict | 5d ago |
| #157 | Data Safety Rules + Extensible Rule System (PR #131 Part 2) | 0 | `conflict:-10 age:+10` | unknown | conflict | 6d ago |
| #156 | Hook Engine + Chained Command Rewriting (PR #131 Part 1) | 15 | `mergeable:+2 age:+10 linked:+3` | unknown | yes | today |
| #153 | feat: add rtk scaffold command for contributor boilerplate | 0 | `conflict:-10 age:+10` | unknown | conflict | 11d ago |
| #150 | feat(hook): native cross-platform (Windows & more) hook-rewrite command | 0 | `conflict:-10 age:+10` | unknown | conflict | 6d ago |
| #138 | feat(wrangler): add Cloudflare Wrangler CLI support | 0 | `conflict:-10 age:+10` | unknown | conflict | 2d ago |

## Duplicate PRs

### Group 1 — similar titles (add, feat) (best: #308)

| # | Score | Mergeable | Author | Title |
|---|-------|-----------|--------|-------|
| #308 ★ | 10 | yes | cmolder | feat: add bazel support |
| #339 | 8 | yes | ComputelessComputer | feat: add OpenCode integration (plugin + setup) |
| #406 | 6 | yes | mcaxtr | feat: add codex review support |
| #394 | 4 | unknown | rursache | feat(xcodebuild): add support |
| #300 | -1 | conflict | zeval | feat: add OpenCode plugin support |

### Group 2 — similar titles (feat, rtk, add, init, support) (best: #254)

| # | Score | Mergeable | Author | Title |
|---|-------|-----------|--------|-------|
| #254 ★ | 12 | yes | sahilmgandhi | feat(init): add Cursor support (`rtk init --cursor`) |
| #174 | 12 | yes | ousamabenyounes | feat: add Gemini CLI support via rtk init --gemini |
| #452 | 3 | yes | daixudk96-max | feat: add Windows hook support for rtk init --global |
| #377 | -5 | conflict | Zacaria |  feat(init): add Codex CLI support via AGENTS.md + RTK.md workflow |

### Group 3 — similar titles (routing, add, with, feat, smart, filter) (best: #232)

| # | Score | Mergeable | Author | Title |
|---|-------|-----------|--------|-------|
| #232 ★ | 12 | yes | denneulin | feat(pnpm): add `rtk pnpm [run] <script>` with smart filter routing |
| #226 | 0 | conflict | denneulin | feat: add yarn workspace command with smart filter routing |
| #317 | -4 | conflict | ThomasHoussin | feat: add rtk yarn command with smart filter routing |

### Group 4 — similar titles (skill, via, integration, add, feat) (best: #357)

| # | Score | Mergeable | Author | Title |
|---|-------|-----------|--------|-------|
| #357 ★ | 7 | yes | ComputelessComputer | feat: add Codex CLI integration via skill |
| #356 | 7 | yes | ComputelessComputer | feat: add Warp (Oz) integration via skill |

### Group 5 — similar titles (context, feat, kubectl, flags, global) (best: #426)

| # | Score | Mergeable | Author | Title |
|---|-------|-----------|--------|-------|
| #426 ★ | 4 | yes | jordi-murgo | feat(kubectl): support global context and identity flags |
| #293 | 0 | conflict | mariusvniekerk | feat(kubectl): add global flags --context, --kubeconfig, -n, -l, --as |

---
*Generated by [wshm](https://github.com/pszymkowiak/wshm)*
