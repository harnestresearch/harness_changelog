# Antigravity 最新版本改动

[English](../antigravity.md) | 简体中文 · **精简版 (Highlight)** | [完整详情 (Full Detail)](full/antigravity.md)

> 五端（`mac`、`win`、`ubuntu`、`ios`、`android`）版本索引（覆盖 **Antigravity Desktop / Hub `2.36.0`** 与 **Antigravity IDE `2.8.0`** 两条独立桌面产品线）见 [antigravity/README.md](antigravity/README.md)。

## Antigravity Desktop（Hub）2.36.0（2026-11-27）

核心亮点见 [antigravity/2026-11-27_2.36.0.md](antigravity/2026-11-27_2.36.0.md)，完整技术细节见 [full/antigravity/2026-11-27_2.36.0.md](full/antigravity/2026-11-27_2.36.0.md)。_（壳层纯版本号变更 + 后端 Go `language_server` rebase 功能更新，构建 `2.36.0-5596661662220288`；`darwin-arm` 主分析 + 六端同构建点测，首次覆盖 `windows-arm64`，Windows `x64`/`arm64` LS PE 未覆盖；签名仅离线解析 CMS 链。）_

### 核心亮点

- **壳层纯版本号递增 + 后端 rebase 功能扩容（`+34` RPC 与 RemoteControl Mesh 传输）**：`app.asar`（`1,167` 文件、`20,690,656` B，六端逐字节一致）仅 `package.json` 版本号升至 `2.36.0`。Go `language_server` rebase 至分支基线 `1030397722`（`cl/1031268331`，`darwin-arm` `−717,648` B，`strings` `+58,899 / −58,470`），新增 `+34` Connect-RPC（`338` → `372`，含新服务 `JetskiRemoteAgentProxyService` 覆盖远程智能体管理、文件/权限、Sidecar 与自动化 Trigger）、RemoteControl **Mesh** 传输（WebChannel 回退，配套 macOS `agy-desktop-rtc` `+22,592` B）、`policyguardian/sensitivity`、Proctor J1/C8 规则、Sentry Go SDK、`4` 个新具名开关及 `neonccpa` → `neondefault`（模型 `44`、`*ToolConfig` `65` 与 CUA `19` 零变化）。
- **官方 `v2.36.0` 说明（`13` 项改进 + `26` 项修复）—— 包内实证与 webapp 区分**：远程智能体云端自动化桌面授权（RPC/服务面）与 `~/.agents/skills` 自定义技能发现（`~/.gemini` 优先）获 `language_server` 静态实证；标题级 UI/策略条目（*最大化面板浮动 composer*、*Auto mode 跨仓库安全编辑*、*语音通话上下文带入*、*MCP OAuth 离线访问*、*File/Zoom 子菜单*、*子代理 LaTeX 渲染*）与 `26` 项修复主要归属远程 Hub webapp/服务端，无法从静态安装包证实。

---

## 前序 Hub 版本：2.35.2（2026-11-25，包 `Last-Modified`）

核心亮点见 [antigravity/2026-11-25_2.35.2.md](antigravity/2026-11-25_2.35.2.md)，完整技术细节见 [full/antigravity/2026-11-25_2.35.2.md](full/antigravity/2026-11-25_2.35.2.md)。_（相对 `2.35.1` 的纯维护版，构建 `2.35.2-4585983447007232`；`darwin-arm` 主分析 + 五端同构建点测，首次覆盖 `darwin-x64` 与 `linux-arm`，Windows LS PE/CL 未覆盖；签名仅离线解析 CMS 链。）_

### 核心亮点

- **相对 `2.35.1` 的纯维护版（壳层仅版本号变更 + 后端同大小同基线重编译）**：`app.asar`（`1,167` 文件、`20,690,656` B，五端逐字节一致）相对 `2.35.1` 仅 `package.json` 版本号升至 `2.35.2`，`chrome-devtools-mcp` `1.12.0` 不变（前序 `2.35.0` / `2.35.1` 变更不归因于 `2.35.2`）。Go `language_server` 同大小重编译（mac `197,343,440` B / linux-x64 `230,003,400` B，同基线 `1027784732`，`cl/1029194470 → cl/1029311855`），RPC（`338`）、开关（`225`）、模型（`44`）、`*ToolConfig`（`65`）与 CUA（`19`）五口径零 diff，零新增语义串；macOS 四件副件同大小重编译。
- **官方独立条目「Switch models while a turn is running」属 Hub webapp，包内不可证**：既有 `2026-11-26` 快照记录的官方唯一修复归属远程 Hub webapp UI，**静态安装包无法取证**；本版未检出官方未单列的包内新能力。

