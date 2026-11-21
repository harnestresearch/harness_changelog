# Cursor Changelog History

English | [简体中文](../../zh-CN/full/cursor/README.md) · [Highlight](../../cursor/README.md) | **Full Detail**

Complete multi-platform version history covering all **446** unified releases of Cursor from `0.7.2` (2023-08-11) to `3.30.14` (2026-11-14) across `mac`, `win`, `ubuntu`, `ios`, and `android` (**426** Desktop/Unified releases + **20** Mobile-only releases).

## Five-Platform Coverage Overview

| Platform | Distribution / Package | Tracked Releases | Version Range | Latest Version |
|---|---|---|---|---|
| `mac` | macOS (`Cursor.app` CDN & Homebrew Cask) | 425 | `0.7.2` → `3.30.14` | [3.30.14](2026-11-14_3.30.14.md) |
| `win` | Windows (`Anysphere.Cursor` User/System Setup & Winget) | 272 | `1.1.3` → `3.30.14` | [3.30.14](2026-11-14_3.30.14.md) |
| `ubuntu` | Ubuntu / Linux (`cursor` APT `.deb` & Official AppImage) | 236 | `0.48.2` → `3.30.14` | [3.30.14](2026-11-14_3.30.14.md) |
| `ios` | iOS App Store (`co.anysphere.cursor`) | 20 | `ios-1.0.0` → `ios-1.17.0` | [ios-1.17.0](2026-11-07_ios-1.17.0.md) |
| `android` | Standalone Cursor Android Client | 0 | _No standalone release yet_ | — |

## Desktop Version Index (`mac` / `win` / `ubuntu`, Newest → Oldest)

