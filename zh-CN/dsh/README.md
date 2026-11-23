# DSH (DeepSeek Harness) 版本变更历史

[English](../../dsh/README.md) | 简体中文 · **精简版 (Highlight)** | [完整详情 (Full Detail)](../full/dsh/README.md)

覆盖 **DSH (DeepSeek Harness)**（`@deepseek-ai/dsh` CLI/Web 与 `@deepseek-ai/dsh-desktop`，`https://github.com/deepseek-ai/deepseek-harness`）在 `mac`、`win`、`ubuntu`、`ios`、`android` 五端的版本演进索引，当前已收录 **5** 个预发布版本（`0.2.2-rc.3` – `0.2.3-alpha.2`，2026-11-13 至 2026-11-22）。

## 五端覆盖概览

| 平台 | 分发渠道 / 包名 | 收录版本数 | 版本范围 | 最新版本 |
|---|---|---|---|---|
| `mac` | macOS（`@deepseek-ai/dsh` npm CLI/Web 与 `@deepseek-ai/dsh-desktop` `mac-arm64` / `mac-x64`） | 5 | `0.2.2-rc.3` – `0.2.3-alpha.2` | [0.2.3-alpha.2](2026-11-22_0.2.3-alpha.2.md)（预发布） |
| `win` | Windows（`@deepseek-ai/dsh` npm CLI/Web 与 `@deepseek-ai/dsh-desktop` `win-x64` NSIS） | 5 | `0.2.2-rc.3` – `0.2.3-alpha.2` | [0.2.3-alpha.2](2026-11-22_0.2.3-alpha.2.md)（预发布） |
| `ubuntu` | Ubuntu / Linux（`@deepseek-ai/dsh` npm CLI/Web） | 5 | `0.2.2-rc.3` – `0.2.3-alpha.2` | [0.2.3-alpha.2](2026-11-22_0.2.3-alpha.2.md)（预发布） |
| `ios` | 独立 DSH iOS 客户端 | 0 | _暂无独立移动端版本_ | — |
| `android` | 独立 DSH Android 客户端 | 0 | _暂无独立移动端版本_ | — |

## 桌面端与 CLI/Web 版本索引（`mac` / `win` / `ubuntu`，最新 → 最早）

| 版本 | 覆盖平台 | 发布日期 | 核心亮点 |
|---|---|---|---|
| [0.2.3-alpha.2](2026-11-22_0.2.3-alpha.2.md) _（预发布）_ | `mac`、`win`、`ubuntu` | 2026-11-22 | 将 `engines.node` 由 `>=24.9.0` 提高至 `^24.22.3 \|\| >=26.13.1`（允许 `24.x >= 24.22.3` 与 `>=26.13.1` 含 semver `27+`，排除 `<24.22.3`、全部 `25.x` 与 `26.0.0`–`26.13.0`；仅清单声明无 CLI 启动拦截，严格 `=== 24.22.3` 仅限 CI `DSH_NODE_COMPAT_BUILD=1` 与内置运行时/exe 打包），同步升级 `undici` 安全固定（`6.29.1`/`7.30.2`/`8.12.4`）、桌面端 Electron `^44.11.5` + `node-addon-require-builtin ^0.1.10`、内置主运行时/Python 单文件 exe 至 Node `24.22.3`，并将 9 个 vendor 包升至 `*-alpha.1`（新增 `1` 条升级指南；相较 `alpha.1` 无产品/UI 功能变更） |
| [0.2.3-alpha.1](2026-11-22_0.2.3-alpha.1.md) _（预发布）_ | `mac`、`win`、`ubuntu` | 2026-11-22 | 插件页统一连接器账号与 MCP OAuth、按需加载 MCP 工具及 7 个独立可选连接器（**Linear**、**Notion**、**腾讯文档**、**飞书**、**企业微信**、**腾讯会议**、**钉钉**）；Web 远程登录/二维码/设备配对与默认强制鉴权 `webServer`；可停靠会话状态面板与跨端已读/未读状态；实验性 Git 仓库插件源、时间线插件、代码审阅页（GitHub PR）与 GitLab 会话 MR 支持；`workspace-write` 随会话实时 `cwd` 切换（移除 `working_directory`）、统一 `ctx.deepseekAuth`（保留 `rc.5` 搜索计费边界）、Cordis `4.0.0-rc.12`、Node PTC 持久作用域 REPL 默认启用并移除 Python PTC、实验性 Windows CUA / `cua-mcp`、`/office` 合并 + `pypdf` 及可选实验性 SQLite 会话存储（新增 `55` 条、更新 `2` 条升级指南） |
| [0.2.2-rc.5](2026-11-18_0.2.2-rc.5.md) _（预发布）_ | `mac`、`win`、`ubuntu` | 2026-11-18 | 网页搜索默认改为 **自动选择**，将 `deepseek-official` / `deepseek-account` 路由搜索分流至 **DeepSeek 服务端搜索**（8 语种由 **DeepSeek（旧版）** 更名；官方声明免按次费但消耗辅助模型 token）、其余路由及模型外调用分流至 **DeepSeek Search API**，支持提取内联 `web_search_result.snippet` 摘要，并新增 `1` 条自定义网关升级指南 |
| [0.2.2-rc.4](2026-11-18_0.2.2-rc.4.md) _（预发布）_ | `mac`、`win`、`ubuntu` | 2026-11-18（UTC+8） | DeepSeek 流式 `stop_reason: "refusal"` 改为先上报计费用量再抛不可重试的 `CONTENT_REFUSED`（附 `stop_details.explanation`，撤回 Web 半截草稿，含 `1` 条替代 `MALFORMED_RESPONSE` 的 SDK/事件升级指南），桌面端 LiveShare 网关工作进程透传 `ELECTRON_RUN_AS_NODE` 解决被单实例锁终止导致无法创建分享的问题 |
| [0.2.2-rc.3](2026-11-13_0.2.2-rc.3.md) _（预发布）_ | `mac`、`win`、`ubuntu` | 2026-11-13 | 新增实验性插件「DeepSeek 会话导入」（支持上传 `deepseek_data-*.zip` 转为所选工作区可续聊会话，覆盖 8 种语言）、`sidebar.session.action` 侧栏槽位与可复用 `workspace.picker` 选择器工厂、会话日志 ZIP 导出缺失附件容错（`attachments-missing.txt` 与流清理）、Windows NSIS 更新重启目录锁修复及 CI `bubblewrap` 校验缓存（无破坏性变化） |
