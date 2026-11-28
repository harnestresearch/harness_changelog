# Harness Changelog（完整技术详情 Full Detail）

[English](../../full/README.md) | 简体中文 · [精简版 (Highlight)](../README.md) | **完整详情 (Full Detail)**

各智能体客户端（Harness）跨五端（`mac`、`win`、`ubuntu`、`ios`、`android`）的深度技术变更日志（Full Detail），涵盖主进程/渲染层具名模块对比、内置 CLI 与引擎升级、IPC/RPC/MCP 协议面演进、环境变量与特性开关以及依赖变更明细。

> 如需浏览仅面向用户感知的产品功能亮点，可切换至默认的 **[精简版 (Highlight)](../README.md)**。

## 最新版本技术概览

| Harness | 最新版本 | 发布日期 | 最新技术摘要 | 完整技术索引 | 对应精简版（Highlight） |
|---|---|---|---|---|---|
| **Antigravity** | `2.36.0`（Hub）/ `2.8.0`（IDE） | 2026-11-27 / 2026-11-19 | [antigravity.md](antigravity.md) | [antigravity/](antigravity/README.md)（共 9 个版本） | [../antigravity/](../antigravity/README.md) |
| **Claude** | `5.11492.5` / `1.261125.19`（`android`）/ `1.261109.19`（`ios`） | 2026-11-27（Uptodown 镜像） | [claude.md](claude.md) | [claude/](claude/README.md)（共 535 个版本） | [../claude/](../claude/README.md) |
| **ChatGPT / Codex** | `26.1111.2228.0`（`win`）/ `26.1111.21308`（`mac`、`ubuntu`）/ `1.2026.314`（`android`）/ `1.2026.307`（`ios`） | 2026-11-16（APKPure 归档） | [codex.md](codex.md) | [codex/](codex/README.md)（共 418 个统一版本） | [../codex/](../codex/README.md) |
| **Cursor** | `3.30.14` / `1.17.0`（`ios`） | 2026-11-14 | [cursor.md](cursor.md) | [cursor/](cursor/README.md)（共 446 个版本） | [../cursor/](../cursor/README.md) |
| **DSH (DeepSeek Harness)** | `0.2.3-alpha.2`（预发布） | 2026-11-22 | [dsh.md](dsh.md) | [dsh/](dsh/README.md)（共 5 个版本） | [../dsh/](../dsh/README.md) |
| **Grok Bot** | `1.2.0` / `1.25.0`（`ios`） | 2026-11-17（包 Last-Modified） | [grok-bot.md](grok-bot.md) | [grok-bot/](grok-bot/README.md)（共 115 个版本） | [../grok-bot/](../grok-bot/README.md) |
| **Kimi** | `3.2.29`（`mac`、`win`）/ `3.1.8`（`ios`） | 2026-11-26 | [kimi.md](kimi.md) | [kimi/](kimi/README.md)（共 186 个版本） | [../kimi/](../kimi/README.md) |
| **Qoder** | `0.5.21`（`mac`、`win`、`ubuntu`）/ `1.46.0`（`ios`）/ `2.0.0`（`android`） | 2026-11-27 | [qoder.md](qoder.md) | [qoder/](qoder/README.md)（共 61 个版本） | [../qoder/](../qoder/README.md) |
| **WorkBuddy** | `5.9.4`（国内 `5.11.0`）/ `2.9.1` | 2026-11-13 | [workbuddy.md](workbuddy.md) | [workbuddy/](workbuddy/README.md)（共 133 个版本） | [../workbuddy/](../workbuddy/README.md) |
| **ZCode** | `3.18.2` | 2026-11-13 | [zcode.md](zcode.md) | [zcode/](zcode/README.md)（共 123 个版本） | [../zcode/](../zcode/README.md) |

## `full/` 目录结构

- `zh-CN/full/<harness>.md`：对应客户端最新深度解析版本的完整技术改动汇总。
- `zh-CN/full/<harness>/README.md`：按发布日期倒序排列的五端完整技术变更索引。
- `zh-CN/full/<harness>/YYYY-MM-DD_<version>.md`：单版本完整技术变更记录（架构、主进程/渲染层模块 diff、RPC/MCP 协议、环境变量/特性开关、依赖及归档包变更明细）。

## 许可协议

本仓库采用 **[CC BY-NC 4.0](../../LICENSE)**（知识共享 署名-非商业性使用 4.0 国际）协议发布，未经书面许可**禁止任何商业用途**。
