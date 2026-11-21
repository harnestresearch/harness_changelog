# DSH (DeepSeek Harness) 最新版本改动

[English](../dsh.md) | 简体中文 · **精简版 (Highlight)** | [完整详情 (Full Detail)](full/dsh.md)

> 五端（`mac`、`win`、`ubuntu`、`ios`、`android`）版本索引（当前收录预发布版 `0.2.2-rc.5`）见 [dsh/README.md](dsh/README.md)。

## 0.2.2-rc.5 — 预发布版 Prerelease（2026-11-18）

承接 `dsh-v0.2.2-rc.4`（`2026-11-18 UTC+8`）的预发布候选版本（`dsh-v0.2.2-rc.5`，官方 GitHub Release `published_at`：`2026-11-18 20:51:39 UTC+8` / `2026-11-18T12:51:39Z` UTC；早先 git 合并提交 `9c2670d3bce` 于 `2026-11-18 17:45:47 UTC+8`）。亮点、路由/回退/计费边界及迁移说明见 [dsh/2026-11-18_0.2.2-rc.5.md](dsh/2026-11-18_0.2.2-rc.5.md)，完整技术细节见 [full/dsh/2026-11-18_0.2.2-rc.5.md](full/dsh/2026-11-18_0.2.2-rc.5.md)。_（仅基于只读 git 标签 diff 与官方 Release 元数据核验，未做运行时或真实账单验证。）_

### 核心亮点

- **按模型路由自动选择网页搜索提供方与设置项更名** _（官方说明：「DeepSeek 模型使用 DeepSeek 服务端搜索，搜索不按次收费；其他模型默认使用 DeepSeek Search API」）_：`dsh-base` 取消写死 `web.searchProvider`，网页搜索提供方默认改为 **自动选择**，未固定时仅在内置 `'deepseek-official'` 与 `'deepseek-account'` 两条模型路由上优先选用 **DeepSeek 服务端搜索**（`deepseek-official`，全 8 语种由 **DeepSeek（旧版）** 更名），在其他模型路由（含经自定义路由接入的 DeepSeek 模型）及模型请求外默认选用 **DeepSeek Search API**（`deepseek-search-api`）；仅支持本地 `available()` 单一可用顺延，执行期零回退（含 `1` 条自定义网关升级指南；官方声明仅免按次费但每次查询仍消耗辅助模型 token，源码不证明实际账单）。
- **DeepSeek 服务端搜索支持内联 `snippet` 摘要提取**：`@deepseek-ai/dsh-web-search-deepseek` 新增优先提取 `web_search_result.snippet`，仅在缺失时回退文本块 `citations[].cited_text`，确保 `/anthropic/v1/messages` 不返回 `citations` 时仍保留网页摘要。

---

## 前序预发布版：0.2.2-rc.4（2026-11-18，UTC+8）

承接 `dsh-v0.2.2-rc.3`（`2026-11-13`）的预发布修复候选版本（`dsh-v0.2.2-rc.4`，官方 GitHub Release `published_at`：`2026-11-18 01:53:41 UTC+8` / `2026-11-17T17:53:41Z` UTC；早先 git 合并提交 `3f321d32bfe` 于 `2026-11-17 21:30:09 UTC+8`）。亮点、官方声明与源码实证对照及破坏性变化见 [dsh/2026-11-18_0.2.2-rc.4.md](dsh/2026-11-18_0.2.2-rc.4.md)，完整技术细节见 [full/dsh/2026-11-18_0.2.2-rc.4.md](full/dsh/2026-11-18_0.2.2-rc.4.md)。_（仅基于只读 git 标签 diff 与官方 Release 元数据核验，未做运行时验证。）_

### 核心亮点

- **DeepSeek 流式内容安全拒答 `CONTENT_REFUSED` 与计费用量保留** _（官方说明：「优化模型请求收到异常消息响应时的表现」）_：DeepSeek Messages 流以 `stop_reason: "refusal"` 结束时，现先产出拒答前已计费的 token 用量，再抛出不可重试的新错误码 `CONTENT_REFUSED`（保留 `stop_details.explanation`，Web 端撤回半截草稿，Session 将其保存在模型历史之外的 `assistant/attempt` 中），不再中途误抛 `MALFORMED_RESPONSE` 并丢弃用量（含 `1` 条 SDK/事件错误码升级指南；请求侧未发送 `safety_check` 字段）。
- **桌面端 LiveShare 隧道子进程透传 `ELECTRON_RUN_AS_NODE`** _（官方说明：「修复 LiveShare 在桌面端无法创建分享的问题」）_：`@deepseek-ai/dsh-experimental-liveshare` 启动 owner-gateway 网关子进程（`process.execPath`）时转发宿主 `ELECTRON_RUN_AS_NODE`，使 `mac` / `win` Electron 桌面端以 Node 模式运行子进程而非作为重复 GUI 实例被单实例锁秒退，并同步修复 `owner-credential-horizon.host.spec.ts` 硬编码日期过期问题。

---

## 前序预发布版：0.2.2-rc.3（2026-11-13）

承接 `dsh-v0.2.2-rc.2`（`2026-11-11`）的预发布候选版本（`dsh-v0.2.2-rc.3`，`2026-11-13 13:26:07 UTC+8`）。亮点、新功能、修复与破坏性变化见 [dsh/2026-11-13_0.2.2-rc.3.md](dsh/2026-11-13_0.2.2-rc.3.md)，完整技术细节见 [full/dsh/2026-11-13_0.2.2-rc.3.md](full/dsh/2026-11-13_0.2.2-rc.3.md)。

### 核心亮点

- **DeepSeek 官网对话导出导入器（实验性插件）**：新增可选实验性插件「DeepSeek 会话导入」（在 **插件 → 更多 → 实验性插件** 中开启），在「新建会话」右侧提供上传按钮，支持将 `chat.deepseek.com` 导出的 `deepseek_data-*.zip` 导入至指定工作区并转为可续聊的原生 DSH 会话（保留标题、时间戳、思考过程、网页搜索/抓取卡片、阅读链接与图片附件，支持 8 种语言），并配套开放 `sidebar.session.action` 侧栏扩展槽与可复用的 `workspace.picker` 工作区选择器工厂。
- **会话日志 ZIP 导出容错增强**：导出会话日志 ZIP 时遇到已删除、合成文件卡片或无效附件引用不再中断整个下载，改为写入 `attachments-missing.txt` 清单并在提前取消时自动关闭所有活动文件流。
- **Windows 更新重启目录占用与 CI 沙箱修复**：修复 Windows NSIS 更新重启状态窗占用安装目录导致替换受阻的问题，为 Linux CI 接入经 SHA-256 校验的 `bubblewrap` 归档缓存与有界下载，且相较 `0.2.2-rc.2` **无破坏性变化**。
