# Qoder Latest Changes

English | [简体中文](zh-CN/qoder.md) · **Highlight** | [Full Detail](full/qoder.md)

> See [qoder/README.md](qoder/README.md) for the complete five-platform index (`mac`, `win`, `ubuntu`, `ios`, `android`) covering all 61 releases (up to `0.5.21` Desktop across `mac`/`win`/`ubuntu`, `1.46.0` iOS, and `2.0.0` Android; intermediate desktop versions between `0.5.13` and `0.5.20` and intermediate Android `0.11.0` were never cataloged in this repository—Android `2.0.0` covers strictly `0.11.0 → 2.0.0`).

## Latest Desktop Release: 0.5.21 (macOS / Windows / Linux, 2026-11-27)

See [qoder/2026-11-27_0.5.21.md](qoder/2026-11-27_0.5.21.md) for highlights, or [full/qoder/2026-11-27_0.5.21.md](full/qoder/2026-11-27_0.5.21.md) for full technical details. _(Official changelog heading `November 27, 2026` — "Everyday Polish" [no standalone `"Qoder 0.5.21"` heading line on the English page, bound via HTML anchors `id="0.5.21"` / `qoder-0521-everyday-polish`, Chinese 「日常优化」, updater manifests, and package metadata]; updater manifest `releaseDate` `2026-11-27T08:03:56.246Z` macOS / `08:14:31.290Z` Windows / `07:54:29.115Z` Linux; shared build commit `eb36b7b303185facdb2ef70f0eaf9f8199b2c413`. Covers adjacent pair `0.5.20 → 0.5.21` on macOS `arm64`, Windows `x64`, and Linux `amd64` `.deb` from versioned `releases/0.5.21/` URLs; `.rpm` manifest/HEAD only, `Qoder-mac-x64.zip` exists on CDN but not downloaded/analyzed, `Qoder-win-arm64-user.exe` returned 404, NSIS not disassembled, Android/iOS uncovered, not executed at runtime.)_

### Highlights

- **Feature — AppHub Connector Sync**: Official notes sync locally authorized Streamable HTTP connectors to the cloud for cloud agents and automations. Static inspection of extracted macOS `arm64` metadata verifies new renderer literals (`appHubError`, `loadingSyncSources`, `streamable_http`), main-process IPC (`cloud-configuration:list-apphub-items`, `cloud-configuration:sync-apphub-vault`), and two credential-chain telemetry strings (`SDK JobToken callback failed`, `SDK JobToken callback returned no credential`); cloud sync execution itself is unverified at runtime.
- **Improvement & Fixes (Statically Unverifiable)**: Official notes add a prompt on the sign-in screen and Settings to re-run network diagnostics after changing proxy settings, plus four fixes (cloud automation editing leaving removed Skills/connectors or clearing selections early, device clock skew rejecting valid registration/pairing/reconnection, local tasks failing to load model lists under a system proxy, and Windows OpenSSH host verification failures). The decoded worker string table is byte-for-byte identical between `0.5.20` and `0.5.21` (`13,966 === 13,966`) and the static diff report records no new fix/prompt copy—none of these five items can be independently verified statically.
- **Runtime & Hotfix Packaging**: Electron remains `43.8.4`; Agent SDK bumps `1.0.62-alpha.9 → 1.0.62-alpha.10` and `qoderCliVersion` bumps `1.1.96-hotfix.8 → 1.1.96-hotfix.9` (dependency set unchanged). Disk deltas: macOS `arm64` zip `−426` B, Windows `x64` `.exe` `−5,880` B, Windows `app.zip` `+8,652` B, Linux `amd64` `.deb` `+652,764` B; static diff report cites `app.asar` `+13,300` B (`electronMain.js` `+9,814` B) and `context-plugin`/`office-xlsx` archive updates.

---

## Latest Android Release: 2.0.0 (Android, 2026-11-27)

