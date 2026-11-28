# Antigravity 最新版本改动

[English](../../full/antigravity.md) | 简体中文 · [精简版 (Highlight)](../antigravity.md) | **完整详情 (Full Detail)**

> 五端（`mac`、`win`、`ubuntu`、`ios`、`android`）技术版本索引（覆盖 **Antigravity Desktop / Hub `2.36.0`** 与 **Antigravity IDE `2.8.0`** 两条独立桌面产品线）见 [antigravity/README.md](antigravity/README.md)。

## Antigravity Desktop（Hub）2.36.0（2026-11-27）

详细改动见 [antigravity/2026-11-27_2.36.0.md](antigravity/2026-11-27_2.36.0.md)。

- **壳层纯版本号递增与 Go `language_server` rebase 更新（`2.36.0-5596661662220288`，`cl/1031268331`，基线 `1030397722`）**
  - Electron `44.9.1` 壳层连续第三版纯版本号变更：`app.asar`（`1,167` 文件、`20,690,656` B，SHA-256 `e0571155… → d2bc25ea…`，六端逐字节一致，首次覆盖 `windows-arm64`［`$PLUGINSDIR/app-arm64.7z`］）仅 `package.json` 版本号更新；macOS `agy-desktop-rtc` 增大 `+22,592` B（`10,573,520 → 10,596,112` B）。
  - `language_server` rebase（`darwin-arm` `196,625,792` B `−717,648` B、`linux-x64` `236,638,920` B `+6.6` MB、`linux-arm` `222,450,352` B；`strings` `+58,899 / −58,470`），Connect-RPC 增至 `372`（`+34`，并列新服务 `JetskiRemoteAgentProxyService`，涵盖 Agent 生命周期/文件权限/Sidecar/Trigger/Blueprint），新增 RemoteControl **Mesh** 传输（`remotecontrol/meshclient`，WebChannel 回退）、`policyguardian/sensitivity`（`+442` 引用）、Proctor J1/C8 供应链与防火墙规则（查询 `deps.dev`/GitHub）、`getsentry/sentry_go`（`523` 符号）、`+4` 具名开关（`225 → 231` 对，含 `enable-resume-conversations-from-restart` 与 `enable-sidecar-pill-auto-open`）及 `gemini-4-neonccpa → gemini-4-neondefault`（模型 `44`、`*ToolConfig` `65` 与 CUA `19` 零变化）。
- **官方 `v2.36.0` 说明（`13` 项改进 + `26` 项修复）与六端覆盖边界**
  - 远程智能体云端自动化授权（RPC/服务面）与 `~/.agents/skills` 自定义技能发现（`~/.gemini` 优先）获 `language_server` 静态实证；标题级 UI/Auto mode/语音上下文/MCP OAuth 离线访问及 `26` 项修复主要归属 Hub webapp/服务端，静态不可证。四端 macOS/Linux 均核实为 `cl/1031268331`；**Windows `x64`/`arm64` 两端 `language_server` PE 仍未覆盖**，签名仅做离线 CMS 链解析。

---

## 前序 Hub 版本：2.35.2（2026-11-25，包 `Last-Modified`）

详细改动见 [antigravity/2026-11-25_2.35.2.md](antigravity/2026-11-25_2.35.2.md)。

- **相对 `2.35.1` 的纯维护版（`2.35.2-4585983447007232`）—— 壳层仅版本号变更 + 后端同大小重编译**
  - `app.asar`（`1,167` 文件、`20,690,656` B，SHA-256 `9f0aad72… → e0571155…`，`darwin-arm`/`darwin-x64`/`linux-x64`/`linux-arm`［`Antigravity-arm64/`］及 Windows 内嵌五端逐字节一致）唯一变化为 `package.json` 版本号升至 `2.35.2`，`dist/`、`node_modules/`、`7` 项依赖与 `chrome-devtools-mcp` `1.12.0` 零变动（不归因 `2.35.0`/`2.35.1` 能力）。
  - Go `language_server` 同大小重编译（`darwin-arm` `197,343,440` B、`linux-x64` `230,003,400` B；`linux-arm` 点测 `216,421,040` B），沿用基线 `1027784732`（`cl/1029194470 → cl/1029311855`，间隔约 2.5 小时；`strings` `+6,466 / −6,307` 全为 `.rodata`/闭包噪声），RPC（`338`）、开关对（`225`）、模型（`44`）、`*ToolConfig`（`65`）与 CUA（`19`）五口径零 diff，零新增语义话术；macOS 四件副件同大小重编译。
