# ChatGPT / Codex Latest Changes

English | [简体中文](zh-CN/codex.md) · **Highlight** | [Full Detail](full/codex.md)

> See [codex/README.md](codex/README.md) for the complete five-platform index (`mac`, `win`, `ubuntu`, `ios`, `android`) covering all 418 unified releases (211 in `26.x` Desktop + 207 in `1.x` Mobile & pre-unification macOS).

## Latest Android Release: 1.2026.314 (Android, 2026-11-16 APKPure Archive)

See [codex/2026-11-16_android-1.2026.314.md](codex/2026-11-16_android-1.2026.314.md) for highlights, or [full/codex/2026-11-16_android-1.2026.314.md](full/codex/2026-11-16_android-1.2026.314.md) for full technical details. _(APKPure archive date `2026-11-16` for `versionCode 2631431` vs. `1.2026.307` / `2630718` archived `2026-11-10`; exact Google Play publish timestamp unconfirmed and no official release notes published. Read-only static diff of `base` + `arm64_v8a` + `en` + `mdpi` split XAPKs only—iOS and `300 → 307` not covered, APKs not executed, full `apksigner` cryptographic verification not performed, and static client code/strings/manifest entries do not confirm live rollout or runtime behavior.)_

- **Embedded `RmcpHttp2Server`, Netty `4.1.140.Final` & Signed RMCP Grant Strings (Static Client Wiring)**: Adds `RmcpHttp2Server`, bundles Netty `4.1.140.Final` HTTP/2 artifacts, and introduces signed RMCP handshake/grant strings (`x-codex-rmcp-grant`, `use_handle_rmcp`, `/mcp`, `/handle-provider-relay`, `Mcp-Session-Id`; `/backend-api/ps/mcp` and `http://127.0.0.1:39801/android-executor/mcp` were already present in `1.2026.307`, and static presence does not prove active listening).
- **MCP Discovery/Skills Types, `thread/delete` RPC & Mobile Codex Remote UI Wiring**: Adds `io.modelcontextprotocol` `DiscoverRequest*`/`DiscoverResult`, `CacheScope`, and `mcp/skill` identifiers, replaces app-server RPC `thread/realtime/listVoices` with `thread/delete` (`+` `thread/deleted`) while keeping the 12 `codex_app` tools and model slug set unchanged, and ships Compose UI strings/components for mobile Codex Remote model menus, host management/reconnection, thread deletion (`CodexRemoteThreadRemovalDialog`), and dual-session conflict notices.
- **Manifest Permissions (`CALL_PHONE`, `FOREGROUND_SERVICE_MEDIA_PLAYBACK`), Notification/ReadAloud Services & Static Feature Modules**: Adds only `CALL_PHONE` and `FOREGROUND_SERVICE_MEDIA_PLAYBACK` to `<uses-permission>`, replaces `MediaAccessNotificationListener` with `DeviceNotificationListener` (`oai_notifications`), registers `ReadAloudPlaybackService` / `ReadAloudPauseReceiver` / `NotificationTapActivity`, ships QR login copy/assets (`qr_sign_in_available=` already existed in `1.2026.307`), Wallet/commerce/learning Valdi modules, and `"dot"` / Gmail OAuth strings, and reduces bundled 3D mesh/runtime assets in the sampled `2631431` XAPK (`DEX` `91,702 → 94,565`, while `assets/orbit-bundled/{descriptor,metadata}.json` and `orbit_*` drawables remain; asset destination unverified).

---

## Latest Windows Desktop Release: 26.1111.2228.0 (Windows, 2026-11-14)

See [codex/2026-11-14_26.1111.2228.0.md](codex/2026-11-14_26.1111.2228.0.md) for highlights, or [full/codex/2026-11-14_26.1111.2228.0.md](full/codex/2026-11-14_26.1111.2228.0.md) for full technical details. _(CDN MSIX `Last-Modified`: `2026-11-14`; Microsoft Store storefront publish timestamp unconfirmed. Store MSIX `26.1106.6628.0 → 26.1111.2228.0` maps internally to cross-platform release line `26.1106.51428 → 26.1111.21308` / build `26605 → 27194`. Static MSIX diff only—Windows client not installed and runtime/MCP handshakes not verified.)_