See [qoder/2026-11-27_2.0.0.md](qoder/2026-11-27_2.0.0.md) for highlights, or [full/qoder/2026-11-27_2.0.0.md](full/qoder/2026-11-27_2.0.0.md) for full technical details. _(Date from official CDN rolling `qoder.apk` HTTP `Last-Modified`: `2026-11-27 14:44:05` UTC / `22:44:05` UTC+8. Official mobile changelog currently stops at `0.11.0` [`2026-11-25`] with no `2.0.0` entry, and Google Play still serves `0.11.0`—Play's `"Updated on Nov 27, 2026"` is **not** a `2.0.0` listing or release date. Intermediate Android `0.11.0` was never cataloged in this repository, so `0.10.0` is **not** the baseline—this entry covers strictly `0.11.0` [`versionCode` `73`] → `2.0.0` [`versionCode` `75`]; skipping `74` and `1.x` reflects official versioning policy. Pure two-APK static diff; iOS uncovered; not executed at runtime.)_

### Highlights

- **QBot Assistant (`features/qbot`, `31` `/api/v1/qbot*` Paths & `335` `qbot.*` Keys)**: Introduces QBot across manifest routes (`qbot`, `qbot_list`), DEX APIs (`0 → 31` `/api/v1/qbot*` paths plus `/signed-artifact-download` and `QBOT_ARTIFACT_*` event codes), `335` new `qbot.*` dynamic-content keys (`2,220 → 2,572`), dual-mode navigation drawer icons, `artifact_file_icons.ttf`, full `qbot_*` visual/audio assets, and Figma connector SVGs (`qbot_connector_figma*.svg`). `streamable_http` does **not** appear in `2.0.0` DEX.
- **Biometric & Local Device Remote-Control Authorization (`USE_BIOMETRIC`)**: Adds `android.permission.USE_BIOMETRIC` in `AndroidManifest.xml` together with `device_management.remote_control.*` copy covering biometric authorization (`"Allow Qoder Mobile to remotely control this device"`), passcode fallback (`"Use device passcode"`), and keeping the device awake while Qoder runs (`"Keep this device awake"`).
- **QBot Schedules, Automation-Run Extensions & Onboarding Assets**: Adds QBot schedule endpoints (`schedules`, `pause`, `unpause`), newly added `/api/v1/qcloud/cloud-automation-runs` and `/api/v1/remote/automation{s,-runs}` paths (distinct from `qcloud`/`remote` endpoints already present in `0.11.0`), `automation_history_empty_pendulum.webp`, and editor-connection GIFs (`home_connect_editor_{en,zh}_{dark,light}.gif`).

---

## Previous Desktop Release: 0.5.20 (macOS / Windows / Linux, 2026-11-25)

See [qoder/2026-11-25_0.5.20.md](qoder/2026-11-25_0.5.20.md) for highlights, or [full/qoder/2026-11-25_0.5.20.md](full/qoder/2026-11-25_0.5.20.md) for full technical details. _(Official changelog heading `November 25, 2026` — "Cross-Device Collaboration and Cloud Tasks"; updater manifest `releaseDate` `2026-11-25T14:26:16.356Z` macOS / `14:34:35.952Z` Windows / `14:13:26.874Z` Linux. Intermediate desktop releases `0.5.14` and `0.5.16`–`0.5.19` are not yet recorded in this repository, so `0.5.13` is **not** the baseline—this entry covers strictly the `0.5.18 → 0.5.20` static diff, deliberately skipping `0.5.19`, which has no official changelog entry and was not analyzed. Full static diff on macOS `arm64`; Windows `x64` `exe`+`app.zip` and Linux `amd64` `.deb` sizes/SHA-256 verified with payload/Authenticode details from static package inspection, NSIS not disassembled, `.rpm` manifest SHA-256 only; macOS `x64`, Windows `arm64`, Android, and iOS uncovered; not executed at runtime.)_

### Highlights

- **Cloud Tasks, Cross-Device Collaboration & Local Task Recovery**: Official `0.5.20` notes introduce desktop cloud tasks, cross-device workspace file downloads and permission-scoped automation management, and resuming unfinished local tasks after quitting or updating. Static diffs confirm `14` new `cloud-session:*` IPC channels, expanded `automations.*` IPC and `+6` new `AUTOMATION_TASK_*` error codes (`2 → 8`), `19` `automationPeer.*` renderer keys, `automations.read.v1`/`manage.v1`, `chatSession.fileDownload.*` / `Resources/runtime/file-transfer.cjs`, and `chat-session-recovery:*` / `.recoveryPhase` / `20261119-00-chat-session-restart-resumption.sql` (cloud/peer execution is server-dependent and unverified at runtime).
- **Managed Device Sign-In, Archive Groups, Extra-Large Text & 125% Scaling**: Official notes add enterprise managed-device sign-in restrictions, group restore/delete for archived local tasks (search bulk delete affects matching items only), extra-large text, and independent `125%` interface scaling. Static diffs confirm `auth.deviceAccountBlocked.{confirm,description}`, `"Device account policy rejected the current login"`, `"Enterprise VPC sign-in"`, `restoreGroupTasks`/`archivedGroupMore`/`deleteArchiveSearchResults*`, and `fontSizeExtraLarge`/`uiScaleExtraLarge` entry strings only (no plaintext layout parameters; enterprise policies are server-dependent).
- **Fixes & Unannounced Runtime/Extension Changes**: Official fixes cover post-migration plugin install failures and restricted Windows plugin background services (partial static clues only: worker archive-install guards, `pluginHost.js` `+1,487` B, removal of `WindowsPluginJob.cs`/`windows-job.ps1`—cannot attribute line-by-line), automation run blocking after disconnect (`20261121-00-automation-run-retry-count.sql` & `20261121-01-automation-manual-pending-index.sql`), valid-model conversation start (indirect sign-out/reselect copy only), and Remote Control message ordering (`20261123-01-async-question-order-clock` + `.messageOrder`). Unannounced changes include `qodercli` `1.1.86-hotfix.19 → 1.1.96-hotfix.8` (`−826,457` B) on Electron `43.8.4`, Agent SDK `1.0.62-alpha.2 → alpha.9`, `qoder.knowledge.center` split into `qoder.knowledge.wiki` + `qoder.qmind`, `@ali/qoder-text-sdk` `0.5.2`, `@qoder-space/in-app-browser`, Qwen sign-in strings, `statusline` prompt split, and refreshed application icons.

---

## Earlier Tracked Desktop Release: 0.5.13 (macOS, 2026-11-16)

See [qoder/2026-11-16_0.5.13.md](qoder/2026-11-16_0.5.13.md) for highlights, or [full/qoder/2026-11-16_0.5.13.md](full/qoder/2026-11-16_0.5.13.md) for full technical details. _(Release date from updater manifest `0.5.13.yml` `releaseDate: 2026-11-16T13:05:09.530Z`; static diff of official macOS `arm64` archives `0.5.12 → 0.5.13` only—Windows and Linux builds were not reverse-engineered and the application was not executed.)_

### Highlights

- **Renderer Subscription Cap Drain-and-Recheck (`ApplicationTransport.subscribe`)**: In renderer chunk `BHeyMntc.js`, reaching the unchanged `64`-subscription limit now awaits in-flight `releaseRequested` releases (`waitForReleases`) and re-checks capacity before throwing `APPLICATION_RATE_LIMITED` (rather than removing the `64` cap), and adds a 30-second-throttled `"Application subscription limit reached"` warning with per-method tallies. Linking this code path to the official fix for tasks failing to open after frequent task switching or notification backlogs is a static behavioral inference without live execution.
- **Worker Runtime Prompt & Telemetry Copy (`14,169 → 14,175`, `+6`)**: Adds six decoded strings in `qoder-worker-runtime.obf.mjs` covering approval-verdict boundaries, Bash risk self-assessment (including nested shells), and four telemetry/field descriptions (`Bash risk input`, `First local Auto gate reason`, `First matching Auto blacklist rule identifier`, `Local Auto approval policy version`)—verifying prompt and description text changes only, not active runtime approval-policy enforcement.
- **Agent SDK `1.0.60-alpha.62`, `qodercli` `1.1.86-hotfix.5.2` & Tiered Official Changelog Mapping**: Upgrades `@qoder-ai/qoder-agent-sdk` / `@qoder-ai/qoder-cn-agent-sdk` `1.0.60-alpha.50 → 1.0.60-alpha.62`, updates `qoderCliVersion` `1.1.86-hotfix.5 → 1.1.86-hotfix.5.2` on Electron `43.8.4`, and rebuilds `qoder-office-xlsx` `xlsx-sidecar`. Among the five remaining official fix notes, slow device-info notification timeouts have indirect transport corroboration only, while subagent model config, `context-limit` compaction recognition, post-switch usage calculation, and fork/resumed compacted message links have no new local static evidence (which does not mean the fixes are absent).

---

## Earlier Tracked Android Release: 0.10.0 (Android, 2026-11-15)

See [qoder/2026-11-15_0.10.0.md](qoder/2026-11-15_0.10.0.md) for highlights, or [full/qoder/2026-11-15_0.10.0.md](full/qoder/2026-11-15_0.10.0.md) for full technical details. _(Google Play date `"Updated on Nov 15, 2026"`, exact storefront publish timestamp unconfirmed; official CDN `qoder.apk` `Last-Modified`: `2026-11-15 10:56:40` UTC. Static diff of APKPure Play-split XAPK `0.9.0` (`versionCode` `67`) vs. official universal single APK `0.10.0` (`versionCode` `70`); iOS not covered, APKs not executed, and `lib/`/`res/`/signing-key differences are subject to cross-channel packaging limits.)_

### Highlights

- **Benefits Center Campaign Models & Hybrid WebView Bridge**: Expands existing `features/credits` (`ChannelValidity` and `UserPlanResponse` in `0.9.0`) with 11 campaign/reward/claim DTOs, `assets/qoder_web_fetch.js` (`window.qoderBenefits` native fetch bridge), and `"Plan & Usage"` / `"Benefits Center"` drawer and settings copy.
- **Model Management Copy & `ModelManagementValue` DTOs (With Preview/Simulation Copy)**: Adds `ModelManagementValue` and 23 `composer.model_management.*` keys covering thinking on/off, 6 thinking effort tiers (`Minimal`–`Maximum`), and context window—alongside `"Model management (Preview)"`, `"Preview only. Desktop settings will not change."`, and `"Simulate *"` strings (live persistence not runtime-verified).
- **Homepage Guidance Cleanup, Drawer Entries & OTLP Technical Batch API**: Removes `ic_home_all_tasks_guidance(.dark).png`, adds empty-state, navigation drawer (`Scheduled Tasks`, `Archived`, `Device Management`, `Invite friends`), Remote Control, voice-input, and `"Smart Glasses"` / `"Theme"` settings copy, and extends the existing `OtlpTelemetryClient` with `exportTechnicalBatch`, `TechnicalSnapshot`, `TechnicalEvent`, and `recordScrollWindow`.

---

## Previous Desktop Release: 0.5.12 (macOS, 2026-11-14)

See [qoder/2026-11-14_0.5.12.md](qoder/2026-11-14_0.5.12.md) for highlights, or [full/qoder/2026-11-14_0.5.12.md](full/qoder/2026-11-14_0.5.12.md) for full technical details. _(Static diff of official macOS `arm64` archives `0.5.11 → 0.5.12` only; Windows and Linux builds were not reverse-engineered and no live runtime verification was performed.)_

### Highlights

- **Session Transcript Resume Validation Strings (Static Evidence)**: Adds four decoded worker runtime diagnostic strings (`transcript.resume.invalid_file_snapshot_skipped`, `transcript.resume.invalid_replacements_skipped`, `transcript.resume.invalid_selected_message`, and `Transcript resume failed: unsafe (`) aligned with the official fix note on conversation interruptions caused by abnormal session snapshots or content-replacement records (runtime behavior not dynamically verified).
- **Agent SDK `1.0.60-alpha.50`, `qodercli` `1.1.86-hotfix.5` & `xlsx-sidecar` Rebuild**: Advances `@qoder-ai/qoder-agent-sdk` / `@qoder-ai/qoder-cn-agent-sdk` from `1.0.60-alpha.36` to `1.0.60-alpha.50`, updates `qoderCliVersion` and its OSS download template from `1.1.86-hotfix.4` to `1.1.86-hotfix.5` on Electron `43.8.4`, and repackages `qoder-office-xlsx` with a recompiled Rust `xlsx-sidecar`.
- **Official Changelog Items Separated from Local Static Evidence**: Four official `0.5.12` notes (automatic task titles, timelier diff preview summary/line counts, missing device-identifier initialization fix, and custom model catalog `reasoning effort` / disabled-reasoning detection) show no new local static diff in the macOS `arm64` bundle (`app/out/renderer` is byte-identical and reasoning validation copy was already present in both `0.5.11` and `0.5.12`); absence of new local static evidence does not mean those capabilities are absent.

---

## Recent Architectural Baseline: 0.5.3 (2026-11-02)

See [qoder/2026-11-02_0.5.3.md](qoder/2026-11-02_0.5.3.md) for highlights, or [full/qoder/2026-11-02_0.5.3.md](full/qoder/2026-11-02_0.5.3.md) for full technical details.

### Highlights

- **Agentic Coding Workbench, Git Worktrees & Multi-Agent Experts**: Combines interactive terminals, Plan mode, goal & scheduled cron tracking, isolated Git Worktree parallel branches, session forking, and specialized multi-agent Experts (researcher, frontend, backend, QA, UX designer, code reviewer, and operations).
- **Semantic Workspace Indexing, Repo Wiki & QMind Notebooks**: Automatically indexes local and remote SSH/WSL projects for instant semantic code search, generates editable structured Repo Wikis and architecture knowledge cards, and integrates QMind notebooks with web/file sources and scheduled knowledge maintenance tasks.
- **Full-Stack Qoder Sites Hosting (Database, Functions, Storage & Analytics)**: Build, preview, and publish full-stack web apps to `.qoder.site` subdomains with managed SQL database migrations, serverless functions with live log inspection, object storage, granular email/account access policies, and 24h/7d/30d traffic analytics.
- **USB iOS & Android Real-Device Automation ("Phone Use")**: Discover, provision, preview, and control locally connected iPhones and Android devices/emulators directly from local tasks—supporting batched UI gestures, app launch verification, and automatic safety pauses on biometric, password, or human-verification screens.
- **Computer Use Recording, Browser Connector, Canvas & `0.5.3` Stability Fixes**: Includes opt-in desktop control with action record-and-replay, a Chrome/Edge Browser Connector extension, interactive Canvas visual recipes, native spreadsheet/slide/CSV previewers, three-tier security scanning, and WeCom/DingTalk IM bot integration; `0.5.3` also fixes workspace/recent-task lists sticking in a loading state during rapid updates and resolves historical task-list loading failures when source-session metadata is empty.
