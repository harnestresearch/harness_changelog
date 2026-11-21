# DSH (DeepSeek Harness) 版本变更历史

[English](../../dsh/README.md) | 简体中文 · **精简版 (Highlight)** | [完整详情 (Full Detail)](../full/dsh/README.md)

覆盖 **DSH (DeepSeek Harness)**（`@deepseek-ai/dsh` CLI/Web 与 `@deepseek-ai/dsh-desktop`，`https://github.com/deepseek-ai/deepseek-harness`）在 `mac`、`win`、`ubuntu`、`ios`、`android` 五端的版本演进索引，当前已收录 **3** 个预发布版本（`0.2.2-rc.3` – `0.2.2-rc.5`，2026-11-13 至 2026-11-18）。

## 五端覆盖概览

| 平台 | 分发渠道 / 包名 | 收录版本数 | 版本范围 | 最新版本 |
|---|---|---|---|---|
| `mac` | macOS（`@deepseek-ai/dsh` npm CLI/Web 与 `@deepseek-ai/dsh-desktop` `mac-arm64` / `mac-x64`） | 3 | `0.2.2-rc.3` – `0.2.2-rc.5` | [0.2.2-rc.5](2026-11-18_0.2.2-rc.5.md)（预发布） |
| `win` | Windows（`@deepseek-ai/dsh` npm CLI/Web 与 `@deepseek-ai/dsh-desktop` `win-x64` NSIS） | 3 | `0.2.2-rc.3` – `0.2.2-rc.5` | [0.2.2-rc.5](2026-11-18_0.2.2-rc.5.md)（预发布） |
| `ubuntu` | Ubuntu / Linux（`@deepseek-ai/dsh` npm CLI/Web） | 3 | `0.2.2-rc.3` – `0.2.2-rc.5` | [0.2.2-rc.5](2026-11-18_0.2.2-rc.5.md)（预发布） |
| `ios` | 独立 DSH iOS 客户端 | 0 | _暂无独立移动端版本_ | — |
| `android` | 独立 DSH Android 客户端 | 0 | _暂无独立移动端版本_ | — |

## 桌面端与 CLI/Web 版本索引（`mac` / `win` / `ubuntu`，最新 → 最早）

| 版本 | 覆盖平台 | 发布日期 | 核心亮点 |
|---|---|---|---|
| [0.2.2-rc.5](2026-11-18_0.2.2-rc.5.md) _（预发布）_ | `mac`、`win`、`ubuntu` | 2026-11-18 | 网页搜索默认改为 **自动选择**，将 `deepseek-official` / `deepseek-account` 路由搜索分流至 **DeepSeek 服务端搜索**（8 语种由 **DeepSeek（旧版）** 更名；官方声明免按次费但消耗辅助模型 token）、其余路由及模型外调用分流至 **DeepSeek Search API**，支持提取内联 `web_search_result.snippet` 摘要，并新增 `1` 条自定义网关升级指南 |
| [0.2.2-rc.4](2026-11-18_0.2.2-rc.4.md) _（预发布）_ | `mac`、`win`、`ubuntu` | 2026-11-18（UTC+8） | DeepSeek 流式 `stop_reason: "refusal"` 改为先上报计费用量再抛不可重试的 `CONTENT_REFUSED`（附 `stop_details.explanation`，撤回 Web 半截草稿，含 `1` 条替代 `MALFORMED_RESPONSE` 的 SDK/事件升级指南），桌面端 LiveShare 网关工作进程透传 `ELECTRON_RUN_AS_NODE` 解决被单实例锁终止导致无法创建分享的问题 |
| [0.2.2-rc.3](2026-11-13_0.2.2-rc.3.md) _（预发布）_ | `mac`、`win`、`ubuntu` | 2026-11-13 | 新增实验性插件「DeepSeek 会话导入」（支持上传 `deepseek_data-*.zip` 转为所选工作区可续聊会话，覆盖 8 种语言）、`sidebar.session.action` 侧栏槽位与可复用 `workspace.picker` 选择器工厂、会话日志 ZIP 导出缺失附件容错（`attachments-missing.txt` 与流清理）、Windows NSIS 更新重启目录锁修复及 CI `bubblewrap` 校验缓存（无破坏性变化） |
