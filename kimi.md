# Kimi Latest Changes

English | [简体中文](zh-CN/kimi.md) · **Highlight** | [Full Detail](full/kimi.md)

> See [kimi/README.md](kimi/README.md) for the complete five-platform index (`mac`, `win`, `ubuntu`, `ios`, `android`) covering all 186 releases (up to `3.2.29` Desktop across `mac` and `win`, and `3.1.8` on iOS; standalone Linux unreleased; intermediate desktop versions between `3.2.25` and `3.2.29` are not all cataloged or analyzed in this repository).

## Latest Analyzed Desktop Release: 3.2.29 (2026-11-26, `mac`, `win`)

See [kimi/2026-11-26_3.2.29.md](kimi/2026-11-26_3.2.29.md) for highlights, or [full/kimi/2026-11-26_3.2.29.md](full/kimi/2026-11-26_3.2.29.md) for full technical details. _(Official release-notes heading date `2026-11-26`; baseline `3.2.28` date `2026-11-18`. Intermediate desktop versions after `3.2.25` are not all cataloged in this repository—`3.2.28` has no entry yet and `3.2.26`/`3.2.27` remain Windows-only `TODO` placeholders—so `3.2.25` is **not** the baseline; this entry covers strictly the **`3.2.28 → 3.2.29`** static dual-package diff across official macOS `arm64` and Windows `x64` installers. macOS Intel was not sampled; Linux is officially not provided; iOS/Android out of scope; not executed at runtime.)_

### Highlights

- **Markdown Preview Outline Navigation & Global Search UI (Confirmed Statically)**: Official notes introduce outline navigation in Markdown preview (`obsidianToc` `0` in `3.2.28` → present in `3.2.29` `WorkbenchPanel` and `en-US`/`zh-CN` locales across macOS and Windows) and global search UI/interaction improvements (`showMoreMatches` and `searchOlderConversations` added alongside updated `GlobalSearchModal` JS + newly added CSS).
- **Module-Level Corroborated & Official-Only Fixes**: Workbench file tree expand/collapse (`WorkbenchFileSurface` added), remote-control permission-mode sync & full-auto spurious approval (`permission-flow`, `RemoteControl*`, `ApprovalPrompt` updated), dictation post-send refill (`MessageList`, `ConversationView` updated), and marketplace plugin authorization expiry (`use-plugin-install-flow` added + plugin pages updated) are corroborated at the module level only (not line-by-line verified). Mobile keyboard obscuring the plugin/skill list, sidebar order jumping on profile refresh, and image preview zooming the wrong target come from the official `3.2.29` notes without independently located in-package targets (`pinch-zoom` preload removal is not cited as line-level zoom-fix evidence).
- **Unannounced `restic`-Backed Local File Version History & Runtime Updates**: Not mentioned in the official changelog, `3.2.29` adds a local file version history subsystem on both macOS and Windows (`restic` `0.19.1` binaries, `0 → 13` `kimi-agent:file-history-*` IPC channels, `18` new main-process chunk stems, `restic-bsd-2-clause.txt`, and `111` of `113` new `zh-CN` keys alongside the `2` global search keys), with `fileHistoryAbEligible` / `isFileHistoryRuntimeEnabled` indicating likely A/B gating. Electron/Chromium remain `43.7.7` / `150.0.7871.250`, `daimon` updates `1.0.14 → 1.0.15`, and `gateway.asar` grows `~6.4` MB on both platforms.

---

## Earlier Analyzed Desktop Release: 3.2.25 (2026-11-05, macOS)

See [kimi/2026-11-05_3.2.25.md](kimi/2026-11-05_3.2.25.md) for highlights, or [full/kimi/2026-11-05_3.2.25.md](full/kimi/2026-11-05_3.2.25.md) for full technical details.

### Highlights

- **Embedded Kimi Code Workspace & Local Toolchains**: Ships a self-contained coding and data-analysis workspace out of the box—run terminal commands, Python scripts, file edits, and structured tasks without manually installing external language runtimes.
- **Desktop Computer Use & Screen Understanding (macOS)**: Enables authorized desktop GUI automation with live screen capture, on-device optical character recognition (OCR), smooth scroll/pointer/keyboard actions, Finder selection awareness, and global quick-input shortcuts.
- **MCP Connectors, One-Click OAuth & Web Tool Discovery**: Connect local and remote external tools with built-in OAuth sign-in, interactive tool-call confirmations, and automatic discovery of structured actions exposed by web pages inside the built-in browser.
- **Kimi Slides, Scientific Previewers & 3D CAD Inspection**: Generate and preview presentation decks locally alongside built-in LaTeX document typesetting, genomics data inspection, and 3D CAD model importing.
- **Desktop Claw Multi-Channel IM Gateway**: Bridges your desktop Kimi workspace with external messaging channels and companion mobile remote-control sessions so tasks can be triggered and steered away from your desk.

---

## Recent Analyzed Android Release: 3.1.5 (2026-10-23)

See [kimi/2026-10-23_android-3.1.5.md](kimi/2026-10-23_android-3.1.5.md) for highlights, or [full/kimi/2026-10-23_android-3.1.5.md](full/kimi/2026-10-23_android-3.1.5.md) for full technical details.

### Highlights

- **Remote Control for Desktop Workspaces**: Monitor and steer tasks running on your desktop Kimi workspace directly from your Android phone, including browsing and picking files, uploading mobile attachments to the desktop session, releasing active sessions, and viewing connection status in real time.
- **Read-Only Remote Image Preview & Live Media Streaming**: Added a dedicated read-only image viewer for inspecting screenshots and visual outputs produced on the remote computer, paired with low-latency real-time audio/video streaming.
- **Kimi Claw Cross-App Authorization**: Added native app-to-app authorization screens so companion Kimi Claw tools and integrations can request account permission with one tap.
- **Multi-Channel Sign-In & Seamless Session Continuity**: Supports SMS verification codes, Chinese carrier one-tap mobile number sign-in, WeChat login, and email login, with automatic background session renewal and device-security protection so long-running tasks stay connected.
