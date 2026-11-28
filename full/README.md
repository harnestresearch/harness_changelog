# Harness Changelog (Full Technical Detail)

English | [简体中文](../zh-CN/full/README.md) · [Highlight](../README.md) | **Full Detail**

In-depth technical diff changelogs across major AI agent harnesses (`mac`, `win`, `ubuntu`, `ios`, `android`), covering main/renderer bundle diffs, embedded CLI & engine updates, IPC/RPC/MCP protocol surfaces, runtime flags, and dependency changes.

> Looking for concise user-facing release notes? Switch to the default **[Highlight](../README.md)** edition.

## Latest Technical Changelogs

| Harness | Latest Version | Release Date | Latest Technical Summary | Full Technical Index | Highlight Edition |
|---|---|---|---|---|---|
| **Antigravity** | `2.36.0` (Hub) / `2.8.0` (IDE) | 2026-11-27 / 2026-11-19 | [antigravity.md](antigravity.md) | [antigravity/](antigravity/README.md) (9 releases) | [../antigravity/](../antigravity/README.md) |
| **Claude** | `5.11492.5` / `1.261125.19` (`android`) / `1.261109.19` (`ios`) | 2026-11-27 (Uptodown) | [claude.md](claude.md) | [claude/](claude/README.md) (535 releases) | [../claude/](../claude/README.md) |
| **ChatGPT / Codex** | `26.1111.2228.0` (`win`) / `26.1111.21308` (`mac`, `ubuntu`) / `1.2026.314` (`android`) / `1.2026.307` (`ios`) | 2026-11-16 (APKPure) | [codex.md](codex.md) | [codex/](codex/README.md) (418 unified releases) | [../codex/](../codex/README.md) |
| **Cursor** | `3.30.14` / `1.17.0` (`ios`) | 2026-11-14 | [cursor.md](cursor.md) | [cursor/](cursor/README.md) (446 releases) | [../cursor/](../cursor/README.md) |
| **DSH (DeepSeek Harness)** | `0.2.3-alpha.2` (prerelease) | 2026-11-22 | [dsh.md](dsh.md) | [dsh/](dsh/README.md) (5 releases) | [../dsh/](../dsh/README.md) |
| **Grok Bot** | `1.2.0` / `1.25.0` (`ios`) | 2026-11-17 (Last-Modified) | [grok-bot.md](grok-bot.md) | [grok-bot/](grok-bot/README.md) (115 releases) | [../grok-bot/](../grok-bot/README.md) |
| **Kimi** | `3.2.29` (`mac`, `win`) / `3.1.8` (`ios`) | 2026-11-26 | [kimi.md](kimi.md) | [kimi/](kimi/README.md) (186 releases) | [../kimi/](../kimi/README.md) |
| **Qoder** | `0.5.21` (`mac`, `win`, `ubuntu`) / `1.46.0` (`ios`) / `2.0.0` (`android`) | 2026-11-27 | [qoder.md](qoder.md) | [qoder/](qoder/README.md) (61 releases) | [../qoder/](../qoder/README.md) |
| **WorkBuddy** | `5.9.4` (`5.11.0` CN) / `2.9.1` | 2026-11-13 | [workbuddy.md](workbuddy.md) | [workbuddy/](workbuddy/README.md) (133 releases) | [../workbuddy/](../workbuddy/README.md) |
| **ZCode** | `3.18.2` | 2026-11-13 | [zcode.md](zcode.md) | [zcode/](zcode/README.md) (123 releases) | [../zcode/](../zcode/README.md) |

## Structure of `full/`

- `full/<harness>.md`: Technical deep-dive summary of the latest analyzed release(s) for each harness.
- `full/<harness>/README.md`: Complete reverse-chronological technical release index.
- `full/<harness>/YYYY-MM-DD_<version>.md`: Per-version technical diff changelog (architecture, main/renderer bundles, RPC/MCP protocol changes, runtime flags, dependencies, and binary/archive diff details).

## License

This repository is licensed under **[CC BY-NC 4.0](../LICENSE)** (Creative Commons Attribution-NonCommercial 4.0 International — Non-Commercial use only).
