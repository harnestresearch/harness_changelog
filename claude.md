# Claude Latest Changes

English | [简体中文](zh-CN/claude.md) · **Highlight** | [Full Detail](full/claude.md)

> See [claude/README.md](claude/README.md) for the complete five-platform index (`mac`, `win`, `ubuntu`, `ios`, `android`) covering all 534 historical releases (245 Desktop + 289 Mobile).

## Latest Android Release: 1.261124.19 (Android, 2026-11-25 Uptodown Window)

See [claude/2026-11-25_1.261124.19.md](claude/2026-11-25_1.261124.19.md) for highlights, or [full/claude/2026-11-25_1.261124.19.md](full/claude/2026-11-25_1.261124.19.md) for full technical details. _(Imprecise `2026-11-25/26` window from Uptodown `"Nov 25, 2026"` + `"Matches the published version"`; `2026-11-26` Google Play US snapshot remained `"Updated on: Nov 24, 2026"` without version numbers. Static diff of **Uptodown third-party mirror** Play-split XAPKs `1.261123.19 → 1.261124.19`—not direct Play downloads; full `apksigner` verify not performed, iOS & historical `1.261120.19`–`1.261122.*` gap not covered, APKs not executed, and static presence does not confirm live rollout.)_

- **GitHub Integration & PR / Plan / Tool-Call Approvals**: Adds `claudeai.code.connect_github_card.*` telemetry, Claude GitHub App installation prompts, granular PR/plan/tool-call approval failure messages, organization connector-approval notices, `CollapsedToolsSheetDestination${HostPage,ProductPage,Viewer}`, and cloud-environment setup prompts.
- **Safeguards Model-Switch Prompts & Places Panel**: Ships ~12 biology/cybersecurity/sensitive-topic safeguards auto-model-switch strings on mobile, adds the `claudeai.places_list.*` Places selection panel (`Next place` / `Previous place`) and `voice.reachability_checked`, and adds usage-page sections, `Default tab` settings, project instructions editing with explicit PHI exclusion, shared-session link visibility, read-aloud limit copy, and ~20 sign-in/maintenance/model-limit error strings while retiring `continue_on_cloud.*` (`8 → 1`), `ready_made_card.rated`, and `money.message_box.*`.
- **Packaging & Invariants**: XAPK members drop `37 → 30` (language splits `28 → 21`: `+te`, `−am/fil/hi/ml/mr/sw/ta/tl`) while all `20` native `.so` libraries remain byte-identical, `minSdkVersion` `32` / `targetSdkVersion` `37`, `66` permissions, and `83` components stay unchanged, and **no API endpoints were added or removed**.

---

## Latest Desktop Release: 5.11492.5 (2026-11-14)

See [claude/2026-11-14_5.11492.5.md](claude/2026-11-14_5.11492.5.md) for highlights, or [full/claude/2026-11-14_5.11492.5.md](full/claude/2026-11-14_5.11492.5.md) for full technical details.

- **Enterprise Managed File-Read Policy & Auto-Mode Guidance**: Added the `blockFileToolReadsOutsideWorkingDirectories` managed setting governing one-time file-read prompts in auto-mode, and clarified machine-wide `env.CLAUDE_CODE_AUTO_MODE_MODEL` override guidance in managed settings documentation.
- **Office Document Skill Security & Diff Hardening**: Hardened the bundled `docx`, `pptx`, and `xlsx` validators against Windows-style drive/root path traversal and out-of-bounds OOXML relationship targets, and replaced external `git diff` subprocesses during document redlining with a work-bounded diff algorithm.
- **Engine Session Storage Validation & 10-Locale Catch-Up**: Added a unified local session storage key validation schema (including `jobs-root` and `setSessionArchived`) in the embedded Claude Code engine, refreshed Cowork sandbox images, and added ~48 translated browser-extension and billing strings across 10 non-English locales (with no new English desktop UI changes over `5.11492.2`).

---

## Previous Android Release: 1.261113.19 (Android, 2026-11-14)