| Version | Platforms | Release Date | Key Changes |
|---|---|---|---|
| [3.30.14](2026-11-14_3.30.14.md) | `mac`, `win`, `ubuntu` | 2026-11-14 | Unified commit `5f54c817` (Electron `43.8.4→43.8.9`); default-off Deploy App (`AppPublishService.getAppsEligibility`, gates `cloud_agent_apps` & `glass_deploy_with_cursor_pill`, `glass_apps_growth_config`, `molten` `apps-publish-CtW5oKQc.js` store & preview cards); `SideChatInfo.subagent_type`; daemon fail-closed `{url, patterns[]}` repo glob governance (`team-repo-rules.js`) & `caller-window.ts`; main-process `grokConfigFiles.js` (`~/.grok/*.toml`) |
| [3.30.8](2026-11-12_3.30.8.md) | `mac`, `win`, `ubuntu` | 2026-11-12 | Unified commit `4a44c846` (`+111` unary RPCs: `DashboardService` `+56` Step-Up/OAuth/session governance, `GrokBotService` `+48` + gated `"Cursor is now Grok Build"` UI); `ToolCall` `+2` (`manage_access`, `execute`); client MCP allowlist/denylist `mcpSurfaceAccess`, OAuth `429` backoff & `mcp_event` triggers; Remote Control P-256 `pairing_proof` & `AgentHostService` `49→59`; `airlockEngine`, daemon `--environment-file` hardening, and `ai-tracking-worker` SQLite |
| [3.29.15](2026-11-08_3.29.15.md) | `mac`, `win`, `ubuntu` | 2026-11-08 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.29.9](2026-11-05_3.29.9.md) | `mac`, `win`, `ubuntu` | 2026-11-05 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.28.7](2026-11-03_3.28.7.md) | `mac`, `win`, `ubuntu` | 2026-11-03 | VS Code `1.128.0` fork (commit `25b52e7`): dual `workbench.desktop` + `workbench.glass` bundles, 17-RPC HTTP/2 Connect `RemoteAgentHostPresenceService` tunnel with ECDSA P-256 `x-cursor-agent-host-proof` DPoP JWTs, 5 `AuthService` mobile session RPCs, and 70+ `agent.v1.ToolCall` schemas (`PromptContextUsageTree`) |
| [3.27.22](2026-10-27_3.27.22.md) | `mac`, `win`, `ubuntu` | 2026-10-27 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.27.14](2026-10-23_3.27.14.md) | `mac`, `win`, `ubuntu` | 2026-10-23 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.27.12](2026-10-23_3.27.12.md) | `mac`, `win`, `ubuntu` | 2026-10-23 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.27.6](2026-10-21_3.27.6.md) | `mac`, `win`, `ubuntu` | 2026-10-21 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.26.16](2026-10-21_3.26.16.md) | `mac`, `win`, `ubuntu` | 2026-10-21 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.26.13](2026-10-20_3.26.13.md) | `mac`, `ubuntu` | 2026-10-20 | `TODO` (`mac`, `ubuntu`) — _detailed diff pending_ |
| [3.25.9](2026-10-17_3.25.9.md) | `mac`, `ubuntu` | 2026-10-17 | `TODO` (`mac`, `ubuntu`) — _detailed diff pending_ |
| [3.25.6](2026-10-15_3.25.6.md) | `mac`, `ubuntu` | 2026-10-15 | `TODO` (`mac`, `ubuntu`) — _detailed diff pending_ |
| [3.24.18](2026-10-13_3.24.18.md) | `mac`, `ubuntu` | 2026-10-13 | `TODO` (`mac`, `ubuntu`) — _detailed diff pending_ |
| [3.24.12](2026-10-09_3.24.12.md) | `mac`, `win`, `ubuntu` | 2026-10-09 | Isolated Electron `utilityProcess` (`mcpProcessMain.js`) with `@modelcontextprotocol/sdk@1.25.1` (`2025-11-25`) + `@anysphere/sandbox-helper`, strict `mcp.json` schema (`envFile`, `auth`, `placement`, `enabledTools`), built-in `cursor-ide-browser` (16 tools) & `cursor-computer-use` (17 tools), and `agent.v1.McpToolDefinition` (`server-tool` naming) |
| [3.24.9](2026-10-08_3.24.9.md) | `mac`, `ubuntu` | 2026-10-08 | `TODO` (`mac`, `ubuntu`) — _detailed diff pending_ |
| [3.23.23](2026-10-05_3.23.23.md) | `mac`, `ubuntu` | 2026-10-05 | `TODO` (`mac`, `ubuntu`) — _detailed diff pending_ |
| [3.23.12](2026-10-01_3.23.12.md) | `mac`, `ubuntu` | 2026-10-01 | `TODO` (`mac`, `ubuntu`) — _detailed diff pending_ |
| [3.22.12](2026-09-28_3.22.12.md) | `mac`, `ubuntu` | 2026-09-28 | `TODO` (`mac`, `ubuntu`) — _detailed diff pending_ |
| [3.22.7](2026-09-24_3.22.7.md) | `mac`, `ubuntu` | 2026-09-24 | `TODO` (`mac`, `ubuntu`) — _detailed diff pending_ |
| [3.21.18](2026-09-22_3.21.18.md) | `mac`, `ubuntu` | 2026-09-22 | `TODO` (`mac`, `ubuntu`) — _detailed diff pending_ |
| [3.21.16](2026-09-19_3.21.16.md) | `mac`, `ubuntu` | 2026-09-19 | `TODO` (`mac`, `ubuntu`) — _detailed diff pending_ |
| [3.21.13](2026-09-18_3.21.13.md) | `mac`, `ubuntu` | 2026-09-18 | `TODO` (`mac`, `ubuntu`) — _detailed diff pending_ |
| [3.21.9](2026-09-17_3.21.9.md) | `mac`, `ubuntu` | 2026-09-17 | `TODO` (`mac`, `ubuntu`) — _detailed diff pending_ |
| [3.20.21](2026-09-14_3.20.21.md) | `mac`, `ubuntu` | 2026-09-14 | `TODO` (`mac`, `ubuntu`) — _detailed diff pending_ |
| [3.20.17](2026-09-12_3.20.17.md) | `mac`, `win`, `ubuntu` | 2026-09-12 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.20.15](2026-09-12_3.20.15.md) | `mac` | 2026-09-12 | `TODO` (`mac`) — _detailed diff pending_ |
| [3.20.14](2026-09-11_3.20.14.md) | `mac`, `win`, `ubuntu` | 2026-09-11 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.20.10](2026-09-10_3.20.10.md) | `mac`, `win`, `ubuntu` | 2026-09-10 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.19.19](2026-09-09_3.19.19.md) | `mac`, `ubuntu` | 2026-09-09 | `TODO` (`mac`, `ubuntu`) — _detailed diff pending_ |
| [3.19.13](2026-09-05_3.19.13.md) | `mac`, `ubuntu` | 2026-09-05 | `TODO` (`mac`, `ubuntu`) — _detailed diff pending_ |
| [3.19.7](2026-09-02_3.19.7.md) | `mac`, `win`, `ubuntu` | 2026-09-02 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.18.25](2026-09-01_3.18.25.md) | `mac`, `win`, `ubuntu` | 2026-09-01 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.18.9](2026-08-29_3.18.9.md) | `mac`, `ubuntu` | 2026-08-29 | `TODO` (`mac`, `ubuntu`) — _detailed diff pending_ |
| [3.17.21](2026-08-26_3.17.21.md) | `mac`, `ubuntu` | 2026-08-26 | `TODO` (`mac`, `ubuntu`) — _detailed diff pending_ |
| [3.17.19](2026-08-24_3.17.19.md) | `mac`, `ubuntu` | 2026-08-24 | `TODO` (`mac`, `ubuntu`) — _detailed diff pending_ |
| [3.17.8](2026-08-20_3.17.8.md) | `mac`, `ubuntu` | 2026-08-20 | `TODO` (`mac`, `ubuntu`) — _detailed diff pending_ |
| [3.16.29](2026-08-19_3.16.29.md) | `mac`, `ubuntu` | 2026-08-19 | `TODO` (`mac`, `ubuntu`) — _detailed diff pending_ |
| [3.16.17](2026-08-15_3.16.17.md) | `mac`, `ubuntu` | 2026-08-15 | `TODO` (`mac`, `ubuntu`) — _detailed diff pending_ |
| [3.15.19](2026-08-12_3.15.19.md) | `mac`, `ubuntu` | 2026-08-12 | `TODO` (`mac`, `ubuntu`) — _detailed diff pending_ |
| [3.15.6](2026-08-06_3.15.6.md) | `mac`, `win`, `ubuntu` | 2026-08-06 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.14.27](2026-08-04_3.14.27.md) | `mac`, `win`, `ubuntu` | 2026-08-04 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.14.7](2026-07-30_3.14.7.md) | `mac`, `win`, `ubuntu` | 2026-07-30 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.13.25](2026-07-28_3.13.25.md) | `mac`, `win`, `ubuntu` | 2026-07-28 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.13.21](2026-07-27_3.13.21.md) | `mac`, `win`, `ubuntu` | 2026-07-27 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.13.10](2026-07-23_3.13.10.md) | `mac`, `win`, `ubuntu` | 2026-07-23 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.12.30](2026-07-21_3.12.30.md) | `mac`, `win`, `ubuntu` | 2026-07-21 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.12.29](2026-07-21_3.12.29.md) | `mac`, `win`, `ubuntu` | 2026-07-21 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.12.17](2026-07-17_3.12.17.md) | `mac`, `win`, `ubuntu` | 2026-07-17 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.12.10](2026-07-16_3.12.10.md) | `mac`, `win`, `ubuntu` | 2026-07-16 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.11.25](2026-07-10_3.11.25.md) | `mac`, `win`, `ubuntu` | 2026-07-10 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.11.19](2026-07-10_3.11.19.md) | `mac`, `win`, `ubuntu` | 2026-07-10 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.11.13](2026-07-10_3.11.13.md) | `mac`, `win`, `ubuntu` | 2026-07-10 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.10.11](2026-07-03_3.10.11.md) | `mac`, `win`, `ubuntu` | 2026-07-03 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.10.20](2026-06-30_3.10.20.md) | `mac`, `win`, `ubuntu` | 2026-06-30 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.10.17](2026-06-30_3.10.17.md) | `mac`, `win`, `ubuntu` | 2026-06-30 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.9.16](2026-06-22_3.9.16.md) | `mac`, `win`, `ubuntu` | 2026-06-22 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.9.8](2026-06-22_3.9.8.md) | `mac`, `win`, `ubuntu` | 2026-06-22 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.8.23](2026-06-22_3.8.23.md) | `mac`, `win`, `ubuntu` | 2026-06-22 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.8.24](2026-06-18_3.8.24.md) | `mac`, `win`, `ubuntu` | 2026-06-18 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.8.22](2026-06-18_3.8.22.md) | `mac`, `win`, `ubuntu` | 2026-06-18 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.8.11](2026-06-18_3.8.11.md) | `mac`, `win`, `ubuntu` | 2026-06-18 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.7.42](2026-06-05_3.7.42.md) | `mac`, `win`, `ubuntu` | 2026-06-05 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.7.36](2026-06-05_3.7.36.md) | `mac`, `win`, `ubuntu` | 2026-06-05 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.7.27](2026-06-05_3.7.27.md) | `mac`, `win`, `ubuntu` | 2026-06-05 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.7.21](2026-06-05_3.7.21.md) | `mac`, `win`, `ubuntu` | 2026-06-05 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.7.19](2026-06-05_3.7.19.md) | `mac`, `win`, `ubuntu` | 2026-06-05 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.7.12](2026-06-05_3.7.12.md) | `mac`, `win`, `ubuntu` | 2026-06-05 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.6.31](2026-05-29_3.6.31.md) | `mac`, `win`, `ubuntu` | 2026-05-29 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.6.21](2026-05-28_3.6.21.md) | `mac`, `win`, `ubuntu` | 2026-05-28 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.5.38](2026-05-20_3.5.38.md) | `mac`, `win`, `ubuntu` | 2026-05-20 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.5.33](2026-05-20_3.5.33.md) | `mac`, `win`, `ubuntu` | 2026-05-20 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.5.17](2026-05-20_3.5.17.md) | `mac`, `win`, `ubuntu` | 2026-05-20 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.4.20](2026-05-13_3.4.20.md) | `mac`, `win`, `ubuntu` | 2026-05-13 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.4.17](2026-05-13_3.4.17.md) | `mac`, `win`, `ubuntu` | 2026-05-13 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.4.16](2026-05-13_3.4.16.md) | `mac`, `win`, `ubuntu` | 2026-05-13 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.3.30](2026-05-07_3.3.30.md) | `mac`, `win`, `ubuntu` | 2026-05-07 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.3.27](2026-05-07_3.3.27.md) | `mac`, `win`, `ubuntu` | 2026-05-07 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.3.22](2026-05-06_3.3.22.md) | `mac`, `win`, `ubuntu` | 2026-05-06 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.3.16](2026-05-06_3.3.16.md) | `mac`, `win`, `ubuntu` | 2026-05-06 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.3.12](2026-05-06_3.3.12.md) | `mac`, `win`, `ubuntu` | 2026-05-06 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.2.21](2026-04-24_3.2.21.md) | `mac`, `win`, `ubuntu` | 2026-04-24 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.2.16](2026-04-24_3.2.16.md) | `mac`, `win`, `ubuntu` | 2026-04-24 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.2.11](2026-04-24_3.2.11.md) | `mac`, `win`, `ubuntu` | 2026-04-24 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.2.10](2026-04-24_3.2.10.md) | `mac`, `win`, `ubuntu` | 2026-04-24 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.1.17](2026-04-13_3.1.17.md) | `mac`, `win`, `ubuntu` | 2026-04-13 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.1.15](2026-04-13_3.1.15.md) | `mac`, `win`, `ubuntu` | 2026-04-13 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.1.14](2026-04-13_3.1.14.md) | `mac`, `win`, `ubuntu` | 2026-04-13 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.1.10](2026-04-13_3.1.10.md) | `mac`, `win`, `ubuntu` | 2026-04-13 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.0.16](2026-04-02_3.0.16.md) | `mac`, `win`, `ubuntu` | 2026-04-02 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.0.13](2026-04-02_3.0.13.md) | `mac`, `win`, `ubuntu` | 2026-04-02 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.0.12](2026-04-02_3.0.12.md) | `mac`, `win`, `ubuntu` | 2026-04-02 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.0.9](2026-04-02_3.0.9.md) | `mac`, `win`, `ubuntu` | 2026-04-02 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.0.8](2026-04-02_3.0.8.md) | `mac`, `win`, `ubuntu` | 2026-04-02 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.0.6](2026-04-02_3.0.6.md) | `mac`, `win`, `ubuntu` | 2026-04-02 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.0.4](2026-04-02_3.0.4.md) | `mac`, `win`, `ubuntu` | 2026-04-02 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.6.22](2026-03-27_2.6.22.md) | `mac`, `win`, `ubuntu` | 2026-03-27 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.6.21](2026-03-03_2.6.21.md) | `mac`, `win`, `ubuntu` | 2026-03-03 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.6.20](2026-03-03_2.6.20.md) | `mac`, `win`, `ubuntu` | 2026-03-03 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.6.19](2026-03-03_2.6.19.md) | `mac`, `win`, `ubuntu` | 2026-03-03 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.6.18](2026-03-03_2.6.18.md) | `mac`, `win`, `ubuntu` | 2026-03-03 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.6.14](2026-03-03_2.6.14.md) | `mac`, `win`, `ubuntu` | 2026-03-03 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.6.13](2026-03-03_2.6.13.md) | `mac`, `win`, `ubuntu` | 2026-03-03 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.6.12](2026-03-03_2.6.12.md) | `mac`, `win`, `ubuntu` | 2026-03-03 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.6.11](2026-03-03_2.6.11.md) | `mac`, `win`, `ubuntu` | 2026-03-03 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.5.26](2026-02-17_2.5.26.md) | `mac`, `win`, `ubuntu` | 2026-02-17 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.5.25](2026-02-17_2.5.25.md) | `mac`, `win`, `ubuntu` | 2026-02-17 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.5.20](2026-02-17_2.5.20.md) | `mac`, `win`, `ubuntu` | 2026-02-17 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.5.17](2026-02-17_2.5.17.md) | `mac`, `win`, `ubuntu` | 2026-02-17 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.4.37](2026-01-22_2.4.37.md) | `mac`, `win`, `ubuntu` | 2026-01-22 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.4.36](2026-01-22_2.4.36.md) | `mac`, `win`, `ubuntu` | 2026-01-22 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.4.31](2026-01-22_2.4.31.md) | `mac`, `win`, `ubuntu` | 2026-01-22 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.4.28](2026-01-22_2.4.28.md) | `mac`, `win`, `ubuntu` | 2026-01-22 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.4.27](2026-01-22_2.4.27.md) | `mac`, `win`, `ubuntu` | 2026-01-22 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.4.23](2026-01-22_2.4.23.md) | `mac`, `win`, `ubuntu` | 2026-01-22 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.4.22](2026-01-22_2.4.22.md) | `mac`, `win`, `ubuntu` | 2026-01-22 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.4.21](2026-01-22_2.4.21.md) | `mac`, `win`, `ubuntu` | 2026-01-22 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.3.41](2025-12-22_2.3.41.md) | `mac`, `win`, `ubuntu` | 2025-12-22 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.3.35](2025-12-22_2.3.35.md) | `mac`, `win`, `ubuntu` | 2025-12-22 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.3.34](2025-12-22_2.3.34.md) | `mac`, `win`, `ubuntu` | 2025-12-22 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.3.29](2025-12-22_2.3.29.md) | `mac`, `win`, `ubuntu` | 2025-12-22 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.3.26](2025-12-22_2.3.26.md) | `mac`, `win`, `ubuntu` | 2025-12-22 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.3.23](2025-12-22_2.3.23.md) | `mac`, `win`, `ubuntu` | 2025-12-22 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.3.21](2025-12-22_2.3.21.md) | `mac`, `win`, `ubuntu` | 2025-12-22 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.3.20](2025-12-22_2.3.20.md) | `mac`, `win`, `ubuntu` | 2025-12-22 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.3.18](2025-12-22_2.3.18.md) | `mac`, `win`, `ubuntu` | 2025-12-22 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.3.15](2025-12-22_2.3.15.md) | `mac`, `win`, `ubuntu` | 2025-12-22 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.2.36](2025-12-18_2.2.36.md) | `mac`, `ubuntu` | 2025-12-18 | `TODO` (`mac`, `ubuntu`) — _detailed diff pending_ |
| [2.2.33](2025-12-18_2.2.33.md) | `mac`, `win`, `ubuntu` | 2025-12-18 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.2.29](2025-12-17_2.2.29.md) | `mac`, `win`, `ubuntu` | 2025-12-17 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.2.44](2025-12-10_2.2.44.md) | `mac`, `win`, `ubuntu` | 2025-12-10 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.2.43](2025-12-10_2.2.43.md) | `mac`, `win`, `ubuntu` | 2025-12-10 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.2.35](2025-12-10_2.2.35.md) | `mac`, `win`, `ubuntu` | 2025-12-10 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.2.20](2025-12-10_2.2.20.md) | `mac`, `win`, `ubuntu` | 2025-12-10 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.2.17](2025-12-10_2.2.17.md) | `mac`, `win`, `ubuntu` | 2025-12-10 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.2.14](2025-12-10_2.2.14.md) | `mac`, `win`, `ubuntu` | 2025-12-10 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.2.12](2025-12-10_2.2.12.md) | `mac`, `win`, `ubuntu` | 2025-12-10 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.2.9](2025-12-10_2.2.9.md) | `mac`, `win`, `ubuntu` | 2025-12-10 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.1.50](2025-12-07_2.1.50.md) | `mac`, `win`, `ubuntu` | 2025-12-07 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.1.49](2025-12-05_2.1.49.md) | `mac`, `win`, `ubuntu` | 2025-12-05 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.1.48](2025-12-04_2.1.48.md) | `mac`, `win`, `ubuntu` | 2025-12-04 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.1.47](2025-12-04_2.1.47.md) | `mac`, `win`, `ubuntu` | 2025-12-04 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.1.46](2025-12-02_2.1.46.md) | `mac`, `win`, `ubuntu` | 2025-12-02 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.1.44](2025-12-01_2.1.44.md) | `mac`, `win`, `ubuntu` | 2025-12-01 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.1.42](2025-12-01_2.1.42.md) | `mac`, `win`, `ubuntu` | 2025-12-01 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.1.41](2025-11-30_2.1.41.md) | `mac`, `win`, `ubuntu` | 2025-11-30 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.1.39](2025-11-27_2.1.39.md) | `mac`, `win`, `ubuntu` | 2025-11-27 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.1.36](2025-11-26_2.1.36.md) | `mac`, `win`, `ubuntu` | 2025-11-26 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.1.34](2025-11-25_2.1.34.md) | `mac`, `win`, `ubuntu` | 2025-11-25 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.1.32](2025-11-25_2.1.32.md) | `mac`, `win`, `ubuntu` | 2025-11-25 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.1.26](2025-11-24_2.1.26.md) | `mac`, `win`, `ubuntu` | 2025-11-24 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.1.25](2025-11-23_2.1.25.md) | `mac`, `win`, `ubuntu` | 2025-11-23 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.1.20](2025-11-22_2.1.20.md) | `mac`, `win`, `ubuntu` | 2025-11-22 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.1.19](2025-11-21_2.1.19.md) | `mac`, `win`, `ubuntu` | 2025-11-21 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.1.17](2025-11-21_2.1.17.md) | `mac`, `win`, `ubuntu` | 2025-11-21 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.0.77](2025-11-13_2.0.77.md) | `mac`, `win`, `ubuntu` | 2025-11-13 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.0.75](2025-11-12_2.0.75.md) | `mac`, `win`, `ubuntu` | 2025-11-12 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.0.74](2025-11-12_2.0.74.md) | `mac`, `win`, `ubuntu` | 2025-11-12 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.0.69](2025-11-07_2.0.69.md) | `mac`, `win`, `ubuntu` | 2025-11-07 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.0.64](2025-11-06_2.0.64.md) | `mac`, `win`, `ubuntu` | 2025-11-06 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.0.63](2025-11-05_2.0.63.md) | `mac`, `win`, `ubuntu` | 2025-11-05 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.0.60](2025-11-05_2.0.60.md) | `mac`, `win`, `ubuntu` | 2025-11-05 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.0.54](2025-11-03_2.0.54.md) | `mac`, `win`, `ubuntu` | 2025-11-03 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.0.43](2025-10-30_2.0.43.md) | `mac`, `win`, `ubuntu` | 2025-10-30 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.0.40](2025-10-30_2.0.40.md) | `mac`, `win`, `ubuntu` | 2025-10-30 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.0.38](2025-10-29_2.0.38.md) | `mac`, `win`, `ubuntu` | 2025-10-29 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [2.0.34](2025-10-29_2.0.34.md) | `mac`, `win`, `ubuntu` | 2025-10-29 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.7.54](2025-10-21_1.7.54.md) | `mac`, `win`, `ubuntu` | 2025-10-21 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.7.53](2025-10-20_1.7.53.md) | `mac`, `win`, `ubuntu` | 2025-10-20 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.7.52](2025-10-17_1.7.52.md) | `mac`, `win`, `ubuntu` | 2025-10-17 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.7.46](2025-10-14_1.7.46.md) | `mac`, `win`, `ubuntu` | 2025-10-14 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.7.44](2025-10-10_1.7.44.md) | `mac`, `win`, `ubuntu` | 2025-10-10 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.7.40](2025-10-09_1.7.40.md) | `mac`, `win`, `ubuntu` | 2025-10-09 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.7.39](2025-10-08_1.7.39.md) | `mac`, `win`, `ubuntu` | 2025-10-08 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.7.38](2025-10-06_1.7.38.md) | `mac`, `win`, `ubuntu` | 2025-10-06 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.7.33](2025-10-03_1.7.33.md) | `mac`, `win`, `ubuntu` | 2025-10-03 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.7.28](2025-10-01_1.7.28.md) | `mac`, `win`, `ubuntu` | 2025-10-01 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.7.25](2025-09-30_1.7.25.md) | `mac`, `win`, `ubuntu` | 2025-09-30 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.7.23](2025-09-30_1.7.23.md) | `mac`, `win`, `ubuntu` | 2025-09-30 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.7.22](2025-09-29_1.7.22.md) | `mac`, `win`, `ubuntu` | 2025-09-29 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.7.17](2025-09-29_1.7.17.md) | `mac`, `win`, `ubuntu` | 2025-09-29 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.7.12](2025-09-28_1.7.12.md) | `mac`, `win`, `ubuntu` | 2025-09-28 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.7.11](2025-09-26_1.7.11.md) | `mac`, `win`, `ubuntu` | 2025-09-26 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.6.45](2025-09-22_1.6.45.md) | `mac`, `win`, `ubuntu` | 2025-09-22 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.6.42](2025-09-20_1.6.42.md) | `mac`, `win`, `ubuntu` | 2025-09-20 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.6.23](2025-09-15_1.6.23.md) | `mac`, `win`, `ubuntu` | 2025-09-15 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.6.22](2025-09-15_1.6.22.md) | `mac` | 2025-09-15 | `TODO` (`mac`) — _detailed diff pending_ |
| [1.6.14](2025-09-12_1.6.14.md) | `mac` | 2025-09-12 | `TODO` (`mac`) — _detailed diff pending_ |
| [1.6.35](2025-09-11_1.6.35.md) | `mac`, `win`, `ubuntu` | 2025-09-11 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.6.27](2025-09-11_1.6.27.md) | `mac`, `win`, `ubuntu` | 2025-09-11 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.6.26](2025-09-11_1.6.26.md) | `mac`, `win`, `ubuntu` | 2025-09-11 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.6.6](2025-09-11_1.6.6.md) | `mac`, `win`, `ubuntu` | 2025-09-11 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.5.5](2025-08-25_1.5.5.md) | `mac`, `win`, `ubuntu` | 2025-08-25 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.5.4](2025-08-22_1.5.4.md) | `mac`, `win`, `ubuntu` | 2025-08-22 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.5.3](2025-08-22_1.5.3.md) | `mac`, `win`, `ubuntu` | 2025-08-22 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.5.2](2025-08-22_1.5.2.md) | `mac`, `win`, `ubuntu` | 2025-08-22 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.5.11](2025-08-21_1.5.11.md) | `mac`, `win`, `ubuntu` | 2025-08-21 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.5.9](2025-08-21_1.5.9.md) | `mac`, `win`, `ubuntu` | 2025-08-21 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.5.7](2025-08-21_1.5.7.md) | `mac`, `win`, `ubuntu` | 2025-08-21 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.5.1](2025-08-21_1.5.1.md) | `mac`, `win`, `ubuntu` | 2025-08-21 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.4.5](2025-08-06_1.4.5.md) | `mac`, `win`, `ubuntu` | 2025-08-06 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.4.3](2025-08-06_1.4.3.md) | `mac`, `win`, `ubuntu` | 2025-08-06 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.4.2](2025-08-06_1.4.2.md) | `mac`, `win`, `ubuntu` | 2025-08-06 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.4.1](2025-08-06_1.4.1.md) | `mac`, `win`, `ubuntu` | 2025-08-06 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.4.0](2025-08-05_1.4.0.md) | `mac`, `win`, `ubuntu` | 2025-08-05 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.3.9](2025-07-29_1.3.9.md) | `mac`, `win`, `ubuntu` | 2025-07-29 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.3.8](2025-07-29_1.3.8.md) | `mac`, `win`, `ubuntu` | 2025-07-29 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.3.7](2025-07-29_1.3.7.md) | `mac`, `win`, `ubuntu` | 2025-07-29 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.3.6](2025-07-29_1.3.6.md) | `mac`, `win`, `ubuntu` | 2025-07-29 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.3.5](2025-07-29_1.3.5.md) | `mac`, `win`, `ubuntu` | 2025-07-29 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.3.4](2025-07-29_1.3.4.md) | `mac`, `win`, `ubuntu` | 2025-07-29 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.3.3](2025-07-26_1.3.3.md) | `mac`, `win`, `ubuntu` | 2025-07-26 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.3.2](2025-07-24_1.3.2.md) | `mac`, `win`, `ubuntu` | 2025-07-24 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.3.1](2025-07-24_1.3.1.md) | `mac`, `win`, `ubuntu` | 2025-07-24 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.3.0](2025-07-23_1.3.0.md) | `mac`, `win`, `ubuntu` | 2025-07-23 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.2.4](2025-07-03_1.2.4.md) | `mac`, `win`, `ubuntu` | 2025-07-03 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.2.2](2025-07-03_1.2.2.md) | `mac`, `win`, `ubuntu` | 2025-07-03 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.2.1](2025-07-03_1.2.1.md) | `mac`, `win`, `ubuntu` | 2025-07-03 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.2.0](2025-07-01_1.2.0.md) | `mac`, `win`, `ubuntu` | 2025-07-01 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.1.4](2025-06-20_1.1.4.md) | `mac` | 2025-06-20 | `TODO` (`mac`) — _detailed diff pending_ |
| [1.1.2](2025-06-13_1.1.2.md) | `mac`, `win`, `ubuntu` | 2025-06-13 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.1.7](2025-06-12_1.1.7.md) | `mac`, `win`, `ubuntu` | 2025-06-12 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.1.6](2025-06-12_1.1.6.md) | `mac`, `win`, `ubuntu` | 2025-06-12 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.1.5](2025-06-12_1.1.5.md) | `mac`, `win`, `ubuntu` | 2025-06-12 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [1.0.1](2025-06-08_1.0.1.md) | `mac` | 2025-06-08 | `TODO` (`mac`) — _detailed diff pending_ |
| [1.0.0](2025-06-04_1.0.0.md) | `mac`, `win`, `ubuntu` | 2025-06-04 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [0.51.2](2025-06-04_0.51.2.md) | `mac` | 2025-06-04 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.51.1](2025-05-31_0.51.1.md) | `mac` | 2025-05-31 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.50.7](2025-05-24_0.50.7.md) | `mac`, `win`, `ubuntu` | 2025-05-24 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [0.50.6](2025-05-23_0.50.6.md) | `mac`, `win`, `ubuntu` | 2025-05-23 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [0.50.5](2025-05-18_0.50.5.md) | `mac`, `win`, `ubuntu` | 2025-05-18 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [0.50.4](2025-05-14_0.50.4.md) | `mac`, `win`, `ubuntu` | 2025-05-14 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [0.50.3](2025-05-13_0.50.3.md) | `mac`, `win`, `ubuntu` | 2025-05-13 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [0.50.2](2025-05-13_0.50.2.md) | `mac` | 2025-05-13 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.49.6](2025-04-25_0.49.6.md) | `mac`, `win`, `ubuntu` | 2025-04-25 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [0.49.5](2025-04-24_0.49.5.md) | `mac`, `win`, `ubuntu` | 2025-04-24 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [0.49.4](2025-04-22_0.49.4.md) | `mac`, `win`, `ubuntu` | 2025-04-22 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [0.49.3](2025-04-21_0.49.3.md) | `mac`, `win`, `ubuntu` | 2025-04-21 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [0.49.2](2025-04-19_0.49.2.md) | `mac`, `win`, `ubuntu` | 2025-04-19 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [0.48.9](2025-04-12_0.48.9.md) | `mac`, `win`, `ubuntu` | 2025-04-12 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [0.48.8](2025-04-07_0.48.8.md) | `mac`, `win`, `ubuntu` | 2025-04-07 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [0.48.7](2025-04-03_0.48.7.md) | `mac` | 2025-04-03 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.48.6](2025-03-31_0.48.6.md) | `mac`, `win`, `ubuntu` | 2025-03-31 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [0.48.5](2025-03-31_0.48.5.md) | `mac` | 2025-03-31 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.48.3](2025-03-29_0.48.3.md) | `mac` | 2025-03-29 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.48.2](2025-03-26_0.48.2.md) | `mac`, `win`, `ubuntu` | 2025-03-26 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [0.48.1](2025-03-25_0.48.1.md) | `mac` | 2025-03-25 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.48.0](2025-03-24_0.48.0.md) | `mac` | 2025-03-24 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.47.9](2025-03-22_0.47.9.md) | `mac` | 2025-03-22 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.47.8](2025-03-18_0.47.8.md) | `mac`, `win` | 2025-03-18 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.47.7](2025-03-18_0.47.7.md) | `mac`, `win` | 2025-03-18 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.47.5](2025-03-14_0.47.5.md) | `mac`, `win` | 2025-03-14 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.47.4](2025-03-14_0.47.4.md) | `mac` | 2025-03-14 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.46.11](2025-03-07_0.46.11.md) | `mac`, `win` | 2025-03-07 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.46.9](2025-03-05_0.46.9.md) | `mac` | 2025-03-05 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.45.17](2025-03-02_0.45.17.md) | `mac` | 2025-03-02 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.45.14](2025-02-19_0.45.14.md) | `mac`, `win` | 2025-02-19 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.45.12](2025-02-18_0.45.12.md) | `mac`, `win` | 2025-02-18 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.45.11](2025-02-07_0.45.11.md) | `mac`, `win` | 2025-02-07 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.45.10](2025-02-05_0.45.10.md) | `mac`, `win` | 2025-02-05 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.45.9](2025-02-02_0.45.9.md) | `mac`, `win` | 2025-02-02 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.45.8](2025-02-01_0.45.8.md) | `mac`, `win` | 2025-02-01 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.45.7](2025-01-30_0.45.7.md) | `mac`, `win` | 2025-01-30 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.45.6](2025-01-30_0.45.6.md) | `mac`, `win` | 2025-01-30 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.45.5](2025-01-28_0.45.5.md) | `mac`, `win` | 2025-01-28 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.45.4](2025-01-26_0.45.4.md) | `mac`, `win` | 2025-01-26 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.45.3](2025-01-24_0.45.3.md) | `mac`, `win` | 2025-01-24 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.45.2](2025-01-23_0.45.2.md) | `mac`, `win` | 2025-01-23 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.45.1](2025-01-21_0.45.1.md) | `mac`, `win` | 2025-01-21 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.45.0](2025-01-20_0.45.0.md) | `mac`, `win` | 2025-01-20 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.44.11](2025-01-03_0.44.11.md) | `mac`, `win` | 2025-01-03 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.44.10](2025-01-02_0.44.10.md) | `mac`, `win` | 2025-01-02 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.44.9](2024-12-26_0.44.9.md) | `mac`, `win` | 2024-12-26 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.44.8](2024-12-22_0.44.8.md) | `mac`, `win` | 2024-12-22 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.44.7](2024-12-22_0.44.7.md) | `mac`, `win` | 2024-12-22 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.44.6](2024-12-21_0.44.6.md) | `mac`, `win` | 2024-12-21 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.44.5](2024-12-20_0.44.5.md) | `mac`, `win` | 2024-12-20 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.44.4](2024-12-19_0.44.4.md) | `mac`, `win` | 2024-12-19 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.44.3](2024-12-18_0.44.3.md) | `mac`, `win` | 2024-12-18 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.44.2](2024-12-18_0.44.2.md) | `mac`, `win` | 2024-12-18 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.44.0](2024-12-18_0.44.0.md) | `mac`, `win` | 2024-12-18 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.43.6](2024-12-06_0.43.6.md) | `mac`, `win` | 2024-12-06 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.43.5](2024-11-27_0.43.5.md) | `mac`, `win` | 2024-11-27 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.43.4](2024-11-26_0.43.4.md) | `mac`, `win` | 2024-11-26 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.43.3](2024-11-24_0.43.3.md) | `mac`, `win` | 2024-11-24 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.43.1](2024-11-24_0.43.1.md) | `mac`, `win` | 2024-11-24 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.43.0](2024-11-24_0.43.0.md) | `win` | 2024-11-24 | `TODO` (`win`) — _detailed diff pending_ |
| [0.42.5](2024-11-14_0.42.5.md) | `mac`, `win` | 2024-11-14 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.42.4](2024-10-29_0.42.4.md) | `mac`, `win` | 2024-10-29 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.42.3](2024-10-16_0.42.3.md) | `mac`, `win` | 2024-10-16 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.42.2](2024-10-12_0.42.2.md) | `mac`, `win` | 2024-10-12 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.42.1](2024-10-11_0.42.1.md) | `mac`, `win` | 2024-10-11 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.42.0](2024-10-09_0.42.0.md) | `mac`, `win` | 2024-10-09 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.41.3](2024-09-25_0.41.3.md) | `mac`, `win` | 2024-09-25 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.41.2](2024-09-21_0.41.2.md) | `mac`, `win` | 2024-09-21 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.41.1](2024-09-18_0.41.1.md) | `mac`, `win` | 2024-09-18 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.40.4](2024-09-05_0.40.4.md) | `mac`, `win` | 2024-09-05 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.40.3](2024-08-29_0.40.3.md) | `mac`, `win` | 2024-08-29 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.40.2](2024-08-28_0.40.2.md) | `mac`, `win` | 2024-08-28 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.40.1](2024-08-24_0.40.1.md) | `mac`, `win` | 2024-08-24 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.40.0](2024-08-22_0.40.0.md) | `mac`, `win` | 2024-08-22 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.39.6](2024-08-19_0.39.6.md) | `mac`, `win` | 2024-08-19 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.39.5](2024-08-14_0.39.5.md) | `mac`, `win` | 2024-08-14 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.39.4](2024-08-10_0.39.4.md) | `mac`, `win` | 2024-08-10 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.39.3](2024-08-09_0.39.3.md) | `mac`, `win` | 2024-08-09 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.39.2](2024-08-08_0.39.2.md) | `mac`, `win` | 2024-08-08 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.39.1](2024-08-07_0.39.1.md) | `mac`, `win` | 2024-08-07 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.39.0](2024-08-02_0.39.0.md) | `mac`, `win` | 2024-08-02 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.38.1](2024-07-25_0.38.1.md) | `mac`, `win` | 2024-07-25 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.38.0](2024-07-23_0.38.0.md) | `mac`, `win` | 2024-07-23 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.37.1](2024-07-14_0.37.1.md) | `mac`, `win` | 2024-07-14 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.36.2](2024-07-07_0.36.2.md) | `mac`, `win` | 2024-07-07 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.36.1](2024-07-06_0.36.1.md) | `mac` | 2024-07-06 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.36.0](2024-07-04_0.36.0.md) | `mac` | 2024-07-04 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.35.1](2024-06-22_0.35.1.md) | `mac` | 2024-06-22 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.35.0](2024-06-08_0.35.0.md) | `mac` | 2024-06-08 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.34.6](2024-06-06_0.34.6.md) | `mac` | 2024-06-06 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.34.5](2024-06-02_0.34.5.md) | `mac` | 2024-06-02 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.34.4](2024-06-01_0.34.4.md) | `mac` | 2024-06-01 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.34.3](2024-05-30_0.34.3.md) | `mac` | 2024-05-30 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.34.2](2024-05-29_0.34.2.md) | `mac` | 2024-05-29 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.34.1](2024-05-28_0.34.1.md) | `mac` | 2024-05-28 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.34.0](2024-05-27_0.34.0.md) | `mac` | 2024-05-27 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.33.4](2024-05-11_0.33.4.md) | `mac` | 2024-05-11 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.33.3](2024-05-11_0.33.3.md) | `mac` | 2024-05-11 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.33.2](2024-05-10_0.33.2.md) | `mac` | 2024-05-10 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.33.1](2024-05-04_0.33.1.md) | `mac` | 2024-05-04 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.33.0](2024-05-04_0.33.0.md) | `mac` | 2024-05-04 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.32.8](2024-04-29_0.32.8.md) | `mac` | 2024-04-29 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.32.7](2024-04-28_0.32.7.md) | `mac` | 2024-04-28 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.32.2](2024-04-18_0.32.2.md) | `mac` | 2024-04-18 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.32.1](2024-04-16_0.32.1.md) | `mac` | 2024-04-16 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.32.0](2024-04-13_0.32.0.md) | `mac` | 2024-04-13 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.31.3](2024-04-02_0.31.3.md) | `mac` | 2024-04-02 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.31.1](2024-04-02_0.31.1.md) | `mac` | 2024-04-02 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.31.0](2024-04-01_0.31.0.md) | `mac` | 2024-04-01 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.30.5](2024-03-27_0.30.5.md) | `mac` | 2024-03-27 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.30.4](2024-03-25_0.30.4.md) | `mac` | 2024-03-25 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.30.3](2024-03-22_0.30.3.md) | `mac` | 2024-03-22 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.30.2](2024-03-22_0.30.2.md) | `mac` | 2024-03-22 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.30.1](2024-03-21_0.30.1.md) | `mac` | 2024-03-21 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.30.0](2024-03-20_0.30.0.md) | `mac` | 2024-03-20 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.29.1](2024-03-02_0.29.1.md) | `mac` | 2024-03-02 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.29.0](2024-03-02_0.29.0.md) | `mac` | 2024-03-02 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.28.1](2024-02-26_0.28.1.md) | `mac` | 2024-02-26 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.28.0](2024-02-25_0.28.0.md) | `mac` | 2024-02-25 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.27.4](2024-02-21_0.27.4.md) | `mac` | 2024-02-21 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.27.3](2024-02-19_0.27.3.md) | `mac` | 2024-02-19 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.27.2](2024-02-16_0.27.2.md) | `mac` | 2024-02-16 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.27.1](2024-02-16_0.27.1.md) | `mac` | 2024-02-16 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.27.0](2024-02-15_0.27.0.md) | `mac` | 2024-02-15 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.26.2](2024-02-12_0.26.2.md) | `mac` | 2024-02-12 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.26.1](2024-02-11_0.26.1.md) | `mac` | 2024-02-11 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.26.0](2024-02-10_0.26.0.md) | `mac` | 2024-02-10 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.25.3](2024-02-07_0.25.3.md) | `mac` | 2024-02-07 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.25.2](2024-02-06_0.25.2.md) | `mac` | 2024-02-06 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.25.1](2024-02-04_0.25.1.md) | `mac` | 2024-02-04 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.25.0](2024-02-03_0.25.0.md) | `mac` | 2024-02-03 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.24.4](2024-01-30_0.24.4.md) | `mac` | 2024-01-30 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.24.3](2024-01-29_0.24.3.md) | `mac` | 2024-01-29 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.24.1](2024-01-27_0.24.1.md) | `mac` | 2024-01-27 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.24.0](2024-01-26_0.24.0.md) | `mac` | 2024-01-26 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.23.9](2024-01-24_0.23.9.md) | `mac` | 2024-01-24 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.23.8](2024-01-24_0.23.8.md) | `mac` | 2024-01-24 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.23.7](2024-01-23_0.23.7.md) | `mac` | 2024-01-23 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.23.6](2024-01-23_0.23.6.md) | `mac` | 2024-01-23 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.23.5](2024-01-22_0.23.5.md) | `mac` | 2024-01-22 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.23.4](2024-01-21_0.23.4.md) | `mac` | 2024-01-21 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.23.3](2024-01-21_0.23.3.md) | `mac` | 2024-01-21 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.23.2](2024-01-20_0.23.2.md) | `mac` | 2024-01-20 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.23.1](2024-01-19_0.23.1.md) | `mac` | 2024-01-19 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.22.2](2024-01-17_0.22.2.md) | `mac` | 2024-01-17 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.22.1](2024-01-09_0.22.1.md) | `mac` | 2024-01-09 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.22.0](2024-01-07_0.22.0.md) | `mac` | 2024-01-07 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.21.1](2023-12-30_0.21.1.md) | `mac` | 2023-12-30 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.21.0](2023-12-29_0.21.0.md) | `mac` | 2023-12-29 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.20.2](2023-12-19_0.20.2.md) | `mac` | 2023-12-19 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.20.1](2023-12-18_0.20.1.md) | `mac` | 2023-12-18 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.20.0](2023-12-17_0.20.0.md) | `mac` | 2023-12-17 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.19.1](2023-12-15_0.19.1.md) | `mac` | 2023-12-15 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.19.0](2023-12-14_0.19.0.md) | `mac` | 2023-12-14 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.18.8](2023-12-09_0.18.8.md) | `mac` | 2023-12-09 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.18.7](2023-12-09_0.18.7.md) | `mac` | 2023-12-09 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.18.6](2023-12-08_0.18.6.md) | `mac` | 2023-12-08 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.18.5](2023-12-06_0.18.5.md) | `mac` | 2023-12-06 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.18.4](2023-12-04_0.18.4.md) | `mac` | 2023-12-04 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.18.3](2023-12-03_0.18.3.md) | `mac` | 2023-12-03 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.18.1](2023-12-01_0.18.1.md) | `mac` | 2023-12-01 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.17.0](2023-11-28_0.17.0.md) | `mac` | 2023-11-28 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.16.0](2023-11-17_0.16.0.md) | `mac` | 2023-11-17 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.15.5](2023-11-15_0.15.5.md) | `mac` | 2023-11-15 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.15.4](2023-11-14_0.15.4.md) | `mac` | 2023-11-14 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.15.3](2023-11-14_0.15.3.md) | `mac` | 2023-11-14 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.15.2](2023-11-13_0.15.2.md) | `mac` | 2023-11-13 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.15.1](2023-11-11_0.15.1.md) | `mac` | 2023-11-11 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.15.0](2023-11-10_0.15.0.md) | `mac` | 2023-11-10 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.14.1](2023-11-10_0.14.1.md) | `mac` | 2023-11-10 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.14.0](2023-11-03_0.14.0.md) | `mac` | 2023-11-03 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.13.4](2023-10-29_0.13.4.md) | `mac` | 2023-10-29 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.13.3](2023-10-25_0.13.3.md) | `mac` | 2023-10-25 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.13.2](2023-10-24_0.13.2.md) | `mac` | 2023-10-24 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.13.1](2023-10-23_0.13.1.md) | `mac` | 2023-10-23 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.13.0](2023-10-22_0.13.0.md) | `mac` | 2023-10-22 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.12.3](2023-10-09_0.12.3.md) | `mac` | 2023-10-09 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.12.0](2023-10-02_0.12.0.md) | `mac` | 2023-10-02 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.11.8](2023-09-29_0.11.8.md) | `mac` | 2023-09-29 | `TODO` (`mac`) — _detailed diff pending_ |
| [1.1.3](2023-09-27_1.1.3.md) | `mac`, `win`, `ubuntu` | 2023-09-27 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [0.11.7](2023-09-26_0.11.7.md) | `mac` | 2023-09-26 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.11.6](2023-09-25_0.11.6.md) | `mac` | 2023-09-25 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.11.5](2023-09-22_0.11.5.md) | `mac` | 2023-09-22 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.11.4](2023-09-22_0.11.4.md) | `mac` | 2023-09-22 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.11.3](2023-09-21_0.11.3.md) | `mac` | 2023-09-21 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.11.2](2023-09-20_0.11.2.md) | `mac` | 2023-09-20 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.11.1](2023-09-20_0.11.1.md) | `mac` | 2023-09-20 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.11.0](2023-09-20_0.11.0.md) | `mac` | 2023-09-20 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.10.4](2023-09-10_0.10.4.md) | `mac` | 2023-09-10 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.10.3](2023-09-10_0.10.3.md) | `mac` | 2023-09-10 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.9.5](2023-09-08_0.9.5.md) | `mac` | 2023-09-08 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.9.3](2023-09-02_0.9.3.md) | `mac` | 2023-09-02 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.9.2](2023-09-01_0.9.2.md) | `mac` | 2023-09-01 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.9.1](2023-08-31_0.9.1.md) | `mac` | 2023-08-31 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.8.6](2023-08-29_0.8.6.md) | `mac` | 2023-08-29 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.8.5](2023-08-27_0.8.5.md) | `mac` | 2023-08-27 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.8.3](2023-08-24_0.8.3.md) | `mac` | 2023-08-24 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.7.3](2023-08-16_0.7.3.md) | `mac` | 2023-08-16 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.7.2](2023-08-11_0.7.2.md) | `mac` | 2023-08-11 | `TODO` (`mac`) — _detailed diff pending_ |

