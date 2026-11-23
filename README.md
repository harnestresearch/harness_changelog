# Harness Changelog

English | [简体中文](zh-CN/README.md) · **Highlight** | [Full Detail](full/README.md)

Curated multi-platform (`mac`, `win`, `ubuntu`, `ios`, `android`) version changelogs across major AI agent harnesses and desktop/mobile clients.

> **Two Reading Modes**:
> - **Highlight (Default — `/` & `zh-CN/`)**: Concise, user-perceivable release highlights focusing on product features, UI/UX improvements, integrations, and fixes.
> - **[Full Detail](full/README.md) (`full/` & `zh-CN/full/`)**: Deep technical changelogs covering runtime/engine upgrades, IPC/RPC & MCP protocol diffs, named bundle changes, environment flags, and dependency diffs.

## Latest Releases Overview

| Harness | Latest Version | Release Date | Latest Highlights | Full Version History (Highlight) | Full Technical Detail |
|---|---|---|---|---|---|
| **Antigravity** | `2.32.2` (Hub) / `2.7.0` (IDE) | 2026-11-17 (Last-Modified) / Unconfirmed | [antigravity.md](antigravity.md) | [antigravity/](antigravity/README.md) (5 releases) | [full/antigravity/](full/antigravity/README.md) |
| **Claude** | `5.11492.5` / `1.261113.19` (`android`) / `1.261109.19` (`ios`) | 2026-11-14 | [claude.md](claude.md) | [claude/](claude/README.md) (533 releases) | [full/claude/](full/claude/README.md) |
| **ChatGPT / Codex** | `26.1111.2228.0` (`win`) / `26.1111.21308` (`mac`, `ubuntu`) / `1.2026.314` (`android`) / `1.2026.307` (`ios`) | 2026-11-16 (APKPure) | [codex.md](codex.md) | [codex/](codex/README.md) (418 unified releases) | [full/codex/](full/codex/README.md) |
| **Cursor** | `3.30.14` / `1.17.0` (`ios`) | 2026-11-14 | [cursor.md](cursor.md) | [cursor/](cursor/README.md) (446 releases) | [full/cursor/](full/cursor/README.md) |
| **DSH (DeepSeek Harness)** | `0.2.3-alpha.2` (prerelease) | 2026-11-22 | [dsh.md](dsh.md) | [dsh/](dsh/README.md) (5 releases) | [full/dsh/](full/dsh/README.md) |
| **Grok Bot** | `1.2.0` / `1.25.0` (`ios`) | 2026-11-17 (Last-Modified) | [grok-bot.md](grok-bot.md) | [grok-bot/](grok-bot/README.md) (115 releases) | [full/grok-bot/](full/grok-bot/README.md) |
| **Kimi** | `3.2.27` / `3.1.8` (`ios`) | 2026-11-12 | [kimi.md](kimi.md) | [kimi/](kimi/README.md) (185 releases) | [full/kimi/](full/kimi/README.md) |
| **Qoder** | `0.5.13` (`mac`) / `0.5.7` (`win`, `ubuntu`) / `1.46.0` (`ios`) / `0.10.0` (`android`) | 2026-11-16 | [qoder.md](qoder.md) | [qoder/](qoder/README.md) (58 releases) | [full/qoder/](full/qoder/README.md) |
| **WorkBuddy** | `5.9.4` (`5.11.0` CN) / `2.9.1` | 2026-11-13 | [workbuddy.md](workbuddy.md) | [workbuddy/](workbuddy/README.md) (133 releases) | [full/workbuddy/](full/workbuddy/README.md) |
| **ZCode** | `3.18.2` | 2026-11-13 | [zcode.md](zcode.md) | [zcode/](zcode/README.md) (123 releases) | [full/zcode/](full/zcode/README.md) |

## Directory Structure

- **Edition Layout**:
  - Root (`/`) and [`zh-CN/`](zh-CN/README.md) serve the **Highlight** edition by default (purely user-perceivable changes).
  - [`full/`](full/README.md) and [`zh-CN/full/`](zh-CN/full/README.md) serve the **Full Detail** edition (rich technical & binary/protocol diff details).
  - Every page includes a top bar to switch seamlessly between `English | 简体中文` and `Highlight | Full Detail`.
- **Overview Files (`<harness>.md`)**: Summarize the latest analyzed release (and adjacent baseline) for each client.
- **Client Directories (`<harness>/`)**:
  - `<harness>/README.md`: Reverse-chronological (`Newest → Oldest`) release index across all 5 platforms.
  - `<harness>/YYYY-MM-DD_<version>.md`: Individual release changelog prefixed with its release date so folders sort chronologically.

## License

This repository is licensed under **[CC BY-NC 4.0](LICENSE)** (Creative Commons Attribution-NonCommercial 4.0 International). Commercial use is strictly prohibited without prior written permission.