See [claude/2026-11-14_1.261113.19.md](claude/2026-11-14_1.261113.19.md) for highlights, or [full/claude/2026-11-14_1.261113.19.md](full/claude/2026-11-14_1.261113.19.md) for full technical details. _(Google Play US `"Updated on: Nov 14, 2026"` + Uptodown `"Matches the published version"`; baseline `1.261112.18` Play release date unconfirmed. Static diff of Uptodown Play-split XAPKs only; iOS not covered, APKs not executed, and static code/string presence does not confirm live rollout or policy/billing enforcement.)_

- **Android 12L Minimum OS (`minSdkVersion` `29` → `32`) & `27 → 30` Locale Splits**: Raises `minSdkVersion` from Android 10 (`29`) to Android 12L (`32`, API 32) with `targetSdkVersion` `37` unchanged, and expands XAPK language splits from `27` to `30` (`37 → 39` total XAPK entries: removed `bho`, added `gu`, `nb`, `ta`, `te`; this sampled Uptodown XAPK omits `config.x86_64.apk`, which is a sample-only observation and does not indicate dropped official `x86_64` support).
- **Standalone Voice Dictation (Including Offline) & Read-Aloud Modules**: Prunes 12 legacy helper/exception classes under `com.anthropic.claude.bell.tts.*` (retaining `TTSPlaybackService`) and introduces `com.anthropic.voice.internal.{readaloud,dictation,dictation/offline}` plus `stt.repo` exceptions and `CallHooks.tools` hook updates.
- **CCR Project Sheets, GitHub SSO, Bottom-Sheet Pickers & Static Credits/KYC Code**: Adds Claude Code Remote project settings sheets, `GitHubSsoRequiredException`, `CoworkTurnOutcomeWorker` completion notifications, a 49-destination bottom-sheet registry, saved-login agent authorization prompts, `"Response font"` / `"Anthropic Serif"`, `<files-path name="kept_tmp">`, and promotional-to-credits migration / voice-credit strings plus `KycStatus` / `organizations/{organization}/kyc_status` client code (building on existing credits UI in `1.261112.18`; static presence only), while retiring mobile Threads views and location telemetry scrub-list keys.

---

## Previous Desktop Release: 5.11492.2 (2026-11-13)

See [claude/2026-11-13_5.11492.2.md](claude/2026-11-13_5.11492.2.md) for highlights, or [full/claude/2026-11-13_5.11492.2.md](full/claude/2026-11-13_5.11492.2.md) for full technical details.

- **Enterprise Configuration Templates & Metered Update Deferral**: Export managed configuration templates directly from Claude Desktop for macOS/Windows IT rollouts, enforce update restart windows with clearer admin guidance, and pause update downloads for up to 12 hours on metered networks.
- **Standalone Sandbox Network Access & Action-Level Chrome Prompts**: Govern sandbox network traffic independently from web-fetching tool permissions, and review per-action prompts in Claude for Chrome before clicks, typing, scrolling, screenshots, or page network inspection.
- **SSH Host Settings, Large-File Reads & Connector OAuth Modes**: Configure per-host SSH settings and inspect host-key diagnostics, read large open files in chunks during local agent sessions, choose among four OAuth credential modes for MCP connectors, preview Loom/Vimeo/YouTube/Drive media, and benefit from Windows `claude://` argument-injection hardening and Linux CDN allowlist parity.

---

## Recent Major Baseline: 5.1231.0 (2026-11-10, `4.x → 5.x`)

See [claude/2026-11-10_5.1231.0.md](claude/2026-11-10_5.1231.0.md) for highlights, or [full/claude/2026-11-10_5.1231.0.md](full/claude/2026-11-10_5.1231.0.md) for full technical details.

- **Chrome Extensions in the Built-in Browser**: Browse, install, toggle, and remove extensions from the Chrome Web Store directly inside Claude's built-in browser.
- **1Password Login Autofill**: Authorize Claude to fill login credentials via 1Password during browser workflows.
- **Interactive 3D Artifacts & Cowork Plugins**: Added 3D scene/model rendering inside Artifacts, support for Cowork plugin directories, and a major desktop runtime upgrade for smoother performance.