- **官方唯一修复（*「Switch models while a turn is running」*）与覆盖边界**
  - 既有 `2026-11-26` 快照记录的官方唯一修复属 Hub webapp UI，**包内静态不可证**（亦无官方未公告的包内新能力）。`cl/1029311855` 在四端 macOS/Linux 均一致（`darwin-x64`/`linux-arm` 仅点测、未做全量 `strings` diff）；**Windows 端 `language_server` PE/CL 仍未覆盖**，签名仅做离线 CMS 链解析。

---

## 前序 Hub 版本：2.35.1（2026-11-25，包 `Last-Modified`）

详细改动见 [antigravity/2026-11-25_2.35.1.md](antigravity/2026-11-25_2.35.1.md)。

- **段二（`2.35.0` → `2.35.1`，构建号 `4615540875067392`）—— 维护重编译与官方 `v2.35.1` 包内零落点**
  - `app.asar`（`1,167` 文件、`20,690,656` B，SHA-256 `99ff7f6c… → 9f0aad72…`，`darwin-arm`/`linux-x64`/Windows 内嵌三端逐字节一致）相对 `2.35.0` 仅 `package.json` 版本号升至 `2.35.1`；Go `language_server` 同基线（`1027784732`）重编译（`cl/1028447422 → cl/1029194470`，`darwin-arm` `+16,528` B、`linux-x64` 同 CL；去重 `strings` `+799 / −792` 全为构建元数据/闭包/rodata 噪声），RPC（`338`）、开关对（`225`）、模型（`44`）、`*ToolConfig`（`65`）与 CUA（`19`）五口径零 diff，macOS 副件同大小重编译。既有 `2026-11-25` 快照记录的官方 `v2.35.1` 三条变更在两段安装包内均**无静态落点**（Hub webapp/运行时侧）。
- **段一（`2.34.0` → `2.35.0`，构建号 `6394266482769920`）—— 壳层重组与 `language_server` rebase 重构（归属 `2.35.0`，不归因 `2.35.1`）**
  - 壳层新增 `appChannel.js`、`customWindowControls.js`、`computer/idleProbe.js`、`computer/permissionGuide.js` 与 macOS `bin/agy-desktop-rtc`（`10,573,520` B），移出 `computer/{hud,hudAgents,hudState}.js`（`chrome-devtools-mcp` `1.12.0` 不变）。`language_server` rebase（`1025139341 → 1027784732`，`cl/1026637980 → cl/1028447422`，`+428,288` B，`strings` `+30,776 / −29,097`）收缩 RPC `380 → 338`（移除 `GetUserMemories`/`GetKnowledgeItems`/`GetUnleashData`/`ImportFromCursor` 等），新增 `AgentRemoteSession` CRUD/订阅/reaction、`ListPluginPermissionGrants`/`RevokePluginPermissionGrant`、`ListRemoteAgents`、`agentapi` 会话管理 CLI、`openai/openai_go`（`10,475` 符号）、`enable-mcp-apps`/orchestrator/swarm 开关（`204 → 225`）及模型资格后缀重排（`42 → 44`）。Windows `language_server` PE/CL 与 `darwin-x64` 未覆盖；签名仅做离线 CMS 链解析。

---

## Antigravity IDE 2.8.0（2026-11-19）

详细改动见 [antigravity/2026-11-19_ide-2.8.0.md](antigravity/2026-11-19_ide-2.8.0.md)。

- **实质代码高度收敛于 `extensions/agy`（`1.11.0` → `1.12.0`，`+66.9` KB）与三连版冻结基座（`2.8.0-6733682917113856`）**
  - 跨 `darwin-arm`（主分析）、`linux-x64` 与 `windows-x64`（Code OSS `1.107.0` / `commit: 8dc5315a` / `languageServerCL: 1025045237` / Electron `39.2.3`），全部业务代码变更集中在 `extensions/agy/{vscode/extension.js (+52,460 B / +74 字面量 / 0 删除), bridge.js (+14,132 B), package.json (+660 B)}` 与 macOS 独有 MSAL 重编译（`libmsalruntime.dylib`、`msal-node-runtime.node`）；`out/`（`27` 文件）、`out/jetskiAgent/main.js`（`11,837,046` B，剥注释 `b674d91f…`）、`351` 方法 `LanguageServerService` 描述符（`a9f7b6f4…`）、`agy/dist/extension.js`（`37` B）、`node_modules/`（`2,628` 尾注释差异）与 hub 启动脚手架连续三版冻结。
