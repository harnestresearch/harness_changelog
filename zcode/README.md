# ZCode Changelog History

English | [简体中文](../zh-CN/zcode/README.md) · **Highlight** | [Full Detail](../full/zcode/README.md)

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

| Version | Platforms | Release Date | Highlights |
|---|---|---|---|
| [3.18.2](2026-11-13_3.18.2.md) | `mac`, `win`, `ubuntu` | 2026-11-13 | Official release succeeding `3.17.2` (accumulating `3.18.0`/`3.18.1` preview changes): preserves OS keyring sign-in across data directory migration, adds Linux local private-key login fallback without Secret Service, unlocks standalone Start Plan for unlinked `zai_cn` accounts, and fixes Windows update checks |
| [3.18.1](2026-11-11_3.18.1.md) | `mac`, `win`, `ubuntu` | 2026-11-11 | Guided macOS microphone permission reset for voice input, macOS font smoothing toggle, narrower sidebar & browser element-picker polish, China web login & updater fixes, and sanitized memory diagnostics in exported logs |
| [3.18.0](2026-11-10_3.18.0.md) | `mac`, `win`, `ubuntu` | 2026-11-10 | Major feature release: composer voice input, parallel Git Worktree tasks, Extensions marketplace, built-in Design plugin & visual browser click-to-edit, multi-session orchestration, Share Management, and 3 new UI languages |
| [3.17.2](2026-11-02_3.17.2.md) | `mac`, `win`, `ubuntu` | 2026-11-02 | Targeted security & stability patch over `3.17.1`: actionable MCP startup failure advice, Plan-mode & custom-command script permission hardening, local web preview URL restrictions, session ownership validation, and macOS/Windows installer & window fixes |
| [3.17.1](2026-10-29_3.17.1.md) | `mac`, `win`, `ubuntu` | 2026-10-29 | Major upgrade to Electron 44 / Chromium 152, adding ZCode Sites one-click web deployment, image annotation editor, unified remote data sync & remote server controls, batch project/data cleanup, node-less MCP startup, workflow quota auto-resume, and 13 new provider templates |
| [3.16.3](2026-10-23_3.16.3.md) | `mac`, `win`, `ubuntu` | 2026-10-23 | Per-session isolated document state with shared plugin process, bounded plugin background retention, copyable device ID & manual login fallback link, and IME/remote/concurrency fixes |
| [3.16.2](2026-10-19_3.16.2.md) | `mac`, `win`, `ubuntu` | 2026-10-19 | Targeted follow-up patch over `3.16.1`: explicit remote Linux `glibc >= 2.28` compatibility check, antialiased Windows taskbar & HiDPI tray unread status dots, and plugin-install write-lock & workflow governor fixes |
| [3.16.1](2026-10-17_3.16.1.md) | `mac`, `win`, `ubuntu` | 2026-10-17 | Major feature update: unified Remote Devices (`SSH`/`WSL`/`Docker`) with persistent remote sessions, on-demand `ToolSearch`, sidebar Office/PDF viewer panels, multi-folder local projects, composer model/effort/plan switcher, popover sharing, plugin marketplace, and 18 bug/security fixes |
| [3.15.3](2026-10-13_3.15.3.md) | `mac`, `win`, `ubuntu` | 2026-10-13 | Second same-day `3.15.x` hotfix: resolves the auto-updater exit hang on `3.15.1`/`3.15.2`, stabilizes parallel Agent request signing across credential refreshes, and fixes repeated or slow-network onboarding prompts |
| [3.15.2](2026-10-13_3.15.2.md) | `mac`, `win`, `ubuntu` | 2026-10-13 | First same-day `3.15.x` hotfix: resolves Settings login & Coding/Team plan connection authentication failures and validates both ZCode JWT and OAuth access tokens on session restore |
| [3.15.1](2026-10-10_3.15.1.md) | `mac`, `win`, `ubuntu` | 2026-10-10 | UI Plugins (MCP Apps), Feishu group/topic collaboration, per-subagent workflow models & live concurrency tuning, safer Autonomous Mode confirmations, built-in browser site permissions, and Linux system tray residency |
| [3.14.5](2026-09-30_3.14.5.md) | `mac`, `win`, `ubuntu` | 2026-09-30 | Fixed remaining quota reset chances count disappearing after a manual quota reset |
| [3.14.4](2026-09-29_3.14.4.md) | `mac`, `win`, `ubuntu` | 2026-09-29 | Disabled CAPTCHA verification on free-tier model requests for smoother uninterrupted conversations |
| [3.14.3](2026-09-22_3.14.3.md) | `mac`, `win`, `ubuntu` | 2026-09-22 | Official `v3.14.3` release-promotion & GitHub open-source tag rebuild (~11h after `3.14.2`) with zero functional or UI changes over `3.14.2` |
| [3.14.2](2026-09-21_3.14.2.md) | `mac`, `win`, `ubuntu` | 2026-09-21 | Dynamic Workflow feature upgrade: live concurrency limit tuning without stopping tasks, on-demand workflow skill loading to cut context tokens, built-in `/workflow` & `bundled-skills`, and bounded real-time status for large workflows |
| [3.14.1](2026-09-20_3.14.1.md) | `mac`, `win`, `ubuntu` | 2026-09-20 | Fixes for Computer Control startup failures, draft/thinking text preservation when collapsing plans or inputs, plugin draft references, and onboarding repeat popups |
| [3.14.0](2026-09-19_3.14.0.md) | `mac`, `win`, `ubuntu` | 2026-09-19 | Dynamic `/workflow` multi-subagent scripting, Office vs. Coding mode switch, custom shortcut recording, role-based onboarding, standalone Start Plan, batch archive deletion, and Invitation Rewards Center |
| [3.12.3](2026-09-16_3.12.3.md) | `mac`, `win`, `ubuntu` | 2026-09-16 | Plan Mode + queued message improvements, OpenCode Go provider template & plan banner polish, database init/upgrade optimization, faster session startup, OpenRouter & streaming retry fixes, and Linux auto-update fix |
| [3.12.2](2026-09-16_3.12.2.md) | `mac`, `win`, `ubuntu` | 2026-09-16 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [3.12.1](2026-09-13_3.12.1.md) | `mac`, `win`, `ubuntu` | 2026-09-13 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [3.11.2](2026-09-04_3.11.2.md) | `mac`, `win`, `ubuntu` | 2026-09-04 | PDF upload/reading/preview and media previews in chat, per-workspace plugins with update prompts, middle-click sidebar tabs, clear blocked-action reasons, and remote/WSL/Linux resource fixes |
| [3.11.1](2026-09-04_3.11.1.md) | `mac`, `win`, `ubuntu` | 2026-09-04 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [3.10.2](2026-08-31_3.10.2.md) | `mac`, `win`, `ubuntu` | 2026-08-31 | Follow-up 3.10 maintenance build across `mac`, `win`, and `ubuntu` (upstream changelog repeated `3.10.1` release notes verbatim without separate delta items) |
| [3.10.1](2026-08-28_3.10.1.md) | `mac`, `win`, `ubuntu` | 2026-08-28 | Introduces Weekend Plan early claiming, searchable thinking traces, MCP protocol version configuration, immediate edited-message sending, composer skills shortcut, and end-of-turn execution summaries |
| [3.10.0](2026-08-27_3.10.0.md) | `mac`, `win`, `ubuntu` | 2026-08-27 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [3.9.2](2026-08-26_3.9.2.md) | `mac`, `win`, `ubuntu` | 2026-08-26 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [3.9.1](2026-08-23_3.9.1.md) | `mac`, `win`, `ubuntu` | 2026-08-23 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [3.8.1](2026-08-20_3.8.1.md) | `mac`, `win`, `ubuntu` | 2026-08-20 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [3.7.7](2026-08-14_3.7.7.md) | `mac`, `win`, `ubuntu` | 2026-08-14 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [3.7.6](2026-08-10_3.7.6.md) | `mac`, `win`, `ubuntu` | 2026-08-10 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [3.7.5](2026-08-10_3.7.5.md) | `mac`, `win`, `ubuntu` | 2026-08-10 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [3.7.3](2026-08-07_3.7.3.md) | `win`, `ubuntu` | 2026-08-07 | `TODO` (`win`, `ubuntu`) — _highlights pending_ |
| [3.6.5](2026-08-03_3.6.5.md) | `mac`, `win`, `ubuntu` | 2026-08-03 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [3.6.2](2026-07-29_3.6.2.md) | `win` | 2026-07-29 | `TODO` (`win`) — _highlights pending_ |
| [3.5.3](2026-07-27_3.5.3.md) | `mac`, `win`, `ubuntu` | 2026-07-27 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [3.5.2](2026-07-26_3.5.2.md) | `mac`, `win`, `ubuntu` | 2026-07-26 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [3.4.2](2026-07-22_3.4.2.md) | `mac`, `win`, `ubuntu` | 2026-07-22 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [3.4.0](2026-07-20_3.4.0.md) | `mac` | 2026-07-20 | `TODO` (`mac`) — _highlights pending_ |
| [3.3.6](2026-07-15_3.3.6.md) | `mac`, `win`, `ubuntu` | 2026-07-15 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [3.3.5](2026-07-13_3.3.5.md) | `mac`, `win`, `ubuntu` | 2026-07-13 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [3.3.4](2026-07-10_3.3.4.md) | `mac`, `win`, `ubuntu` | 2026-07-10 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [3.3.3](2026-07-08_3.3.3.md) | `mac`, `win`, `ubuntu` | 2026-07-08 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [3.3.2](2026-07-08_3.3.2.md) | `mac`, `win`, `ubuntu` | 2026-07-08 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [3.3.1](2026-07-08_3.3.1.md) | `mac`, `win` | 2026-07-08 | `TODO` (`mac`, `win`) — _highlights pending_ |
| [3.3.0](2026-07-07_3.3.0.md) | `mac`, `win`, `ubuntu` | 2026-07-07 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [3.2.5](2026-07-03_3.2.5.md) | `mac`, `win`, `ubuntu` | 2026-07-03 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [3.2.4](2026-07-03_3.2.4.md) | `win`, `ubuntu` | 2026-07-03 | `TODO` (`win`, `ubuntu`) — _highlights pending_ |
| [3.2.3](2026-07-02_3.2.3.md) | `win`, `ubuntu` | 2026-07-02 | `TODO` (`win`, `ubuntu`) — _highlights pending_ |
| [3.2.2](2026-07-01_3.2.2.md) | `win`, `ubuntu` | 2026-07-01 | `TODO` (`win`, `ubuntu`) — _highlights pending_ |
| [3.2.1](2026-06-30_3.2.1.md) | `win`, `ubuntu` | 2026-06-30 | `TODO` (`win`, `ubuntu`) — _highlights pending_ |
| [3.2.0](2026-06-29_3.2.0.md) | `win`, `ubuntu` | 2026-06-29 | `TODO` (`win`, `ubuntu`) — _highlights pending_ |
| [3.1.8](2026-06-26_3.1.8.md) | `win`, `ubuntu` | 2026-06-26 | `TODO` (`win`, `ubuntu`) — _highlights pending_ |
| [3.1.7](2026-06-26_3.1.7.md) | `win`, `ubuntu` | 2026-06-26 | `TODO` (`win`, `ubuntu`) — _highlights pending_ |
| [3.1.6](2026-06-25_3.1.6.md) | `win` | 2026-06-25 | `TODO` (`win`) — _highlights pending_ |
| [3.1.5](2026-06-24_3.1.5.md) | `win` | 2026-06-24 | `TODO` (`win`) — _highlights pending_ |
| [3.1.4](2026-06-23_3.1.4.md) | `win`, `ubuntu` | 2026-06-23 | `TODO` (`win`, `ubuntu`) — _highlights pending_ |
| [3.1.3](2026-06-23_3.1.3.md) | `win` | 2026-06-23 | `TODO` (`win`) — _highlights pending_ |
| [3.1.2](2026-06-17_3.1.2.md) | `win`, `ubuntu` | 2026-06-17 | `TODO` (`win`, `ubuntu`) — _highlights pending_ |
| [3.1.1](2026-06-16_3.1.1.md) | `win`, `ubuntu` | 2026-06-16 | `TODO` (`win`, `ubuntu`) — _highlights pending_ |
| [3.1.0](2026-06-15_3.1.0.md) | `win` | 2026-06-15 | `TODO` (`win`) — _highlights pending_ |
| [3.0.1](2026-06-14_3.0.1.md) | `win` | 2026-06-14 | `TODO` (`win`) — _highlights pending_ |
| [3.0.0](2026-06-13_3.0.0.md) | `win` | 2026-06-13 | `TODO` (`win`) — _highlights pending_ |
| [2.13.0](2026-05-29_2.13.0.md) | `win`, `ubuntu` | 2026-05-29 | `TODO` (`win`, `ubuntu`) — _highlights pending_ |
| [2.12.0](2026-05-28_2.12.0.md) | `win` | 2026-05-28 | `TODO` (`win`) — _highlights pending_ |
| [2.11.0](2026-05-27_2.11.0.md) | `win` | 2026-05-27 | `TODO` (`win`) — _highlights pending_ |
| [2.10.0](2026-05-26_2.10.0.md) | `win` | 2026-05-26 | `TODO` (`win`) — _highlights pending_ |
| [2.9.0](2026-05-25_2.9.0.md) | `win` | 2026-05-25 | `TODO` (`win`) — _highlights pending_ |
| [2.8.0](2026-05-22_2.8.0.md) | `win` | 2026-05-22 | `TODO` (`win`) — _highlights pending_ |
| [2.7.0](2026-05-21_2.7.0.md) | `win` | 2026-05-21 | `TODO` (`win`) — _highlights pending_ |
| [2.6.0](2026-05-20_2.6.0.md) | `win` | 2026-05-20 | `TODO` (`win`) — _highlights pending_ |
| [2.5.0](2026-05-19_2.5.0.md) | `win` | 2026-05-19 | `TODO` (`win`) — _highlights pending_ |
| [2.4.1](2026-05-19_2.4.1.md) | `win` | 2026-05-19 | `TODO` (`win`) — _highlights pending_ |
| [2.4.0](2026-05-18_2.4.0.md) | `win` | 2026-05-18 | `TODO` (`win`) — _highlights pending_ |
| [2.3.1](2026-05-17_2.3.1.md) | `win` | 2026-05-17 | `TODO` (`win`) — _highlights pending_ |
| [2.3.0](2026-05-16_2.3.0.md) | `win` | 2026-05-16 | `TODO` (`win`) — _highlights pending_ |
| [2.2.0](2026-05-14_2.2.0.md) | `win` | 2026-05-14 | `TODO` (`win`) — _highlights pending_ |
| [2.1.1](2026-05-13_2.1.1.md) | `win` | 2026-05-13 | `TODO` (`win`) — _highlights pending_ |
| [2.1.0](2026-05-12_2.1.0.md) | `win` | 2026-05-12 | `TODO` (`win`) — _highlights pending_ |
| [2.0.0](2026-05-11_2.0.0.md) | `win` | 2026-05-11 | `TODO` (`win`) — _highlights pending_ |
| [1.11.0](2026-05-09_1.11.0.md) | `win` | 2026-05-09 | `TODO` (`win`) — _highlights pending_ |
| [1.10.0](2026-05-08_1.10.0.md) | `win` | 2026-05-08 | `TODO` (`win`) — _highlights pending_ |
| [1.9.0](2026-05-07_1.9.0.md) | `win` | 2026-05-07 | `TODO` (`win`) — _highlights pending_ |
| [1.8.0](2026-05-01_1.8.0.md) | `win` | 2026-05-01 | `TODO` (`win`) — _highlights pending_ |
| [1.7.0](2026-04-29_1.7.0.md) | `win` | 2026-04-29 | `TODO` (`win`) — _highlights pending_ |
| [1.6.1](2026-04-28_1.6.1.md) | `win` | 2026-04-28 | `TODO` (`win`) — _highlights pending_ |
| [1.6.0](2026-04-28_1.6.0.md) | `win` | 2026-04-28 | `TODO` (`win`) — _highlights pending_ |
| [1.5.0](2026-04-27_1.5.0.md) | `win` | 2026-04-27 | `TODO` (`win`) — _highlights pending_ |
| [1.4.0](2026-04-25_1.4.0.md) | `win` | 2026-04-25 | `TODO` (`win`) — _highlights pending_ |
| [1.3.0](2026-04-23_1.3.0.md) | `win` | 2026-04-23 | `TODO` (`win`) — _highlights pending_ |
| [1.2.1](2026-04-22_1.2.1.md) | `win` | 2026-04-22 | `TODO` (`win`) — _highlights pending_ |
| [1.2.0](2026-04-22_1.2.0.md) | `win` | 2026-04-22 | `TODO` (`win`) — _highlights pending_ |
| [1.1.1](2026-04-22_1.1.1.md) | `win` | 2026-04-22 | `TODO` (`win`) — _highlights pending_ |
| [1.0.0](2026-04-21_1.0.0.md) | `win` | 2026-04-21 | `TODO` (`win`) — _highlights pending_ |
| [0.28.1](2026-04-16_0.28.1.md) | `mac`, `win` | 2026-04-16 | `TODO` (`mac`, `win`) — _highlights pending_ |
| [0.28.0](2026-04-15_0.28.0.md) | `mac`, `win` | 2026-04-15 | `TODO` (`mac`, `win`) — _highlights pending_ |
| [0.27.2](2026-04-13_0.27.2.md) | `mac`, `win` | 2026-04-13 | `TODO` (`mac`, `win`) — _highlights pending_ |
| [0.27.1](2026-04-10_0.27.1.md) | `mac`, `win` | 2026-04-10 | `TODO` (`mac`, `win`) — _highlights pending_ |
| [0.25.1](2026-03-31_0.25.1.md) | `mac`, `win` | 2026-03-31 | `TODO` (`mac`, `win`) — _highlights pending_ |
| [0.25.0](2026-03-27_0.25.0.md) | `mac`, `win` | 2026-03-27 | `TODO` (`mac`, `win`) — _highlights pending_ |
| [0.24.4](2026-03-26_0.24.4.md) | `mac`, `win` | 2026-03-26 | `TODO` (`mac`, `win`) — _highlights pending_ |
| [0.24.3](2026-03-25_0.24.3.md) | `mac`, `win` | 2026-03-25 | `TODO` (`mac`, `win`) — _highlights pending_ |
| [0.24.1](2026-03-23_0.24.1.md) | `mac`, `win` | 2026-03-23 | `TODO` (`mac`, `win`) — _highlights pending_ |
| [0.24.0](2026-03-20_0.24.0.md) | `mac`, `win` | 2026-03-20 | `TODO` (`mac`, `win`) — _highlights pending_ |
| [0.23.1](2026-03-18_0.23.1.md) | `mac`, `win` | 2026-03-18 | `TODO` (`mac`, `win`) — _highlights pending_ |
| [0.22.1](2026-03-14_0.22.1.md) | `mac`, `win` | 2026-03-14 | `TODO` (`mac`, `win`) — _highlights pending_ |
| [0.21.1](2026-03-10_0.21.1.md) | `mac`, `win` | 2026-03-10 | `TODO` (`mac`, `win`) — _highlights pending_ |
| [0.21.0](2026-03-06_0.21.0.md) | `mac`, `win` | 2026-03-06 | `TODO` (`mac`, `win`) — _highlights pending_ |
| [0.20.5](2026-03-03_0.20.5.md) | `mac`, `win` | 2026-03-03 | `TODO` (`mac`, `win`) — _highlights pending_ |
| [0.20.4](2026-02-13_0.20.4.md) | `mac`, `win` | 2026-02-13 | `TODO` (`mac`, `win`) — _highlights pending_ |
| [0.20.2](2026-02-12_0.20.2.md) | `mac`, `win` | 2026-02-12 | `TODO` (`mac`, `win`) — _highlights pending_ |
| [0.20.1](2026-02-11_0.20.1.md) | `mac`, `win` | 2026-02-11 | `TODO` (`mac`, `win`) — _highlights pending_ |
| [0.15.1](2026-01-26_0.15.1.md) | `mac`, `win` | 2026-01-26 | `TODO` (`mac`, `win`) — _highlights pending_ |
| [0.14.2](2026-01-16_0.14.2.md) | `mac`, `win` | 2026-01-16 | `TODO` (`mac`, `win`) — _highlights pending_ |
| [0.13.3](2026-01-12_0.13.3.md) | `mac`, `win` | 2026-01-12 | `TODO` (`mac`, `win`) — _highlights pending_ |
| [0.12.2](2026-01-04_0.12.2.md) | `mac`, `win` | 2026-01-04 | `TODO` (`mac`, `win`) — _highlights pending_ |
| [0.12.1](2025-12-31_0.12.1.md) | `mac`, `win` | 2025-12-31 | `TODO` (`mac`, `win`) — _highlights pending_ |
| [0.11.1](2025-12-29_0.11.1.md) | `mac`, `win` | 2025-12-29 | `TODO` (`mac`, `win`) — _highlights pending_ |
| [0.10.0](2025-12-29_0.10.0.md) | `mac` | 2025-12-29 | `TODO` (`mac`) — _highlights pending_ |
| [0.9.1](2025-12-25_0.9.1.md) | `mac`, `win` | 2025-12-25 | `TODO` (`mac`, `win`) — _highlights pending_ |
| [0.8.0](2025-12-23_0.8.0.md) | `mac`, `win` | 2025-12-23 | `TODO` (`mac`, `win`) — _highlights pending_ |
| [0.2.0](2025-12-01_0.2.0.md) | `mac`, `win` | 2025-12-01 | `TODO` (`mac`, `win`) — _highlights pending_ |
| [0.1.8](2025-11-28_0.1.8.md) | `mac`, `win` | 2025-11-28 | `TODO` (`mac`, `win`) — _highlights pending_ |
| [0.1.7](2025-11-27_0.1.7.md) | `mac`, `win` | 2025-11-27 | `TODO` (`mac`, `win`) — _highlights pending_ |