---

## 前序 Hub 版本：2.35.1（2026-11-25，包 `Last-Modified`）

核心亮点见 [antigravity/2026-11-25_2.35.1.md](antigravity/2026-11-25_2.35.1.md)，完整技术细节见 [full/antigravity/2026-11-25_2.35.1.md](full/antigravity/2026-11-25_2.35.1.md)。_（两段分列对比 `2.34.0 → 2.35.0` 与 `2.35.0 → 2.35.1`，不混称归属；`darwin-arm` 主轴全量对比，配合 `linux-x64` asar/LS CL 与 `windows-x64` 内嵌 asar 核对，Windows LS PE/CL 与 `darwin-x64` 未覆盖；签名仅离线解析 CMS 链。）_

### 核心亮点

- **`2.35.0` → `2.35.1`（维护版；官方 `v2.35.1` 三条无包内静态落点）**：`app.asar`（`1,167` 文件、`20,690,656` B）相对 `2.35.0` 仅 `package.json` 版本号更新；Go `language_server` 同基线（`1027784732`）重编译（`cl/1028447422 → cl/1029194470`，`+16.5` KB），RPC（`338`）、开关（`225`）、模型（`44`）、`*ToolConfig`（`65`）与 CUA（`19`）五口径零差异，macOS 副件同大小重编译。既有 `2026-11-25` 快照记录的官方 `v2.35.1` 三条说明（重启恢复会话、插件面板自动打开、诊断上传压缩）在两段包内均**无静态落点**（属 Hub webapp/运行时侧）。
- **`2.34.0` → `2.35.0`（前序功能与重构段，不归因于 `2.35.1`）**：`2.35.0` 重组桌面壳层 `computer/`（移出 `hud`/`hudAgents`/`hudState`，新增 `customWindowControls.js`、`permissionGuide.js`、`idleProbe.js`、`appChannel.js` 及 macOS `agy-desktop-rtc`），并将 `language_server` rebase 重构（`+428` KB，`strings` `+30,776/−29,097`），新增 `agentapi` 会话管理 CLI 子命令、`AgentRemoteSession` CRUD/订阅/reaction、`ListPluginPermissionGrants`/`RevokePluginPermissionGrant`、`openai/openai_go`（`10,475` 符号）及 `enable-mcp-apps`/orchestrator/swarm 等开关，同时 RPC 面由 `380` 收缩至 `338`（而无限历史与 conversations skill 资产在包内不可证）。

---

## Antigravity IDE 2.8.0（2026-11-19）

核心亮点见 [antigravity/2026-11-19_ide-2.8.0.md](antigravity/2026-11-19_ide-2.8.0.md)，完整技术细节见 [full/antigravity/2026-11-19_ide-2.8.0.md](full/antigravity/2026-11-19_ide-2.8.0.md)。_（全部代码改动集中于 `extensions/agy` `1.11.0 → 1.12.0`［`+66.9` KB］与 macOS 独有 MSAL 原生库重编译；Code OSS `1.107.0` 基座连续三版冻结，构建号 `2.8.0-6733682917113856`；`darwin-arm` 主分析 + `linux-x64`/`windows-x64` 核对。）_

### 核心亮点

- **后台周期更新检查、即刻启动与防降级保护**：新增后端周期更新检查与 **“Restart Agent Server”** 重启提示、已装后端启动期延迟检查，以及 `downgrade_skipped`、`same_version_rebuild`、`staged_promoted`、`check_deferred` 等防多窗口降级与防恢复超时重复下载保护机制。
- **远程登录端口转发、授权码回退与自定义根证书 / 代理支持**：面向 `ssh-remote`、`dev-container`、`attached-container`、`cloud-shell`、`cloud-workstations`、`codespaces` 六类远程环境新增登录端口转发与 OOB 授权码回退（扩展侧直连 `SwitchLoginToAuthCode` 指向运行时 `agy`），并新增 `antigravity.caCertificates` 与企业自定义根证书/代理配置读取。
- **会话内搜索快捷键、`+26` 桥接 Schema 与官方条目核对**：新增 Agent 面板聚焦 `Ctrl+F`（macOS `Cmd+F`）会话内搜索转发与 `+26` 个同步 webview Schema（定制解析、Harness 步骤、模型目录、内容层）；官方 `v2.8.0` `12` 条中有 `3` 条（*60s 就绪超时*、*Windows 注销恢复死循环修复*、*Windows 通知聚焦修复*）不在 IDE 静态包面内（归属运行时 `agy` CLI 或远程 webview）。

