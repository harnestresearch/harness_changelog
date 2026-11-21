# Cursor 最新版本改动

[English](../../full/cursor.md) | 简体中文 · [精简版 (Highlight)](../cursor.md) | **完整详情 (Full Detail)**

> 五端（`mac`、`win`、`ubuntu`、`ios`、`android`）完整 446 个历史版本索引（含 426 个桌面版本至 `3.30.14` 与 20 个 iOS 版本至 `ios-1.17.0`；独立 Android 端暂未发布）见 [cursor/README.md](cursor/README.md)。

## 3.30.14（2026-11-14）

详细改动见 [cursor/2026-11-14_3.30.14.md](cursor/2026-11-14_3.30.14.md)。_（CDN 发布时间：北京时间 `2026-11-14 04:27` / `2026-11-13 20:27:26` GMT；三端同一生产构建 `5f54c817…`；官方 changelog 尚未收录。）_

- **默认关闭的「Deploy App」在线应用发布（Unary RPC `+1`；特性开关 `+2`；动态配置 `+5`）**
  - 新增全协议唯一新方法 `AppPublishService.getAppsEligibility`（Unary RPC `2,555 → 2,556`，消息 `5,923 → 5,925`）、默认关闭的 `cloud_agent_apps` 与 `glass_deploy_with_cursor_pill`、`glass_apps_growth_config`（部署意图关键词表与云端仓库根 `publish-app` 提示词）、`molten` `apps-publish-CtW5oKQc.js` 发布提案确认流与状态机（`submitting`/`published`/`refused`）及 `dev-server-open.ts`/`preview-card.tsx`/`forwarded-port.ts`，以及 `21` 条桌面 NLS 文案（工程上云时明确排除依赖、构建产物与 `.env` 文件）。
- **守护进程仓库路径 Glob 规则、调用窗口识别与 `SideChatInfo` 子代理字段**
  - `daemon.cjs`（`+4.2 KB`）新增 `../local-exec/dist/services/team-repo-rules.js`，将 `getTeamRepos()` 团队黑白名单从整仓 URL 匹配细化为默认阻断（fail-closed）的 `{url, patterns[]}` Glob 规则（`picomatch` `{dot: true}` + `2,048` 项 LRU 缓存、支持 `*` 通配仓与 `org-*` URL 通配、`inCursorDataDir` 豁免），并新增 `src/identity/caller-window.ts`（解析 `x-cursor-client-layout` / `x-cursor-glass-renderer` 标记 `isGlassRoot`）、`SideChatInfo.subagent_type`（`no:3`）及 MCP placement 路由错误分类（`needs_auth`/`not_reachable`/`tool_not_found`）。
- **主进程 `grokConfigFiles.js`、Electron `43.8.9` 升级与冻结的工具/远控/安全面**
  - `out/main.js` 新增跨平台模块 `grokConfigFiles.js` 读取 `GROK_HOME` 或 `~/.grok/{managed_config,config,requirements}.toml`、校验 `trace_upload_credentials_file`（绝对路径且 `≤64 KB`）并支持提交 Grok 反馈；三端同步升级 Electron `43.8.4 → 43.8.9`（重编 `@parcel/watcher` 与 `tree-sitter`），`agent.v1.ToolCall`、`mcpProcessMain.js`、`cursor-mcp`、Remote Control（`17` + `59` RPC、`pairing_proof`）、`x-cursor-checksum` 与窗口加固计数均零变化。

---

## 上一版本：3.30.8（2026-11-12）

详细改动见 [cursor/2026-11-12_3.30.8.md](cursor/2026-11-12_3.30.8.md)。_（安装包发布时间：Win/macOS 北京时间 `2026-11-12 06:23`，Linux 北京时间 `2026-11-12 10:26`；三端同一生产构建 `4a44c846…`；官方 changelog 尚未收录。）_

- **协议与后台安全治理扩张（Unary RPC `+111`；消息 `+200`）**
  - `DashboardService` 新增 `56` 个 RPC（Step-Up 二次认证、第三方 OAuth 应用全生命周期、`staff*` API Key 盘点、成员会话吊销、Grok 积分包计费与 Sand 出站/预算控制）；`GrokBotService` 新增 `48` 个 RPC（日历流式监听、购物车、试穿、短信绑定，配合默认关闭的 `glass_grok_build_unboxing` *"Cursor is now Grok Build"* 弹窗）；新增 QUIC 探测 `https://cursor-cdn.com/cdn-cgi/trace` 与 `voiceCallReachability.js`（`https://api.x.ai/v1/realtime`）。
