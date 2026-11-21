# ChatGPT / Codex Latest Changes

English | [简体中文](../zh-CN/full/codex.md) · [Highlight](../codex.md) | **Full Detail**

> See [codex/README.md](codex/README.md) for the complete five-platform index (`mac`, `win`, `ubuntu`, `ios`, `android`) covering all 418 unified releases (211 in `26.x` Desktop + 207 in `1.x` Mobile & pre-unification macOS).

## Latest Android Release: 1.2026.314 (Android, 2026-11-16 APKPure Archive)

See [codex/2026-11-16_android-1.2026.314.md](codex/2026-11-16_android-1.2026.314.md) for full details. _(APKPure archive date `2026-11-16` for `com.openai.chatgpt` `versionCode 2631431` vs. `1.2026.307` / `2630718` archived `2026-11-10`; Google Play publish timestamp unconfirmed and no official release notes published. Read-only static diff of sampled `base` + `arm64_v8a` + `en` + `mdpi` XAPKs only—APKs not executed, full `apksigner` cryptographic signature verification not performed, and extracted signer certs match the saved `2026-11-07` `chat.openai.com` `assetlinks.json` snapshot.)_

- **Codex / MCP Client Transport, SDK & Remote UI Static Wiring**
  - Introduces `com.openai.feature.deviceexecutor.impl.RmcpHttp2Server` (`RmcpHttp2Server$Frame`), bundles Netty `4.1.140.Final` HTTP/2 metadata/classes, and adds signed RMCP handshake/grant strings (`x-codex-rmcp-grant`, `use_handle_rmcp`, offer/grant/binding error strings, `/mcp`, `/handle-provider-relay`, `Mcp-Session-Id`; `/backend-api/ps/mcp` and `http://127.0.0.1:39801/android-executor/mcp` were already present in `1.2026.307`, and static strings do not prove active listening).
  - Adds `io.modelcontextprotocol` `DiscoverRequest*`/`DiscoverResult`, `CacheScope`, and `mcp/skill` identifiers (protocol versions remain `2025-03-26` / `2025-06-18` / `2025-11-25`), replaces app-server RPC `thread/realtime/listVoices` with `thread/delete` (`+` `thread/deleted`) with zero changes to the 12 `codex_app` tool names or model slug set, and adds mobile Codex Remote Compose components (`CodexRemoteComposerModelMenuPopup`, `CodexRemoteThreadRemovalDialog`, `X-Codex-Surface`, `codex_remote.json`, `chatgpt_codex_web_routing_free_v2_group`).
- **Android Manifest, Platform Valdi Modules & Packaging Deltas (`DEX` `91,702 → 94,565`)**
  - `<uses-permission>` adds only `CALL_PHONE` and `FOREGROUND_SERVICE_MEDIA_PLAYBACK` (`+2 / -0`; other permission diff blocks are XML reorderings); `<application>` swaps `MediaAccessNotificationListener` for `DeviceNotificationListener`, adds `ReadAloudPlaybackService`, `ReadAloudPauseReceiver`, `NotificationTapActivity`, and `<meta-data android:name="com.openai.play_features" android:value="orbit"/>`; `<queries>` adds WeChat/Viber/Zalo packages and 5 notification/health/`http` intents (manifest declarations do not establish runtime notification reading or call placement).
  - Expands `assets/*.valdimodule` `118 → 121` (`+` `oai_notifications`, `chatgpt_commerce_reporting`, `chatgpt_learning`), updates `chatgpt_wallet_core`, and adds static QR login assets/copy (`qr_sign_in_available=` already existed in `307`), `"dot"` / Gmail OAuth strings (`https://auth.api.openai.org/api/accounts/authorize`), and feature flag literals (static code/copy presence does not establish live user enablement or billing).
  - In the sampled `2631431` XAPK, `libcapture.so` shrinks `-946` KB (`-35.6%`) and most 3D mesh/runtime files under `assets/{meshes,fitted,orbit-runtime,orbit-thumbnails,orbit-licenses}/` and `assets/native-resources.bin` are absent (`base.apk` `+1.07` MB net), while `assets/orbit-bundled/{descriptor,metadata}.json`, `orbit_*` drawables, and `liborbit_characters_jni.so` remain (destination of absent 3D assets unverified).

---

## Latest Windows Desktop Release: 26.1111.2228.0 (Windows, 2026-11-14)

See [codex/2026-11-14_26.1111.2228.0.md](codex/2026-11-14_26.1111.2228.0.md) for full details. _(CDN MSIX `Last-Modified`: `2026-11-14`; Microsoft Store storefront publish timestamp unconfirmed. Store MSIX `26.1106.6628.0 → 26.1111.2228.0` maps internally to `26.1106.51428 → 26.1111.21308` / build `26605 → 27194`. Static dual-MSIX diff only—no Windows installation, runtime execution, or live MCP handshake verification.)_

- **MSIX Manifest, Engine & Chromium Runtime Updates**
  - Flips `<uap5:StartupTask TaskId="App">` in `AppxManifest.xml` from `Enabled="true"` to `Enabled="false"` (manifest default change only; OS install/upgrade behavior unverified); `windows-store-update.json` publishes both Store `buildVersion` (`26.1111.2228.0`) and cross-platform `releaseVersion` (`26.1111.21308`).
  - Upgrades bundled Codex engine version strings (`0.167.0-alpha.4.1 → 0.169.0-alpha.11.1`) across both native `resources/codex.exe` (`+8.8` MB) and byte-identical WSL Linux ELF `resources/codex` (`c147ac3b…`; engine tool-set parity with Linux `21308` inferred from the ELF copy), bumps Chromium `157.0.8103.51 → 157.0.8103.78`, recompiles all native modules, and adds `resources/native/shared-texture.node` (`codex-shared-texture-create`).
