# WorkBuddy 最新版本改动

[English](../../full/workbuddy.md) | 简体中文 · [精简版 (Highlight)](../workbuddy.md) | **完整详情 (Full Detail)**

> 五端（`mac`、`win`、`ubuntu`、`ios`、`android`）完整 133 个历史版本索引（国际版桌面正式版 `5.9.4`、国内版灰度 `5.11.0`、iOS `2.9.0`、Android `2.9.1`）见 [workbuddy/README.md](workbuddy/README.md)。

## 5.9.4（2026-10-29，国际版桌面正式版）

详细改动见 [workbuddy/2026-10-29_5.9.4.md](workbuddy/2026-10-29_5.9.4.md)。

### 版本概览

WorkBuddy Desktop `5.9.4`（构建号 `5.9.4.42593613`，commit `fa0a0901`）基于 `@genie/workbuddy-desktop` Electron 架构，内置 `main/server.js` 应用服务层并注册 **28 个内置 MCP 工具**（支持 `defer_loading` 延迟下发与敏感凭据结果自动脱敏），同时集成 `ClientToolRegistry`（`wb-client:*`）、内嵌 `codebuddy-lite-wb.mjs` CLI 与 `deep-research.workflow.js` 深度研究工作流、`@agentclientprotocol/sdk@1.7.0` ACP 协议、约 340 个操作的 Office 文档引擎（`@tencent/tencent-docs-ai-engine@0.2.220-wb`）、基于 Rust `im-napi.node` 的五大 IM 渠道连接器以及多后端 `llama.cpp` 本地推理运行时。

### 内置 MCP 工具面（`main/server.js` — 共 28 个工具）

所有内置工具通过工厂函数构造并经 `workbuddyConnector.registerBuiltinTool({...tool, defer_loading})` 注入会话，通过标准 MCP JSON-RPC（`tools/list` / `tools/call`）向模型暴露，支持 `promptCacheStability: "stable"` 提示词缓存标记、`isAvailable(ctx)` 会话许可门控及 `sensitiveResultPolicy: "automatic-protection"` 自动结果脱敏：

- **产物呈现与生成式交互 UI（3 个）**：
  - `present_files`（统一以产物卡片或内置浏览器打开文件与 URL，强制 `.genie` 条目排在末尾）、`show_widget`（内联渲染裸 SVG/HTML 交互图表与组件，约定 `0 0 680` 视口与渐进式 `loading_messages`）以及 `widget_guidelines`（按需拉取 `diagram/mockup/interactive/art/chart` 设计规范）。
- **深度研究、云记忆与企业知识检索（3 个）**：
  - `domain_search`（委托远程子代理执行多步垂直领域研究）、`conversation_search`（支持 ISO-8601 时间范围的跨会话历史记忆检索，随云记忆开关动态增删）以及 `knowledge_search`（检索用户有权限的 `workbuddy_library`、`ima`、`tencent_docs`、`tencent_meeting`、`tencent_drive` 内部资料，支持创建/更新时间过滤）。
- **连接器、专家与技能全生命周期管理（7 个，默认 `defer_loading: true`）**：
  - `search_plugins`（检索 `connector` / `expert`）、`suggest_plugin_install`（向用户展示 1–3 个内联安装推荐卡片，严格校验最近一次搜索 ID）、`list_installed_plugins`、`reconnect_plugin`、`uninstall_plugin`（合并为单次确认弹窗），以及 `search_and_install_skills` 与 `skill_management`（`list` / `disable`）。
- **定时自动化任务（2 个）**：
  - `automation_update`（支持 `list/view/create/update/delete`、RFC 5545 `rrule` 周期规则、多工作目录 `cwds`、`expertId` 与 `connectorIds`，受 `isAutomationWbSdkRefactorEnabled` 门控）与需会话投递许可的 `send_automation_result`。
