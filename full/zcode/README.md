# ZCode Changelog History

English | [简体中文](../../zh-CN/full/zcode/README.md) · [Highlight](../../zcode/README.md) | **Full Detail**

Complete multi-platform version history covering all **123** unified releases of ZCode from `0.1.7` (2025-11-27) to `3.18.2` (2026-11-13) across `mac`, `win`, `ubuntu`, `ios`, and `android`.

## Five-Platform Coverage Overview

| Platform | Distribution / Package | Tracked Releases | Version Range | Latest Version |
|---|---|---|---|---|
| `mac` | macOS (`z-code` / `ZCode.app` CDN & Homebrew Cask) | 74 | `0.1.7` → `3.18.2` | [3.18.2](2026-11-13_3.18.2.md) |
| `win` | Windows (`ZhipuAI.ZCode` Winget & CDN) | 121 | `0.1.7` → `3.18.2` | [3.18.2](2026-11-13_3.18.2.md) |
| `ubuntu` | Ubuntu / Linux (`ZCode` `.deb` & AppImage CDN / AUR) | 54 | `2.13.0` → `3.18.2` | [3.18.2](2026-11-13_3.18.2.md) |
| `ios` | Standalone ZCode iOS Client | 0 | _No standalone iOS release yet_ | — |
| `android` | Standalone ZCode Android Client | 0 | _No standalone Android release yet_ | — |

## Desktop Version Index (`mac` / `win` / `ubuntu`, Newest → Oldest)