- **MCP Apps Preloads, Tool Name Set & `cua_node` Windows `window3` API**
  - Ships `sandbox-preload.js` (`+115,494` B, `workers-module` Web Worker RPC + `structured-clone` serializer) and new `application-websocket-preload.js` (`55,745` B) byte-identical to Linux `26.1111.21308`, plus persisted `mcp-app-permission-declarations-v2` in `early-bootstrap.js` and the 36-file Windows `window3` GUI automation API in `cua_node`.
  - All 95 renderer `snake_case` MCP tool names, 8 plugin `.mcp.json` files, `codex-app-tools/server.mjs` (`f0f5230d…`), and `26` `codex_desktop:*` IPC channel names show zero set additions/removals (full per-tool interface semantics and live MCP handshakes were not runtime-verified).
- **Main/Renderer Gate & String-Set Additions (Static Gate/String Evidence)**
  - Adds the same 6 literal feature gates as `26.1111.21308` (`codex-app-synced-skill-import`, `codex_desktop_cloud_previews`, `codex_app_worktrees`, `codex-app-serial-number`, `codex-default-environment-server-settings`, `lenovo_preload_reward_device_serial`) plus `mcp_lazy_stdio_startup`, `claude-code-local-skills`, Cloud Preview/Worktree/SSH Portal strings, `+19` Protobuf events (`1,280 → 1,299`), automation inbox / stop-turn / Spaces / `2026-11` connector strings, College Plan & Birthday deep links, Quartz icon, and inline-SVG shimmer loader (`gpt-instant-fallback` slug and `aeon-*` UI strings removed; gate/string presence does not confirm live user enablement).

---

## Latest Linux / macOS Desktop Release: 26.1111.21308 (Linux / macOS, 2026-11-13)

See [codex/2026-11-13_26.1111.21308.md](codex/2026-11-13_26.1111.21308.md) for full details.

- **Engine & Runtime Upgrades**
  - Upgraded the bundled Codex CLI engine across two minor versions to `0.169.0-alpha.11.1` (reducing `resources/codex` by `26.3` MB and `codex-code-mode-host` by `9.2` MB; adding `mcp_lazy_stdio_startup`, `websocket_upgrade`, `skill_namespace`, `execution_scope`, and `approved_plan`).
  - Upgraded the Chromium runtime to `157.0.8103.78` and introduced the `desktop:native:shared-texture` workspace package (`codex-shared-texture-create`).
- **MCP Apps Web Worker Sandbox & Application WebSocket Preload**
  - Expanded `sandbox-preload.js` (`+115` KB) with `workers-module` Web Worker RPC and full stream/fetch structured-clone serialization; added `application-websocket-preload.js` (`55.7` KB) with frame validation and `admission_cancelled` close handling; added per-origin `mcp-app-permission-declarations-v2` persistence.
- **External Skill Import, Cloud Previews & Expanded Worktrees**
  - Added two-level `SKILL.md` scanning and synced skill import for `claude-code` and `cursor` (`codex-app-synced-skill-import`), Cloud Preview controls (`codex_desktop_cloud_previews`), expanded Worktree modals/settings (`codex_app_worktrees`) and linked Git checkout attachments, lazy stdio MCP startup, and Windows Store/MSIX installer-takeover telemetry.
- **Automation Inbox, Global Search, Spaces & Built-in Plugins**
  - Added the automation run inbox, active-turn stop confirmation, `chatgpt-global-search`, Spaces persistence, November 2026 DocuSign/HubSpot/Klaviyo connectors, 43 new Protobuf analytics events (`1,256 → 1,299`), and Windows `window3` GUI automation in `cua_node`.

---

## Recent Releases on Other Platforms

- **Desktop (macOS) `26.1106.51428` (2026-11-11)** — see [codex/2026-11-11_26.1106.51428.md](codex/2026-11-11_26.1106.51428.md)
  - Upgraded Codex CLI to `0.167.0-alpha.4.1` and Chromium to `157.0.8103.51`, added multi-account switching with `desktop-switch-loader`, reactive Cloud SSH Portal state machine, main-process `automation_update` handler, Code Review PR persistence, Pages collaborative docs (DIL), in-image text editing, and `gpt-5-t-mini`.
- **Desktop (Linux) `26.1103.60933` (2026-11-09)** — see [codex/2026-11-09_26.1103.60933.md](codex/2026-11-09_26.1103.60933.md)
  - Introduced generation counters in account state persistence to prevent cross-account write races, added the `codex_desktop:network-online` IPC channel, `active_turn_mismatch` error mapping, 6 composer policy disable reasons, Page/artifact annotation modules, and confirmation prompts for `delete_thread`.
- **Android `1.2026.300` (2026-10-31)** — see [codex/2026-10-31_android-1.2026.300.md](codex/2026-10-31_android-1.2026.300.md)
  - Embedded the official MCP Kotlin SDK and a local Streamable-HTTP MCP server (`android executor`) for the first time so the phone itself can be mounted as a Codex execution environment; added Noise-encrypted chunked `exec-server` relay, Elicitation response loops, Health Connect integration, and removed the legacy exported auth token service.
