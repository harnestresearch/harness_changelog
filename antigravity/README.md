# Antigravity Changelog History

English | [简体中文](../zh-CN/antigravity/README.md) · **Highlight** | [Full Detail](../full/antigravity/README.md)

Multi-platform version history for Google **Antigravity** (`https://antigravity.google`) across `mac`, `win`, `ubuntu`, `ios`, and `android`, covering **5** analyzed releases across its two distinct desktop product lines:
- **Antigravity Desktop (`antigravity-hub`)**: standalone Electron agent client (`2.31.2` → `2.32.2` across `mac`, `win`, `ubuntu`, latest 2026-11-17 package `Last-Modified`).
- **Antigravity IDE (`Antigravity IDE`)**: Code OSS `1.107.0`-based AI IDE (`2.7.0` across `mac`, `win`, `ubuntu`; release time unconfirmed — `2026-11-11 12:46` UTC+8 in `product.json` is the build time, not the release time).

## Five-Platform Coverage Overview

| Platform | Distribution / Package | Tracked Releases | Version Range | Latest Version |
|---|---|---|---|---|
| `mac` | macOS (`Antigravity.dmg` Hub GCS CDN & `Antigravity IDE.app` `darwin-arm` edgedl CDN) | 4 | `2.32.0` → `2.32.2` (Hub) / `ide-2.7.0` (IDE) | [2.32.2](2026-11-17_2.32.2.md) / [IDE 2.7.0](2026-11-11_ide-2.7.0.md) |
| `win` | Windows (`Antigravity` Hub Setup & `Antigravity IDE.exe` `windows-x64` Inno Setup) | 4 | `2.32.0` → `2.32.2` (Hub) / `ide-2.7.0` (IDE) | [2.32.2](2026-11-17_2.32.2.md) / [IDE 2.7.0](2026-11-11_ide-2.7.0.md) |
| `ubuntu` | Ubuntu / Linux (`Antigravity.tar.gz` Hub & `Antigravity IDE.tar.gz` `linux-x64`) | 5 | `2.31.2` → `2.32.2` (Hub) / `ide-2.7.0` (IDE) | [2.32.2](2026-11-17_2.32.2.md) / [IDE 2.7.0](2026-11-11_ide-2.7.0.md) |
| `ios` | Standalone Antigravity iOS Client | 0 | _No standalone mobile release tracked_ | — |
| `android` | Standalone Antigravity Android Client | 0 | _No standalone mobile release tracked_ | — |

## Desktop Version Index (`mac` / `win` / `ubuntu`, Newest → Oldest)

| Version | Platforms | Release Date | Highlights |
|---|---|---|---|
| [2.32.2 (Hub)](2026-11-17_2.32.2.md) | `mac`, `win`, `ubuntu` | 2026-11-17 (Last-Modified) | Maintenance point build (`darwin-arm` dual-DMG primary diff, `linux-x64` same-build/LS spot-checks, `windows-x64` spot-checks): `1,068`-file Electron `44.9.1` shell differs only in `package.json` version (`2.32.1` → `2.32.2`), `chrome-devtools-mcp` `1.9.0` is unchanged, and recompiled Go `language_server` (`cl/1022991777`) shows only internal telemetry CEL timeout helper and `Shutdown` closure symbol changes with unchanged extracted model/RPC/flag/tool text lists |
| [2.32.1 (Hub)](2026-11-14_2.32.1.md) | `mac`, `win`, `ubuntu` | 2026-11-14 | Next-day patch build adding **Gemini 4 Hydrogen** (`low` / `medium` / `high`) to the built-in default model catalog alongside `Gemini 4 Argon` and `Gemini 4 Carbon`, with a byte-identical Electron `44.9.1` shell carrying forward all `2.32.0` features and fixes |
| [2.32.0 (Hub)](2026-11-13_2.32.0.md) | `mac`, `win`, `ubuntu` | 2026-11-13 | Dynamic Workflows rollout (bundled Python runtime), Everforest Light/Dark themes, prompt navigation & Submit Prompt shortcuts, signed-out cross-site browser frames & Electron UA fix, auth-code sign-in fallback, Cloud GitHub repo cloning, clean `SIGTERM` shutdown & CJK bold fix (11 improvements, 13 fixes), plus flag-gated SSH remote & Computer Use foundations |
| [2.31.2 (Hub)](2026-11-12_2.31.2.md) | `ubuntu` | 2026-11-12 | In-page Guest WebMCP browser bridge (payment/IDP blocklist, 64 KiB cap, 30s timeout), native Swarm board collaboration, direct remote MCP OAuth sign-in, plan-execute transitions, persistent terminals, notebook execution, and `DevToolsActivePort` permission hardening |
| [IDE 2.7.0](2026-11-11_ide-2.7.0.md) | `mac`, `win`, `ubuntu` | Unconfirmed _(built 2026-11-11)_ | Auth-aware status bar with cross-window sign-in sync, split Current-File vs. All-Files diff accept/reject commands, background task & browser recording bridge support, and Google Cloud Workstations `/usr/bin/agy` pre-installed CLI detection |