- **智能体工具面与客户端 MCP 策略落地**
  - `agent.v1.ToolCall`（`72 → 74`）新增 `manage_access_tool_call`（`no:95`）与服务端下发代码兜底 `execute_tool_call`（`no:1000`，含 `rejected` 拒绝分支）；客户端新增 `McpError.policy_blocked_reason` + `mcpSurfaceAccess.js` + `mcpRepoScope.js` 落地管理员 MCP 黑白名单与跨 Worktree 状态共享；`mcpProcessMain.js` 新增 OAuth discovery `429`/`503` 退避、禁用 V8 编译缓存与备用 PowerShell 预热池，新增 `McpSuccess.mcp_app_document`、`mcp_event` 自动化触发器与 `kalshi` 连接器（移除旧 Outlook/OneDrive/Teams 屏蔽集合）。
- **远控 `pairing_proof`、`molten` Worker 与主进程加固**
  - `TrustControllerRequest` / `PendingControllerApproval` 新增 P-256 `pairing_proof` 配对证明，`AgentHostService` 扩充 `10` 个方法（`RestoreFileCheckpoints`、`ListMcpServers`、`UpdateMcpServer`、会话归档/置顶/未读及 `WatchDaemonReports`）；`molten` 新增 `ai-tracking-worker.cjs`（本地 SQLite `~/.cursor/ai-tracking/ai-code-tracking.db`），主进程新增 `27` 个模块涵盖 `airlockEngine.js`（Docker/Podman）+ `admitOrbitAirlockLocalTurn`、守护进程 `--environment-file` 严格校验后即读即删及 `6` 个空闲更新重启模块。

---

## 近期架构基线版本：3.28.7（2026-11-03）

详细改动见 [cursor/2026-11-03_3.28.7.md](cursor/2026-11-03_3.28.7.md)。

### 版本概览

Cursor Desktop `3.28.7`（commit `25b52e7`，基于 VS Code `1.128.0`）采用双工作台包架构（经典 IDE `workbench.desktop.main.js` 与独立 **Agents / Glass** 窗口 `workbench.glass.main.js`），由云端承载智能体主循环并向本地派发 **70+ 种强类型 `agent.v1.ToolCall` 客户端工具**，通过基于 ECDSA P-256 DPoP 密钥证明与 6 位配对码挑战签名的 HTTP/2 Connect 双向出站隧道（`aiserver.v1.RemoteAgentHostPresenceService`）实现 **Remote Control（「Steer from Phone」手机远程控本机）**，并延续 `3.24.x` 引入的独立 Electron `utilityProcess` MCP 沙箱宿主架构（详见 [cursor/2026-10-09_3.24.12.md](cursor/2026-10-09_3.24.12.md)）。

### Remote Control 出站中继隧道与密码学配对机制

- **「推理上云、工具留本机」混合执行模型**：
  - 在 Agents 窗口开启 Remote Control 后，智能体会话循环迁移至 Cursor 云端运行，而文件读写、Ripgrep 搜索与终端命令仍经出站隧道回落至用户本机执行，无需开放任何入站端口或 P2P 打洞；支持开启防休眠（`Keep this computer awake`）及一键将本地会话迁移至云端虚拟机（`Move to Cloud`）。
- **`aiserver.v1.RemoteAgentHostPresenceService`（17 个 Connect-RPC 方法）**：
  - 客户端主动向 `https://api2.cursor.sh` 建立 `ConnectTarget` HTTP/2 Connect 持久双向流，复用承载反向工具调用、Git 状态同步、主机注册、心跳续租、配对审批与唤醒在线状态管理。
- **ECDSA P-256 主机密钥、`x-cursor-agent-host-proof` DPoP 证明与 6 位配对码**：
  - 本机生成持久化 ECDSA P-256 密钥对并经 Electron `safeStorage`（前缀 `cursor-safe-storage:v1:`）加密存储，每次隧道与在线状态请求均签发短期 DPoP 风格 JWT 写入 `x-cursor-agent-host-proof` 请求头。
  - 手机控制端配对时展示 6 位字母数字配对码，对移动端会话与本机公钥执行挑战签名绑定。

### 网络拓扑、桌面登录流与移动端会话契约