- **MSIX `StartupTask` Manifest Default Changed (`Enabled="true"` → `"false"`)**: Updates `<uap5:StartupTask TaskId="App">` in `AppxManifest.xml` so the package-declared startup task defaults to disabled (manifest default change only; actual Windows install/upgrade behavior unverified).
- **Codex Engine `0.169.0-alpha.11.1`, Chromium `157.0.8103.78` & MCP Apps Preloads**: Upgrades both native `codex.exe` and the bundled WSL Linux ELF `codex` engine to `0.169.0-alpha.11.1`, updates Chromium to `157.0.8103.78` with recompiled native modules plus new `shared-texture.node`, expands `sandbox-preload.js` with Web Worker RPC and structured-clone serialization, adds `application-websocket-preload.js`, `mcp-app-permission-declarations-v2`, and the `cua_node` Windows `window3` automation API, while keeping all 95 MCP tool names and 8 plugin `.mcp.json` manifests unchanged in count (full per-tool interface semantics not runtime-verified).
- **Feature-Gated Skill Import, Cloud Previews, Worktrees & UI Strings (Static Gate/String Evidence)**: Ships main-process and primary UI bundle gates and strings aligned with the `26.1111.21308` line—including `claude-code-local-skills` / `codex-app-synced-skill-import`, `codex_desktop_cloud_previews`, `codex_app_worktrees`, `mcp_lazy_stdio_startup`, automation inbox read-state actions, stop-turn confirmation, Spaces thumbnails, November 2026 DocuSign/HubSpot/Klaviyo connector IDs, College Plan / Birthday deep links, the Quartz icon, and the inline-SVG shimmer loader (gate/string presence does not confirm live user rollout).

---

## Latest Linux / macOS Desktop Release: 26.1111.21308 (Linux / macOS, 2026-11-13)

See [codex/2026-11-13_26.1111.21308.md](codex/2026-11-13_26.1111.21308.md) for highlights, or [full/codex/2026-11-13_26.1111.21308.md](full/codex/2026-11-13_26.1111.21308.md) for full technical details.

- **Claude Code & Cursor Skill Import, Cloud Previews & Expanded Worktrees**: Automatically detect and import local custom skills (`SKILL.md`) from Claude Code and Cursor, open and manage live Cloud Previews, and configure Git Worktrees via a dedicated settings page, branch setup modal, move-to-worktree dialog, and linked Git checkouts.
- **Automation Inbox, Global Search, Spaces & Turn Controls**: Manage background automation runs in an inbox with unread run counters and mark-all-read actions, confirm before stopping active turns, search across workspaces with Global Search, organize Spaces with thumbnails and custom sidebar order, and convert local projects directly into chats.
- **Richer Interactive MCP Apps, November Connectors & Faster MCP Startup**: Run MCP App widgets with background Web Workers and per-origin permissions, lazily start local stdio MCP servers, and use updated November 2026 DocuSign/HubSpot/Klaviyo connectors, restored Office workbooks, the Quartz app icon, and a redesigned startup shimmer screen.

---

## Recent Releases on Other Platforms

- **Desktop (macOS / Linux) `26.1106.51428` (2026-11-11)** — [Highlight](codex/2026-11-11_26.1106.51428.md) · [Full Detail](full/codex/2026-11-11_26.1106.51428.md)
  - Multi-account management with seamless workspace switching and tiered sign-out, Code Review PR pinning, Pages collaborative documents, in-image text editing, wide-mode charts, and `gpt-5-t-mini` support.
- **Desktop (Linux / macOS) `26.1103.60933` (2026-11-09)** — [Highlight](codex/2026-11-09_26.1103.60933.md) · [Full Detail](full/codex/2026-11-09_26.1103.60933.md)
  - Safer multi-account sidebar state sync, clearer composer restriction notices under workspace policies, inline response annotations & Page context citations, and confirmation prompts before deleting threads.
- **Android `1.2026.300` (2026-10-31)** — [Highlight](codex/2026-10-31_android-1.2026.300.md) · [Full Detail](full/codex/2026-10-31_android-1.2026.300.md)
  - Pair an Android phone as an encrypted remote execution environment for Codex with interactive mobile approval dialogs, alongside Health Connect integration, shopping assistant cards, browser sign-in handoff, and 1Password / OTP autofill.
