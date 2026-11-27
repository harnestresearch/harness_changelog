# Harness Changelog

[English](../README.md) | 简体中文 · **精简版 (Highlight)** | [完整详情 (Full Detail)](full/README.md)

各智能体客户端（Harness）跨五端（`mac`、`win`、`ubuntu`、`ios`、`android`）的版本变更日志汇总。

> **双版本阅读模式**：
> - **精简版 Highlight（默认 — `/` 与 `zh-CN/`）**：聚焦**用户可感知**的新功能、界面交互、连接器集成与问题修复，简明易读。
> - **[完整详情 Full Detail](full/README.md)（`full/` 与 `zh-CN/full/`）**：包含深度技术变更细节（运行时/引擎升级、IPC/RPC 与 MCP 协议变更、具名模块体积对比、环境变量/特性开关及依赖变更等）。

## 最新版本概览

| Harness | 最新版本 | 发布日期 | 最新核心亮点 | 完整版本索引（精简版） | 完整技术详情（Full Detail） |
|---|---|---|---|---|---|
| **Antigravity** | `2.35.2`（Hub）/ `2.7.0`（IDE） | 2026-11-25（包 Last-Modified）/ 未确认 | [antigravity.md](antigravity.md) | [antigravity/](antigravity/README.md)（共 7 个版本） | [full/antigravity/](full/antigravity/README.md) |
| **Claude** | `5.11492.5` / `1.261124.19`（`android`）/ `1.261109.19`（`ios`） | 2026-11-25（Uptodown 镜像） | [claude.md](claude.md) | [claude/](claude/README.md)（共 534 个版本） | [full/claude/](full/claude/README.md) |
| **ChatGPT / Codex** | `26.1111.2228.0`（`win`）/ `26.1111.21308`（`mac`、`ubuntu`）/ `1.2026.314`（`android`）/ `1.2026.307`（`ios`） | 2026-11-16（APKPure 归档） | [codex.md](codex.md) | [codex/](codex/README.md)（共 418 个统一版本） | [full/codex/](full/codex/README.md) |
| **Cursor** | `3.30.14` / `1.17.0`（`ios`） | 2026-11-14 | [cursor.md](cursor.md) | [cursor/](cursor/README.md)（共 446 个版本） | [full/cursor/](full/cursor/README.md) |
| **DSH (DeepSeek Harness)** | `0.2.3-alpha.2`（预发布） | 2026-11-22 | [dsh.md](dsh.md) | [dsh/](dsh/README.md)（共 5 个版本） | [full/dsh/](full/dsh/README.md) |
| **Grok Bot** | `1.2.0` / `1.25.0`（`ios`） | 2026-11-17（包 Last-Modified） | [grok-bot.md](grok-bot.md) | [grok-bot/](grok-bot/README.md)（共 115 个版本） | [full/grok-bot/](full/grok-bot/README.md) |
| **Kimi** | `3.2.29`（`mac`、`win`）/ `3.1.8`（`ios`） | 2026-11-26 | [kimi.md](kimi.md) | [kimi/](kimi/README.md)（共 186 个版本） | [full/kimi/](full/kimi/README.md) |
| **Qoder** | `0.5.20`（`mac`、`win`、`ubuntu`）/ `1.46.0`（`ios`）/ `0.10.0`（`android`） | 2026-11-25 | [qoder.md](qoder.md) | [qoder/](qoder/README.md)（共 59 个版本） | [full/qoder/](full/qoder/README.md) |
| **WorkBuddy** | `5.9.4`（国内 `5.11.0`）/ `2.9.1` | 2026-11-13 | [workbuddy.md](workbuddy.md) | [workbuddy/](workbuddy/README.md)（共 133 个版本） | [full/workbuddy/](full/workbuddy/README.md) |
| **ZCode** | `3.18.2` | 2026-11-13 | [zcode.md](zcode.md) | [zcode/](zcode/README.md)（共 123 个版本） | [full/zcode/](full/zcode/README.md) |

## 目录结构说明

- **双精度与多语言对称布局**：
  - 仓库根目录（`/`）与 `zh-CN/` 默认提供**精简版（Highlight）**，仅展示用户能直接感知的产品与体验变化。
  - [`full/`](../full/README.md) 与 [`zh-CN/full/`](full/README.md) 提供对称的**完整详情版（Full Detail）**，包含翔实的底层模块、协议与代码级 diff 细节。
  - 所有页面顶部均支持 `English | 简体中文` 与 `Highlight | Full Detail` 一键互跳。
- **概览文件（`<harness>.md`）**：汇总对应客户端最新深度解析版本的核心改动与紧邻基线版本背景。
- **客户端目录（`<harness>/`）**：
  - `<harness>/README.md`：按发布日期倒序（最新 → 最早）排列的五端完整版本索引。
  - `<harness>/YYYY-MM-DD_<version>.md`：以首发日期为前缀命名的单版本变更记录，使文件夹内天然按发布时间顺序排列。

## 许可协议

本仓库采用 **[CC BY-NC 4.0](../LICENSE)**（知识共享 署名-非商业性使用 4.0 国际）协议发布，未经书面许可**禁止任何商业用途**。
