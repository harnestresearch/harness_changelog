# Qoder Latest Changes

English | [简体中文](zh-CN/qoder.md) · **Highlight** | [Full Detail](full/qoder.md)

> See [qoder/README.md](qoder/README.md) for the complete five-platform index (`mac`, `win`, `ubuntu`, `ios`, `android`) covering all 58 releases (up to `0.5.13` macOS / `0.5.7` Windows & Linux Desktop, `1.46.0` iOS, and `0.10.0` Android).

## Latest Desktop Release: 0.5.13 (macOS, 2026-11-16)

See [qoder/2026-11-16_0.5.13.md](qoder/2026-11-16_0.5.13.md) for highlights, or [full/qoder/2026-11-16_0.5.13.md](full/qoder/2026-11-16_0.5.13.md) for full technical details. _(Release date from updater manifest `0.5.13.yml` `releaseDate: 2026-11-16T13:05:09.530Z`; static diff of official macOS `arm64` archives `0.5.12 → 0.5.13` only—Windows and Linux builds were not reverse-engineered and the application was not executed.)_

### Highlights

- **Renderer Subscription Cap Drain-and-Recheck (`ApplicationTransport.subscribe`)**: In renderer chunk `BHeyMntc.js`, reaching the unchanged `64`-subscription limit now awaits in-flight `releaseRequested` releases (`waitForReleases`) and re-checks capacity before throwing `APPLICATION_RATE_LIMITED` (rather than removing the `64` cap), and adds a 30-second-throttled `"Application subscription limit reached"` warning with per-method tallies. Linking this code path to the official fix for tasks failing to open after frequent task switching or notification backlogs is a static behavioral inference without live execution.
- **Worker Runtime Prompt & Telemetry Copy (`14,169 → 14,175`, `+6`)**: Adds six decoded strings in `qoder-worker-runtime.obf.mjs` covering approval-verdict boundaries, Bash risk self-assessment (including nested shells), and four telemetry/field descriptions (`Bash risk input`, `First local Auto gate reason`, `First matching Auto blacklist rule identifier`, `Local Auto approval policy version`)—verifying prompt and description text changes only, not active runtime approval-policy enforcement.
- **Agent SDK `1.0.60-alpha.62`, `qodercli` `1.1.86-hotfix.5.2` & Tiered Official Changelog Mapping**: Upgrades `@qoder-ai/qoder-agent-sdk` / `@qoder-ai/qoder-cn-agent-sdk` `1.0.60-alpha.50 → 1.0.60-alpha.62`, updates `qoderCliVersion` `1.1.86-hotfix.5 → 1.1.86-hotfix.5.2` on Electron `43.8.4`, and rebuilds `qoder-office-xlsx` `xlsx-sidecar`. Among the five remaining official fix notes, slow device-info notification timeouts have indirect transport corroboration only, while subagent model config, `context-limit` compaction recognition, post-switch usage calculation, and fork/resumed compacted message links have no new local static evidence (which does not mean the fixes are absent).

---

## Latest Android Release: 0.10.0 (Android, 2026-11-15)

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
