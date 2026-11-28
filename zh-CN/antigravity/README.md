# Antigravity 版本变更历史

[English](../../antigravity/README.md) | 简体中文 · **精简版 (Highlight)** | [完整详情 (Full Detail)](../full/antigravity/README.md)

覆盖 Google **Antigravity**（`https://antigravity.google`）在 `mac`、`win`、`ubuntu`、`ios`、`android` 五端的版本演进索引，当前共收录 **9** 个版本条目，分属两条独立桌面产品线：
- **Antigravity Desktop（`antigravity-hub`）**：独立 Electron 桌面智能体客户端（`2.31.2` → `2.36.0`，覆盖 `mac`、`win`、`ubuntu`，最新 2026-11-27）。
- **Antigravity IDE（`Antigravity IDE`）**：基于 Code OSS `1.107.0` 的 AI IDE（`2.7.0` → `2.8.0`，覆盖 `mac`、`win`、`ubuntu`，最新 2026-11-19）。

## 五端覆盖概览

| 平台 | 分发渠道 / 包名 | 收录版本数 | 版本范围 | 最新版本 |
|---|---|---|---|---|
| `mac` | macOS（`Antigravity.dmg` Hub 官方 GCS 源与 `Antigravity IDE.app` `darwin-arm` 官方 edgedl 源） | 8 | `2.32.0` → `2.36.0`（Hub）/ `ide-2.7.0` → `ide-2.8.0`（IDE） | [2.36.0](2026-11-27_2.36.0.md) / [IDE 2.8.0](2026-11-19_ide-2.8.0.md) |
| `win` | Windows（`Antigravity` Hub 安装包与 `Antigravity IDE.exe` `windows-x64` Inno Setup） | 8 | `2.32.0` → `2.36.0`（Hub）/ `ide-2.7.0` → `ide-2.8.0`（IDE） | [2.36.0](2026-11-27_2.36.0.md) / [IDE 2.8.0](2026-11-19_ide-2.8.0.md) |
| `ubuntu` | Ubuntu / Linux（`Antigravity.tar.gz` Hub 与 `Antigravity IDE.tar.gz` `linux-x64`） | 9 | `2.31.2` → `2.36.0`（Hub）/ `ide-2.7.0` → `ide-2.8.0`（IDE） | [2.36.0](2026-11-27_2.36.0.md) / [IDE 2.8.0](2026-11-19_ide-2.8.0.md) |
| `ios` | 独立 Antigravity iOS 客户端 | 0 | _暂无独立移动端版本_ | — |
| `android` | 独立 Antigravity Android 客户端 | 0 | _暂无独立移动端版本_ | — |

## 桌面端版本索引（`mac` / `win` / `ubuntu`，最新 → 最早）