| Version | Platforms | Release Date | Key Changes |
|---|---|---|---|
| [3.18.2](2026-11-13_3.18.2.md) | `mac`, `win`, `ubuntu` | 2026-11-13 | Official release succeeding `3.17.2` (binary diff vs preview `3.18.1`): `credential-key-share` IPC for migrated data directories, main-process-wired Linux `0600` private-file key fallback (`enablePrivateFileKeyFallback`), decoupled Start Plan material + `zai_cn` → `bigmodel` mapping, and Windows updater fix |
| [3.18.1](2026-11-11_3.18.1.md) | `mac`, `win`, `ubuntu` | 2026-11-11 | macOS `tccutil` microphone permission reset IPC & multi-phase guide popover, macOS font smoothing toggle, bounded CLI V8 heap diagnostic snapshots, and fixes for China web login, browser picker view jumps, and leftover updater processes |
| [3.18.0](2026-11-10_3.18.0.md) | `mac`, `win`, `ubuntu` | 2026-11-10 | Voice input, managed Worktrees, MCP Extensions host, Design plugin & browser click-to-edit, 12 multi-session control tools, OS keyring storage, and Japanese/Korean/Russian locales |
| [3.17.2](2026-11-02_3.17.2.md) | `mac`, `win`, `ubuntu` | 2026-11-02 | MCP `failureAdvice` (`+21` i18n keys), `zcode:browser-view-load-url` local preview URL allowlist, `handOffCustomCommandShellBlocks` `Bash` approval & subtask Plan-mode reminders, `validateSessionActivationWorkspace`, and platform fixes |
| [3.17.1](2026-10-29_3.17.1.md) | `mac`, `win`, `ubuntu` | 2026-10-29 | Electron `44.7.0` / Chromium `152` upgrade, `zcode-site` (`v0.4.2`), `sharp` image editor, `remoteSync.*` & remote server control IPC, `projectManagement.*`, bundled `npm 12.2.0` MCP fallback, `CronPauseSelf`, `ProviderBuiltinToolStreamRewriter`, and `+13` provider templates |
| [3.16.3](2026-10-23_3.16.3.md) | `mac`, `win`, `ubuntu` | 2026-10-23 | Independent per-session document viewer state over a shared document plugin process, capped plugin background retention, self-healing built-in component rebuilds, and multi-session concurrent write & remote latency fixes |
| [3.16.2](2026-10-19_3.16.2.md) | `mac`, `win`, `ubuntu` | 2026-10-19 | Host `assertSupportedGlibc` (`glibc >= 2.28` check), main-process antialiased taskbar/tray status-dot compositing (`composeTrayBadgeRepresentation`), and CLI `withWriteLock` / `readDynamicWorkflowOfferedMode` / `isWorkflowStopFailure` |
| [3.16.1](2026-10-17_3.16.1.md) | `mac`, `win`, `ubuntu` | 2026-10-17 | `source-server` Remote Devices & 6 migration ledger tables, `ToolSearch` (`--toolsearch-mode` / `DeferredToolCall`), Office/PDF MCP viewer surfaces (`+325` files), multi-folder `additionalDirectories`, `xiaomi-mimo-token-plan` (`1M` default context rule), and 18 fixes |
| [3.15.3](2026-10-13_3.15.3.md) | `mac`, `win`, `ubuntu` | 2026-10-13 | Main-process auto-updater install admission state machine & `recoverFromFailedUpdateInstall` relaunch, CLI `ClientRequestSigningV4Manager` lazy `scopes` & `disposed` guard, plus onboarding fixes |
| [3.15.2](2026-10-13_3.15.2.md) | `mac`, `win`, `ubuntu` | 2026-10-13 | Host OAuth business prefix expansion (`/api/biz/` & `/api/pay/`), active bare-token `getCustomerInfo` validation (`confirmBusinessCredentialInvalid`), `project-token` `Bearer` header fix, and dual-key cached session expiry check |
| [3.15.1](2026-10-10_3.15.1.md) | `mac`, `win`, `ubuntu` | 2026-10-10 | MCP App UI plugins, interactive message-stream UI, Feishu group/topic integration, per-subagent workflow model routing & runtime concurrency control, browser site permission prompts, Linux tray close behavior, and Windows URI launch hardening |
| [3.14.5](2026-09-30_3.14.5.md) | `mac`, `win`, `ubuntu` | 2026-09-30 | UI state fix preserving the displayed count of remaining manual quota reset chances after redemption |
| [3.14.4](2026-09-29_3.14.4.md) | `mac`, `win`, `ubuntu` | 2026-09-29 | Removed model-request CAPTCHA verification gate on the free plan tier |
| [3.14.3](2026-09-22_3.14.3.md) | `mac`, `win`, `ubuntu` | 2026-09-22 | Pure release-tag packaging rebuild (`3.14.2-7756 → 3.14.3-7762`, commit `ab4d5e6b` / GitHub `29628c9a`): byte-identical `glm/zcode.cjs`, identical `326,913,762` B `app.asar` size, and zero string/i18n changes over `3.14.2` |
| [3.14.2](2026-09-21_3.14.2.md) | `mac`, `win`, `ubuntu` | 2026-09-21 | In-place `AmendWorkflow` concurrency retuning (`createWorkflowRunSeatGate` / `run-caps-changed`), `428` `requireDynamicWorkflowSkill` context diet, non-uninstallable `bundled-skills` & `/workflow` synthesis, and bounded run-table truncation |
| [3.14.1](2026-09-20_3.14.1.md) | `mac`, `win`, `ubuntu` | 2026-09-20 | Patch release fixing Computer Control startup, composer draft/thinking retention on collapse, plugin draft reference insertion, unnamed provider identity retention, and onboarding persistence |
| [3.14.0](2026-09-19_3.14.0.md) | `mac`, `win`, `ubuntu` | 2026-09-19 | First open-source-synced release (`zai-org/ZCode`): script-driven multi-subagent `/workflow` engine, Office/Coding dual modes, live keybinding recorder, standalone Start Plan, CUA invocation refinements, and 14 bug fixes |
| [3.12.3](2026-09-16_3.12.3.md) | `mac`, `win`, `ubuntu` | 2026-09-16 | Plan Mode + message queue coordination, OpenCode Go provider template & site mapping, DB initialization/upgrade optimization, provider config non-blocking reads, OpenRouter connection testing, and Linux auto-update fix |
| [3.12.2](2026-09-16_3.12.2.md) | `mac`, `win`, `ubuntu` | 2026-09-16 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.12.1](2026-09-13_3.12.1.md) | `mac`, `win`, `ubuntu` | 2026-09-13 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.11.2](2026-09-04_3.11.2.md) | `mac`, `win`, `ubuntu` | 2026-09-04 | In-chat PDF & media preview pipeline, workspace-scoped plugin management, independent per-task browser windows, command output truncation for UI responsiveness, and Linux/WSL/SSH stability fixes |
| [3.11.1](2026-09-04_3.11.1.md) | `mac`, `win`, `ubuntu` | 2026-09-04 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.10.2](2026-08-31_3.10.2.md) | `mac`, `win`, `ubuntu` | 2026-08-31 | Follow-up 3.10 maintenance build (`235,495,948` B `mac-arm64` / `140,633,020` B `linux-arm64`); upstream `zcode.z.ai/changelog` repeated `3.10.1` notes verbatim |
| [3.10.1](2026-08-28_3.10.1.md) | `mac`, `win`, `ubuntu` | 2026-08-28 | Initial 3.10 feature rollout: searchable thinking traces, configurable MCP protocol versions, immediate edited-message dispatch, turn duration summaries, template plugin one-click install, and MCP OAuth / Computer Use fixes |
| [3.10.0](2026-08-27_3.10.0.md) | `mac`, `win`, `ubuntu` | 2026-08-27 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.9.2](2026-08-26_3.9.2.md) | `mac`, `win`, `ubuntu` | 2026-08-26 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.9.1](2026-08-23_3.9.1.md) | `mac`, `win`, `ubuntu` | 2026-08-23 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.8.1](2026-08-20_3.8.1.md) | `mac`, `win`, `ubuntu` | 2026-08-20 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.7.7](2026-08-14_3.7.7.md) | `mac`, `win`, `ubuntu` | 2026-08-14 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.7.6](2026-08-10_3.7.6.md) | `mac`, `win`, `ubuntu` | 2026-08-10 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.7.5](2026-08-10_3.7.5.md) | `mac`, `win`, `ubuntu` | 2026-08-10 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.7.3](2026-08-07_3.7.3.md) | `win`, `ubuntu` | 2026-08-07 | `TODO` (`win`, `ubuntu`) — _detailed diff pending_ |
| [3.6.5](2026-08-03_3.6.5.md) | `mac`, `win`, `ubuntu` | 2026-08-03 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.6.2](2026-07-29_3.6.2.md) | `win` | 2026-07-29 | `TODO` (`win`) — _detailed diff pending_ |
| [3.5.3](2026-07-27_3.5.3.md) | `mac`, `win`, `ubuntu` | 2026-07-27 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.5.2](2026-07-26_3.5.2.md) | `mac`, `win`, `ubuntu` | 2026-07-26 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.4.2](2026-07-22_3.4.2.md) | `mac`, `win`, `ubuntu` | 2026-07-22 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.4.0](2026-07-20_3.4.0.md) | `mac` | 2026-07-20 | `TODO` (`mac`) — _detailed diff pending_ |
| [3.3.6](2026-07-15_3.3.6.md) | `mac`, `win`, `ubuntu` | 2026-07-15 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.3.5](2026-07-13_3.3.5.md) | `mac`, `win`, `ubuntu` | 2026-07-13 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.3.4](2026-07-10_3.3.4.md) | `mac`, `win`, `ubuntu` | 2026-07-10 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.3.3](2026-07-08_3.3.3.md) | `mac`, `win`, `ubuntu` | 2026-07-08 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.3.2](2026-07-08_3.3.2.md) | `mac`, `win`, `ubuntu` | 2026-07-08 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.3.1](2026-07-08_3.3.1.md) | `mac`, `win` | 2026-07-08 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [3.3.0](2026-07-07_3.3.0.md) | `mac`, `win`, `ubuntu` | 2026-07-07 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.2.5](2026-07-03_3.2.5.md) | `mac`, `win`, `ubuntu` | 2026-07-03 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [3.2.4](2026-07-03_3.2.4.md) | `win`, `ubuntu` | 2026-07-03 | `TODO` (`win`, `ubuntu`) — _detailed diff pending_ |
| [3.2.3](2026-07-02_3.2.3.md) | `win`, `ubuntu` | 2026-07-02 | `TODO` (`win`, `ubuntu`) — _detailed diff pending_ |
| [3.2.2](2026-07-01_3.2.2.md) | `win`, `ubuntu` | 2026-07-01 | `TODO` (`win`, `ubuntu`) — _detailed diff pending_ |
| [3.2.1](2026-06-30_3.2.1.md) | `win`, `ubuntu` | 2026-06-30 | `TODO` (`win`, `ubuntu`) — _detailed diff pending_ |
| [3.2.0](2026-06-29_3.2.0.md) | `win`, `ubuntu` | 2026-06-29 | `TODO` (`win`, `ubuntu`) — _detailed diff pending_ |
| [3.1.8](2026-06-26_3.1.8.md) | `win`, `ubuntu` | 2026-06-26 | `TODO` (`win`, `ubuntu`) — _detailed diff pending_ |
| [3.1.7](2026-06-26_3.1.7.md) | `win`, `ubuntu` | 2026-06-26 | `TODO` (`win`, `ubuntu`) — _detailed diff pending_ |
| [3.1.6](2026-06-25_3.1.6.md) | `win` | 2026-06-25 | `TODO` (`win`) — _detailed diff pending_ |
| [3.1.5](2026-06-24_3.1.5.md) | `win` | 2026-06-24 | `TODO` (`win`) — _detailed diff pending_ |
| [3.1.4](2026-06-23_3.1.4.md) | `win`, `ubuntu` | 2026-06-23 | `TODO` (`win`, `ubuntu`) — _detailed diff pending_ |
| [3.1.3](2026-06-23_3.1.3.md) | `win` | 2026-06-23 | `TODO` (`win`) — _detailed diff pending_ |
| [3.1.2](2026-06-17_3.1.2.md) | `win`, `ubuntu` | 2026-06-17 | `TODO` (`win`, `ubuntu`) — _detailed diff pending_ |
| [3.1.1](2026-06-16_3.1.1.md) | `win`, `ubuntu` | 2026-06-16 | `TODO` (`win`, `ubuntu`) — _detailed diff pending_ |
| [3.1.0](2026-06-15_3.1.0.md) | `win` | 2026-06-15 | `TODO` (`win`) — _detailed diff pending_ |
| [3.0.1](2026-06-14_3.0.1.md) | `win` | 2026-06-14 | `TODO` (`win`) — _detailed diff pending_ |
| [3.0.0](2026-06-13_3.0.0.md) | `win` | 2026-06-13 | `TODO` (`win`) — _detailed diff pending_ |
| [2.13.0](2026-05-29_2.13.0.md) | `win`, `ubuntu` | 2026-05-29 | `TODO` (`win`, `ubuntu`) — _detailed diff pending_ |
| [2.12.0](2026-05-28_2.12.0.md) | `win` | 2026-05-28 | `TODO` (`win`) — _detailed diff pending_ |
| [2.11.0](2026-05-27_2.11.0.md) | `win` | 2026-05-27 | `TODO` (`win`) — _detailed diff pending_ |
| [2.10.0](2026-05-26_2.10.0.md) | `win` | 2026-05-26 | `TODO` (`win`) — _detailed diff pending_ |
| [2.9.0](2026-05-25_2.9.0.md) | `win` | 2026-05-25 | `TODO` (`win`) — _detailed diff pending_ |
| [2.8.0](2026-05-22_2.8.0.md) | `win` | 2026-05-22 | `TODO` (`win`) — _detailed diff pending_ |
| [2.7.0](2026-05-21_2.7.0.md) | `win` | 2026-05-21 | `TODO` (`win`) — _detailed diff pending_ |
| [2.6.0](2026-05-20_2.6.0.md) | `win` | 2026-05-20 | `TODO` (`win`) — _detailed diff pending_ |
| [2.5.0](2026-05-19_2.5.0.md) | `win` | 2026-05-19 | `TODO` (`win`) — _detailed diff pending_ |
| [2.4.1](2026-05-19_2.4.1.md) | `win` | 2026-05-19 | `TODO` (`win`) — _detailed diff pending_ |
| [2.4.0](2026-05-18_2.4.0.md) | `win` | 2026-05-18 | `TODO` (`win`) — _detailed diff pending_ |
| [2.3.1](2026-05-17_2.3.1.md) | `win` | 2026-05-17 | `TODO` (`win`) — _detailed diff pending_ |
| [2.3.0](2026-05-16_2.3.0.md) | `win` | 2026-05-16 | `TODO` (`win`) — _detailed diff pending_ |
| [2.2.0](2026-05-14_2.2.0.md) | `win` | 2026-05-14 | `TODO` (`win`) — _detailed diff pending_ |
| [2.1.1](2026-05-13_2.1.1.md) | `win` | 2026-05-13 | `TODO` (`win`) — _detailed diff pending_ |
| [2.1.0](2026-05-12_2.1.0.md) | `win` | 2026-05-12 | `TODO` (`win`) — _detailed diff pending_ |
| [2.0.0](2026-05-11_2.0.0.md) | `win` | 2026-05-11 | `TODO` (`win`) — _detailed diff pending_ |
| [1.11.0](2026-05-09_1.11.0.md) | `win` | 2026-05-09 | `TODO` (`win`) — _detailed diff pending_ |
| [1.10.0](2026-05-08_1.10.0.md) | `win` | 2026-05-08 | `TODO` (`win`) — _detailed diff pending_ |
| [1.9.0](2026-05-07_1.9.0.md) | `win` | 2026-05-07 | `TODO` (`win`) — _detailed diff pending_ |
| [1.8.0](2026-05-01_1.8.0.md) | `win` | 2026-05-01 | `TODO` (`win`) — _detailed diff pending_ |
| [1.7.0](2026-04-29_1.7.0.md) | `win` | 2026-04-29 | `TODO` (`win`) — _detailed diff pending_ |
| [1.6.1](2026-04-28_1.6.1.md) | `win` | 2026-04-28 | `TODO` (`win`) — _detailed diff pending_ |
| [1.6.0](2026-04-28_1.6.0.md) | `win` | 2026-04-28 | `TODO` (`win`) — _detailed diff pending_ |
| [1.5.0](2026-04-27_1.5.0.md) | `win` | 2026-04-27 | `TODO` (`win`) — _detailed diff pending_ |
| [1.4.0](2026-04-25_1.4.0.md) | `win` | 2026-04-25 | `TODO` (`win`) — _detailed diff pending_ |
| [1.3.0](2026-04-23_1.3.0.md) | `win` | 2026-04-23 | `TODO` (`win`) — _detailed diff pending_ |
| [1.2.1](2026-04-22_1.2.1.md) | `win` | 2026-04-22 | `TODO` (`win`) — _detailed diff pending_ |
| [1.2.0](2026-04-22_1.2.0.md) | `win` | 2026-04-22 | `TODO` (`win`) — _detailed diff pending_ |
| [1.1.1](2026-04-22_1.1.1.md) | `win` | 2026-04-22 | `TODO` (`win`) — _detailed diff pending_ |
| [1.0.0](2026-04-21_1.0.0.md) | `win` | 2026-04-21 | `TODO` (`win`) — _detailed diff pending_ |
| [0.28.1](2026-04-16_0.28.1.md) | `mac`, `win` | 2026-04-16 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.28.0](2026-04-15_0.28.0.md) | `mac`, `win` | 2026-04-15 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.27.2](2026-04-13_0.27.2.md) | `mac`, `win` | 2026-04-13 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.27.1](2026-04-10_0.27.1.md) | `mac`, `win` | 2026-04-10 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.25.1](2026-03-31_0.25.1.md) | `mac`, `win` | 2026-03-31 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.25.0](2026-03-27_0.25.0.md) | `mac`, `win` | 2026-03-27 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.24.4](2026-03-26_0.24.4.md) | `mac`, `win` | 2026-03-26 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.24.3](2026-03-25_0.24.3.md) | `mac`, `win` | 2026-03-25 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.24.1](2026-03-23_0.24.1.md) | `mac`, `win` | 2026-03-23 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.24.0](2026-03-20_0.24.0.md) | `mac`, `win` | 2026-03-20 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.23.1](2026-03-18_0.23.1.md) | `mac`, `win` | 2026-03-18 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.22.1](2026-03-14_0.22.1.md) | `mac`, `win` | 2026-03-14 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.21.1](2026-03-10_0.21.1.md) | `mac`, `win` | 2026-03-10 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.21.0](2026-03-06_0.21.0.md) | `mac`, `win` | 2026-03-06 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.20.5](2026-03-03_0.20.5.md) | `mac`, `win` | 2026-03-03 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.20.4](2026-02-13_0.20.4.md) | `mac`, `win` | 2026-02-13 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.20.2](2026-02-12_0.20.2.md) | `mac`, `win` | 2026-02-12 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.20.1](2026-02-11_0.20.1.md) | `mac`, `win` | 2026-02-11 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.15.1](2026-01-26_0.15.1.md) | `mac`, `win` | 2026-01-26 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.14.2](2026-01-16_0.14.2.md) | `mac`, `win` | 2026-01-16 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.13.3](2026-01-12_0.13.3.md) | `mac`, `win` | 2026-01-12 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.12.2](2026-01-04_0.12.2.md) | `mac`, `win` | 2026-01-04 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.12.1](2025-12-31_0.12.1.md) | `mac`, `win` | 2025-12-31 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.11.1](2025-12-29_0.11.1.md) | `mac`, `win` | 2025-12-29 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.10.0](2025-12-29_0.10.0.md) | `mac` | 2025-12-29 | `TODO` (`mac`) — _detailed diff pending_ |
| [0.9.1](2025-12-25_0.9.1.md) | `mac`, `win` | 2025-12-25 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.8.0](2025-12-23_0.8.0.md) | `mac`, `win` | 2025-12-23 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.2.0](2025-12-01_0.2.0.md) | `mac`, `win` | 2025-12-01 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.1.8](2025-11-28_0.1.8.md) | `mac`, `win` | 2025-11-28 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
| [0.1.7](2025-11-27_0.1.7.md) | `mac`, `win` | 2025-11-27 | `TODO` (`mac`, `win`) — _detailed diff pending_ |