- **后端管理面增强、`SwitchLoginToAuthCode`、自定义 CA / 代理与 `+26` Iframe Schema**
  - 新增周期更新检查（`ANTIGRAVITY_PERIODIC_UPDATE_CHECK_INTERVAL_MS`、`ANTIGRAVITY_STALE_SERVER_UPGRADE_PROMPT_MS`、`"Restart Agent Server"`、`upgrade_prompt` 遥测）+ `11` 个安装决策遥测码（`downgrade_skipped`、`same_version_rebuild`、`startup_background`、`check_deferred`、`staged_promoted` 等）、直连 `POST …/LanguageServerService/SwitchLoginToAuthCode`（冻结 `351` 描述符外方法，指向运行时 `agy`）+ `ANTIGRAVITY_REMOTE_OOB_AUTH` 与 `6` 类远端目标、`antigravity.caCertificates` + `geminicodeassist` 双前缀 CA 及 VS Code `http.proxy*`/代理环境变量读取、Manifest `findInConversation` `ctrl+f`/`cmd+f`，以及两侧同步扩容的 `+26` 个 iframe Schema（`bridge.js` `2,137 → 2,163`：`Resolved*` 定制解析、`HarnessMessageStep`/实验步骤、模型目录、内容层）。
- **官方 `v2.8.0` 说明（`7` 项改进 + `5` 项修复）核对**
  - `4` 项在 `extensions/agy/` 包内实证、`3` 项获静态线索或命令入口实证，另有 `3` 项（*60s 就绪超时*、*Windows 注销恢复死循环修复*、*Windows 多窗口通知聚焦修复*）不在 IDE 静态包面内（归属运行时 `agy` CLI 或远程 webview）。

---

## 前序补丁构建（Hub）：2.32.2（2026-11-17，包 `Last-Modified`）

详细改动见 [antigravity/2026-11-17_2.32.2.md](antigravity/2026-11-17_2.32.2.md)。

- **Electron 壳层仅版本号更新及跨端 `app.asar` 核验（`2.32.1` → `2.32.2`，构建号 `4665802025205760`）**
  - 基于官方 `darwin-arm` 双 DMG 全量解包比对确认：`app.asar`（`1,068` 个文件、`18,668,119` B，归档 `5,656,861` B，SHA-256 `5b493943… → 056ba838…`，Electron `44.9.1`，`7` 项依赖）唯一变化为 `package.json` 版本号升至 `2.32.2`，`app.asar.unpacked`（`chrome-devtools-mcp` `1.9.0`）在 `darwin-arm` 与 `linux-x64` 两端均零差异（`windows-x64` 内嵌 `app.asar` 与 `376` 条 RPC 仅来自点测而非全量解包对比，`darwin-x64` 仅 HTTP `HEAD` 探测；未运行程序且未联网验签）。
- **Go `language_server` 静态重编译（`cl/1021296516` → `cl/1022991777`）与抽取文本清单不变**
  - 重编译 `language_server`（`darwin-arm`：`205,328,064 → 205,328,032` B，去重 `strings` `+765 / −703`；`linux-x64`：`239,952,296` B 同大小，去重 `strings` `+194 / −239`）除构建元数据更新外仅检出 `cel.WithDefaultHTTPTimeout` → `cel.withDefaultCELHTTPTimeout` 改名与 3 个 `telemetryclient`/`clearcutLogger` `Shutdown` 闭包符号消失（属静态重编译证据，不臆造功能修复）；静态抽取的 `376` 条 RPC、`189` 对特性开关、`65` 项 `*ToolConfig`、`9` 档 `gemini-4-*` 模型串以及 `9,000` B `run_workflow` 文档和 `agy_tool_safety` 块均无变化（仅代表静态文本清单不变，非运行时或服务端证明；外部 `10%` rollout 仅属早期瞬态采样，不代表全量发布）。