- **多域名服务分工（`aiserver.v1.*` 与 `origin.v1.*`）**：
  - 常规 Connect-RPC 默认发往 `api2.cursor.sh`；Cursor Tab 补全与指标走 `api3.cursor.sh` 及区域节点 `api4.cursor.sh`；按隐私模式分流的 Agent 流式请求走 `agent*.api5.cursor.sh`；代码库索引与遥测走带独立 `repo42AuthToken` 的 `repo42.cursor.sh`；云端 Agent、沙箱 SCM 与托管 `cursor-origin` MCP（`https://api.origin.cursor.com/mcp`）走 `api.origin.cursor.com`；认证走 `prod.authentication.cursor.sh` 与 `authenticator.cursor.sh`。
- **Challenge/Verifier 轮询登录与自定义请求头**：
  - 桌面端登录拉起 `/loginDeepControl?challenge=...&uuid=...`（Agents 窗口附加 `&surface=glass`）并以 500 ms 间隔轮询 `/auth/poll`（辅以 `cursor://cursorAuth` 深链兜底），签发的标准三段式 JWT 存入 `safeStorage`。
  - 统一通过 `setCommonHeaders` 注入 `x-cursor-checksum`（链式 XOR 混淆时间戳 + `machineId` + 网卡 MAC 的 SHA-256）、`x-cursor-client-version`、`x-cursor-client-layout`、`x-cursor-glass-renderer`、`x-ghost-mode` 及企业策略头 `x-cursor-mdm-signin-policy`。
- **移动端会话与 iOS 灵动岛协议契约**：
  - 协议层共享 `aiserver.v1.AuthService` 的 5 个移动端专属会话 RPC（`CreateMobileSession`、`UpgradeMobileSession`、`RefreshMobileSession`、`RevokeMobileSessionFamily`、`ConvertMobileSessionToRefreshPair`）以及 `SyncLiveActivity` 与 `/api/auth/registerPushNotificationToken`，支撑官方 iOS 客户端（`co.anysphere.cursor`，要求 `iOS 26.0+`）最多同时在锁屏/灵动岛追踪 8 个并行 Agent。

### 三代并存的客户端内置工具体系（70+ 工具）

- **`agent.v1.ToolCall` 强类型联合体与 `ClientSideToolV2` 兼容层**：
  - 完整覆盖文件与检索（`read_file_v2`、`edit_file_v2` / `apply_patch`、`delete_file`、`list_dir_v2`、`ripgrep_raw_search`、`glob_file_search`、`semantic_search_full`、`read_lints`）、受 `@anysphere/sandbox-helper`（及 Linux `cursor-sandbox-apparmor`）沙箱保护的 `run_terminal_command_v2`、多子代理集群与后台任务编排、`write_canvas` 交互画布、PR **Code Tour** 代码导览、`computer_use` 及 `mcp_tool_call` / `get_mcp_tools`。
  - 内置 `PromptContextUsageTree` 分层统计系统提示词、规则、文件与工具结果的上下文 Token 消耗。

---

## 近期架构基线版本：3.24.12（2026-10-09）

详细改动见 [cursor/2026-10-09_3.24.12.md](cursor/2026-10-09_3.24.12.md)。

### 版本概览

Cursor Desktop `3.24.12` 奠定了 Cursor 3.x 的多进程 MCP（Model Context Protocol）核心架构：外部 MCP 服务器统一交由独立的 Electron `utilityProcess`（`out/vs/code/electron-utility/mcpProcess/mcpProcessMain.js`）托管并结合 `@anysphere/sandbox-helper` 实施沙箱隔离；同时通过内部扩展通道 `mcp-provider://` 在进程内原生提供 `cursor-ide-browser`（16 个工具）与 `cursor-computer-use`（17 个工具）两大官方自动化服务。

### 独立 `utilityProcess` MCP 宿主与协议握手

- **辅助进程隔离与沙箱化子进程派生**：
  - 主进程拉起共享的 `mcpProcessMain.js`（Electron `utilityProcess`），通过 IPC 与各工作台窗口通信。
  - 基于 `@modelcontextprotocol/sdk@1.25.1` 支持三种客户端传输：`StdioClientTransport`（按策略调用 `@anysphere/sandbox-helper` 施加文件与网络沙箱）、`StreamableHTTPClientTransport`（默认开启旧版 SSE 自动降级与 404 会话墓碑机制）以及 `SSEClientTransport`。