---

## 前序补丁构建（Hub）：2.32.2（2026-11-17，包 `Last-Modified`）

核心亮点见 [antigravity/2026-11-17_2.32.2.md](antigravity/2026-11-17_2.32.2.md)，完整技术细节见 [full/antigravity/2026-11-17_2.32.2.md](full/antigravity/2026-11-17_2.32.2.md)。

### 核心亮点

- **桌面壳层与内置 MCP 零功能变动的维护补丁构建**：Electron `44.9.1` 桌面壳层（`app.asar` 全量提取 `1,068` 个文件、`18,668,119` B）仅 `package.json` 版本号由 `2.32.1` 升至 `2.32.2`，随包 `chrome-devtools-mcp` `1.9.0`（`app.asar.unpacked`）零差异，完整继承下方 [2.32.1](antigravity/2026-11-14_2.32.1.md) 与 [2.32.0](antigravity/2026-11-13_2.32.0.md) 既有功能与修复。
- **后端重编译与内部遥测符号级微调**：基于官方 `darwin-arm` 双 DMG 主分析（配合 `linux-x64` 同构建及 LS 点测、`windows-x64` 点测，非三端全量提取树 diff），重编译 Go `language_server`（`cl/1021296516` → `cl/1022991777`）未检出新增 UI 话术、且静态抽取的 `9` 档 `gemini-4-*` 模型预设、`376` 条 RPC 前缀、`189` 对特性开关及 `65` 项 `*ToolConfig` 清单均无变化；仅检出内部遥测 CEL 超时函数改名及 `Shutdown` 闭包符号串变化（仅属静态重编译证据，不声称功能修复或全量放量）。

---

## 前序补丁构建（Hub）：2.32.1（2026-11-14）

核心亮点见 [antigravity/2026-11-14_2.32.1.md](antigravity/2026-11-14_2.32.1.md)，完整技术细节见 [full/antigravity/2026-11-14_2.32.1.md](full/antigravity/2026-11-14_2.32.1.md)。

### 核心亮点

- **默认模型目录新增 `Gemini 4 Hydrogen` 档位**：在内置默认模型目录中新增 **Gemini 4 Hydrogen** 的低、中、高三档推理强度预设（如 `Gemini 4 Hydrogen (High)`），与既有 `Gemini 4 Argon`、`Gemini 4 Carbon` 档位并列提供。
- **延续 `2.32.0` 全量能力的次日补丁构建**：保持 Electron `44.9.1` 桌面壳层与内置浏览器 MCP 工具集与 `2.32.0` 逐字节一致，同步更新后端核心构建，完整继承下方 [2.32.0](antigravity/2026-11-13_2.32.0.md) 全部改进与修复。

---

## 近期主版本基线（Hub）：2.32.0（2026-11-13）

核心亮点见 [antigravity/2026-11-13_2.32.0.md](antigravity/2026-11-13_2.32.0.md)，完整技术细节见 [full/antigravity/2026-11-13_2.32.0.md](full/antigravity/2026-11-13_2.32.0.md)。

### 核心亮点

- **Dynamic Workflows 动态工作流上线**：正式开放 **Dynamic Workflows**，支持智能体直接借助随包内置的独立 Python 运行时编写并编排多步骤任务与并行子代理（Subagents）工作流。
- **Everforest 亮/暗主题与提示词跳转快捷键**：在 `Settings > Appearance` 中新增低对比度护眼配色的 **Everforest Light** 与 **Everforest Dark** 主题；支持在输入框或阅读视图中通过快捷键跳转上/下一条提示词，支持在 `Settings > Shortcuts` 中绑定可选的 **Submit Prompt** 发送快捷键，并修复 Linux 下固定会话快捷键与 Chrome 标签组的冲突。
- **内置浏览器标签页隔离加固与站点兼容修复**：智能体控制的浏览器标签页中跨站子框架（Cross-site Frames）默认以未登录态加载（剥离跨站凭据），且在未经显式允许与指定前对智能体截图和页面快照保持隐藏；导航拦截范围由支付页扩展至受保护登录页；文件类型受阻的下载会通知智能体并在下载抽屉显示拦截状态；同时移除内置浏览器 User-Agent 中的 `Electron` 标识（保留 Google 登录兼容特判），解决部分外部网站拦截内置浏览器的问题。
- **授权码登录兜底、云端 GitHub 仓库克隆与交互改进**：新增浏览器自动回跳失败时复制登录链接或粘贴一次性授权码的登录方式；使用远程智能体时支持从工作区选择器将云端 GitHub 仓库克隆至本地并在应用内直接登录 PR 链接；模型选择菜单支持自适应屏幕高度并在加载失败时提供 **Refresh** 重试按钮；插件卡片与详情页直接展示 MCP Server 启动报错，权限菜单在宿主不支持终端沙箱时说明隐藏 Default / Auto 模式的原因。
- **退出残留进程清理、中日韩粗体渲染等 13 项修复与底层基建**：重写登录 Shell 环境变量读取逻辑以确保退出桌面端时正常关闭后台进程，增强设置保存对临时文件锁的容错，修复 CJK 粗体字重退化、长对话上滚卡顿、回退对话工具栏闪烁、草稿/排队消息列表扁平化、插件更新后全屏视图空白及 Google Drive `@` 提及登录；同时随包合入受实验开关门控的 SSH 远程主机栈（`--ssh-host`）、桌面控制（Computer Use）子代理插件与三层访客视图手势栈。

