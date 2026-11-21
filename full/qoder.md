# Qoder Latest Changes

English | [简体中文](../zh-CN/full/qoder.md) · [Highlight](../qoder.md) | **Full Detail**

> See [qoder/README.md](qoder/README.md) for the complete five-platform index (`mac`, `win`, `ubuntu`, `ios`, `android`) covering all 58 releases (up to `0.5.13` macOS / `0.5.7` Windows & Linux Desktop, `1.46.0` iOS, and `0.10.0` Android).

## Latest Desktop Release: 0.5.13 (macOS, 2026-11-16)

See [qoder/2026-11-16_0.5.13.md](qoder/2026-11-16_0.5.13.md) for full details. Static diff of official macOS `arm64` archives (`0.5.12` → `0.5.13`, `Qoder-mac-arm64.zip` `342,120,251` → `342,127,454` B, `+7,203` B; `releaseDate: 2026-11-16T13:05:09.530Z` in updater manifest `0.5.13.yml`, where empty `releaseNotes: {}` does not imply no official web notes and archive `mtime` is not treated as `Last-Modified`; Windows/Linux not reverse-engineered, client not executed):

- **Renderer `ApplicationTransport.subscribe` Wait-for-Release (`Dta6yTTQ.js` `176,239` B → `BHeyMntc.js` `177,975` B)**: Retains the `64`-subscription cap (`subscriptions.size >= 64`) rather than removing it, awaits in-flight `releaseRequested` subscriptions (`waitForReleases` / `releaseSubscription`) before re-checking capacity and throwing `APPLICATION_RATE_LIMITED`, and adds a 30s-throttled (`lastLimitLogAt`) `warn` log `"Application subscription limit reached"` (`ApplicationTransport`, tracking per-method `{active, establishing, releasing, releaseFailed, oldestAgeMs}`). Connecting this to the official task-switching / notification-backlog hang fix is a static behavioral inference without runtime execution.
- **Worker Decoded String Table (`14,169 → 14,175`, `+6 / −0`)**: `qoder-worker-runtime.obf.mjs` (`+10,705` B, commit `0b1f085` → `cfef7df`) adds 6 strings—an approval-verdict boundary prompt, a Bash risk self-assessment prompt covering nested shells, and 4 telemetry/field descriptions (`Bash risk input`, `First local Auto gate reason`, `First matching Auto blacklist rule identifier`, `Local Auto approval policy version`)—confirming prompt and description text additions only rather than active runtime policy enforcement.
- **SDK `1.0.60-alpha.62`, `qodercli` `1.1.86-hotfix.5.2` & Tiered Official Changelog Stratification**: Bumps `@qoder-ai/qoder-agent-sdk` / `@qoder-ai/qoder-cn-agent-sdk` `1.0.60-alpha.50 → 1.0.60-alpha.62`, updates `qoderCliVersion` and the OSS worker URL template `1.1.86-hotfix.5 → 1.1.86-hotfix.5.2` (Electron `43.8.4`, `electronMain.js` `+10,751` B re-obfuscated with zero plaintext natural-language string delta), and repackages `qoder-office-xlsx` (`dd2dff0f…` → `9927b58d…`, Rust `xlsx-sidecar` `8,730,592 → 8,730,704` B). Remaining official fix notes stratify into indirect-only (`device info` slow notification timeout) and no new local static evidence found (subagent model config, `context-limit` compaction recovery, post-switch usage calculation, and fork/resumed compacted message links—not ruling out obfuscated logic or remote configuration).

---

## Latest Android Release: 0.10.0 (Android, 2026-11-15)

See [qoder/2026-11-15_0.10.0.md](qoder/2026-11-15_0.10.0.md) for full details. Static cross-channel diff of APKPure Google Play split XAPK `0.9.0` (`versionCode` `67`, `minSdkVersion` `28`, `targetSdkVersion` `36`) vs. official universal single APK `0.10.0` (`versionCode` `70`; Play date `2026-11-15` without exact timestamp, CDN `Last-Modified`: `2026-11-15 10:56:40` UTC; iOS not covered, APKs not executed; `lib/`/`res/`/`resources.arsc` and channel-wrapper manifest diffs reflect split-vs-universal packaging, and the signing key difference `ddf5ab4a…` vs. `a54169cc…` is an unconfirmed channel hypothesis only):