## Mobile Version Index (`ios`, Newest → Oldest)

| Version | Platforms | Release Date | Key Changes |
|---|---|---|---|
| [ios-1.17.0](2026-11-07_ios-1.17.0.md) | `ios` | 2026-11-07 | `TODO` (`ios`) — _detailed diff pending_ |
| [ios-1.16.0](2026-10-27_ios-1.16.0.md) | `ios` | 2026-10-27 | `TODO` (`ios`) — _detailed diff pending_ |
| [ios-1.15.0](2026-10-24_ios-1.15.0.md) | `ios` | 2026-10-24 | `TODO` (`ios`) — _detailed diff pending_ |
| [ios-1.14.0](2026-10-17_ios-1.14.0.md) | `ios` | 2026-10-17 | `TODO` (`ios`) — _detailed diff pending_ |
| [ios-1.13.0](2026-10-08_ios-1.13.0.md) | `ios` | 2026-10-08 | `TODO` (`ios`) — _detailed diff pending_ |
| [ios-1.12.0](2026-10-03_ios-1.12.0.md) | `ios` | 2026-10-03 | `TODO` (`ios`) — _detailed diff pending_ |
| [ios-1.10.0](2026-09-24_ios-1.10.0.md) | `ios` | 2026-09-24 | `TODO` (`ios`) — _detailed diff pending_ |
| [ios-1.9.0](2026-09-19_ios-1.9.0.md) | `ios` | 2026-09-19 | `TODO` (`ios`) — _detailed diff pending_ |
| [ios-1.8.0](2026-09-02_ios-1.8.0.md) | `ios` | 2026-09-02 | `TODO` (`ios`) — _detailed diff pending_ |
| [ios-1.7.0](2026-08-20_ios-1.7.0.md) | `ios` | 2026-08-20 | `TODO` (`ios`) — _detailed diff pending_ |
| [ios-1.6.1](2026-08-13_ios-1.6.1.md) | `ios` | 2026-08-13 | `TODO` (`ios`) — _detailed diff pending_ |
| [ios-1.6.0](2026-08-12_ios-1.6.0.md) | `ios` | 2026-08-12 | `TODO` (`ios`) — _detailed diff pending_ |
| [ios-1.5.0](2026-07-30_ios-1.5.0.md) | `ios` | 2026-07-30 | `TODO` (`ios`) — _detailed diff pending_ |
| [ios-1.4.0](2026-07-23_ios-1.4.0.md) | `ios` | 2026-07-23 | `TODO` (`ios`) — _detailed diff pending_ |
| [ios-1.3.1](2026-07-18_ios-1.3.1.md) | `ios` | 2026-07-18 | `TODO` (`ios`) — _detailed diff pending_ |
| [ios-1.3.0](2026-07-16_ios-1.3.0.md) | `ios` | 2026-07-16 | `TODO` (`ios`) — _detailed diff pending_ |
| [ios-1.2.1](2026-07-11_ios-1.2.1.md) | `ios` | 2026-07-11 | `TODO` (`ios`) — _detailed diff pending_ |
| [ios-1.2.0](2026-07-05_ios-1.2.0.md) | `ios` | 2026-07-05 | `TODO` (`ios`) — _detailed diff pending_ |
| [ios-1.1.0](2026-07-03_ios-1.1.0.md) | `ios` | 2026-07-03 | `TODO` (`ios`) — _detailed diff pending_ |
| [ios-1.0.0](2026-07-01_ios-1.0.0.md) | `ios` | 2026-07-01 | `TODO` (`ios`) — _detailed diff pending_ |