---

## 前序 IDE 版本：Antigravity IDE 2.7.0（发布时间未确认；构建于 2026-11-11）

核心亮点见 [antigravity/2026-11-11_ide-2.7.0.md](antigravity/2026-11-11_ide-2.7.0.md)，完整技术细节见 [full/antigravity/2026-11-11_ide-2.7.0.md](full/antigravity/2026-11-11_ide-2.7.0.md)。_（发布时间未确认；`product.json` 中的北京时间 `2026-11-11 12:46` 是构建时间，不是发布时间。）_

### 核心亮点

- **登录态感知状态栏与多窗口认证同步**：底部状态栏升级为登录态三态按钮（未登录时点击直接触发登录，已登录时展开快捷状态菜单），新增登录/登出命令、跨窗口登录态自动同步及 Google Cloud / 企业服务条款状态识别。
- **区分「当前文件」与「全部文件」差异操作及新快捷键**：将行内与并排 Diff 审阅标题明确为「当前文件」，拆出独立的「接受/拒绝全部文件改动」命令，新增新建对话、切换聊天焦点与插入终端输出命令，并细化终端 `Ctrl+L` / `Ctrl+Alt+L` 快捷键分工。
- **后台任务与录制桥接及云工作站预装 CLI 识别**：扩展智能体界面桥接以支持后台任务（`ManageTask`）、多媒体处理与浏览器录制；在 Google Cloud Workstations / Cloud Shell 中自动复用预装 `/usr/bin/agy`、支持本地服务端口冲突重试，并在一键反馈中标识 Antigravity IDE。

---

## Antigravity Desktop（Hub）2.31.2（2026-11-12）

核心亮点见 [antigravity/2026-11-12_2.31.2.md](antigravity/2026-11-12_2.31.2.md)，完整技术细节见 [full/antigravity/2026-11-12_2.31.2.md](full/antigravity/2026-11-12_2.31.2.md)。

### 核心亮点

- **内置浏览器页面级 WebMCP 工具桥接**：新增 Guest WebMCP 桥，支持在内置浏览器中发现、调用与取消由网页自身通过 Chromium WebMCP 暴露的结构化工具（不向页面注入额外脚本），仅限 HTTPS 与本地回环地址，内置 30 秒默认超时（1–120 秒范围）、64 KiB 结果上限，并自动拦截 Stripe、PayPal、Adyen、Google Pay 等支付与身份认证域名。
- **原生多智能体 Swarm 看板协同**：移除旧版单一静态模板，上线原生 Swarm 协同工具族，支持管理并行工作节点、向共享看板投递消息、按未读或提及筛选读取看板以及等待/汇合多节点任务。
- **远程 MCP 服务器直连 OAuth 登录**：新增面向 MCP 服务器的独立 OAuth 登录入口，与现有插件授权体系及 `~/.gemini/config/mcp_config.json` 本地/远程自定义 MCP 配置并存。
- **规划—执行门控、持久终端与 Notebook 执行**：新增规划模式进入/退出门控工具与焦点追踪，终端命令执行支持持久会话（跨轮次保留环境变量与 Shell 变量）及通知超时配置，并新增独立的 Jupyter Notebook 单元格编辑与运行工具。
- **本地调试端口权限加固与安全预筛**：收紧本地应用数据目录（`0700`）与浏览器调试端口文件（`0600`）访问权限，升级 Electron 桌面运行时，放宽内置浏览器 MCP 回退启动器的 Node 版本匹配，并在 30 项工具 / 43 条命令只读安全白名单旁新增轻量模型威胁预筛器（日志模式）。