- **Expanded `features/credits` & `qoder_web_fetch.js` Bridge**: Builds on pre-existing `ChannelValidity` and `UserPlanResponse` in `0.9.0` by adding 11 campaign/reward/claim models (`+ JsonAdapter`s), `assets/qoder_web_fetch.js` (`5,397` B, hooking WebView `window.fetch` via `window.qoderBenefits`), and `"Plan & Usage"` / `"Benefits Center"` / WebView-update dynamic-content keys (`1,852 → 1,928` keys, `+79 / -3`).
- **`ModelManagementValue` & Graded Thinking/Context UI Copy**: Adds `ModelManagementValue` (`+ JsonAdapter`) and `ModelManagement{Binding,Configuration,Directory,Editor}` (expanding `AvailableModelDTO` / `EnvironmentAvailableModelDTO` while keeping `AvailableModelPromotionDTO`), plus 23 `composer.model_management.*` keys spanning 6 thinking-effort tiers and context window alongside `"Model management (Preview)"`, `"Preview only. Desktop settings will not change."`, and `"Simulate *"` strings.
- **Homepage/Drawer Strings & OTLP Technical Batch Extension**: Removes `ic_home_all_tasks_guidance(.dark).png`, adds empty-state, drawer, Remote Control CLI/Desktop/Cloud, voice-input (`assets/qoduck_voice/*.webp`), and `"Smart Glasses"` / `"Theme"` copy, and extends the existing `OtlpTelemetryClient` with `exportTechnicalBatch`, `TechnicalSnapshot`, `TechnicalScalarValues`, `TechnicalEvent`, and `recordScrollWindow(TechnicalScrollWindow)`.

---

## Previous Desktop Release: 0.5.12 (macOS, 2026-11-14)

See [qoder/2026-11-14_0.5.12.md](qoder/2026-11-14_0.5.12.md) for full details. Static diff of official macOS `arm64` archives (`0.5.11` → `0.5.12`, `Qoder-mac-arm64.zip` `342,109,501` B → `342,120,251` B; Windows/Linux not reverse-engineered, client not executed):

- **Worker `transcript.resume.*` Static String Evidence**: Decoded `qoder-worker-runtime.obf.mjs` (`+2,423` B, commit `2c8933e` → `0b1f085`) adds exactly 4 strings (`transcript.resume.invalid_file_snapshot_skipped`, `transcript.resume.invalid_replacements_skipped`, `transcript.resume.invalid_selected_message`, `Transcript resume failed: unsafe (`) corresponding to the official session-snapshot/replacement-record interruption fix note (runtime skip/failure behavior not dynamically verified).
- **SDK `1.0.60-alpha.50`, `qodercli` `1.1.86-hotfix.5` & `qoder-office-xlsx` Rebuild**: Upgrades `@qoder-ai/qoder-agent-sdk` / `@qoder-ai/qoder-cn-agent-sdk` (`npm:@ali/qoder{,cn}-agent-sdk-next`) `1.0.60-alpha.36` → `1.0.60-alpha.50`, bumps `qoderCliVersion` and the OSS worker-runtime URL template `1.1.86-hotfix.4` → `1.1.86-hotfix.5` (Electron `43.8.4`, `electronMain.js` `+4,898` B RC4 re-obfuscated with zero plaintext natural-language string delta), and repackages `qoder-office-xlsx` (`0ed5a5ea…` → `dd2dff0f…`, Rust `xlsx-sidecar` recompiled `8,730,672` → `8,730,592` B, `catalog.v1.json` digests refreshed).
- **Official Changelog Separation**: Four official `0.5.12` items (automatic task title improvements, timelier diff preview summary/line counts, missing device-identifier init fix, and custom model catalog `reasoning effort` / disabled-reasoning recognition) have no new local static diff evidence (`app/out/renderer` byte-identical; `device`/`umid` string sets unchanged; existing reasoning copy already present in both `0.5.11` and `0.5.12`), which does not rule out logic in obfuscated `electronMain.js`, remote configuration, or on-demand `qodercli` `1.1.86-hotfix.5`.