- **全栈建站、托管 Serverless 云服务与小程序脚手架（4 个，`defer_loading: true`）**：
  - `workbuddy_sites_deploy`（支持发布 `node/python/go/static` 项目至 `<=32` 位自定义子域名前缀，要求 `userAskedToPublish`）、`workbuddy_sites_unpublish`、`workbuddy_cloud_service`（为 `wbapp_*` Web 或小程序项目巡检/开通含数据库、鉴权、存储与免密 LLM API 的托管 Serverless 后端）以及 `workbuddy_miniprogram_scaffold`（在可信工作区相对路径下展开原生微信小程序模板）。
- **凭据桥接、Agent Mail、IM 读取与会话辅助（9 个）**：
  - `connect_cloud_service`（静默换取 Miora 生图/生视频前置 `clientTempToken` 并自动脱敏）、`connect_open_platform`（换取 `op_xxx` 短期开放平台令牌）、`workbuddy_request_mcp_connection`（阻塞式多 MCP 服务授权卡片）、`agent_mail_upload_attachment`、`agent_mail_download_attachment`（下载附件自动去除可执行权限隔离）、`im_list_conversations`、`im_get_messages`（单次最多 50 条）、桌面端专属 `pick_location`（地图 POI 选点弹窗）与 `workbuddy_app_set_conversation_title`。

### 客户端工具注册表、内嵌引擎与原生子系统

- **`ClientToolRegistry` 与 Office 编辑器 SDK**：
  - `main/conversations.js` 维护独立的 `ClientToolRegistry`，线上标识格式为 `wb-client:<conversationId>:<providerId>:<toolId>`，返回带耗时的 `{status, error: {message, code}, duration}` 结构。
  - 内置 `@tencent/tencent-docs-ai-engine@0.2.220-wb`，提供涵盖 `doc_*`（约 120 个）、`sheet_*`（约 110 个）、`slide_*`（约 110 个）与 `smartsheet_*` 的 ~340 项原生文档编辑能力。
- **内嵌编程 CLI、深度研究工作流与 ACP 协议**：
  - 随包集成 `cli/codebuddy-lite-wb.mjs`、`deep-research.workflow.js` 及 `@agentclientprotocol/sdk@1.7.0`，由后台守护进程模块（`daemon-bootstrap.js`、`daemon-app-server-main.js`）托管生命周期。
- **多端 IM 连接器与原生 NAPI / Sidecar 模块**：
  - 原生接入企业微信（`@wecom/aibot-node-sdk@1.0.7`、`@tencent/wwapi-electron@0.1.25`）、飞书（`@larksuiteoapi/node-sdk@1.60.0`）、钉钉（`dingtalk-stream@2.1.5`）、Slack（`@slack/socket-mode@2.0.7`）与 QQ 机器人（`@tencent-connect/qqbot-connector@1.1.0`），底层由 Rust 编译的 `im-napi.node` 驱动。
  - 随包构建 `computer-use-launcher`、`wechat-copydata-decoder`、`turing-sdk`、`qimei`（`@tencent/qimei-node@1.2.2`）、`perf-metrics`、`default-open-handler` 与 `@lydell/node-pty@1.2.0-beta.14` 等原生模块。
- **本地大模型引擎、`5.9.4` 版本更新项与全平台自更新器**：
  - 支持按需下载 `llama.cpp` 本地推理后端（覆盖 CPU、CUDA、ROCm、Vulkan 与 Intel GPU 变体）。
  - `5.9.4` 版本新增日/韩/法/西/越/泰/阿 7 种界面语言、消息中心、本地 PPT 演讲者视图、系统主题跟随、基于 `high-credit-tools.json` 的生图/生视频高积分调用前确认、HTTP MCP 安全中心网络策略强约束、Gmail 增量授权与 OAuth 自动刷新、单会话本地记忆开关，并修复上下文压缩或子代理运行期间任务状态误判取消、WPS 文件锁冲突、Windows 注册表主线程阻塞、macOS 更新中断闪退与编译缓存损坏白屏问题。
  - 基于 `/v2/update` 接口提供覆盖 macOS（`darwin-arm64` / `darwin-x64`）、Windows（带 Authenticode 签名校验）及 Linux（`.deb`、AppImage 自更新及统信 UOS / 银河麒麟信创包）的自动更新机制。
