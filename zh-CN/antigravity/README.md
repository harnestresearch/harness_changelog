# Antigravity 版本变更历史

[English](../../antigravity/README.md) | 简体中文 · **精简版 (Highlight)** | [完整详情 (Full Detail)](../full/antigravity/README.md)

覆盖 Google **Antigravity**（`https://antigravity.google`）在 `mac`、`win`、`ubuntu`、`ios`、`android` 五端的版本演进索引，当前共收录 **5** 个版本条目，分属两条独立桌面产品线：
- **Antigravity Desktop（`antigravity-hub`）**：独立 Electron 桌面智能体客户端（`2.31.2` → `2.32.2`，覆盖 `mac`、`win`、`ubuntu`，最新 2026-11-17 包 `Last-Modified`）。
- **Antigravity IDE（`Antigravity IDE`）**：基于 Code OSS `1.107.0` 的 AI IDE（覆盖 `mac`、`win`、`ubuntu` 的 `2.7.0`；发布时间未确认——`product.json` 中的北京时间 `2026-11-11 12:46` 为构建时间而非发布时间）。

## 五端覆盖概览

| 平台 | 分发渠道 / 包名 | 收录版本数 | 版本范围 | 最新版本 |
|---|---|---|---|---|
| `mac` | macOS（`Antigravity.dmg` Hub 官方 GCS 源与 `Antigravity IDE.app` `darwin-arm` 官方 edgedl 源） | 4 | `2.32.0` → `2.32.2`（Hub）/ `ide-2.7.0`（IDE） | [2.32.2](2026-11-17_2.32.2.md) / [IDE 2.7.0](2026-11-11_ide-2.7.0.md) |
| `win` | Windows（`Antigravity` Hub 安装包与 `Antigravity IDE.exe` `windows-x64` Inno Setup） | 4 | `2.32.0` → `2.32.2`（Hub）/ `ide-2.7.0`（IDE） | [2.32.2](2026-11-17_2.32.2.md) / [IDE 2.7.0](2026-11-11_ide-2.7.0.md) |
| `ubuntu` | Ubuntu / Linux（`Antigravity.tar.gz` Hub 与 `Antigravity IDE.tar.gz` `linux-x64`） | 5 | `2.31.2` → `2.32.2`（Hub）/ `ide-2.7.0`（IDE） | [2.32.2](2026-11-17_2.32.2.md) / [IDE 2.7.0](2026-11-11_ide-2.7.0.md) |
| `ios` | 独立 Antigravity iOS 客户端 | 0 | _暂无独立移动端版本_ | — |
| `android` | 独立 Antigravity Android 客户端 | 0 | _暂无独立移动端版本_ | — |

## 桌面端版本索引（`mac` / `win` / `ubuntu`，最新 → 最早）

| 版本 | 覆盖平台 | 发布日期 | 核心亮点 |
|---|---|---|---|
| [2.32.2 (Hub)](2026-11-17_2.32.2.md) | `mac`、`win`、`ubuntu` | 2026-11-17（包 Last-Modified） | 维护补丁构建（官方 `darwin-arm` 双 DMG 主分析，`linux-x64` 同构建及 LS 点测，`windows-x64` 点测）：Electron `44.9.1` 壳层 `1,068` 文件仅 `package.json` 版本号更新为 `2.32.2`，随包 `chrome-devtools-mcp` `1.9.0` 零差异，重编译 Go `language_server`（`cl/1022991777`）仅检出内部遥测 CEL 超时函数改名及 `Shutdown` 闭包符号串变化，静态抽取的模型/RPC/开关/工具文本清单不变 |
| [2.32.1 (Hub)](2026-11-14_2.32.1.md) | `mac`、`win`、`ubuntu` | 2026-11-14 | 次日补丁构建，在内置默认模型目录中新增 **Gemini 4 Hydrogen** 低/中/高三档推理强度预设（与 `Gemini 4 Argon`、`Gemini 4 Carbon` 并列），Electron `44.9.1` 壳层与内置浏览器 MCP 工具集保持逐字节一致并完整继承 `2.32.0` 全部特性与修复 |
| [2.32.0 (Hub)](2026-11-13_2.32.0.md) | `mac`、`win`、`ubuntu` | 2026-11-13 | 正式开放 Dynamic Workflows（内置 Python 运行时并行子代理编排）、Everforest 亮/暗主题、提示词跳转与自定义发送快捷键、智能体浏览器跨站框架未登录隔离与 `Electron` UA 清洗修复、授权码登录兜底、云端 GitHub 仓库本地克隆、退出残留进程清理与 CJK 粗体修复（11 项改进、13 项修复），并合入开关门控的 SSH 远程与桌面控制基建 |
| [2.31.2 (Hub)](2026-11-12_2.31.2.md) | `ubuntu` | 2026-11-12 | 新增内置浏览器 Guest WebMCP 页面工具桥（含支付/IDP 域名拦截、64 KiB 上限与 30 秒超时）、原生 Swarm 看板多节点协同、远程 MCP 直连 OAuth 登录、规划—执行门控、持久终端、Notebook 单元格执行，以及 `DevToolsActivePort` 权限加固 |
| [IDE 2.7.0](2026-11-11_ide-2.7.0.md) | `mac`、`win`、`ubuntu` | 未确认 _（构建于 2026-11-11）_ | 登录态感知三态状态栏与跨窗口认证同步、拆分「当前文件」与「全部文件」Diff 接受/拒绝命令、扩展后台任务与浏览器录制桥接，以及 Google Cloud Workstations `/usr/bin/agy` 预装 CLI 自动识别 |