---

## Recent Architectural Baseline: 0.5.3 (2026-11-02)

See [qoder/2026-11-02_0.5.3.md](qoder/2026-11-02_0.5.3.md) for full details.

### Overview

Qoder Desktop `0.5.3` pairs an Electron host (`out/main/electronMain.js` + `out/main/pluginHost.js` + 11 built-in `.qoder-app-plugin` extensions) with `@qoder-ai/qoder-agent-sdk@1.0.59-alpha.9` (`qoder-worker-runtime.obf.mjs` / Go-based `qodercli` `1.1.79-hotfix.11`, wire protocol `1.5.0`, streaming `proto/chat.proto` OpenAI-compatible function calls). Capabilities are exposed through **35+ core runtime tools** and **four parallel MCP registration channels** spanning `stdio`, `StreamableHTTP`/`SSE`, and zero-copy in-process SDK servers (`mcp.registerInProcessServer`).

### Core Agent Runtime & Built-in Tool Registry (`qoder-worker-runtime`)

- **File, Search & Interactive PTY Execution**: `Read`, `Write`, `Edit`, `Glob`, `Grep`, `GrepRipgrep`, `Bash` (with interactive PTY `BashInput`, `BashOutput`, `BashResize`, and background process `Monitor`), `WebFetch`, and `WebSearch`.
- **Planning, Worktrees, Goals, Cron & Subagent Orchestration**:
  - `TodoWrite`, `AskUserQuestion`, `EnterPlanMode` / `ExitPlanMode`, `EnterWorktree` / `ExitWorktree`, `CreateGoal` / `UpdateGoal`, `CronCreate` / `CronList` / `CronDelete`, `Skill`, and `Workflow`.
  - Multi-agent orchestration via `Agent` (supporting `fork` and Claude Code `.claude` agent compatibility via `loadAgentsFromClaudeCodeProject()`), `SendMessage`, and `Task` / `TaskList` / `TaskUpdate` across 8 `subagent_type` roles (`researcher`, `frontend-dev`, `backend-dev`, `qa`, `ux-designer`, `code-reviewer`, `operations`, `general-engineer`), plus `Codebase` structural symbol relation queries (`calls`, `called_by`, `references`, `extends`, `implements`, `overrides`, etc.).
- **Multimodal Generation & Lazy MCP Discovery**:
  - `ImageSearch`, `ImageGen`, `VideoGen`, and dynamic MCP meta-tools `mcp_list`, `mcp_get`, and `mcp_call` (with per-tool permission namespace `mcp__<server>__<tool>` and policies `always_allow | always_ask | always_deny`).

### Four-Channel Built-in MCP & Extension Architecture

1. **Channel 1 — Native Workspace Semantic Index (`qoder-context` `1.0.91.b22f2d0a`)**:
   - Invisible mandatory bundled plugin (`qoder-context@qoderapp-bundler`) running `qoder-search.bundle.mjs mcp-bridge` under `ELECTRON_RUN_AS_NODE` locally—or `${QODER_REMOTE_RUNTIME_ROOT}/bin/node` automatically over SSH/WSL remote sessions—backed by native NAPI `mtree.node`, embedded `rg`, and lifecycle hooks (`SessionStart`, `UserPromptSubmit`, `PostToolUse`, `Stop`).
   - Exposes `alwaysLoad` tools `SearchWorkspace` and `SearchKnowledge`.