---

## 前序补丁构建（Hub）：2.32.1（2026-11-14）

详细改动见 [antigravity/2026-11-14_2.32.1.md](antigravity/2026-11-14_2.32.1.md)。

- **默认模型目录新增 `Gemini 4 Hydrogen` 档位与后端重编译（`2.32.0` → `2.32.1`）**
  - `language_server` 同体积重编译（`239,952,296` B，`cl/1020489536 → cl/1021296516`，SHA-256 `b9a8f18d… → 4847eb00…`，去重 `strings` 差集仅 `+1,085 / −1,115`），唯一语义变更为在内置默认模型目录中新增 `gemini-4-hydrogen-{low,medium,high}`（显示名 `Gemini 4 Hydrogen (High)`，符号 `defaultmodels.Gemini4Hydrogen`，指标 `gemini-4-hydrogenaicode_latency_ms`）。
- **Electron 壳层逐字节一致且协议/开关/工具零漂移**
  - `app.asar`（`dist/` + `node_modules/`，`1,068` 个文件、`18,668,119` B，Electron `44.9.1`，`7` 项依赖）及解包 `chrome-devtools-mcp` `1.9.0` 除 `package.json` 版本号升至 `2.32.1` 外与 `2.32.0` 逐字节一致；`375` 个真实 `LanguageServerService` RPC、`112` 个特性开关、`49` 类 `*ToolConfig` 与 `agy_tool_safety` 白名单零变化。

---

## 近期主版本基线（Hub）：2.32.0（2026-11-13）

详细改动见 [antigravity/2026-11-13_2.32.0.md](antigravity/2026-11-13_2.32.0.md)。

- **体积与构建基线（`2.31.2` → `2.32.0`；三平面 MCP 基线保持不变）**
  - 维持 Electron `44.9.1`、`CHROME_DEVTOOLS_MCP_JS` 注入、内置 `chrome_devtools` `18 + 1` 工具集及逐字节相同的随包 `chrome-devtools-mcp` `1.9.0`；`app.asar/dist` 顶层由 `59` 扩至 `70` 项并新增 `30` 文件的 `dist/remote/`，Go `language_server` 由 `206.8` MB 增至 `240.0` MB（`+33,124,376` B / `+31.6` MiB，`cl/1020489536`，约 90% 增量位于 `.noptrdata` protobuf 描述符）。
- **Electron 壳层：SSH 远程开发栈、Catcher 三层视图、跨站凭据剥离与移除 `shell-env`**
  - 新增 `30` 文件 SSH 远程开发栈（`--ssh-host=`、`--agy-backend=ssh`、`bootstrapScript.js` 随机 secret marker 引导协议、断连存活 `--persistent_mode` 远端 LS、`27` 通道 `remoteIpcChannels.js` 白名单 + `localOnly` 纵深拦截）与 `base UI + clip view + catcher overlay` 三层访客视图栈（`9` 条 `wcv:catcher-*` 手势通道）。
  - 新增跨站子框架凭据剥离（`guestCrossSiteCredentials.js` + 单管线 `guestRequestHeaders.js`）与访客 UA `Electron/<ver>` 清洗（`stripGuestElectronUserAgentToken`，含 Google BotGuard 特判）；移除 `shell-env ^4.0.3`（依赖 `8 → 7`，`node_modules` `−20` 包）改用自研 `loginShellEnv*.js` 以根治 `execa` 重置 `SIGTERM` 导致退出残留 `language_server` 的问题，并补齐 `StorageFullError` 与 `EPERM`/`EACCES` 重命名容错。
- **Go `language_server`：`computer` 桌面控制插件、`CloneGitHubRepo` RPC、`+58` 特性开关与 Dynamic Workflows 核验**
  - 新增受门控的 `cortex/ext/plugins/computer`（符号 `0 → 896`，约 40 个 Go 文件、`ComputerViewerService`、含 `AX_*` 在内的 `18` 项 `COMPUTER_ACTION_TYPE_*` 动作及 `computer` / `browser_eval_gate` 内置代理）、`LanguageServerService/CloneGitHubRepo`（真实 RPC `374 → 375`）、`remote_plugin` 族、`WatchTopic` `AgentRemoteSessionMessages`、`openaiResponsesConverter`、登录/支付页联合阻断话术及 `+58` 个特性开关（`54 → 112`）；静态审计证实 `run_workflow` 与 `embeddedpython` 在 `2.31.2` 已逐字节存在，本次连同官方 `11` 项改进与 `13` 项修复一并开放上线。

