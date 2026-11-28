# Claude Latest Changes

English | [简体中文](zh-CN/claude.md) · **Highlight** | [Full Detail](full/claude.md)

> See [claude/README.md](claude/README.md) for the complete five-platform index (`mac`, `win`, `ubuntu`, `ios`, `android`) covering all 535 historical releases (245 Desktop + 290 Mobile).

## Latest Android Release: 1.261125.19 (Android, 2026-11-27 Uptodown Window)

See [claude/2026-11-27_1.261125.19.md](claude/2026-11-27_1.261125.19.md) for highlights, or [full/claude/2026-11-27_1.261125.19.md](full/claude/2026-11-27_1.261125.19.md) for full technical details. _(`2026-11-26/27` release window: Uptodown lists `"Nov 27, 2026"` + `"Matches the published version"`, while Google Play US shows `"Updated on Nov 26, 2026"` without a visible version number and embeds `1.261125.19` with unix `1795755160` [`2026-11-26 20:52:40` PST / `2026-11-27 12:52:40` UTC+8]. Static diff of archived **Uptodown third-party mirror** Play-split XAPKs `1.261124.19 → 1.261125.19` [`801b77ee…`]; live Uptodown pages have since rotated to a different `44.03 MB` / `39662257…` container not analyzed here. Full `apksigner` verify not performed, iOS not covered, APKs not executed, and static presence does not confirm live rollout.)_

- **Usage Credits Auto-Reload & IAP Identity Check UI**: Adds usage-credits auto-reload copy (`"Turn on usage credits?"`, `"Auto-reload will charge your card when your credits run low."`) + `claudeai.usage_credits.code_limit_offer.step`, government photo ID capture checklist copy (`"Before you start"`, `"An unexpired government photo ID"`, optional selfie), Google Play readiness notice, `claudeai.iap.identity_check.*` telemetry, and `PurchaseCancellation` (static presence only).
- **Reflect (`cardinal`) & GitHub Repository Creation**: Expands `1.261124.19`'s Reflect support with background-writing notification opt-in, explicit memory prerequisite, `"Delete all reflections?"`, and `claudeai.cardinal.{notify.{offered,answered},recap.read,wait.left}`; adds `"Create on GitHub"` / `"New repository"` / `"Approve on GitHub"` copy, `claudeai.code.repository_picker.new_repository.{shown,opened,finished}`, and repository-creation error taxonomy (name collision, SSO, permissions, indeterminate state).
- **Media, Feedback Cleanup & Packaging**: Adds sub-one-minute video upload limit copy and `"Pause/Play %1$s preview"` controls, removes `"Conversation outline (Ant only)"` and legacy feedback category strings; in the archived XAPK (`30` members), `config.x86_64.apk` (`10` `.so`) returns after absence since the `1.261113` era, language splits shift `21 → 20` (`+gu`, `+hi`, `−da`, `−nb`, `−te`), `arm64-v8a` / `armeabi-v7a` (`20` `.so`) remain unchanged across `1.261123.19`–`1.261125.19`, total DEX grows `+286,852` B (~`+0.29` MB), and `minSdk`/`targetSdk` `32`/`37`, `66` `uses-permission` entries, and `83` components stay unchanged.

---

## Latest Desktop Release: 5.11492.5 (2026-11-14)

See [claude/2026-11-14_5.11492.5.md](claude/2026-11-14_5.11492.5.md) for highlights, or [full/claude/2026-11-14_5.11492.5.md](full/claude/2026-11-14_5.11492.5.md) for full technical details.

- **Enterprise Managed File-Read Policy & Auto-Mode Guidance**: Added the `blockFileToolReadsOutsideWorkingDirectories` managed setting governing one-time file-read prompts in auto-mode, and clarified machine-wide `env.CLAUDE_CODE_AUTO_MODE_MODEL` override guidance in managed settings documentation.
- **Office Document Skill Security & Diff Hardening**: Hardened the bundled `docx`, `pptx`, and `xlsx` validators against Windows-style drive/root path traversal and out-of-bounds OOXML relationship targets, and replaced external `git diff` subprocesses during document redlining with a work-bounded diff algorithm.
- **Engine Session Storage Validation & 10-Locale Catch-Up**: Added a unified local session storage key validation schema (including `jobs-root` and `setSessionArchived`) in the embedded Claude Code engine, refreshed Cowork sandbox images, and added ~48 translated browser-extension and billing strings across 10 non-English locales (with no new English desktop UI changes over `5.11492.2`).

---

## Previous Android Release: 1.261124.19 (Android, 2026-11-25 Uptodown Window)

See [claude/2026-11-25_1.261124.19.md](claude/2026-11-25_1.261124.19.md) for highlights, or [full/claude/2026-11-25_1.261124.19.md](full/claude/2026-11-25_1.261124.19.md) for full technical details. _(Imprecise `2026-11-25/26` window from Uptodown `"Nov 25, 2026"` + `"Matches the published version"`; `2026-11-26` Google Play US snapshot remained `"Updated on: Nov 24, 2026"` without version numbers. Static diff of **Uptodown third-party mirror** Play-split XAPKs `1.261123.19 → 1.261124.19`—not direct Play downloads; full `apksigner` verify not performed, iOS & historical `1.261120.19`–`1.261122.*` gap not covered, APKs not executed, and static presence does not confirm live rollout.)_

- **GitHub Integration & PR / Plan / Tool-Call Approvals**: Adds `claudeai.code.connect_github_card.*` telemetry, Claude GitHub App installation prompts, granular PR/plan/tool-call approval failure messages, organization connector-approval notices, `CollapsedToolsSheetDestination${HostPage,ProductPage,Viewer}`, and cloud-environment setup prompts.
- **Safeguards Model-Switch Prompts & Places Panel**: Ships ~12 biology/cybersecurity/sensitive-topic safeguards auto-model-switch strings on mobile, adds the `claudeai.places_list.*` Places selection panel (`Next place` / `Previous place`) and `voice.reachability_checked`, and adds usage-page sections, `Default tab` settings, project instructions editing with explicit PHI exclusion, shared-session link visibility, read-aloud limit copy, and ~20 sign-in/maintenance/model-limit error strings while retiring `continue_on_cloud.*` (`8 → 1`), `ready_made_card.rated`, and `money.message_box.*`.
- **Packaging & Invariants**: XAPK members drop `37 → 30` (language splits `28 → 21`: `+te`, `−am/fil/hi/ml/mr/sw/ta/tl`) while all `20` native `.so` libraries remain byte-identical, `minSdkVersion` `32` / `targetSdkVersion` `37`, `66` permissions, and `83` components stay unchanged, and **no API endpoints were added or removed**.

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