- **协议版本协商与 MCP Apps 交互式 UI 扩展**：
  - `initialize` 固定请求 `protocolVersion: "2025-11-25"`、`clientInfo: { name: "cursor-vscode", version: "1.0.0" }`（HTTP 传输 `User-Agent` 携带真实 `Cursor/<version> (<platform> <arch>)`），声明能力 `{ elicitation: { form: {} }, roots: { listChanged: false }, extensions: { "io.modelcontextprotocol/ui": { mimeTypes: ["text/html;profile=mcp-app"] } } }`（刻意不开放 `sampling/createMessage`）。
  - 自动翻页拉取全部 `tools/list`（`nextCursor`），支持基于 `_meta.progressToken` 的进度超时重置，并在大文本结果超阈值时自动落盘替换为文件路径摘要。

### `mcp.json` 配置体系、OAuth 2.1 认证与安全审批

- **六层配置合并与跨端自动发现**：
  - 按优先级合并 `default`、`~/.cursor/mcp.json`（写入自动 `chmod 0600`）、`<workspaceFolder>/.cursor/mcp.json`、扩展注册、插件与 `mcp-provider://`，并支持通过 `chat.mcp.discovery.enabled` 自动发现 `<folder>/.vscode/mcp.json`、Claude Desktop `claude_desktop_config.json` 与 Windsurf `mcp_config.json`（默认标记为未信任，首次调用强制弹窗确认）。
  - 运行时支持 JSONC 注释与尾逗号容错，提供 `${ENV:-default}` 与 VS Code `${workspaceFolder}` / `${userHome}` / `${command:...}` 双阶段变量插值；`stdio` 分支支持 `{command, args, env, envFile, enabledTools}`，远程分支支持 `{url, headers, auth: {CLIENT_ID, CLIENT_SECRET, scopes}, placement: "server" | "client", enabledTools}`。
- **OAuth 2.1 自动发现与托管 REST-MCP**：
  - 支持读取 `.well-known/oauth-protected-resource` 元数据（含 `cursor_client_id`、`cursor_backend_only_token_exchange` 等扩展字段）、内置 Google Workspace / Slack / Shopify / HubSpot / X 等静态 OAuth 配置，监听 `cursor://anysphere.cursor-mcp/oauth/return` 与本地回环端口回调，并对 `https://api.cursor.com/rest-mcp/<provider>/mcp` 及内置 `cursor-origin` 自动注入 `x-cursor-auth` 鉴权头。
- **项目级配置哈希重审批与权限白名单**：
  - 对项目级 `.cursor/mcp.json` 条目计算 16 位配置哈希（`<identifier>:<hash16>` 存入 `approvedProjectMcpServers`），仓库内配置一旦变更立即自动禁用并要求用户重新审批。
  - `ComposerDecisionsService` 综合评估 `composerState.mcpAllowedTools`（支持 `*` 通配符的 `serverId:toolName`）、`permissions.json`（自动将导入的 `mcp__server__tool` 转换为 `MCP:<toolName>`）、`cursor/requiresConfirmation` 注解与企业级 `allowedMcpConfiguration` 策略；在 `agent.v1.AgentRunRequest` 中以 `${serverIdentifier}-${toolName}` 命名打包 `McpToolDefinition`。

### 内置官方扩展 MCP 服务

- **`cursor-ide-browser`（16 个 `browser_*` 工具 + CDP）**：
  - 通过 `mcp-provider://cursor-ide-browser` 进程内注册，提供页面导航（`browser_navigate`、`browser_navigate_back`、`browser_reload`）、状态观测（`browser_snapshot`、`browser_take_screenshot`、`browser_console_messages`、`browser_network_requests`）、交互控制（`browser_click`、`browser_type`、`browser_hover`、`browser_drag`、`browser_select_option`、`browser_press_key`、`browser_wait_for`、`browser_resize`）与标签页管理（`browser_tabs`）。
- **`cursor-computer-use`（17 个 `computer_*` 工具，支持 macOS 与 Windows）**：
  - 通过 `mcp-provider://cursor-computer-use` 进程内注册，提供涵盖屏幕/窗口截图、光标移动、单双击/右键/中键、拖拽、滚动、文本输入、组合快捷键、光标坐标查询与等待同步的 17 项原生桌面操控工具。