| 版本 | 覆盖平台 | 发布日期 | 核心亮点 |
|---|---|---|---|
| [2.36.0 (Hub)](2026-11-27_2.36.0.md) | `mac`、`win`、`ubuntu` | 2026-11-27 | 壳层连续第三个纯版本号版本 + 后端 Go `language_server` rebase 功能更新（构建 `5596661662220288`；`darwin-arm` 主分析 + 六端同构建点测，首次覆盖 `windows-arm64`，Win `x64`/`arm64` LS PE 未覆盖）：新增 `+34` Connect-RPC（`338 → 372`，含新服务 `JetskiRemoteAgentProxyService` 支撑远程智能体管理与云端自动化授权）、RemoteControl Mesh 传输（macOS `agy-desktop-rtc` `+22.6` KB）、`policyguardian/sensitivity`、Proctor J1/C8 规则、Sentry SDK 及 `~/.agents/skills` 技能发现；官方标题级 UI/Auto mode/语音上下文条目与 26 项修复多属 Hub webapp/服务端，包内不可证 |
| [2.35.2 (Hub)](2026-11-25_2.35.2.md) | `mac`、`win`、`ubuntu` | 2026-11-25（包 Last-Modified） | 相对 `2.35.1` 的纯维护版（构建 `4585983447007232`；`darwin-arm` 主分析 + 五端同构建点测，首次覆盖 `darwin-x64` 与 `linux-arm`，Win LS PE/CL 未覆盖）：`app.asar` 仅改版本号，Go `language_server` 同大小同基线重编译（`cl/1029311855`，五口径零 diff）；官方独立修复「Switch models while a turn is running」属 Hub webapp，包内静态不可证 |
| [2.35.1 (Hub)](2026-11-25_2.35.1.md) | `mac`、`win`、`ubuntu` | 2026-11-25（包 Last-Modified） | 两段分列静态对比（`2.34.0 → 2.35.0` 与 `2.35.0 → 2.35.1` 不混称；`darwin-arm` 主轴，`linux-x64` asar/CL 与 `windows-x64` 内嵌 asar 核对，Win LS PE 与 `darwin-x64` 未覆盖）：`2.35.1` 为维护版（壳层仅 version 变更、LS 同基线重编译，官方 `2.35.1` 三条在包内无静态落点）；前序 `2.35.0` 重组壳层 `computer/`（移出 HUD、新增 `customWindowControls.js` 与 `agy-desktop-rtc`）并重构 LS（`AgentRemoteSession` CRUD、`openai_go` SDK、`agentapi` CLI、RPC `380 → 338`、`enable-mcp-apps` / orchestrator / swarm 开关） |
| [IDE 2.8.0](2026-11-19_ide-2.8.0.md) | `mac`、`win`、`ubuntu` | 2026-11-19 | `extensions/agy` `1.11.0 → 1.12.0`（`+66.9` KB），Code OSS 基座连续三版冻结（`darwin-arm` 主分析 + `linux-x64`/`windows-x64` 核对）：新增后台周期更新检查与 `"Restart Agent Server"` 重启提示、启动延迟检查与防降级保护（`downgrade_skipped`/`same_version_rebuild`）、6 类远程环境登录端口转发与 `SwitchLoginToAuthCode` 授权码回退、`antigravity.caCertificates` 与企业根证书/代理配置、Agent 面板 `Ctrl+F`/`Cmd+F` 会话内搜索快捷键及 `+26` 项 webview 桥接 Schema；官方 12 条中 3 条（60s 就绪超时、Windows 注销恢复死循环、Windows 通知聚焦）不在 IDE 静态包面内 |
| [2.32.2 (Hub)](2026-11-17_2.32.2.md) | `mac`、`win`、`ubuntu` | 2026-11-17（包 Last-Modified） | 维护补丁构建（官方 `darwin-arm` 双 DMG 主分析，`linux-x64` 同构建及 LS 点测，`windows-x64` 点测）：Electron `44.9.1` 壳层 `1,068` 文件仅 `package.json` 版本号更新为 `2.32.2`，随包 `chrome-devtools-mcp` `1.9.0` 零差异，重编译 Go `language_server`（`cl/1022991777`）仅检出内部遥测 CEL 超时函数改名及 `Shutdown` 闭包符号串变化，静态抽取的模型/RPC/开关/工具文本清单不变 |
| [2.32.1 (Hub)](2026-11-14_2.32.1.md) | `mac`、`win`、`ubuntu` | 2026-11-14 | 次日补丁构建，在内置默认模型目录中新增 **Gemini 4 Hydrogen** 低/中/高三档推理强度预设（与 `Gemini 4 Argon`、`Gemini 4 Carbon` 并列），Electron `44.9.1` 壳层与内置浏览器 MCP 工具集保持逐字节一致并完整继承 `2.32.0` 全部特性与修复 |
| [2.32.0 (Hub)](2026-11-13_2.32.0.md) | `mac`、`win`、`ubuntu` | 2026-11-13 | 正式开放 Dynamic Workflows（内置 Python 运行时并行子代理编排）、Everforest 亮/暗主题、提示词跳转与自定义发送快捷键、智能体浏览器跨站框架未登录隔离与 `Electron` UA 清洗修复、授权码登录兜底、云端 GitHub 仓库本地克隆、退出残留进程清理与 CJK 粗体修复（11 项改进、13 项修复），并合入开关门控的 SSH 远程与桌面控制基建 |
| [2.31.2 (Hub)](2026-11-12_2.31.2.md) | `ubuntu` | 2026-11-12 | 新增内置浏览器 Guest WebMCP 页面工具桥（含支付/IDP 域名拦截、64 KiB 上限与 30 秒超时）、原生 Swarm 看板多节点协同、远程 MCP 直连 OAuth 登录、规划—执行门控、持久终端、Notebook 单元格执行，以及 `DevToolsActivePort` 权限加固 |
| [IDE 2.7.0](2026-11-11_ide-2.7.0.md) | `mac`、`win`、`ubuntu` | 未确认 _（构建于 2026-11-11）_ | 登录态感知三态状态栏与跨窗口认证同步、拆分「当前文件」与「全部文件」Diff 接受/拒绝命令、扩展后台任务与浏览器录制桥接，以及 Google Cloud Workstations `/usr/bin/agy` 预装 CLI 自动识别 |