---

## 前序 IDE 版本：Antigravity IDE 2.7.0（发布时间未确认；构建于 2026-11-11）

详细改动见 [antigravity/2026-11-11_ide-2.7.0.md](antigravity/2026-11-11_ide-2.7.0.md)。_（发布时间未确认；`product.json` 中的北京时间 `2026-11-11 12:46` / `2026-11-11T04:46:27.114Z` 是构建时间，不是发布时间。）_

- **变更高度收敛于 `extensions/agy`（`0.0.1` → `1.11.0`；仅 4 个实质变更文件）**
  - 跨 `linux-x64`、`windows-x64`、`darwin-arm` 三端共 6 个安装包（Code OSS `1.107.0` / Electron `39.2.3`）复核确证：`2.6.0` → `2.7.0` 的全部实质代码变更仅位于 `extensions/agy/{package.json, package.json.patch, vscode/extension.js (+90,987 B), bridge.js (+9,333 B)}`；`out/`、`out/jetskiAgent/`（`11.8 MB`）、`node_modules/` 与其余 `101` 项内置扩展仅存在末尾 37 字节 sourcemap commit 哈希轮换（`9e3a5da5… → 71bedb45…`）。
- **三态登录状态栏、回环 `GetAuthStatus` 探测、Diff 命令重排与 `+35` Iframe Schema**
  - 新增三态登录状态栏（`signedOut` 直绑 `antigravity.signIn`，`unknown`/`signedIn` 绑 `antigravity.statusMenu`）、跨窗口密钥同步 `antigravity.authSync`、窗口打开 5 秒后回环探测 `POST /exa.language_server_pb.LanguageServerService/GetAuthStatus`（带 `x-codeium-csrf-token`）、GCP 条款标识 `isGcpTos`、命令 `25 → 33`（拆分单文件 *in Current File* 与跨文件 *in All Files* 的 `acceptAllChanges`/`rejectAllChanges`）、`antigravity.isAntigravityIde` 反馈与 webview 宿主分流（`productId` `5372208`），以及两侧同步新增的 `35` 个 iframe 消息 Schema（`ManageTask`、媒体处理、浏览器录制）。
- **云开发环境（CDE）`/usr/bin/agy` 优先路径与端口冲突重试**
  - 新增 `CDE_PREINSTALLED_BINARY_PATH = "/usr/bin/agy"`（检测 `GOOGLE_CLOUD_WORKSTATIONS` / `CLOUD_SHELL` 优先复用预装 CLI）及 `agy --hub` 启动 `canRetryPortCollision` 端口碰撞重试；内联 `351` 方法 `LanguageServerService` 描述符（`327` unary + `23` server-streaming + `1` client-streaming）与 `45` 类 `*ToolConfigSchema` 保持冻结。

---

## Antigravity Desktop（Hub）2.31.2（2026-11-12）

详细改动见 [antigravity/2026-11-12_2.31.2.md](antigravity/2026-11-12_2.31.2.md)。

### 版本概览

Antigravity 桌面端（`antigravity-hub`，`productName: "Antigravity"`，`--subclient_type hub`）`2.31.2` 将 Electron 宿主自 `44.5.1`（`2.29.0`，构建于 `2026-11-04`）升级至 `44.9.1`，Go 单体后端 `language_server`（`third_party/jetski/cortex/*` + 静态内嵌 Rust `ripgrep`，`go1.28-20261102-RC00 cl/1012564305`）由 `195.9` MB 扩容至 `206.8` MB，同时保持「Electron 瘦壳 `dist/languageServer.js` + 内置 `chrome_devtools` 18 工具注入 + 随包 `chrome-devtools-mcp` `1.9.0`」三平面核心接线与 `2.29.0` 逐字节一致。

### Electron 壳层与 Guest WebMCP 桥（`dist/` `37 → 56` 个文件）