2. **Channel 2 — Knowledge Center (`repowiki` In-Process + `qoder-qmind` Stdio, 29 Tools)**:
   - In-process server `repowiki` (14 tools): read-only `ListWiki` / `ReadWiki` plus 12 gated write/graph tools (`list_wiki`, `read_wiki`, `edit_wiki`, `write_wiki`, `delete_wiki`, `reset_wiki_update_commit`, `list_knowledge`, `read_knowledge`, `edit_knowledge`, `write_knowledge`, `delete_knowledge`, `link_knowledge`, `unlink_knowledge`).
   - Stdio server `qoder-qmind` (`CONTRACT_VERSION = "5.4.0"`, 15 strict Zod v4 tools): `qmind.create_notebook`, `delete_notebook`, `list_notebooks`, `retrieve`, `list_sources`, `get_source`, `read_source`, `add_source` (HTTPS URL or local file), `delete_source`, `create_directory`, `move_source`, and cron-scheduled maintenance tools `qmind.{create,update,delete,list}_scheduled_task` (`compilation`, `condensation`, `lint`, `source_refresh`, `source_binding_sync`).
3. **Channel 3 — Full-Stack Hosting (`qoder_sites` In-Process, 33 Tools)**:
   - Registers `qoder_sites` (`v0.1.0`) enforcing host-sealed opaque references (`siteRef`, `backendRef`, `schemaRef`, `planRef`, `secretRef`, `accessRef`) and `confirm: true` gates across 33 tools: site lifecycle & subdomain checks (`list_sites`, `prepare_site`, `publish_site`, `show_publish_confirmation`, `check_subdomain`, `update_site`, `resume_site`, `delete_project`), access control (`get_site_access`, `update_access_policy`, `put_access_target`, `remove_access_target`), serverless backend & SQL migrations (`ensure_backend`, `get_database_schema`, `create_database_migration`, `apply_database_migration`, single-PK `query/insert/update/delete_database_row*`, `get_function_logs`, `get_analytics`), and object storage (`list/upload/download/delete_storage_*`, capped at `10 MiB`).
4. **Channel 4 — Real-Device Mobile Control (`qoder.phone-use` In-Process, 50 Tools) & Desktop/IM Bridges**:
   - Registers three local-only (`executionLocation === "local"`) in-process MCP servers: `mobile` (`mobile_list_devices`), `ios` (`v0.4.0`, **28 `ios_*` tools** wrapping bundled `wda/QoderControl.ipa` WebDriverAgent Runner, Xcode team signing provisioning, element/selector/coordinate `tap`/`swipe`/`type_text`, `ios_collect_list`, `ios_pause`/`ios_resume` for biometric/CAPTCHA handoff, and `ios_batch` up to 20 steps), and `android` (`v0.5.2`, **21 `android_*` tools** wrapping SHA-256 verified `QoderControl.apk` + `scrcpy-server.jar`, intentionally omitting `Enter`/submit from `android_press_key` for safety).
   - `qoder.computer-control`: Launches native `QoderComputerUseBridge` (`Qoder Computer Use.app` / `QoderComputerUse.exe`) exposing `event-stream` stdio MCP (`event_stream_start`, `event_stream_status`, `event_stream_stop`) alongside `computer-use`, `record-and-replay`, and `browser-use` skills.
   - `qoder.communication`: Bridges marketplace IM workers (`wecom-channel`, `dingtalk-channel`) into host sessions via `registerInProcessServer` with `_meta["com.qoder/turnContext"]` propagation.
   - **Browser Connector, Native Helpers & `0.5.3` Fixes**: Ships Chrome extension `v1.7.6` (`oknkojfamnpljdfpinkhbibicojelkoj`) + Native Messaging host `qoder-app-host.cjs` forwarding page-level `webmcp_list_tools` / `webmcp_invoke_tool`, `xlsx-sidecar` binary for `qoder.office`, `@ali/qoder-collab-cli@0.1.7`, and 6 native helpers in `Resources/bin/` (including `dji_mic_button.node`, `hosted_presentation_host.node`, `native_clipboard.node`, and `notification_permission.node`); `0.5.3` ("Everyday Polish") also resolves workspace/recent-task list loading-state stalls under rapid updates and historical task-list loading failures when source-session metadata is empty.
