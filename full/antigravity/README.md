# Antigravity Changelog History

English | [简体中文](../../zh-CN/full/antigravity/README.md) · [Highlight](../../antigravity/README.md) | **Full Detail**

Multi-platform technical version history for Google **Antigravity** (`https://antigravity.google`) across `mac`, `win`, `ubuntu`, `ios`, and `android`, covering **5** analyzed releases across its two distinct desktop product lines:
- **Antigravity Desktop (`antigravity-hub`)**: standalone Electron `44.9.1` app bundling monolithic Go `language_server` (`2.31.2` → `2.32.2` across `mac`, `win`, `ubuntu`, latest 2026-11-17 package `Last-Modified`; `2.31.2`–`2.32.1` static diffs anchored on `linux-x64` from `2.29.0` baseline, `2.32.2` primary diff on `darwin-arm` dual DMGs with `linux-x64` same-build/LS spot-checks and `windows-x64` spot-checks).
- **Antigravity IDE (`Antigravity IDE`)**: Code OSS `1.107.0` / Electron `39.2.3` IDE spawning on-demand `~/.gemini/bin/agy --hub` (`2.7.0` across `mac`, `win`, `ubuntu`, diffed against `2.6.0`; release time unconfirmed — `2026-11-11 12:46` UTC+8 in `product.json` is the build time, not the release time).

## Five-Platform Coverage Overview

| Platform | Distribution / Package | Tracked Releases | Version Range | Latest Version |
|---|---|---|---|---|
| `mac` | macOS (`Antigravity.dmg` Hub GCS CDN & `Antigravity IDE.app` `darwin-arm` edgedl CDN) | 4 | `2.32.0` → `2.32.2` (Hub) / `ide-2.7.0` (IDE) | [2.32.2](2026-11-17_2.32.2.md) / [IDE 2.7.0](2026-11-11_ide-2.7.0.md) |
| `win` | Windows (`Antigravity` Hub Setup & `Antigravity IDE.exe` `windows-x64` Inno Setup `6.4.0.1`) | 4 | `2.32.0` → `2.32.2` (Hub) / `ide-2.7.0` (IDE) | [2.32.2](2026-11-17_2.32.2.md) / [IDE 2.7.0](2026-11-11_ide-2.7.0.md) |
| `ubuntu` | Ubuntu / Linux (`Antigravity.tar.gz` Hub & `Antigravity IDE.tar.gz` `linux-x64`) | 5 | `2.31.2` → `2.32.2` (Hub) / `ide-2.7.0` (IDE) | [2.32.2](2026-11-17_2.32.2.md) / [IDE 2.7.0](2026-11-11_ide-2.7.0.md) |
| `ios` | Standalone Antigravity iOS Client | 0 | _No standalone mobile release tracked_ | — |
| `android` | Standalone Antigravity Android Client | 0 | _No standalone mobile release tracked_ | — |

## Desktop Version Index (`mac` / `win` / `ubuntu`, Newest → Oldest)

| Version | Platforms | Release Date | Key Changes |
|---|---|---|---|
| [2.32.2 (Hub)](2026-11-17_2.32.2.md) | `mac`, `win`, `ubuntu` | 2026-11-17 (Last-Modified) | Primary `darwin-arm` dual-DMG static diff (`execution_id` `4665802025205760`, `linux-x64` same-build/LS spot-check, `windows-x64` spot-check): `app.asar` (`1,068` files, `18,668,119` B, SHA-256 `056ba838…`) differs only in `package.json` `version` (`2.32.2`), `chrome-devtools-mcp` `1.9.0` is unchanged, and recompiled Go `language_server` (`cl/1021296516 → cl/1022991777`, `darwin-arm` `−32` B / `strings` `+765 / −703`) shows only `cel.withDefaultCELHTTPTimeout` rename and `Shutdown` closure symbol changes with unchanged extracted RPC (`376`), flag-pair (`189`), `*ToolConfig` (`65`), and `gemini-4-*` (`9`) text lists |
| [2.32.1 (Hub)](2026-11-14_2.32.1.md) | `mac`, `win`, `ubuntu` | 2026-11-14 | Same-size Go `language_server` rebuild (`239,952,296` B, `cl/1020489536 → cl/1021296516`, `strings` `+1,085 / −1,115`): adds `gemini-4-hydrogen-{low,medium,high}` (`defaultmodels.Gemini4Hydrogen`, `gemini-4-hydrogenaicode_latency_ms`) to the default model catalog; `app.asar` (`dist/` + `node_modules/`, `1,068` files) and `chrome-devtools-mcp` `1.9.0` are byte-identical to `2.32.0`, with zero RPC (`375`), flag (`112`), or tool (`49`) drift |
| [2.32.0 (Hub)](2026-11-13_2.32.0.md) | `mac`, `win`, `ubuntu` | 2026-11-13 | Electron `44.9.1`, Go `language_server` `206.8 → 240.0` MB (`cl/1020489536`, `.noptrdata` `+29.6` MB): `30`-file `dist/remote/` SSH stack (`--ssh-host`, `27`-channel IPC allowlist), Catcher 3-layer guest views, `guestCrossSiteCredentials.js` & `stripGuestElectronUserAgentToken`, `shell-env` removal (`8 → 7` deps), gated `cortex/ext/plugins/computer` (`ComputerViewerService`, `18` actions), `CloneGitHubRepo` RPC (`374 → 375`), `+58` flags (`54 → 112`), `AgentRemoteSessionMessages`, `openaiResponsesConverter`, and Dynamic Workflows / Everforest rollout (`11` improvements, `13` fixes) |
| [2.31.2 (Hub)](2026-11-12_2.31.2.md) | `ubuntu` | 2026-11-12 | Electron `44.5.1 → 44.9.1`, Go `language_server` `195.9 → 206.8` MB (`~50 → ~60` native tools): CDP `WebMCP.*` Guest WebMCP bridge (`64` KiB cap, `PROTECTED_PAYMENT_HOSTS`), `0o600` `DevToolsActivePort`, `native_swarm` (`manage_swarm`/`post_message`/`read_board`/`swarm_wait`), `planexecute` `enter`/`exit`, `RunPersistent` terminals, `notebook_execution`, `oneharness` (14 tools), `sir_flash_lite` (`mode: LOG`), and `StartMcpOAuthSignIn` RPC (`365 → 374`) |
| [IDE 2.7.0](2026-11-11_ide-2.7.0.md) | `mac`, `win`, `ubuntu` | Unconfirmed _(built 2026-11-11)_ | Code OSS `1.107.0` (`71bedb45`, `languageServerCL` `1018779249`): all substantive diffs in `extensions/agy` `0.0.1 → 1.11.0` (`vscode/extension.js` `+90,987` B, `bridge.js` `+9,333` B) — 3-state auth status bar, `authSync`, loopback `POST .../GetAuthStatus`, `25 → 33` commands, `+35` iframe schemas (`ManageTask`, media, browser recording), `isAntigravityIde` (`productId` `5372208`), CDE `/usr/bin/agy` fast path, and `canRetryPortCollision` (`out/` & `jetskiAgent` 0 code diff) |