- **CDP Guest WebMCP 桥（`dist/` 含 `mcp` 文件数 `1 → 6`）**：
  - 新增 `dist/guestWebMcpController.js`（`GuestWebMcpController`，默认 `enabled = false`，注释明确 *"Nothing is injected into guests"*），通过 CDP `WebMCP.{enable,disable,invokeTool,cancelInvocation}` 与事件 `WebMCP.{toolsAdded,toolsRemoved,toolResponded}` 消费内置浏览器网页通过 `window.modelcontextprotocol` 自声明的工具。
  - 配套在 `dist/wcvBrowserRegistry.js:336-354` 开启 `enableBlinkFeatures: 'WebMCP'`，在 `dist/ipcHandlers.js:838-850` 新增 4 条 `webview:webmcp-*` IPC 通道，在 `dist/preload.js:261-264` 暴露渲染端桥接接口，并在 `dist/wcvIpcHandlers.js:137-142` 的 `wcv:acquire` 中实施仅限 Hub 主框架授权的 `webmcpEnabled` 门控。
  - 安全防线涵盖单次结果 `64` KiB 截断、超时钳制 `1s–120s`（默认 `30s`）、仅限 HTTPS 或 loopback（`isSecureWebMcpUrl`），以及 `PROTECTED_PAYMENT_HOSTS` 黑名单（拦截 Stripe、PayPal、Adyen、Google Pay 等支付与身份认证域，返回 `IDP_OR_PAYMENT_BLOCKED`）。
- **本地调试端口文件权限加固**：
  - `dist/main.js:244` 新增调用 `tightenActivePortPermissions(userData, DevToolsActivePort)`（实现于 `dist/paths.js:92-110`），将 `userDataDir` 收紧至 `0o700`、`DevToolsActivePort` 收紧至 `0o600`（保留 `--remote-debugging-port=0`）。

### Go `language_server` 原生工具注册表、安全链与 Connect-RPC（`~50 → ~60` 个工具）

- **原生 Swarm、规划门控、持久终端与 Notebook 演进**：
  - 主注册表 `ToolConverter` 类型由 `32` 增至 `35`，`cortex_pb.*ToolConfig` 由 `45` 增至 `49`（新增 `FileEdit`、`GrepSearch`、`ManageTask`、`RunWorkflow`），在 `invopop/jsonschema` 结构体反射（`exa.chat_pb.ChatToolDefinition`）之外新增 `ParameterSchema() encoding/json/jsontext.Value` 编译期 Schema 校验路径（`core.compileParameterSchema`）。
  - 移除静态字面模板 `tool_schema_swarm_manage.json`，上线 `cortex/core/native_swarm/` 原生协同工具族（`manage_swarm`、`post_message`、`read_board`、`swarm_wait`，含 `join` 支持）。
  - 新增 `planexecute` `enter`/`exit` 门控工具、`update_focus`、`run_workflow`、`list_plugin_accounts`、`search_marketplace` 与 `notebook_execution`，将 `edit_notebook` 对外改名为 `notebook_edit`，为 `run_command` 新增 `RunPersistent` / `RequestedTerminalID` / `NotificationTimeoutSeconds`，重写 `execute_browser_javascript`（`observation` + `intention` + `script` + `urls`，面向 `webview_browser`），并引入包含 14 个工具的并行 `oneharness` 框架。
- **威胁预筛监视器、`StartMcpOAuthSignIn` 与回退启动器泛化**：
  - 在保持 `agy_tool_safety`（`version: "5a260837"`）`30` 项 `allowed_tools`、`43` 条 `allowed_commands` 与 `3` 项 `allowed_tool_actions` 白名单不变的基础上，新增轻量 LLM 威胁预筛器 `sir_flash_lite`（`MODEL_TIER_FLASH_LITE`，`mode: LOG`，覆盖威胁信号 A–M）。
  - Connect-RPC `LanguageServerService` 由 `365` 增至 `374` 个方法，新增 `StartMcpOAuthSignIn`（与 `CompleteMcpOAuth`、`DisconnectMcpOAuth`、`StartPluginAuthSignIn` 并列支持 MCP Server 直连 OAuth 登录），并将内嵌 `chrome-devtools-mcp` 回退启动脚本中的 Playwright Node 路径由固定 `ms-playwright-go/1.57.0/node` 泛化为通配 `ms-playwright-go/*/node`。
