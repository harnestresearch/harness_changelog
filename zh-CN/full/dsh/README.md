# DSH (DeepSeek Harness) 版本变更历史

[English](../../../full/dsh/README.md) | 简体中文 · [精简版 (Highlight)](../../dsh/README.md) | **完整详情 (Full Detail)**

覆盖 **DSH (DeepSeek Harness)**（`@deepseek-ai/dsh` CLI/Web 与 `@deepseek-ai/dsh-desktop`，`https://github.com/deepseek-ai/deepseek-harness`）在 `mac`、`win`、`ubuntu`、`ios`、`android` 五端的技术版本演进索引，当前已收录 **3** 个源码 diff 版本（预发布版 `0.2.2-rc.3` – `0.2.2-rc.5`，2026-11-13 至 2026-11-18）。

## 五端覆盖概览

| 平台 | 分发渠道 / 包名 | 收录版本数 | 版本范围 | 最新版本 |
|---|---|---|---|---|
| `mac` | macOS（`@deepseek-ai/dsh` npm CLI/Web 与 `@deepseek-ai/dsh-desktop` Electron `mac-arm64` / `mac-x64`） | 3 | `0.2.2-rc.3` – `0.2.2-rc.5` | [0.2.2-rc.5](2026-11-18_0.2.2-rc.5.md)（预发布） |
| `win` | Windows（`@deepseek-ai/dsh` npm CLI/Web 与 `@deepseek-ai/dsh-desktop` Electron `win-x64` NSIS） | 3 | `0.2.2-rc.3` – `0.2.2-rc.5` | [0.2.2-rc.5](2026-11-18_0.2.2-rc.5.md)（预发布） |
| `ubuntu` | Ubuntu / Linux（`@deepseek-ai/dsh` npm CLI/Web） | 3 | `0.2.2-rc.3` – `0.2.2-rc.5` | [0.2.2-rc.5](2026-11-18_0.2.2-rc.5.md)（预发布） |
| `ios` | 独立 DSH iOS 客户端 | 0 | _暂无独立移动端版本_ | — |
| `android` | 独立 DSH Android 客户端 | 0 | _暂无独立移动端版本_ | — |

## 桌面端与 CLI/Web 版本索引（`mac` / `win` / `ubuntu`，最新 → 最早）

| 版本 | 覆盖平台 | 发布日期 | 核心变更摘要 |
|---|---|---|---|
| [0.2.2-rc.5](2026-11-18_0.2.2-rc.5.md) _（预发布）_ | `mac`、`win`、`ubuntu` | 2026-11-18 | `dsh-v0.2.2-rc.4 → dsh-v0.2.2-rc.5`（`5` 个提交、`433` 个文件，含 PR #8707 的 `53` 个非清单文件与 `0` 净 diff 的 PR #8595 合并）：`dsh-base` 取消 `web.searchProvider` 默认值，`@deepseek-ai/dsh-web` 新增 `WebSearchRequest.llmProvider` 与 `DEEPSEEK_MODEL_ROUTES`（`deepseek-official` / `deepseek-account` → `deepseek-official` Messages 搜索，其余路由与模型外调用 → `deepseek-search-api`，执行期零回退），设置页默认切为 **自动选择** 并将 8 语种 **DeepSeek（旧版）** 更名为 **DeepSeek 服务端搜索**，提取内联 `WebSearchResultItem.snippet`，新增 `1` 条自定义网关 `web-search-deepseek.baseURL` 升级指南 |
| [0.2.2-rc.4](2026-11-18_0.2.2-rc.4.md) _（预发布）_ | `mac`、`win`、`ubuntu` | 2026-11-18（UTC+8） | `dsh-v0.2.2-rc.3 → dsh-v0.2.2-rc.4`（`8` 个提交、`395` 个文件，含 `15` 个非清单文件）：`@deepseek-ai/dsh-llm` 新增非重试错误码 `CONTENT_REFUSED`，`@deepseek-ai/dsh-llm-deepseek` 在 `stop_reason: "refusal"` 时先 yield 计费 `usage` 再抛 `CONTENT_REFUSED`（附 `stop_details.explanation`，未注入请求侧 `safety_check`，含 `1` 条替代 `MALFORMED_RESPONSE` 的 `docs/upgrade-guide` 记录），`@deepseek-ai/dsh-experimental-liveshare` 的 `TunnelWorker.start()` 新增 `workerNodeModeEnv()` 转发 `ELECTRON_RUN_AS_NODE`，并修复 `owner-credential-horizon.host.spec.ts` 真实时钟偏移 |
| [0.2.2-rc.3](2026-11-13_0.2.2-rc.3.md) _（预发布）_ | `mac`、`win`、`ubuntu` | 2026-11-13 | `dsh-v0.2.2-rc.2 → dsh-v0.2.2-rc.3`（`6` 个提交、`515` 个文件）：新增可选实验包 `@deepseek-ai/dsh-deepseek-chat-import`（`POST /api/deepseek-chat-import/archive`、`fflate` 两遍流式导入、`512 MiB` / `256 MiB` / `1,000` 会话边界与受保护空 `system/message` 表面头节点 `0`）、`sidebar.session.action` HOC 槽与 `workspace.picker` 工厂（`3` 处 `DirectoryFlowSlotName` 子槽）、`@deepseek-ai/dsh-session-log-export` 的 `attachments-missing.txt` + `headOf()`/`Promise.allSettled` 流清理、`apps/desktop/installer/restart-status.h` 的 `GetSystemDirectoryW` 工作目录修复，以及 CI `bubblewrap` 校验归档缓存（`0` 项 `docs/upgrade-guide` 破坏性变化） |
