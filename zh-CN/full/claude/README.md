# Claude 版本变更历史

[English](../../../full/claude/README.md) | 简体中文 · [精简版 (Highlight)](../../claude/README.md) | **完整详情 (Full Detail)**

覆盖 `mac`、`win`、`ubuntu`、`ios`、`android` 五端共 **534** 个统一版本号（桌面端 **245** 个版本 + 移动端 **289** 个版本）的完整演进索引。

## 五端覆盖概览

| 平台 | 分发渠道 / 包名 | 收录版本数 | 版本范围 | 最新版本 |
|---|---|---|---|---|
| `mac` | macOS（`Claude.app` / Cask & CDN） | 228 | `0.4.8` → `5.11492.5` | [5.11492.5](2026-11-14_5.11492.5.md) |
| `win` | Windows（`Anthropic.Claude` Winget、Squirrel 与 MSIX） | 206 | `0.4.9` → `5.11492.5` | [5.11492.5](2026-11-14_5.11492.5.md) |
| `ubuntu` | Ubuntu / Debian APT（`claude-desktop`） | 70 | `1.17180.0` → `5.11492.5` | [5.11492.5](2026-11-14_5.11492.5.md) |
| `ios` | iOS App Store（`com.anthropic.claude`） | 171 | `1.240826.1` → `1.261109.19` | [1.261109.19](2026-11-11_1.261109.19.md) |
| `android` | Android（`com.anthropic.claude`） | 155 | `1.240805.17` → `1.261124.19` | [1.261124.19](2026-11-25_1.261124.19.md) |

## 关键架构与功能里程碑

| 里程碑 | 首次引入版本 | 发布日期 | 说明 |
|---|---|---|---|
| 初始桌面版与 `claude-native` | [0.4.8](2024-10-31_0.4.8.md) | 2024-10-31 | 主窗口 + Quick Window、Rust 原生辅助模块、MCP SDK 0.1 |
| MCP 管理界面与开发者模式 | [0.7.1](2024-11-22_0.7.1.md) | 2024-11-22 | 本地 MCP Server 安装确认、日志入口与 React 设置界面 |
| Swift 原生插件与 Quick Entry | [0.9.4](2025-06-03_0.9.4.md) / [0.12.15](2025-07-14_0.12.15.md) | 2025-06-03 | `claude-swift` 原生桥接落地，后续上线语音听写权限与快捷输入条 |
| 1.0 正式版与终端 `node-pty` | [1.0.734](2025-11-21_1.0.734.md) / [1.0.2768](2026-01-05_1.0.2768.md) | 2025-11-21 | 步入 `1.x` 正式版本线，并在 `1.0.2768` 集成内置伪终端模块 `node-pty` |
| Cowork 虚拟机镜像 `smol-bin` | [1.1.280](2026-01-16_1.1.280.md) | 2026-01-16 | 内置 Apple Virtualization 轻量虚拟机镜像，开启本地隔离执行架构 |
| Computer Use 原生模块 | [1.1.8308](2026-03-23_1.1.8308.md) | 2026-03-23 | 新增 `@ant/claude-swift` 下属 `computer_use.node` 屏幕操控模块 |
| 离线前端包 `ion-dist` | [1.2.234](2026-04-01_1.2.234.md) | 2026-04-01 | 首次将 Web 前端完整离线打包进客户端资源目录 |
| 内置 Skills 技能包 | [1.15962.0](2026-06-25_1.15962.0.md) | 2026-06-25 | 随包分发 `docx`、`pdf`、`pptx`、`xlsx`、`frontend-design` 等技能包 |
| `2.x` 主版本升级 | [2.110.0](2026-09-15_2.110.0.md) | 2026-09-15 | 升级至 `2.x` 系列，引入模型目录、自托管第三方推理、企业托管策略与云会话 |
| `3.x` Artifact Shell 网络桥 | [3.1623.0](2026-10-20_3.1623.0.md) | 2026-10-20 | Electron 44.9、`artifactShell.js` 与本地 OOXML/Frame 后端成型 |
| `4.x` 全量 ASAR 完整性封装 | [4.29.0](2026-10-27_4.29.0.md) | 2026-10-27 | `ion-dist.asar` 化并纳入完整性校验，后续在 [4.16336.0](2026-11-03_4.16336.0.md) 上线 `design`/`slides` Frame 运行时与 Gmail/Drive MCP |
| `5.x` 内置浏览器扩展生态 | [5.1231.0](2026-11-10_5.1231.0.md) | 2026-11-10 | Electron 45.2.1、Chrome Web Store 应用内扩展安装、1Password 自动填充桥与 Three.js 3D Artifact 渲染 |

## 桌面端版本索引（`mac` / `win` / `ubuntu`，最新 → 最早）

| 版本 | 覆盖平台 | 发布日期 | Electron | 核心变更摘要 |
|---|---|---|---|---|
| [5.11492.5](2026-11-14_5.11492.5.md) | `mac`、`win`、`ubuntu` | 2026-11-14 | 45.2.1 | 引擎功能小版本 + Office 技能安全加固（桌面 UI 零新增）：新增会话存储键 schema（`index.chunk-BDY2-Sqh.js`、`jobs-root`、`setSessionArchived`）与受管键 `blockFileToolReadsOutsideWorkingDirectories`；`docx`/`pptx`/`xlsx` 落地 `names_another_root`、关系包含检查与上限化 `SequenceMatcher`；`ion-dist` 10 语种翻译追赶、全端 `smol-bin` 与 mac 原生件轮换 |
| [5.11492.2](2026-11-13_5.11492.2.md) | `mac`、`win`、`ubuntu` | 2026-11-13 | 45.2.1 | 新日期段纪元（并入 `5.11492.0`）：新增 `ConfigTemplateExport` 窗口/eipc、`SandboxNetworkAccess` 规则类型、`ssh_host_settings`、`readOpenedFileChunk`、`openMicrophoneSettings`、Chrome 逐动作授权、4 类 MCP OAuth 模式；加固 Windows `claude://` `-- "%1"`，Linux 主程序权限改 `0755` 并补齐 Artifact CDN 白名单 |
| [5.1231.2](2026-11-11_5.1231.2.md) | `mac`、`ubuntu` | 2026-11-11 | 45.2.1 | 快速热修：更新权限提示、design system 文件夹接入与定时任务细节；1Password 域名补全 |
| [5.1231.0](2026-11-10_5.1231.0.md) | `mac`、`ubuntu` | 2026-11-10 | 45.2.1 | 主版本号 4→5 = 扩展生态里程碑：应用内 Chrome Web Store 安装/管理、扩展 agentic 桥（含 1Password 凭据自动填充）、Cowork 插件目录；ion-dist 引入 three.js 3D artifact 渲染；Electron 升至 45.2.1 |
| [4.23118.1](2026-11-09_4.23118.1.md) | `mac`、`ubuntu` | 2026-11-09 | 44.9.3 | 稳定性补丁：官方插件市场仓库引用、zod v4 内部标识符（\$Zod* 全家桶，CLI 校验库升级）、多语言补齐；无结构性变化 |
| [4.23118.0](2026-11-05_4.23118.0.md) | `mac`、`ubuntu` | 2026-11-05 | 44.9.3 | Web 端 GitHub/SSH 连接 UI 与 Claude Slides 集成成型；桌面端规则系统、会话交接与 CLI 按需下载；CLI 引导安装到 VS Code/JetBrains |
| [4.16336.0](2026-11-03_4.16336.0.md) | `mac`、`ubuntu` | 2026-11-03 | 44.9.3 | 重磅更新：Google Gmail/Drive 官方 MCP 端点、design/slides 两类 artifact frame 运行时（268 文件）与 MCP App 视图窗口；Linux VM 下载端点出现，Cowork 向 Linux 虚拟化延伸 |
| [4.4212.0](2026-10-29_4.4212.0.md) | `mac`、`ubuntu` | 2026-10-29 | 44.9.3 | 网页端功能更新（artifact 空状态、浏览器远程连接、Cloudflare 挑战处理）+ 内嵌 CLI 例行刷新；新标识符 ADD_CUSTOM_CONNECTOR_ARRIVAL_*、ArtifactsNewMenu*（自定义连接器引导） |
| [4.29.0](2026-10-27_4.29.0.md) | `mac`、`ubuntu` | 2026-10-27 | 44.9.3 | 主版本号 3→4 是一次工程化里程碑：web 前端与语言包全部 asar 化并纳入完整性校验，资源目录大幅收敛；smol-bin 镜像扩容 |
| [3.6556.2](2026-10-23_3.6556.2.md) | `mac`、`win`、`ubuntu` | 2026-10-23 | 44.9.3 | 无实质功能变化（例行重建 + 内嵌 CLI 字符串轮换 + skills ref bump） |
| [3.6556.1](2026-10-22_3.6556.1.md) | `mac`、`win`、`ubuntu` | 2026-10-22 | 44.9.3 | 3.x 内部大版本：frame-local-worker 落地（本地 artifact frame 宿主 + HTML 重写），Google Drive MCP 与 Slack 企业域接入；标识符出现 ANTHROPIC_DEFAULT_FABLE_MODEL/MYTHOS_MODEL（新模型代号）与 CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS |
| [3.1623.4](2026-10-22_3.1623.4.md) | `mac`、`win`、`ubuntu` | 2026-10-22 | 44.9.0 | 同日热修：围绕 Cowork/Dispatch 云端任务副本与挂载问题的修复，无结构性变化 |
| [3.1623.3](2026-10-22_3.1623.3.md) | `mac`、`win`、`ubuntu` | 2026-10-22 | 44.9.0 | 内嵌 Claude Code CLI 大版本刷新：完整 OAuth 流端点、多云供应商接入环境变量（ANTHROPIC_* Bedrock/Vertex/Foundry/Google Cloud、AWS_* 全家桶）、federation/gateway 标识符集中出现 |
| [3.1623.1](2026-10-21_3.1623.1.md) | `mac`、`win`、`ubuntu` | 2026-10-21 | 44.9.0 | 小补丁：Slack Connector、iOS Simulator 状态提示与前端渲染库 URL 纳入 |
| [3.1623.0](2026-10-20_3.1623.0.md) | `mac`、`win`、`ubuntu` | 2026-10-20 | 44.9.0 | 主版本号 2→3：Electron 44.9 + 防降级开关 + artifactShell 新 bundle（Cowork artifact 网络桥）+ OOXML→HTML/frame-local-backend 两个新内部包，是 Cowork artifact 渲染栈重构的起点；无破坏性 UI 重排 |
| [2.42304.2](2026-10-19_2.42304.2.md) | `mac`、`win`、`ubuntu` | 2026-10-19 | 44.7.2 | 热修型补丁：Office 365 MCP 的 OOXML 解析与 GitHub API 集成增强，Claude Code CLI 内嵌版本刷新（大量 CLAUDE_CODE_* 代理/证书环境变量） |
| [2.42304.0](2026-10-15_2.42304.0.md) | `mac`、`win`、`ubuntu` | 2026-10-15 | 44.7.2 | SSH 远程主机功能落地（askpass helper + ssh2 传输 + session host 概念），插件市场与 Slack 连接器开始铺字符串；node-pty 打包方式调整 |
| [2.37337.1](2026-10-13_2.37337.1.md) | `mac`、`win`、`ubuntu` | 2026-10-13 | 44.7.0 | Electron 升级 + 大量 Claude Code/Cowork 面向"文件夹访问、PR 自动修复、模型目录"的功能铺开；首次出现 Figma 远程 MCP 与 model-catalog 端点 |
| [2.31226.1](2026-10-09_2.31226.1.md) | `mac`、`win`、`ubuntu` | 2026-10-09 | 44.4.3 | 小版本：agent-sdk 0.3.295 正式版落地，无其他功能变化 |
| [2.31226.0](2026-10-08_2.31226.0.md) | `mac`、`win`、`ubuntu` | 2026-10-08 | 44.4.3 | 企业 Tool policy（端点+规则）与 Cowork 文件读取校验上线；SSH 远程会话传输层硬化与 HIPAA 合规文案 |
| [2.26454.2](2026-10-07_2.26454.2.md) | `mac`、`win`、`ubuntu` | 2026-10-07 | 44.4.3 | 主进程侧修复版（web 前端冻结）：RC SDK + 沙箱设置文档链接 |
| [2.26454.0](2026-10-06_2.26454.0.md) | `mac`、`win`、`ubuntu` | 2026-10-06 | 44.4.3 | heavy-work worker 内嵌 xterm headless 终端（配合新依赖 @xterm/headless 6.0.0，为会话终端/quick write 提供仿真）；Quick Write、M365 Windows 账号登录、connector 浏览器内登录等新开关；Office MCP 更新 |
| [2.19675.1](2026-10-05_2.19675.1.md) | `mac`、`win`、`ubuntu` | 2026-10-05 | 44.4.3 | 小版本：SDK 升级、pptx skill 更新、一条沙箱提示 |
| [2.19675.0](2026-10-01_2.19675.0.md) | `mac`、`win` | 2026-10-01 | 44.4.3 | Android/iOS 移动构建指引与仓库信任（trust this repository）流程上线；SDK 0.3.286 |
| [2.16120.0](2026-09-30_2.16120.0.md) | `mac`、`win` | 2026-09-30 | 44.4.3 | Cowork EDR 集成（企业安全对接 Cowork VM 的标志性开关）+ 插件 MCP 封禁清单 + 企业 GitHub/GitLab 扩展 |
| [2.9939.4](2026-09-28_2.9939.4.md) | `mac`、`win`、`ubuntu` | 2026-09-28 | 44.4.3 | 无实质功能变化（RC SDK + web 重建/chunk 重排） |
| [2.9939.2](2026-09-24_2.9939.2.md) | `mac`、`win` | 2026-09-24 | 44.4.3 | 重建 + SDK 小版本；fileIndexWorker 体积减半属打包优化，无功能变化 |
| [2.9939.1](2026-09-24_2.9939.1.md) | `mac` | 2026-09-24 | 44.4.3 | 组织插件/技能市场与共享治理上线；Claude in Chrome 密码管理器、网关托管 Claude Code 两个新开关 |
| [2.7032.0](2026-09-22_2.7032.0.md) | `mac`、`win`、`ubuntu` | 2026-09-22 | 44.4.3 | Electron 44.4.3 升级 + 企业管控扩展（corporate launcher、device tools、keep-awake、IdP OIDC），并接入 Figma MCP |
| [2.2553.13](2026-09-22_2.2553.13.md) | `mac`、`win`、`ubuntu` | 2026-09-22 | 44.2.0 | 重建 + RC 版 agent-sdk；无实质功能变化 |
| [2.2553.1](2026-09-18_2.2553.1.md) | `mac`、`win`、`ubuntu` | 2026-09-18 | 44.2.0 | 小版本：SDK 升级 + 重建 |
| [2.2553.0](2026-09-17_2.2553.0.md) | `mac`、`ubuntu` | 2026-09-17 | 44.2.0 | 云端 Claude Code 会话（cloud sessions + Remote Control）与组织插件 MCP 治理进入桌面端；版本号跳到 2553 系内部 build 号 |
| [2.110.1](2026-09-17_2.110.1.md) | `mac`、`ubuntu` | 2026-09-17 | 44.2.0 | 无实质功能变化（仅重建/重签名/chunk 重排） |
| [2.110.0](2026-09-15_2.110.0.md) | `mac`、`ubuntu` | 2026-09-15 | 44.2.0 | 2.0 里程碑版本。版本号第二段改为内部 build 号（110，用于发布列车号）；核心新能力是模型目录（catalog.json + 默认模型/effort 设置）与自托管第三方推理（Azure AI Foundry / Microsoft Entra OIDC / 凭据 helper 脚本全家族设置），并新增 iOS 模拟器桥二进制、强化 MCP/文件系统安全；Web 前端同步换用新构建管线并大幅扩文案。Claude Code 云会话等能力在此版尚未出现在设置中（见 2.2553.0） |
| [1.52386.6](2026-09-13_1.52386.6.md) | `mac`、`ubuntu` | 2026-09-13 | 44.2.0 | 1.x 最终版：agent-sdk 升至 0.3.270，打包器更新，无用户可见功能变化 |
| [1.52386.4](2026-09-12_1.52386.4.md) | `mac` | 2026-09-12 | 44.2.0 | 重建版本；实质变化只有 Windows VM 文件共享回退的默认值翻转为关闭 |
| [1.52386.3](2026-09-11_1.52386.3.md) | `mac`、`win`、`ubuntu` | 2026-09-11 | 44.2.0 | 纯重建/重签名版本，唯一功能差异是撤下 Windows VM file-share fallback 设置项 |
| [1.52386.1](2026-09-11_1.52386.1.md) | `mac` | 2026-09-11 | 44.2.0 | 内嵌 agent 运行时（Claude Code）显著扩充：git worktree 后台检出、AWS 凭证、GitHub 用户信息/device-code 登录；白名单中露出 MYTHOS/FABLE 模型族与 AGENT_TEAMS 实验开关（均为内部代号，功能未公开） |
| [1.52386.0](2026-09-11_1.52386.0.md) | `mac`、`ubuntu` | 2026-09-11 | 44.2.0 | SSH 双引擎（ssh2 + 原生 OpenSSH）与 PTY Host 服务命名、MCP elicitation/sampling 能力协商、Argon2 加密参数进入 heavy-work worker；GitHub REST/GraphQL API 与 claude.com/claude-code 链接进入主进程 |
| [1.49585.0](2026-09-08_1.49585.0.md) | `mac`、`win`、`ubuntu` | 2026-09-08 | 44.2.0 | 阶段性重大更新：Electron 44.2.0 带来 macOS 13+ 门槛与 ANGLE 库合并；iOS 模拟器助手瘦身（去内嵌 frameworks）；office365 MCP 明确 stdio 入口并强化 MSAL 令牌加密存储 |
| [1.46388.4](2026-09-05_1.46388.4.md) | `mac`、`win` | 2026-09-05 | 42.10.0 | 无实质功能变化（Web 前端与 skills 全量重发布） |
| [1.46388.3](2026-09-04_1.46388.3.md) | `mac`、`win` | 2026-09-04 | 42.10.0 | 无实质功能变化（重建） |
| [1.46388.2](2026-09-04_1.46388.2.md) | `mac`、`win`、`ubuntu` | 2026-09-04 | 42.10.0 | 基本无实质功能变化（重建 + 一条连接提示文案） |
| [1.46388.1](2026-09-04_1.46388.1.md) | `mac`、`win` | 2026-09-04 | 42.10.0 | 小改：Remote Control 注册上报粒度说明进入 chunk；其余为重建 |
| [1.46388.0](2026-09-03_1.46388.0.md) | `mac` | 2026-09-03 | 42.10.0 | GitHub PR 自动修复（auto-fix）与 SSH 密钥识别能力上线到主进程 chunk；bash shell 集成增加 trap/nonce 防护标识 |
| [1.44121.4](2026-09-03_1.44121.4.md) | `mac`、`win` | 2026-09-03 | 42.10.0 | 无实质功能变化（重建） |
| [1.44121.2](2026-09-02_1.44121.2.md) | `mac`、`win`、`ubuntu` | 2026-09-02 | 42.10.0 | 无实质功能变化（重建） |
| [1.44121.1](2026-09-02_1.44121.1.md) | `mac` | 2026-09-02 | 42.10.0 | 引入 CLAUDE_REMOTE_TOOLS_BRIDGE_URL 等远程工具桥接环境变量与权限作用域说明；其余为重建 |
| [1.44121.0](2026-09-02_1.44121.0.md) | `mac` | 2026-09-02 | 42.10.0 | 渲染端构建管线大重构（chunk 拆分 + CSS code-split）；主进程嵌入的 Cowork/沙箱 agent 提示词显著扩充，MCP 校验迁移到 Zod v4 |
| [1.40609.1](2026-09-01_1.40609.1.md) | `mac`、`win`、`ubuntu` | 2026-09-01 | 42.10.0 | 无实质功能变化（重建） |
| [1.40609.0](2026-08-28_1.40609.0.md) | `mac`、`win`、`ubuntu` | 2026-08-28 | 42.10.0 | Office 文档处理能力扩展（Word/Excel/PPT 格式化、图表、公式等技能化操作）与 GitHub PR 自动修复 agent 语义进入主进程；ion-dist 新增 frame-connect/frame-manage 两个 artifact 框架入口 |
| [1.37937.3](2026-08-26_1.37937.3.md) | `mac`、`win`、`ubuntu` | 2026-08-26 | 42.10.0 | 无实质功能变化（同日第三次重发） |
| [1.37937.2](2026-08-26_1.37937.2.md) | `mac` | 2026-08-26 | 42.10.0 | 无实质功能变化（Web 前端与 skills 全量重发布） |
| [1.37937.1](2026-08-26_1.37937.1.md) | `mac`、`win`、`ubuntu` | 2026-08-26 | 42.10.0 | 基本无实质功能变化（重建）；唯一线索是 chunk 内嵌入了原生 WebSocket 客户端实现 |
| [1.37937.0](2026-08-25_1.37937.0.md) | `mac`、`win`、`ubuntu` | 2026-08-25 | 42.10.0 | 两个重点：Electron 升至 42.10.0；引入 macOS Quick Actions/Services 集成（quick-actions 模板）。主 Info.plist 的 NSUserActivityTypes 同时新增 `com.apple.corespotlightitem`（CoreSpotlight/Handoff 支持） |
| [1.34493.1](2026-08-21_1.34493.1.md) | `mac`、`win`、`ubuntu` | 2026-08-21 | 42.9.2 | 无实质功能变化（仅重建/重签名/chunk 重排），一天内的热修复式重发 |
| [1.34493.0](2026-08-20_1.34493.0.md) | `mac`、`win`、`ubuntu` | 2026-08-20 | 42.9.2 | 新增 designWindow preload 与 V8 compile-cache（双架构字节码）；网页端引入版本化 frame 内核（kernel-0.1.x）；SSH 连接配置校验文案完善；包体积显著缩小 |
| [1.32885.1](2026-08-18_1.32885.1.md) | `mac`、`win`、`ubuntu` | 2026-08-18 | 42.9.2 | 无实质功能变化（重建）。同日 .0/.1 两连发 |
| [1.32885.0](2026-08-18_1.32885.0.md) | `mac` | 2026-08-18 | 42.9.2 | 接近重建级别的小版本；网页端新增 embed 运行时模块，其余为重排 |
| [1.32352.1](2026-08-18_1.32352.1.md) | `mac`、`win`、`ubuntu` | 2026-08-18 | 42.9.2 | 无实质功能变化（重建） |
| [1.32352.0](2026-08-17_1.32352.0.md) | `mac`、`win`、`ubuntu` | 2026-08-17 | 42.9.2 | Electron 升级 42.9.2；插件与技能市场、Widget/Device Hub 文案集中出现，网页端 407 个新资产；heavy-work worker 改用 Rolldown 打包；bundle 内置 mime-db |
| [1.30096.5](2026-08-15_1.30096.5.md) | `mac`、`win`、`ubuntu` | 2026-08-15 | 42.7.0 | 无实质功能变化（重建；skills 清单引用更新） |
| [1.30096.1](2026-08-14_1.30096.1.md) | `mac`、`win`、`ubuntu` | 2026-08-14 | 42.7.0 | 无实质功能变化（重建） |
| [1.30096.0](2026-08-13_1.30096.0.md) | `mac` | 2026-08-13 | 42.7.0 | OAuth 体系切换到 platform.claude.com（含 CLI API key 发放与积分购买），出现 FedStart 专属域名与 mcp-proxy.anthropic.com；Buddy 桌面配件仓库公开；网页端 install-hub 图标 PNG 化并新增 Apple 渠道图标；index2 chunk 实验回退 |
| [1.28929.0](2026-08-12_1.28929.0.md) | `mac`、`ubuntu` | 2026-08-12 | 42.7.0 | 内置 ssh2 与 GitHub App/CLI 授权——远程开发（Claude SSH）与 GitHub MCP 完整接线；新增 app-cu-helper；渲染窗口样式体系更名；网页端加入 Code Review 宣传素材与 room/sample 运行时模块 |
| [1.26832.0](2026-08-07_1.26832.0.md) | `mac`、`ubuntu` | 2026-08-07 | 42.7.0 | 接通 GitHub MCP（api.github.com + GitHub App 授权）；新计划/提醒类任务文案与 Artifact 分享（自动发布）流程；Buddy 蓝牙传输与 computer-use 实时预览等新能力标识出现 |
| [1.25927.0](2026-08-04_1.25927.0.md) | `mac`、`win`、`ubuntu` | 2026-08-04 | 42.7.0 | 阶段性重大更新：内置 GitHub MCP server 二进制与 permission-fixer helper；主进程新增本地执行授权窗口（localExecConsent）与 stall-sampler worker；bundle 双 chunk 命名空间化并打入 node-forge/rxjs/winston；端点层面引入 Claude Code/Claude SSH 官方二进制下载、M365/Box/Slack/Bedrock/Google OAuth 等大量企业集成入口；语言目录改名 |
| [1.24012.11](2026-08-03_1.24012.11.md) | `mac`、`win`、`ubuntu` | 2026-08-03 | 42.7.0 | 无实质功能变化（重建）。距上一版 10 天，仍为同一代码树的轮换构建 |
| [1.24012.9](2026-07-24_1.24012.9.md) | `mac`、`win`、`ubuntu` | 2026-07-24 | 42.7.0 | 无实质功能变化（重建 + 网页 shared chunk 重组） |
| [1.24012.1](2026-07-21_1.24012.1.md) | `mac`、`win` | 2026-07-21 | 42.7.0 | 无实质功能变化（同日热修复重建） |
| [1.24012.0](2026-07-21_1.24012.0.md) | `mac`、`win`、`ubuntu` | 2026-07-21 | 42.7.0 | Electron 升级到 42.7.0；网页端 frame 运行时大幅扩展（translate/downloads/mcp/permissions/user 模块）；主进程加入内置 MCP 登录错误类型（BuiltinMcpNeedsAuthError/BuiltinMcpSignInCanceledError）、模拟器录制与 Android Studio 探测、skills 推荐话术 |
| [1.22209.3](2026-07-19_1.22209.3.md) | `mac`、`win`、`ubuntu` | 2026-07-19 | 42.5.1 | 修补版本：新增 Anthropic on Google Cloud 相关环境变量与设备模拟器平台开关文案，其余为全量重建 |
| [1.22209.0](2026-07-16_1.22209.0.md) | `mac`、`ubuntu` | 2026-07-16 | 42.5.1 | 引入 Claude Code 移动模拟器工具：内置 iOS Simulator 控制 helper（Facebook idb 框架）+ Android Emulator（adb）接入，配套设置项、管理员封禁策略与 statsig 面板（"Claude Code iOS Simulator"/"Claude Code Android Emulator" dashboard uuid）；同时 heavy-work worker 并入 node-forge PKI 与 gitignore 匹配能力 |
| [1.21459.3](2026-07-16_1.21459.3.md) | `mac`、`win`、`ubuntu` | 2026-07-16 | 42.5.1 | 无实质功能变化（仅重建）。同日连发 .1/.3 两次热修版本 |
| [1.21459.1](2026-07-16_1.21459.1.md) | `mac`、`win`、`ubuntu` | 2026-07-16 | 42.5.1 | 无实质功能变化（仅重建/重签名/chunk 重排） |
| [1.21459.0](2026-07-14_1.21459.0.md) | `mac`、`win`、`ubuntu` | 2026-07-14 | 42.5.1 | 新增 pty-host worker（终端宿主服务化）与 swift memoryPressure 原生接口，heavy-work/transcript-search/directMcpHost 大幅扩容；frame 运行时补齐 comments/downloads/permissions/mcp 模块；网页端随 claude.ai 大改版同步了海量新文案 |
| [1.20186.9](2026-07-14_1.20186.9.md) | `mac`、`win`、`ubuntu` | 2026-07-14 | 42.5.1 | 无实质功能变化（agent-sdk 升级 + 重建热修） |
| [1.20186.7](2026-07-14_1.20186.7.md) | `mac`、`ubuntu` | 2026-07-14 | 42.5.1 | 无实质功能变化（仅重建 + Skills 刷新） |
| [1.20186.1](2026-07-11_1.20186.1.md) | `mac`、`win`、`ubuntu` | 2026-07-11 | 42.5.1 | 无实质功能变化（仅重建 + Skills 刷新） |
| [1.20186.0](2026-07-09_1.20186.0.md) | `mac`、`win` | 2026-07-09 | 42.5.1 | 大规模更新（zip +20MB，主要来自 ion-dist）：新增 heavy-work worker 与 Claude Browser/浏览操控能力文案，Cowork 会话文件夹授权对话框上线；OAuth 端点全面切换到 platform.claude.com 并出现 FedStart 政府云域名 |
| [1.19367.0](2026-07-07_1.19367.0.md) | `mac`、`win`、`ubuntu` | 2026-07-07 | 42.5.1 | 重要依赖升级版：agent SDK/TS SDK 大版本跃迁，主进程 bundle 首次哈希分块（+48 chunk），新增 file-index worker 与 agent-base；字符串显示内置了 GitHub PR 操作、SSH 远程、MCPB 打包、Slack 连接器与 Claude Code CLI 下载等本地 agent 能力（多数由内嵌 agent-sdk 携带） |
| [1.18286.2](2026-07-07_1.18286.2.md) | `mac`、`win`、`ubuntu` | 2026-07-07 | 42.5.1 | 无实质功能变化（agent-sdk 升级 + 重建热修） |
| [1.18286.0](2026-07-02_1.18286.0.md) | `mac`、`win`、`ubuntu` | 2026-07-02 | 42.5.1 | 主进程小改（shell-path worker、Callback port）；网页端为会话内 dev-server 预览与聊天记忆功能放量 |
| [1.17377.2](2026-07-01_1.17377.2.md) | `mac`、`win`、`ubuntu` | 2026-07-01 | 42.5.1 | 无实质功能变化（仅重建 + Skills 刷新） |
| [1.17377.1](2026-07-01_1.17377.1.md) | `mac`、`win`、`ubuntu` | 2026-07-01 | 42.5.1 | 无实质功能变化（agent-sdk 小版本升级 + Skills 刷新 + 重建） |
| [1.17377.0](2026-06-30_1.17377.0.md) | `mac`、`ubuntu` | 2026-06-30 | 42.5.1 | 主进程无实质变化；网页端新增 worktree 会话与后台任务交接文案（为 Cowork git 工作流上线铺垫） |
| [1.17282.0](2026-06-30_1.17282.0.md) | `mac`、`ubuntu` | 2026-06-30 | 42.5.1 | 主体为重建 + Skills 刷新；网页端小步更新（密钥显示/隐藏、allowed sites 管理） |
| [1.15962.2](2026-06-30_1.15962.2.md) | `win` | 2026-06-30 | — | `TODO`（`win`）— _详细技术差分待补充_ |
| [1.17180.0](2026-06-29_1.17180.0.md) | `mac`、`ubuntu` | 2026-06-29 | 42.5.1 | Electron 升 42.5.1；新增 computer-use watch/record 双 bundle 与 swift watchRecorder 原生接口；内置 Skills 内容刷新（agentSkillsRef 1782518167）；网页端为组织角色/审批策略大更新，并出现 Linux 打包准备痕迹 |
| [1.15962.1](2026-06-26_1.15962.1.md) | `mac`、`win` | 2026-06-26 | 42.4.0 | 无实质功能变化（仅重建/重签名/chunk 重排） |
| [1.15962.0](2026-06-25_1.15962.0.md) | `mac`、`win` | 2026-06-25 | 42.4.0 | 首次内置 6 个 Office/文档 Agent Skills（docx/pdf/pptx/xlsx + pdf-reading、frontend-design），directMcpHost 显著扩容；新增 @google-cloud/storage 依赖（服务于 GCS 相关上传/同步，未见明确 UI） |
| [1.15200.0](2026-06-23_1.15200.0.md) | `mac`、`win` | 2026-06-23 | 42.4.0 | 企业/云接入大版本：node-pty 升级并改为双架构 prebuilds；主进程落地内置 Microsoft 365 MCP 服务器配置、AWS Bedrock/Vertex/Foundry 云厂商接入与托管配置（managed-config）策略 UI；MCP SDK 升 1.29.0 |
| [1.14271.0](2026-06-18_1.14271.0.md) | `mac`、`win` | 2026-06-18 | 42.4.0 | 企业管控铺垫版：新增 managed-config 依赖（受管 IdP/OIDC 配置，index.js 中可见 issuer/authorizationUrl/tokenUrl/oidc/bootstrapUrl 校验与 healthy/invalid_config/auth_failed 等状态机），网页端加入组织限制与花费限额 UI |
| [1.13576.4](2026-06-18_1.13576.4.md) | `mac`、`win` | 2026-06-18 | 42.4.0 | 无实质功能变化（app.asar 与 ion-dist 全量重建、纯哈希重排） |
| [1.13576.1](2026-06-17_1.13576.1.md) | `mac`、`win` | 2026-06-17 | 42.4.0 | 无实质功能变化（仅重建/重签名 + IPC UUID 轮换） |
| [1.13576.0](2026-06-16_1.13576.0.md) | `mac`、`win` | 2026-06-16 | 42.4.0 | 功能版：新增 Bedrock Mantle 网关与 Claude API 凭证类型、beta 功能管理开关；office365-mcp 打包结构精简，并为 Linux 发行引入 deb 打包器 |
| [1.12603.1](2026-06-11_1.12603.1.md) | `mac`、`win` | 2026-06-11 | 42.4.0 | 无实质功能变化（热修复/重建） |
| [1.12603.0](2026-06-11_1.12603.0.md) | `mac` | 2026-06-11 | 42.4.0 | 重量级版本：Electron 升至 42.4.0，首次内置 office365-mcp 服务器（带微软原生认证 MSAL 与 PDF 抽取），应用体积增加约 8MB |
| [1.11847.5](2026-06-09_1.11847.5.md) | `mac`、`win` | 2026-06-09 | 41.6.1 | 网页端新增 frame-gallery 入口并重组动态 i18n 目录；主进程仅模型发现错误处理的小改动 |
| [1.11187.4](2026-06-05_1.11187.4.md) | `mac`、`win` | 2026-06-05 | 41.6.1 | 无实质功能变化（小修复/重建） |
| [1.11187.3](2026-06-05_1.11187.3.md) | `mac` | 2026-06-05 | 41.6.1 | 无主进程功能变化，网页前端更新 |
| [1.11187.2](2026-06-05_1.11187.2.md) | `mac` | 2026-06-05 | 41.6.1 | 主进程随 SDK 更新，本版主要为网页前端更新 |
| [1.11187.1](2026-06-04_1.11187.1.md) | `mac`、`win` | 2026-06-04 | 41.6.1 | 以浏览器工具/凭证健壮性为主的迭代；引入 @ant/browser-tool-schemas 依赖，网页前端例行更新 |
| [1.10628.2](2026-06-03_1.10628.2.md) | `mac`、`win` | 2026-06-03 | 41.6.1 | 主进程无实质变化，网页前端更新 |
| [1.10628.0](2026-06-03_1.10628.0.md) | `mac`、`win` | 2026-06-03 | 41.6.1 | 功能铺垫版：网页端拆出 frame-shell 独立入口、语音 worklet 更新，主进程新增 Auto mode 管控并移除 Swift 热键绑定 |
| [1.9659.4](2026-06-02_1.9659.4.md) | `mac`、`win` | 2026-06-02 | 41.6.1 | 无实质功能变化（agent-sdk 升级 + 重建） |
| [1.9659.2](2026-05-29_1.9659.2.md) | `mac`、`win` | 2026-05-29 | 41.6.1 | 无实质功能变化（agent-sdk 升级 + 重建） |
| [1.9659.1](2026-05-28_1.9659.1.md) | `mac`、`win` | 2026-05-28 | 41.6.1 | 功能版：接入 Box 连接器端点、Claude.ai 数据导入（SSO）、Chat/Cowork 分 Tab 管控策略，并加固 shell 探测子进程的进程组清理 |
| [1.9255.2](2026-05-27_1.9255.2.md) | `mac`、`win` | 2026-05-27 | 41.6.1 | 无实质功能变化（小修复/重建） |
| [1.9255.0](2026-05-26_1.9255.0.md) | `mac`、`win` | 2026-05-26 | 41.6.1 | 为托盘用量统计与 Chat 内代码执行开关铺路，网页端出现 Outlook 连接器安装入口 |
| [1.8555.2](2026-05-23_1.8555.2.md) | `mac`、`win` | 2026-05-23 | 41.6.1 | 主进程仅小幅改动，本版主要是网页前端（ion-dist）更新 |
| [1.8555.1](2026-05-22_1.8555.1.md) | `mac`、`win` | 2026-05-22 | 41.6.1 | 无实质功能变化（agent-sdk 升级 + 重建） |
| [1.8555.0](2026-05-21_1.8555.0.md) | `mac`、`win` | 2026-05-21 | 41.6.1 | 常规迭代：agent-sdk 升级、MCP instructions 透传、shell 环境白名单收紧，并同步了一轮网页前端与全部语言包 |
| [1.8089.1](2026-05-19_1.8089.1.md) | `mac`、`win` | 2026-05-19 | 41.6.1 | 无实质功能变化（仅重建/重签名/version bump） |
| [1.8089.0](2026-05-19_1.8089.0.md) | `mac`、`win` | 2026-05-19 | 41.6.1 | Electron 41.6.1 + 企业第三方推理配置完善（Anthropic API provider、模型发现、自定义推理头、proxy 支持 https-proxy-agent）；Info.plist 新增 NSDesktopFolderUsageDescription / NSDocumentsFolderUsageDescription（"Claude stores your scheduled tasks, live artifacts and other Cowork files here."）/ NSDownloadsFolderUsageDescription（Cowork 文件夹权限明文化）；插件分发 MCP 服务器的管理员工具策略（"Admin policy applied to plugin-delivered MCP servers."）；启动时公司公告（"Company announcements to display at startup"）；git commit/PR 署名（attribution）设置与 auto-compact 会话压缩设置 |
| [1.7196.3](2026-05-18_1.7196.3.md) | `mac`、`win` | 2026-05-18 | 41.5.0 | 无实质功能变化（纯版本号提升 + 重签名重发包） |
| [1.7196.1+abcd6556](2026-05-16_1.7196.1+abcd6556.md) | `mac`、`win` | 2026-05-16 | 41.5.0 | 远程 SSH 部署（Cowork 远程主机路径）错误处理补全："failed to install claude cli" / "failed to start remote server" / "server --install" / "sftp transfer stalled" / "ssh connection setup timed out" / "cannot parse privatekey" / "vm_pre_boot_error" / "host denied" / EADDRNOTAVAIL / "text file busy"——修复远程 VM 部署（在远程主机安装 claude cli）失败的系列问题 |
| [1.7196.1+ddbeb72e](2026-05-15_1.7196.1+ddbeb72e.md) | `mac` | 2026-05-15 | 41.5.0 | 设备证明与连接健壮性：DEVICE_ATTESTATION_STATUS_ / VERIFIED_BY_GATE / bridge_event_attestation（桥接事件设备证明）；ANTHROPIC_WORKSPACE_ID；SSE 长连接保活（session_keepalive_heartbeat / liveness_timeout / "SSE stream ended by server, reconnecting" / cli_sse_event_filtered）；background_tasks |
| [1.7196.0](2026-05-12_1.7196.0.md) | `mac`、`win` | 2026-05-12 | 41.5.0 | 企业身份与管控增强：ANTHROPIC_* 凭据环境变量族（ANTHROPIC_IDENTITY_TOKEN(_FILE) / SERVICE_ACCOUNT_ID / FEDERATION_RULE_ID / PROFILE / ORGANIZATION_ID / SCOPE / CONFIG_DIR，供 CLI/网关鉴权传递）；MCP Elicitation 支持（Elicitation/ElicitationResult）；管理项 "Disable claude:// deep-link handling"、"Disable model verification"；GrowthbookExperimentEvent（A/B 实验事件）；模型名 "Claude Opus 4" 首现；"Halo detached."（Buddy Halo 悬浮窗状态） |
| [1.6608.2](2026-05-09_1.6608.2.md) | `mac`、`win` | 2026-05-09 | 41.5.0 | 小型热修复：新增 permission_stall 遥测（检测权限请求卡死/未决状态，针对 1.6608.0 发布后的问题） |
| [1.6608.1](2026-05-08_1.6608.1.md) | `win` | 2026-05-08 | — | `TODO`（`win`）— _详细技术差分待补充_ |
| [1.6608.0](2026-05-07_1.6608.0.md) | `mac`、`win` | 2026-05-07 | 41.5.0 | 大扫除 + 新能力：drizzle/operon 本地 SQLite 栈整体移除（改为远端/网页侧存储）；新增 Cowork artifact 分享与 SafeFs 沙箱文件系统错误码族（ERR_SAFE_FS_DISPOSED/ESCAPE/NOT_REGULAR/ROOT/SIZE/SYMLINK）；出现 condadata.img / condadata.vhdx（VM 附加数据盘命名，承载 conda/Python 环境）；Info.plist 新增 "ElectronTeamID": "Q6L2SF6YDW"（通知签名团队 ID）；"Microsoft 365" 字面量（office365-mcp 集成入口） |
| [1.6259.1](2026-05-06_1.6259.1.md) | `mac`、`win` | 2026-05-06 | 41.5.0 | 无实质功能变化（同日热修复重发/重建） |
| [1.6259.0](2026-05-06_1.6259.0.md) | `mac`、`win` | 2026-05-06 | 41.5.0 | Electron 41.5.0 + Bedrock SSO（IAM Identity Center，X-Amzn-Bedrock-Service-Tier 服务层级头）；"Hide Anthropic sign-in"（第三方网关白标选项）；工具审批锁定（"Lock the approval state for specific tools. Unlisted tools stay user-controlled."）；egress 硬拦截（"Link-local and metadata addresses are not allowed."，防 SSRF）；Edit 等内置工具参数说明更新（随 agent-sdk 0.2.128） |
| [1.5354.0](2026-04-29_1.5354.0.md) | `mac`、`win` | 2026-04-29 | 41.3.0 | 凭据类型注册表大扩容（github-pat/fine-grained/app-token/refresh-token、gitlab-deploy-token/pat、databricks-api-token、digitalocean-access-token/pat、gcp-api-key、aws-access-token、azure-ad-client-secret、huggingface-access-token、grafana-api-key×3、hashicorp-tf-api-token、anthropic-api-key/admin-api-key——用于敏感凭据识别与日志脱敏）；新增 claude-simulator、cowork-desktop-dispatch、get_desktop_info（桌面信息 MCP 工具）；iOS Simulator 可用性检查（"iOS Simulator requires macOS"）；bootstrapOidc 端点强制 https |
| [1.5220.0](2026-04-28_1.5220.0.md) | `mac`、`win` | 2026-04-28 | 41.3.0 | 托管配置体系深化：Bedrock service tier、Gateway auth scheme、凭据 helper（外部可执行文件打印凭据 + Headers helper 脚本 + 缓存 TTL）、自动更新强制安装窗口（默认 72 小时）、组织 workspace 文件夹白名单（"Folders users may attach as workspace"）、Cowork 工具 egress 域名配置（"Domains Cowork's tools may reach during a turn"）、"Built-in tools removed from Cowork."、PR 自动化（CHANGES_REQUESTED / Auto-archive on PR close）；新增 VM 帧缓冲预览能力 |
| [1.4758.0](2026-04-24_1.4758.0.md) | `mac`、`win` | 2026-04-24 | 41.3.0 | 本阶段最重一版：Electron 41.3.0 + 企业第三方推理网关（Bedrock/Vertex/Azure AI Foundry/OIDC Gateway SSO "Gateway SSO is not configured"）+ Sentry/Crashpad/winston/OTel 遥测全链接线 + "Open Chrome and click Connect in the Claude extension"（Chrome 扩展配对引导）+ Info.plist NSUserActivityTypes 改为 com.anthropic.claude.code.session；Web 前端随版多语言化 |
| [1.3883.0](2026-04-21_1.3883.0.md) | `mac`、`win` | 2026-04-21 | 41.2.0 | Info.plist 新增 NSUserActivityTypes=["com.anthropic.claude.session"]（macOS Handoff 接力支持）；SSH 管控（"SSH connections are disabled by your organization's managed settings." / SshPolicyError / claude-ssh is not available for platform）；Bootstrap OIDC 初始配置（Bootstrap config URL/server、Bootstrap sign-in (OIDC)、LoopbackPkceError）；插件安装包限定 .zip/.plugin；desktop_update_rollback_detected 更新回滚检测遥测 |
| [1.3561.0](2026-04-20_1.3561.0.md) | `mac`、`win` | 2026-04-20 | 41.2.0 | 可观测性导出配置完整化：OTEL_EXPORTER_OTLP_* 全套环境变量（含 mTLS client certificate/key、logs/metrics/traces 分别 endpoint）；BuddyRemoteFeed（Buddy 远程画面配合视频喂食/展示）；X-Trusted-Device-Token 请求头；RemotePluginSync / RemoteStdioTransport（远程插件同步传输）；artifact 限流参数（artifactMcpCallsPerMinute、artifactDataCacheTtlMs）；"Not available in CCD mode"（Claude Code Desktop 模式限制）；文件夹浏览器 Windows UNC 路径报错文案 |
| [1.3109.0](2026-04-16_1.3109.0.md) | `mac`、`win` | 2026-04-16 | 41.2.0 | 主 bundle 一次性打入 @sentry/opentelemetry 与整套 @opentelemetry/instrumentation-*（pg/redis/ioredis/kafkajs/express/fastify/graphql/mongodb/mysql2/undici/dataloader/fs 等 ~25 个 instrumentation，含 @langchain/*、@google/genai、@firebase/firestore 等目标模块名注册表）——可观测性 SDK 就位但未接 DSN，为 1.4758.0 的遥测接线铺路 |
| [1.3036.0](2026-04-16_1.3036.0.md) | `mac`、`win` | 2026-04-16 | 41.2.0 | 管理员 workspace 文件夹创建流程 + Claude Code 会话检测；PalantirFedStart 定制域名被移除（合作关系调整） |
| [1.2773.0](2026-04-15_1.2773.0.md) | `mac`、`win` | 2026-04-15 | 41.2.0 | 企业能力遥测化：desktop_enterprise_host_mode_changed、probeEgressHosts/Egress connectivity（出口连通性探测）、lastSeenRequireCoworkFullVmSandbox；agent-sdk 回滚一版 + Sentry SDK 升级，为后续可观测性接线做准备 |
| [1.2581.0](2026-04-14_1.2581.0.md) | `mac`、`win` | 2026-04-14 | 41.2.0 | 当天快速跟进版：文件夹授权弹窗、Cowork 文件预览、MCP Python 运行时支持落地 |
| [1.2278.0](2026-04-14_1.2278.0.md) | `mac`、`win` | 2026-04-14 | 41.2.0 | Electron 41.2.0 升级 + VM 镜像扩容 + Buddy BLE maker 桥指南；同时内置企业遥测/自动更新管控的托管配置骨架 |
| [1.1617.0](2026-04-09_1.1617.0.md) | `mac`、`win` | 2026-04-09 | 40.8.5 | host_grants 增加 ro/rw 模式（默认只读，权限模型收紧）；其余为 ion-dist 滚动更新与重建 |
| [1.1348.0](2026-04-08_1.1348.0.md) | `mac`、`win` | 2026-04-08 | 40.8.5 | 阶段性重大功能版本（zip +15MB）：Buddy 蓝牙硬件伴侣（配对/装固件/游戏化统计，代号 Nibblet ）以独立 buddy_window 落地；数据层新增 compute_usage 等四张表（为 Cowork 用量计量与内置 agent 配置铺路） |
| [1.1062.0](2026-04-07_1.1062.0.md) | `mac`、`win` | 2026-04-07 | 40.8.5 | 企业功能大批量落地：托管配置新增 LLM 推理网关体系（inferenceProvider / inferenceGatewayBaseUrl/ApiKey / Bedrock bearerToken+VPCE+region / Vertex project+region+credentialsFile+baseUrl / Foundry resource+apiKey / credentialHelper+TTL / token 窗口限额 / models 白名单），并支持 Windows 原生注册表读取托管 MCP 配置（"Native registry reading failed"、"must be a JSON array of valid MCP server configs"）；本地新增会话记录搜索 worker 与 host_call_log 迁移；shell 路径 worker 加固文件权限 |
| [1.569.0](2026-04-03_1.569.0.md) | `mac`、`win` | 2026-04-03 | 40.8.5 | 版本号切换为 1.<build>.0 方案的首个版本；Cowork artifact 页新增 back/forward 导航桥；其余为 ion-dist 常规滚动与重建 |
| [1.2.234](2026-04-01_1.2.234.md) | `mac`、`win` | 2026-04-01 | 40.8.5 | 阶段性重要版本：Electron 升级到 40.8.5；claude.ai 前端首次离线打包进应用（ion-dist，781 文件）；移除 claude-ssh 辅助二进制；新增音频采集权限声明；版本号方案由 1.1.x（四段）改为 1.2.x（三段） |
| [1.1.9669](2026-03-31_1.1.9669.md) | `mac`、`win` | 2026-03-31 | 40.4.1 | direct MCP host 上线：主进程自带完整 MCP SDK（zod v4 校验、elicitation、OAuth DCR、任务与 SSE），为第三方/直连 MCP server 提供运行时（与 directMcpHost 命名对应的"直连宿主"模式） |
| [1.1.9493](2026-03-29_1.1.9493.md) | `mac`、`win` | 2026-03-29 | 40.4.1 | 无实质功能变化（仅重建） |
| [1.1.9310](2026-03-27_1.1.9310.md) | `mac`、`win` | 2026-03-27 | 40.4.1 | Cowork artifact 桥接 preload 上线：artifact 页面获得 MCP 工具调用能力 |
| [1.1.9134](2026-03-27_1.1.9134.md) | `mac`、`win` | 2026-03-27 | 40.4.1 | 无实质功能变化（仅重建） |
| [1.1.8986](2026-03-26_1.1.8986.md) | `mac` | 2026-03-26 | 40.4.1 | Cowork 数据层成形：drizzle SQLite 迁移管线 + 4 个生物主题示例项目种子（CRISPR 筛选、酶工程、极端微生物、免疫疗法），为 sqlite-worker 配套的本地会话/项目存储铺路 |
| [1.1.8629](2026-03-25_1.1.8629.md) | `mac`、`win` | 2026-03-25 | 40.4.1 | 无实质功能变化（仅重建） |
| [1.1.8359](2026-03-24_1.1.8359.md) | `mac`、`win` | 2026-03-24 | 40.4.1 | 回滚 bioknowledge 技能包，其余为重建；computer_use 与 sqlite-worker 保留 |
| [1.1.8308](2026-03-23_1.1.8308.md) | `mac` | 2026-03-23 | 40.4.1 | 三件事：computer_use 原生模块与 teach 预加载上线；node:sqlite worker（Cowork 本地数据库底座）加入；一次性打包 757 个 bioknowledge 生物技能文件（次日即回滚，见下一条） |
| [1.1.7714](2026-03-19_1.1.7714.md) | `mac`、`win` | 2026-03-19 | 40.4.1 | 基本为重建；仅新增一条 https 强制校验文案（为配置项安全加固） |
| [1.1.7464](2026-03-18_1.1.7464.md) | `mac`、`win` | 2026-03-18 | 40.4.1 | 无实质功能变化（仅重建） |
| [1.1.7203](2026-03-17_1.1.7203.md) | `mac`、`win` | 2026-03-17 | 40.4.1 | shell-path worker 的子进程 stdio 描述符清理修复，其余为重建 |
| [1.1.7053](2026-03-17_1.1.7053.md) | `mac`、`win` | 2026-03-17 | 40.4.1 | Cowork 插件系统落地（VM 内 shim 确认协议）+ pty 环境支持 Git 提交签名；另引入 imagine-server 依赖（与图像生成 imagine 功能有关，仅依赖声明，未见独立进程文件） |
| [1.1.6679](2026-03-13_1.1.6679.md) | `mac`、`win` | 2026-03-13 | 40.4.1 | 无实质功能变化（仅重建） |
| [1.1.6452](2026-03-12_1.1.6452.md) | `mac`、`win` | 2026-03-12 | 40.4.1 | 无实质功能变化（仅重建/重签名/chunk 重排） |
| [1.1.6041](2026-03-10_1.1.6041.md) | `mac`、`win` | 2026-03-10 | 40.4.1 | agent-sdk 0.2.72 升级与主题 design token 重命名的工程版本；无新功能字符串 |
| [1.1.5749](2026-03-08_1.1.5749.md) | `mac`、`win` | 2026-03-08 | 40.4.1 | computer-use 能力接入原生通道（computer-use-mcp 依赖 + claude-swift 绑定 + computerUseEnabled 配置）；为企业 SSL 检查代理透传证书环境变量 |
| [1.1.5368](2026-03-05_1.1.5368.md) | `mac`、`win` | 2026-03-05 | 40.4.1 | 阶段性重大更新：Echo 托盘应用整体移除；接入 ion-preview.claude.ai 预览源（Ion 前端迁移前兆）；新增 conway-client 与 tweetnacl 依赖；自动更新修复与 Claude in Chrome 引导等大量用户可见流程更新 |
| [1.1.4498](2026-02-27_1.1.4498.md) | `mac`、`win` | 2026-02-27 | 40.4.1 | 打通用户 shell 环境与 Claude Code 会话：shell 探测 worker 显式透传 CLI 配置与 OTEL 遥测环境变量（含 ANTHROPIC_BASE_URL 自定义网关支持） |
| [1.1.4328](2026-02-25_1.1.4328.md) | `mac`、`win` | 2026-02-25 | 40.4.1 | 企业管控与平台兼容性版本：管理员可禁用 Cowork/Claude Code，不允许的扩展由"移除"改为"禁用"，新增设置损坏自愈提示；Cowork 支持矩阵（OS 版本/架构门槛）明确化 |
| [1.1.4173](2026-02-24_1.1.4173.md) | `mac`、`win` | 2026-02-24 | 40.4.1 | agent-sdk 0.2.51 升级为主的重建；同日第二构建 |
| [1.1.4088](2026-02-24_1.1.4088.md) | `mac`、`win` | 2026-02-24 | 40.4.1 | 主进程 bundle 小幅增长但无字符串/资源级变化（内部逻辑微调，依据不足不展开） |
| [1.1.4010](2026-02-22_1.1.4010.md) | `mac`、`win` | 2026-02-22 | 40.4.1 | 无实质功能变化（仅重建/重签名/chunk 重排） |
| [1.1.3963](2026-02-21_1.1.3963.md) | `mac`、`win` | 2026-02-21 | 40.4.1 | 无实质功能变化（仅重建/重签名/chunk 重排）；同日第二构建 |
| [1.1.3918](2026-02-21_1.1.3918.md) | `mac`、`win` | 2026-02-21 | 40.4.1 | MCP SDK 升级至 1.26.0 为主；无新功能字符串 |
| [1.1.3830](2026-02-20_1.1.3830.md) | `mac`、`win` | 2026-02-20 | 40.4.1 | 无实质功能变化（重建 + agent-sdk dev 快照更新）；同日第二构建 |
| [1.1.3770](2026-02-20_1.1.3770.md) | `mac`、`win` | 2026-02-20 | 40.4.1 | claude-ssh 成为正式依赖、agent-sdk 升至 0.2.49，属功能配套的工程化版本 |
| [1.1.3647](2026-02-19_1.1.3647.md) | `mac`、`win` | 2026-02-19 | 40.4.1 | 无实质功能变化（仅重建/重签名/chunk 重排 + agent-sdk dev 版更新）；同日第二构建 |
| [1.1.3541](2026-02-19_1.1.3541.md) | `mac`、`win` | 2026-02-19 | 40.4.1 | 为 SSH 远程会话功能补齐 mac 平台 claude-ssh 二进制（可向 mac 远端主机部署 CLI），配 agent-sdk 升级 |
| [1.1.3363](2026-02-17_1.1.3363.md) | `mac`、`win` | 2026-02-17 | 40.4.1 | claude-swift VM 状态 API 异步化（Cowork VM 稳定性）；新增 CDP 远程调试端口令牌认证（Ed25519 签名 + 5 分钟时效）；引入 playwright-core（供自动化测试） |
| [1.1.3189](2026-02-14_1.1.3189.md) | `mac`、`win` | 2026-02-14 | 40.4.1 | Electron 40.4.1；VM 镜像按 CPU 架构分发（zip 增 11MB），远程 CLI 部署升级为带 sha256 校验的 zstd 分发；"VM" 在用户文案中统一更名为 "Cowork VM" |
| [1.1.3149](2026-02-13_1.1.3149.md) | `win` | 2026-02-13 | — | `TODO`（`win`）— _详细技术差分待补充_ |
| [1.1.2998](2026-02-12_1.1.2998.md) | `mac`、`win` | 2026-02-12 | 40.4.0 | Electron 大版本升级 39.5.0 → 40.4.0；Cowork 获得工作区重装/Net Log 诊断菜单，并向 VM 内 CLI 注入 opt-in OTEL 遥测配置 |
| [1.1.2685](2026-02-10_1.1.2685.md) | `mac`、`win` | 2026-02-10 | 39.5.0 | 远程主机 Claude CLI 部署（ccd-cli）逻辑首次进入主进程（服务于 SSH 远程会话功能）；同日第二构建，其余为重建 |
| [1.1.2512](2026-02-10_1.1.2512.md) | `mac`、`win` | 2026-02-10 | 39.5.0 | 常规迭代版本，主要为 shell-path worker 对 disclaimer 助手二进制缺失时的错误处理改进；其余为重建与哈希重排 |
| [1.1.2321](2026-02-07_1.1.2321.md) | `mac`、`win` | 2026-02-07 | 39.5.0 | Electron 39.5 小版本升级 + Claude in Chrome 多浏览器切换的准备代码 |
| [1.1.2156](2026-02-06_1.1.2156.md) | `mac`、`win` | 2026-02-06 | 39.4.0 | 无实质功能变化（代码整理/重建） |
| [1.1.2128](2026-02-05_1.1.2128.md) | `mac`、`win` | 2026-02-05 | 39.4.0 | 无实质功能变化（小步迭代） |
| [1.1.2102](2026-02-05_1.1.2102.md) | `mac`、`win` | 2026-02-05 | 39.4.0 | 技能分发的用户侧入口（拖放 .skill 安装）+ Chrome 扩展同账号提示 |
| [1.1.1890](2026-02-04_1.1.1890.md) | `mac`、`win` | 2026-02-04 | 39.4.0 | Electron 39 升级 + FedStart 政府云部署支持是两大主题；其余为 Chrome/SSH/Skills 的持续迭代 |
| [1.1.1520](2026-01-30_1.1.1520.md) | `mac`、`win` | 2026-01-30 | 37.10.3 | 把 ssh2（含端口转发/Unix domain 转发）整体内联进主进程，是 Cowork VM 网络能力（端口转发、编辑器/服务接入）的关键一步 |
| [1.1.1200](2026-01-28_1.1.1200.md) | `mac`、`win` | 2026-01-28 | 37.10.3 | SSH 基础设施版：自带双架构 Linux SSH 二进制 + ws 依赖 + 主进程 SSH 会话管理，为 VM 端口转发/远程访问铺路 |
| [1.1.1093](2026-01-27_1.1.1093.md) | `mac`、`win` | 2026-01-27 | 37.10.3 | Cowork Shortcuts（自动化快捷方式）桥接层与可信目录设置入包，尚无对用户暴露的文案 |
| [1.1.886](2026-01-24_1.1.886.md) | `mac`、`win` | 2026-01-24 | 37.10.3 | 本地 skill 文件（.skill，30MB 上限）打开/预览能力与本地插件清单（skills/commands/agents/hooks/mcpServers）解析落地 |
| [1.1.799](2026-01-23_1.1.799.md) | `mac`、`win` | 2026-01-23 | 37.10.3 | 无实质功能变化（当日第三个小修版） |
| [1.1.762](2026-01-23_1.1.762.md) | `mac`、`win` | 2026-01-23 | 37.10.3 | Claude in Chrome 一键安装/重启流程上线，桌面端可直接把扩展装进 Chrome/Brave |
| [1.1.673](2026-01-23_1.1.673.md) | `mac`、`win` | 2026-01-23 | 37.10.3 | Cowork 成型版：独立 cowork MCP server、知识库工具、本地插件目录与家目录限制；Echo 窗口功能继续加厚 |
| [1.1.381](2026-01-18_1.1.381.md) | `mac`、`win` | 2026-01-18 | 37.10.3 | 无实质功能变化（MCP 相关小调整 + 重建） |
| [1.1.351](2026-01-17_1.1.351.md) | `mac`、`win` | 2026-01-17 | 37.10.3 | 无实质功能变化（小步重建/内部微调） |
| [1.1.329](2026-01-16_1.1.329.md) | `win` | 2026-01-16 | — | `TODO`（`win`）— _详细技术差分待补充_ |
| [1.1.280](2026-01-16_1.1.280.md) | `mac`、`win` | 2026-01-16 | 37.10.3 | 1.1 系列起点 = Cowork 预研版：10MiB 占位 VM 镜像 + 目录挂载/文件删除授权 MCP 工具入包，功能仍藏于调试菜单之后（默认不可见，等待后续开关放量） |
| [1.0.3218](2026-01-12_1.0.3218.md) | `mac`、`win` | 2026-01-12 | 37.10.3 | Skills 下发/挂载基础设施与 VM 会话管理、日志化反馈的首个实现版；对外文案集中在本地代理模式与浏览器工具授权 |
| [1.0.2768](2026-01-05_1.0.2768.md) | `mac`、`win` | 2026-01-05 | 37.10.3 | 功能大版本：终端（node-pty）、Claude in Chrome 改名 + 独立 helper、Echo 设备窗口（API key 配对/通知）落地；同时旧内部更新体系文案清除 |
| [1.0.2339](2025-12-16_1.0.2339.md) | `win` | 2025-12-16 | — | `TODO`（`win`）— _详细技术差分待补充_ |
| [1.0.1768](2025-12-06_1.0.1768.md) | `win` | 2025-12-06 | — | `TODO`（`win`）— _详细技术差分待补充_ |
| [1.0.1656](2025-12-04_1.0.1656.md) | `win` | 2025-12-04 | — | `TODO`（`win`）— _详细技术差分待补充_ |
| [1.0.1405](2025-12-01_1.0.1405.md) | `win` | 2025-12-01 | — | `TODO`（`win`）— _详细技术差分待补充_ |
| [1.0.1307](2025-11-26_1.0.1307.md) | `win` | 2025-11-26 | — | `TODO`（`win`）— _详细技术差分待补充_ |
| [1.0.1217](2025-11-24_1.0.1217.md) | `win` | 2025-11-24 | — | `TODO`（`win`）— _详细技术差分待补充_ |
| [1.0.734](2025-11-21_1.0.734.md) | `mac`、`win` | 2025-11-21 | 37.10.0 | 1.0 首版 = 渠道迁移 + 工程大清理：包名改 @ant/* 体系、252 个构建工具包移出分发物、IPC 通道签名轮换，同时预置 Clod 宠物资源包、Claude for Chrome 集成入口与 macOS 13 门槛。功能面变化不大，但发行结构完全换代 |
| [1.0.332](2025-11-05_1.0.332.md) | `win` | 2025-11-05 | — | `TODO`（`win`）— _详细技术差分待补充_ |
| [1.0.211](2025-10-31_1.0.211.md) | `win` | 2025-10-31 | — | `TODO`（`win`）— _详细技术差分待补充_ |
| [0.14.10](2025-10-28_0.14.10.md) | `mac`、`win` | 2025-10-28 | 37.6.0 | 表面是重建版（chunk 重排 + Sentry id 轮换），实质变化是把更新源指向 downloads.claude.ai 渠道，是 0.x → 1.0 渠道迁移的最后一步准备 |
| [0.14.7](2025-10-28_0.14.7.md) | `win` | 2025-10-28 | — | `TODO`（`win`）— _详细技术差分待补充_ |
| [0.14.4](2025-10-21_0.14.4.md) | `win` | 2025-10-21 | — | `TODO`（`win`）— _详细技术差分待补充_ |
| [0.14.1](2025-10-21_0.14.1.md) | `mac` | 2025-10-21 | 37.6.0 | 0.14 系列开局：主进程拆出 index.pre.js 启动前置模块，品牌主题色变量全面更新，图标资源（Assets.car）更新，并切换到新的 Sentry 上报项目 |
| [0.13.108](2025-10-17_0.13.108.md) | `mac`、`win` | 2025-10-17 | 37.6.0 | 与 0.13.106 同日的纯重建版本（chunk 重排/重签名），无实质功能变化 |
| [0.13.106](2025-10-17_0.13.106.md) | `mac` | 2025-10-17 | 37.6.0 | 帮助菜单从"反馈"转向"支持"入口，Chrome 扩展引导补充登录前置条件；其余为重建 |
| [0.13.91](2025-10-10_0.13.91.md) | `mac` | 2025-10-10 | 37.6.0 | 打包事故版本：MSIX 打包器等构建工具链整体泄漏进 app.asar（+3627 文件，约 7MB zip 增量）；功能面仅 Claude for Chrome 引导文案细化 |
| [0.13.64](2025-10-08_0.13.64.md) | `mac`、`win` | 2025-10-08 | 37.6.0 | Electron 37.6.0；字体切换为 AnthropicSans/AnthropicSerif 新品牌字族；引入 JWT 依赖（组织扩展签名验证）；宣布 Claude for Chrome 集成 |
| [0.13.37](2025-09-25_0.13.37.md) | `mac`、`win` | 2025-09-25 | 37.5.1 | Quick Entry/听写体验继续打磨（Caps Lock、麦克风权限引导、打开文档枚举），新增安装 ID 复制支持诊断 |
| [0.13.19](2025-09-18_0.13.19.md) | `mac`、`win` | 2025-09-18 | 37.5.1 | Electron 37.5.1 + mime 依赖；Quick Entry 提交携带文件路径。接近纯重建 |
| [0.13.11](2025-09-12_0.13.11.md) | `mac`、`win` | 2025-09-12 | 37.4.0 | 升级 Electron 37.4.0；最近会话（recent chats）菜单数据通道就位；听写权限被拒的引导文案上线 |
| [0.12.129](2025-08-30_0.12.129.md) | `mac`、`win` | 2025-08-30 | 36.8.1 | 为升级 Electron 37 做准备的技术版本（preload 导入方式调整），无用户可见变化 |
| [0.12.125](2025-08-29_0.12.125.md) | `mac`、`win` | 2025-08-29 | 36.8.1 | claude-swift 发布为 @anthropic-ai 官方包并合并为单一 universal 二进制；扩展安装报错文案打磨；其余为重建 |
| [0.12.112](2025-08-20_0.12.112.md) | `mac`、`win` | 2025-08-20 | 36.8.1 | 阶段性重大架构版本：Electron 升至 36.8.1，打包方式从"node_modules + 分散 renderer assets"改为全量内联单 bundle；原生层由 claude-swift 完全接管（claude-native node 退场）；Quick Entry/听写/拖拽截图 UI 齐备并完成 11 语种本地化 |
| [0.12.55](2025-07-25_0.12.55.md) | `mac`、`win` | 2025-07-25 | 36.4.0 | Quick Entry 窗口获得独立 preload（quickWindow.js），与 About 窗口对齐；其余为重建 |
| [0.12.49](2025-07-23_0.12.49.md) | `mac`、`win` | 2025-07-23 | 36.4.0 | claude-native 职责重塑（新增 About 窗口 preload、MCP 宿主路径修复、MCP SDK/zod 升级），claude.com 域名进入客户端 |
| [0.12.28](2025-07-19_0.12.28.md) | `mac`、`win` | 2025-07-19 | 36.4.0 | 原生层重构：Swift 插件暂时退场，claude-native 吸收系统读取能力（registry/plist）并把构建依赖整体内嵌；应用内更新器文案完善 |
| [0.12.20](2025-07-17_0.12.20.md) | `mac`、`win` | 2025-07-17 | 36.4.0 | MCP server 加载改为 ESM 动态 import（支持 ESM 格式的 MCP server），其余为重建 |
| [0.12.19](2025-07-17_0.12.19.md) | `mac`、`win` | 2025-07-17 | 36.4.0 | 品牌字体打包位置调整（asar renderer assets → app Resources/fonts），其余为重建 |
| [0.12.16](2025-07-14_0.12.16.md) | `mac`、`win` | 2025-07-14 | 36.4.0 | 同日发布的纯重建/重签名版本，无实质功能变化（chunk 重排 + IPC channel 标识符再生成） |
| [0.12.15](2025-07-14_0.12.15.md) | `mac`、`win` | 2025-07-14 | 36.4.0 | 语音听写（dictation）与 Quick Entry（⌥Space 快捷输入，支持附图）在本版落地：麦克风/语音识别权限声明、claude-swift 提交事件齐备；同时本地设置窗口被移除，设置转向 web |
| [0.11.6](2025-06-30_0.11.6.md) | `mac`、`win` | 2025-06-30 | 36.4.0 | 例行重建版本：仅 MCP runtime 的 stdin 处理重写 + 全量 chunk 重排，无用户可见功能变化 |
| [0.11.4](2025-06-28_0.11.4.md) | `mac`、`win` | 2025-06-28 | 36.4.0 | 基本为重建版本，仅扩展详情页 markdown 样式微调；无实质功能变化 |
| [0.11.3](2025-06-26_0.11.3.md) | `mac`、`win` | 2025-06-26 | 36.4.0 | CDX 正式更名 DXT（Desktop Extension）：扩展注册表、blocklist 封禁、签名校验、自动更新框架就位；同时上线 Statsig 事件遥测通道，主 bundle 改为哈希分块加载 |
| [0.10.38](2025-06-17_0.10.38.md) | `mac`、`win` | 2025-06-17 | 36.4.0 | 扩展系统（CDX）与内置 MCP Node Host 落地的关键版本：.cdx 文件关联、扩展安装 UI、API Key 管理、完整 auto-updater（定时+空闲感知+自动重启）与主进程 Sentry 崩溃上报同时上线；claude-studio 独立包被移除 |
| [0.10.14](2025-06-05_0.10.14.md) | `mac`、`win` | 2025-06-05 | 36.4.0 | claude-studio大规模扩容；桌面端加入硬件加速开关与缓存清理/重置对话框 |
| [0.9.4](2025-06-03_0.9.4.md) | `mac`、`win` | 2025-06-03 | 36.2.1 | 跨一个月的大版本：升级 Electron 36、引入 Swift 原生插件实验与 claude-studio 包（内含 MCP 权限服务器 + React 渲染端 + 随包 TypeScript 全套），zip 体积 +18MB |
| [0.9.3](2025-04-30_0.9.3.md) | `mac`、`win` | 2025-04-30 | 34.0.2 | 增加主窗口 webview 卡死检测与自动 kill+reload 的看门狗机制（为修复挂死问题） |
| [0.9.2+b2184e2c](2025-04-14_0.9.2+b2184e2c.md) | `mac`、`win` | 2025-04-14 | 34.0.2 | 无实质功能变化（仅重建/重签名/chunk 重排；主 Info.plist 仅代码签名 hash 变化） |
| [0.9.2+d5e83a89](2025-04-08_0.9.2+d5e83a89.md) | `mac` | 2025-04-08 | 34.0.2 | 网络错误页与 claude.ai 重定向提示；同版本号第二构建（+d5e83a89 artifact 后缀开始出现） |
| [0.9.1](2025-04-01_0.9.1.md) | `mac`、`win` | 2025-04-01 | 34.0.2 | 小版本：帮助菜单入口微调，其余为哈希重排 |
| [0.9.0](2025-03-27_0.9.0.md) | `mac`、`win` | 2025-03-27 | 34.0.2 | 新增页内查找功能（独立 preload + 渲染窗口），Sentry 事件缓冲满丢弃日志（"Skipped sending event because buffer is full."） |
| [0.8.1](2025-03-14_0.8.1.md) | `mac`、`win` | 2025-03-14 | 34.0.2 | 加入 About（关于）窗口，带全套 Anthropic 品牌字体，并链接 support.anthropic.com |
| [0.8.0](2025-02-28_0.8.0.md) | `mac`、`win` | 2025-02-28 | 34.0.2 | 国际化版本：react-intl + 16 个语言包入包，所有菜单与设置文案改为词条化；同时升级 Electron 34 |
| [0.7.9](2025-02-10_0.7.9.md) | `mac`、`win` | 2025-02-10 | 33.3.1 | MCP SDK 1.4.1；MCP 服务器启动/连接的状态反馈与配置校验完善，桌面 bridge 权限模型初现 |
| [0.7.8](2025-01-08_0.7.8.md) | `mac`、`win` | 2025-01-08 | 33.3.1 | 首次加入完整原生菜单栏（New Conversation 快捷键等），Electron 小版本升级；auto-updater 日志流程完善 |
| [0.7.7](2024-12-19_0.7.7.md) | `mac`、`win` | 2024-12-19 | 33.2.1 | 升级 Electron 33 并接入内部 design-system 包；登录项（开机自启）设置与 preload 大扩容，MCP 调试文档链接入包 |
| [0.7.6](2024-12-19_0.7.6.md) | `win` | 2024-12-19 | — | `TODO`（`win`）— _详细技术差分待补充_ |
| [0.7.5](2024-12-02_0.7.5.md) | `mac`、`win` | 2024-12-02 | 32.1.2 | MCP SDK 升到 1.0.1；设置页用 Tailwind + Phosphor 图标重写，主进程 bundle 瘦身拆块 |
| [0.7.1](2024-11-22_0.7.1.md) | `mac`、`win` | 2024-11-22 | 32.1.2 | MCP 管理界面首次成型（安装确认、本地目录选择、日志打开、Developer Mode），设置/主窗体重构并引入 React |
| [0.6.2](2024-11-13_0.6.2.md) | `mac`、`win` | 2024-11-13 | 32.1.2 | MCP SDK 升至 0.4.0 并引入 rxjs；claude-native 增加一整套窗口/无障碍 API，Quick Window 支持多行输入与点击外部关闭 |
| [0.6.0](2024-11-11_0.6.0.md) | `win` | 2024-11-11 | — | `TODO`（`win`）— _详细技术差分待补充_ |
| [0.5.0](2024-11-08_0.5.0.md) | `win` | 2024-11-08 | — | `TODO`（`win`）— _详细技术差分待补充_ |
| [0.4.9](2024-11-02_0.4.9.md) | `mac`、`win` | 2024-11-02 | 32.1.2 | 两天后的跟版：把主进程日志切换到 winston（"A logger for just about everything."），无用户可见功能变化 |
| [0.4.8](2024-10-31_0.4.8.md) | `mac` | 2024-10-31 | 32.1.2 | macOS 桌面端初始发布基线：搭载主窗口与 Quick Window 快捷窗、claude-native 原生模块及 MCP SDK 0.1 |

## 移动端版本索引（`ios` / `android`，最新 → 最早）

| 版本 | 覆盖平台 | 发布日期 | 核心变更摘要 |
|---|---|---|---|
| [1.261124.19](2026-11-25_1.261124.19.md) | `android` | 2026-11-25（Uptodown 镜像） | Uptodown 第三方 Play 原签分包 XAPK 静态差分（`1.261123.19 → 1.261124.19`，`versionCode` `26112319 → 26112419`；不含 iOS 与 `120`–`122` 缺口，未做 `apksigner` 全量校验）：XAPK `37 → 30`（语言分包 `28 → 21`：`+te`、`−am/fil/hi/ml/mr/sw/ta/tl`）、`20/20` 原生库逐字节一致、DEX `+~1.0` MB（池 `171,650 → 173,615`）、`connect_github_card.*` + GitHub App + PR/plan/工具审批失败分类 + `CollapsedToolsSheetDestination${HostPage,ProductPage,Viewer}`、约 12 条 safeguards 换模型文案、`places_list.*`、`usage.section.*`、`settings.default_tab.*`、PHI 声明、移除 `continue_on_cloud.*`（`8 → 1`），`66` 权限/`83` 组件/API 端点零增删 |
| [1.261113.19](2026-11-14_1.261113.19.md) | `android` | 2026-11-14 | Play-split XAPK 静态差分（`1.261112.18 → 1.261113.19`）：`minSdkVersion` `29 → 32`（Android 10 → 12L，`targetSdkVersion` `37`）、XAPK 总条目 `37 → 39`（语言 split `27 → 30`）、`voice.internal.{readaloud,dictation,dictation/offline}` 重构（保留 `TTSPlaybackService`）、CCR `ProjectSheet*` / `GitHubSsoRequiredException` / `CoworkTurnOutcomeWorker` / 49 项底部导航、移除旧 Threads 与位置事件属性清单，并携带静态促销转额度/KYC 代码 |
| [1.261109.19](2026-11-11_1.261109.19.md) | `ios`、`android` | 2026-11-11 | `TODO`（`ios`、`android`）— _详细技术差分待补充_ |
| [1.261106.19](2026-11-09_1.261106.19.md) | `ios`、`android` | 2026-11-09 | `TODO`（`ios`、`android`）— _详细技术差分待补充_ |
| [1.260813.10](2026-11-09_1.260813.10.md) | `android` | 2026-11-09 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.250602.7](2026-11-09_1.250602.7.md) | `android` | 2026-11-09 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.261103.19](2026-11-08_1.261103.19.md) | `android` | 2026-11-08 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.261104.19](2026-11-07_1.261104.19.md) | `ios`、`android` | 2026-11-07 | `TODO`（`ios`、`android`）— _详细技术差分待补充_ |
| [1.261102.19](2026-11-05_1.261102.19.md) | `android` | 2026-11-05 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260831.0](2026-11-03_1.260831.0.md) | `android` | 2026-11-03 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.261030.19](2026-11-02_1.261030.19.md) | `ios`、`android` | 2026-11-02 | `TODO`（`ios`、`android`）— _详细技术差分待补充_ |
| [1.261029.20](2026-11-01_1.261029.20.md) | `android` | 2026-11-01 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.261022.20](2026-11-01_1.261022.20.md) | `android` | 2026-11-01 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.261020.20](2026-11-01_1.261020.20.md) | `android` | 2026-11-01 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.261028.19](2026-10-30_1.261028.19.md) | `ios`、`android` | 2026-10-30 | `TODO`（`ios`、`android`）— _详细技术差分待补充_ |
| [1.261027.19](2026-10-30_1.261027.19.md) | `android` | 2026-10-30 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.261026.51](2026-10-30_1.261026.51.md) | `android` | 2026-10-30 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.261026.20](2026-10-29_1.261026.20.md) | `ios` | 2026-10-29 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.261023.20](2026-10-25_1.261023.20.md) | `ios`、`android` | 2026-10-25 | `TODO`（`ios`、`android`）— _详细技术差分待补充_ |
| [1.261021.51](2026-10-24_1.261021.51.md) | `ios`、`android` | 2026-10-24 | `TODO`（`ios`、`android`）— _详细技术差分待补充_ |
| [1.261016.51](2026-10-24_1.261016.51.md) | `android` | 2026-10-24 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.261019.51](2026-10-23_1.261019.51.md) | `ios` | 2026-10-23 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.261019.20](2026-10-22_1.261019.20.md) | `ios`、`android` | 2026-10-22 | `TODO`（`ios`、`android`）— _详细技术差分待补充_ |
| [1.261015.20](2026-10-21_1.261015.20.md) | `android` | 2026-10-21 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.261016.20](2026-10-19_1.261016.20.md) | `ios` | 2026-10-19 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250512.27](2026-10-19_1.250512.27.md) | `android` | 2026-10-19 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.261014.20](2026-10-17_1.261014.20.md) | `ios`、`android` | 2026-10-17 | `TODO`（`ios`、`android`）— _详细技术差分待补充_ |
| [1.261013.20](2026-10-16_1.261013.20.md) | `ios`、`android` | 2026-10-16 | `TODO`（`ios`、`android`）— _详细技术差分待补充_ |
| [1.261012.20](2026-10-15_1.261012.20.md) | `ios`、`android` | 2026-10-15 | `TODO`（`ios`、`android`）— _详细技术差分待补充_ |
| [1.261009.20](2026-10-12_1.261009.20.md) | `ios`、`android` | 2026-10-12 | `TODO`（`ios`、`android`）— _详细技术差分待补充_ |
| [1.240805.17](2026-10-12_1.240805.17.md) | `android` | 2026-10-12 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260918.19](2026-10-11_1.260918.19.md) | `android` | 2026-10-11 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.261008.20](2026-10-10_1.261008.20.md) | `android` | 2026-10-10 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.261007.20](2026-10-10_1.261007.20.md) | `ios`、`android` | 2026-10-10 | `TODO`（`ios`、`android`）— _详细技术差分待补充_ |
| [1.261005.20](2026-10-08_1.261005.20.md) | `ios`、`android` | 2026-10-08 | `TODO`（`ios`、`android`）— _详细技术差分待补充_ |
| [1.261002.20](2026-10-05_1.261002.20.md) | `ios`、`android` | 2026-10-05 | `TODO`（`ios`、`android`）— _详细技术差分待补充_ |
| [1.260930.20](2026-10-04_1.260930.20.md) | `ios`、`android` | 2026-10-04 | `TODO`（`ios`、`android`）— _详细技术差分待补充_ |
| [1.260928.20](2026-09-30_1.260928.20.md) | `ios`、`android` | 2026-09-30 | `TODO`（`ios`、`android`）— _详细技术差分待补充_ |
| [1.260925.19](2026-09-29_1.260925.19.md) | `ios` | 2026-09-29 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.260923.51](2026-09-27_1.260923.51.md) | `ios` | 2026-09-27 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.260923.20](2026-09-26_1.260923.20.md) | `ios`、`android` | 2026-09-26 | `TODO`（`ios`、`android`）— _详细技术差分待补充_ |
| [1.260921.19](2026-09-25_1.260921.19.md) | `ios`、`android` | 2026-09-25 | `TODO`（`ios`、`android`）— _详细技术差分待补充_ |
| [1.260910.12](2026-09-22_1.260910.12.md) | `android` | 2026-09-22 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260209.37](2026-09-21_1.260209.37.md) | `android` | 2026-09-21 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260916.19](2026-09-18_1.260916.19.md) | `ios`、`android` | 2026-09-18 | `TODO`（`ios`、`android`）— _详细技术差分待补充_ |
| [1.260914.19](2026-09-16_1.260914.19.md) | `android` | 2026-09-16 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260911.19](2026-09-14_1.260911.19.md) | `ios`、`android` | 2026-09-14 | `TODO`（`ios`、`android`）— _详细技术差分待补充_ |
| [1.260909.19](2026-09-12_1.260909.19.md) | `ios`、`android` | 2026-09-12 | `TODO`（`ios`、`android`）— _详细技术差分待补充_ |
| [1.260907.19](2026-09-10_1.260907.19.md) | `ios`、`android` | 2026-09-10 | `TODO`（`ios`、`android`）— _详细技术差分待补充_ |
| [1.260806.20](2026-09-10_1.260806.20.md) | `android` | 2026-09-10 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260904.19](2026-09-07_1.260904.19.md) | `ios`、`android` | 2026-09-07 | `TODO`（`ios`、`android`）— _详细技术差分待补充_ |
| [1.260902.20](2026-09-04_1.260902.20.md) | `ios`、`android` | 2026-09-04 | `TODO`（`ios`、`android`）— _详细技术差分待补充_ |
| [1.260831.1](2026-09-03_1.260831.1.md) | `ios` | 2026-09-03 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.260828.1](2026-09-01_1.260828.1.md) | `ios` | 2026-09-01 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.260828.0](2026-08-31_1.260828.0.md) | `ios`、`android` | 2026-08-31 | `TODO`（`ios`、`android`）— _详细技术差分待补充_ |
| [1.260826.0](2026-08-29_1.260826.0.md) | `ios`、`android` | 2026-08-29 | `TODO`（`ios`、`android`）— _详细技术差分待补充_ |
| [1.260721.20](2026-08-29_1.260721.20.md) | `android` | 2026-08-29 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260702.10](2026-08-29_1.260702.10.md) | `android` | 2026-08-29 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260604.20](2026-08-29_1.260604.20.md) | `android` | 2026-08-29 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260528.10](2026-08-28_1.260528.10.md) | `android` | 2026-08-28 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260824.0](2026-08-27_1.260824.0.md) | `ios`、`android` | 2026-08-27 | `TODO`（`ios`、`android`）— _详细技术差分待补充_ |
| [1.260820.0](2026-08-22_1.260820.0.md) | `ios`、`android` | 2026-08-22 | `TODO`（`ios`、`android`）— _详细技术差分待补充_ |
| [1.260817.0](2026-08-20_1.260817.0.md) | `ios`、`android` | 2026-08-20 | `TODO`（`ios`、`android`）— _详细技术差分待补充_ |
| [1.260814.0](2026-08-18_1.260814.0.md) | `ios` | 2026-08-18 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.260813.0](2026-08-14_1.260813.0.md) | `ios`、`android` | 2026-08-14 | `TODO`（`ios`、`android`）— _详细技术差分待补充_ |
| [1.260810.0](2026-08-13_1.260810.0.md) | `ios`、`android` | 2026-08-13 | `TODO`（`ios`、`android`）— _详细技术差分待补充_ |
| [1.260611.30](2026-08-13_1.260611.30.md) | `android` | 2026-08-13 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260806.0](2026-08-12_1.260806.0.md) | `ios` | 2026-08-12 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.260430.10](2026-08-11_1.260430.10.md) | `android` | 2026-08-11 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260316.47](2026-08-06_1.260316.47.md) | `android` | 2026-08-06 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260618.10](2026-08-04_1.260618.10.md) | `android` | 2026-08-04 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.250113.17](2026-07-28_1.250113.17.md) | `android` | 2026-07-28 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260721.0](2026-07-23_1.260721.0.md) | `ios` | 2026-07-23 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.260716.0](2026-07-19_1.260716.0.md) | `ios` | 2026-07-19 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.260709.10](2026-07-19_1.260709.10.md) | `android` | 2026-07-19 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260709.0](2026-07-10_1.260709.0.md) | `ios`、`android` | 2026-07-10 | `TODO`（`ios`、`android`）— _详细技术差分待补充_ |
| [1.260702.3](2026-07-10_1.260702.3.md) | `ios` | 2026-07-10 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.260625.30](2026-07-10_1.260625.30.md) | `android` | 2026-07-10 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260702.2](2026-07-09_1.260702.2.md) | `ios` | 2026-07-09 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.260625.20](2026-07-09_1.260625.20.md) | `android` | 2026-07-09 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260702.0](2026-07-07_1.260702.0.md) | `ios` | 2026-07-07 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.260625.0](2026-07-01_1.260625.0.md) | `ios` | 2026-07-01 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.260618.1](2026-06-24_1.260618.1.md) | `ios` | 2026-06-24 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.260618.0](2026-06-23_1.260618.0.md) | `ios` | 2026-06-23 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.260611.20](2026-06-20_1.260611.20.md) | `android` | 2026-06-20 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260611.1](2026-06-17_1.260611.1.md) | `ios` | 2026-06-17 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.260604.30](2026-06-17_1.260604.30.md) | `android` | 2026-06-17 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260409.10](2026-06-17_1.260409.10.md) | `android` | 2026-06-17 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260112.27](2026-06-14_1.260112.27.md) | `android` | 2026-06-14 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.250120.7](2026-06-14_1.250120.7.md) | `android` | 2026-06-14 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260611.0](2026-06-13_1.260611.0.md) | `ios`、`android` | 2026-06-13 | `TODO`（`ios`、`android`）— _详细技术差分待补充_ |
| [1.260604.0](2026-06-09_1.260604.0.md) | `ios` | 2026-06-09 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.260521.20](2026-06-07_1.260521.20.md) | `android` | 2026-06-07 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260521.10](2026-06-05_1.260521.10.md) | `android` | 2026-06-05 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260528.1](2026-06-04_1.260528.1.md) | `ios` | 2026-06-04 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.260528.0](2026-06-03_1.260528.0.md) | `ios` | 2026-06-03 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.260507.10](2026-05-29_1.260507.10.md) | `android` | 2026-05-29 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260521.1](2026-05-28_1.260521.1.md) | `ios` | 2026-05-28 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.260423.20](2026-05-28_1.260423.20.md) | `android` | 2026-05-28 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260521.0](2026-05-27_1.260521.0.md) | `ios` | 2026-05-27 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.241111.5](2026-05-26_1.241111.5.md) | `android` | 2026-05-26 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260514.0](2026-05-20_1.260514.0.md) | `ios`、`android` | 2026-05-20 | `TODO`（`ios`、`android`）— _详细技术差分待补充_ |
| [1.260302.17](2026-05-14_1.260302.17.md) | `android` | 2026-05-14 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260507.0](2026-05-13_1.260507.0.md) | `ios` | 2026-05-13 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250106.7](2026-05-10_1.250106.7.md) | `android` | 2026-05-10 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260430.0](2026-05-06_1.260430.0.md) | `ios`、`android` | 2026-05-06 | `TODO`（`ios`、`android`）— _详细技术差分待补充_ |
| [1.260423.1](2026-05-01_1.260423.1.md) | `ios` | 2026-05-01 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.260423.0](2026-04-29_1.260423.0.md) | `ios` | 2026-04-29 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.260416.20](2026-04-27_1.260416.20.md) | `android` | 2026-04-27 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260416.0](2026-04-21_1.260416.0.md) | `ios` | 2026-04-21 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.260330.27](2026-04-20_1.260330.27.md) | `android` | 2026-04-20 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.250303.27](2026-04-18_1.250303.27.md) | `android` | 2026-04-18 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260409.1](2026-04-15_1.260409.1.md) | `ios` | 2026-04-15 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.260409.0](2026-04-14_1.260409.0.md) | `ios` | 2026-04-14 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.260402.20](2026-04-13_1.260402.20.md) | `android` | 2026-04-13 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260216.27](2026-04-10_1.260216.27.md) | `android` | 2026-04-10 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260402.0](2026-04-08_1.260402.0.md) | `ios` | 2026-04-08 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.260323.7](2026-04-03_1.260323.7.md) | `android` | 2026-04-03 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260309.17](2026-04-03_1.260309.17.md) | `android` | 2026-04-03 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260330.1](2026-04-01_1.260330.1.md) | `ios` | 2026-04-01 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.260330.0](2026-03-31_1.260330.0.md) | `ios` | 2026-03-31 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.260323.4](2026-03-27_1.260323.4.md) | `ios` | 2026-03-27 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.260323.3](2026-03-26_1.260323.3.md) | `ios` | 2026-03-26 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.260323.2](2026-03-25_1.260323.2.md) | `ios` | 2026-03-25 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.260316.3](2026-03-22_1.260316.3.md) | `ios` | 2026-03-22 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.260316.1](2026-03-20_1.260316.1.md) | `ios` | 2026-03-20 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.260316.0](2026-03-18_1.260316.0.md) | `ios` | 2026-03-18 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.260316.27](2026-03-17_1.260316.27.md) | `android` | 2026-03-17 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260309.1](2026-03-12_1.260309.1.md) | `ios` | 2026-03-12 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.260302.0](2026-03-04_1.260302.0.md) | `ios` | 2026-03-04 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.260223.17](2026-03-02_1.260223.17.md) | `android` | 2026-03-02 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260216.17](2026-03-01_1.260216.17.md) | `android` | 2026-03-01 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260223.3](2026-02-28_1.260223.3.md) | `ios` | 2026-02-28 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.260223.2](2026-02-25_1.260223.2.md) | `ios` | 2026-02-25 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250428.17](2026-02-24_1.250428.17.md) | `android` | 2026-02-24 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.251124.27](2026-02-23_1.251124.27.md) | `android` | 2026-02-23 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260216.3](2026-02-22_1.260216.3.md) | `ios` | 2026-02-22 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.260216.2](2026-02-19_1.260216.2.md) | `ios` | 2026-02-19 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.260209.0](2026-02-11_1.260209.0.md) | `ios` | 2026-02-11 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.260202.37](2026-02-09_1.260202.37.md) | `android` | 2026-02-09 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260202.5](2026-02-08_1.260202.5.md) | `ios` | 2026-02-08 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.260202.27](2026-02-05_1.260202.27.md) | `android` | 2026-02-05 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260126.27](2026-02-05_1.260126.27.md) | `android` | 2026-02-05 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260202.3](2026-02-04_1.260202.3.md) | `ios` | 2026-02-04 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.260119.17](2026-01-29_1.260119.17.md) | `android` | 2026-01-29 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260126.0](2026-01-28_1.260126.0.md) | `ios` | 2026-01-28 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.251027.7](2026-01-28_1.251027.7.md) | `android` | 2026-01-28 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260119.0](2026-01-21_1.260119.0.md) | `ios` | 2026-01-21 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.260112.17](2026-01-20_1.260112.17.md) | `android` | 2026-01-20 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.241014.17](2026-01-16_1.241014.17.md) | `android` | 2026-01-16 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.260112.1](2026-01-13_1.260112.1.md) | `ios` | 2026-01-13 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250217.2](2026-01-11_1.250217.2.md) | `android` | 2026-01-11 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.250519.17](2026-01-06_1.250519.17.md) | `android` | 2026-01-06 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.251013.27](2026-01-04_1.251013.27.md) | `android` | 2026-01-04 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.251208.37](2026-01-01_1.251208.37.md) | `android` | 2026-01-01 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.251117.27](2025-12-31_1.251117.27.md) | `android` | 2025-12-31 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.251013.17](2025-12-29_1.251013.17.md) | `android` | 2025-12-29 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.250127.7](2025-12-29_1.250127.7.md) | `android` | 2025-12-29 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.251215.57](2025-12-28_1.251215.57.md) | `android` | 2025-12-28 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.251208.27](2025-12-22_1.251208.27.md) | `android` | 2025-12-22 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.251110.27](2025-12-22_1.251110.27.md) | `android` | 2025-12-22 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.251215.4](2025-12-20_1.251215.4.md) | `ios` | 2025-12-20 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.251215.47](2025-12-17_1.251215.47.md) | `android` | 2025-12-17 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.251215.2](2025-12-17_1.251215.2.md) | `ios` | 2025-12-17 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.251215.37](2025-12-16_1.251215.37.md) | `android` | 2025-12-16 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.251208.5](2025-12-13_1.251208.5.md) | `ios` | 2025-12-13 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.251208.4](2025-12-12_1.251208.4.md) | `ios` | 2025-12-12 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.251208.3](2025-12-10_1.251208.3.md) | `ios` | 2025-12-10 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.251124.3](2025-11-28_1.251124.3.md) | `ios` | 2025-11-28 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250728.36](2025-11-28_1.250728.36.md) | `android` | 2025-11-28 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.241007.7](2025-11-27_1.241007.7.md) | `android` | 2025-11-27 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.251117.17](2025-11-25_1.251117.17.md) | `android` | 2025-11-25 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.251124.2](2025-11-24_1.251124.2.md) | `ios` | 2025-11-24 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.251117.1](2025-11-20_1.251117.1.md) | `ios` | 2025-11-20 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250922.37](2025-11-19_1.250922.37.md) | `android` | 2025-11-19 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.251110.1](2025-11-11_1.251110.1.md) | `ios` | 2025-11-11 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250908.37](2025-11-11_1.250908.37.md) | `android` | 2025-11-11 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.240923.17](2025-11-11_1.240923.17.md) | `android` | 2025-11-11 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.250818.16](2025-11-10_1.250818.16.md) | `android` | 2025-11-10 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.250526.17](2025-11-08_1.250526.17.md) | `android` | 2025-11-08 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.250505.27](2025-11-08_1.250505.27.md) | `android` | 2025-11-08 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.251103.2](2025-11-05_1.251103.2.md) | `ios` | 2025-11-05 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250609.27](2025-11-04_1.250609.27.md) | `android` | 2025-11-04 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.250811.6](2025-10-30_1.250811.6.md) | `android` | 2025-10-30 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.251027.0](2025-10-29_1.251027.0.md) | `ios` | 2025-10-29 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.251020.1](2025-10-22_1.251020.1.md) | `ios` | 2025-10-22 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.251020.17](2025-10-21_1.251020.17.md) | `android` | 2025-10-21 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.251020.0](2025-10-21_1.251020.0.md) | `ios` | 2025-10-21 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.251013.5](2025-10-15_1.251013.5.md) | `ios` | 2025-10-15 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.251006.1](2025-10-08_1.251006.1.md) | `ios` | 2025-10-08 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.251006.17](2025-10-07_1.251006.17.md) | `android` | 2025-10-07 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.250929.67](2025-10-07_1.250929.67.md) | `android` | 2025-10-07 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.250929.4](2025-10-01_1.250929.4.md) | `ios` | 2025-10-01 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250825.27](2025-09-25_1.250825.27.md) | `android` | 2025-09-25 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.250922.1](2025-09-23_1.250922.1.md) | `ios` | 2025-09-23 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250915.1](2025-09-17_1.250915.1.md) | `ios` | 2025-09-17 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250908.3](2025-09-09_1.250908.3.md) | `ios` | 2025-09-09 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250901.17](2025-09-08_1.250901.17.md) | `android` | 2025-09-08 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.250901.1](2025-09-04_1.250901.1.md) | `ios` | 2025-09-04 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250804.26](2025-08-30_1.250804.26.md) | `android` | 2025-08-30 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.250825.1](2025-08-27_1.250825.1.md) | `ios` | 2025-08-27 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250818.1](2025-08-20_1.250818.1.md) | `ios` | 2025-08-20 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250714.7](2025-08-20_1.250714.7.md) | `android` | 2025-08-20 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.250811.1](2025-08-13_1.250811.1.md) | `ios` | 2025-08-13 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250804.1](2025-08-06_1.250804.1.md) | `ios` | 2025-08-06 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250728.1](2025-07-30_1.250728.1.md) | `ios` | 2025-07-30 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250721.17](2025-07-30_1.250721.17.md) | `android` | 2025-07-30 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.250721.4](2025-07-25_1.250721.4.md) | `ios` | 2025-07-25 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250721.3](2025-07-23_1.250721.3.md) | `ios` | 2025-07-23 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250714.0](2025-07-15_1.250714.0.md) | `ios` | 2025-07-15 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250707.37](2025-07-13_1.250707.37.md) | `android` | 2025-07-13 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.250630.7](2025-07-12_1.250630.7.md) | `android` | 2025-07-12 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.250707.0](2025-07-09_1.250707.0.md) | `ios` | 2025-07-09 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250630.4](2025-07-02_1.250630.4.md) | `ios` | 2025-07-02 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250623.2](2025-06-25_1.250623.2.md) | `ios` | 2025-06-25 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250616.2](2025-06-20_1.250616.2.md) | `ios` | 2025-06-20 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250616.1](2025-06-18_1.250616.1.md) | `ios` | 2025-06-18 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250609.1](2025-06-13_1.250609.1.md) | `ios` | 2025-06-13 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250609.0](2025-06-11_1.250609.0.md) | `ios` | 2025-06-11 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250210.2](2025-06-10_1.250210.2.md) | `android` | 2025-06-10 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.250602.0](2025-06-04_1.250602.0.md) | `ios` | 2025-06-04 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250519.4](2025-05-24_1.250519.4.md) | `ios` | 2025-05-24 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250519.3](2025-05-23_1.250519.3.md) | `ios` | 2025-05-23 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250512.6](2025-05-14_1.250512.6.md) | `ios` | 2025-05-14 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250505.2](2025-05-07_1.250505.2.md) | `ios` | 2025-05-07 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250428.4](2025-05-01_1.250428.4.md) | `ios` | 2025-05-01 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250428.2](2025-04-30_1.250428.2.md) | `ios` | 2025-04-30 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250421.0](2025-04-24_1.250421.0.md) | `ios` | 2025-04-24 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250421.17](2025-04-22_1.250421.17.md) | `android` | 2025-04-22 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.250414.27](2025-04-21_1.250414.27.md) | `android` | 2025-04-21 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.250414.3](2025-04-18_1.250414.3.md) | `ios` | 2025-04-18 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250414.2](2025-04-16_1.250414.2.md) | `ios` | 2025-04-16 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250407.47](2025-04-14_1.250407.47.md) | `android` | 2025-04-14 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.240902.17](2025-04-14_1.240902.17.md) | `android` | 2025-04-14 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.250324.17](2025-04-13_1.250324.17.md) | `android` | 2025-04-13 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.241216.7](2025-04-13_1.241216.7.md) | `android` | 2025-04-13 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.240826.27](2025-04-12_1.240826.27.md) | `android` | 2025-04-12 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.241021.17](2025-04-11_1.241021.17.md) | `android` | 2025-04-11 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.250407.0](2025-04-10_1.250407.0.md) | `ios` | 2025-04-10 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250331.7](2025-04-10_1.250331.7.md) | `android` | 2025-04-10 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.241104.5](2025-04-10_1.241104.5.md) | `android` | 2025-04-10 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.241104.7](2025-04-08_1.241104.7.md) | `android` | 2025-04-08 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.240812.7](2025-04-08_1.240812.7.md) | `android` | 2025-04-08 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.250217.10](2025-04-07_1.250217.10.md) | `android` | 2025-04-07 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.240916.17](2025-04-03_1.240916.17.md) | `android` | 2025-04-03 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.250331.0](2025-04-02_1.250331.0.md) | `ios` | 2025-04-02 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250224.17](2025-03-31_1.250224.17.md) | `android` | 2025-03-31 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.250224.27](2025-03-30_1.250224.27.md) | `android` | 2025-03-30 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.250310.7](2025-03-29_1.250310.7.md) | `android` | 2025-03-29 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.241028.27](2025-03-27_1.241028.27.md) | `android` | 2025-03-27 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.250324.0](2025-03-26_1.250324.0.md) | `ios` | 2025-03-26 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250317.17](2025-03-24_1.250317.17.md) | `android` | 2025-03-24 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.250317.1](2025-03-20_1.250317.1.md) | `ios` | 2025-03-20 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250317.0](2025-03-19_1.250317.0.md) | `ios` | 2025-03-19 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250310.1](2025-03-13_1.250310.1.md) | `ios` | 2025-03-13 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250310.0](2025-03-12_1.250310.0.md) | `ios` | 2025-03-12 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250303.0](2025-03-05_1.250303.0.md) | `ios` | 2025-03-05 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250224.2](2025-02-27_1.250224.2.md) | `ios` | 2025-02-27 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250224.1](2025-02-26_1.250224.1.md) | `ios` | 2025-02-26 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250217.0](2025-02-20_1.250217.0.md) | `ios` | 2025-02-20 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250210.0](2025-02-12_1.250210.0.md) | `ios` | 2025-02-12 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250203.0](2025-02-06_1.250203.0.md) | `ios` | 2025-02-06 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250127.0](2025-01-30_1.250127.0.md) | `ios` | 2025-01-30 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250120.1](2025-01-22_1.250120.1.md) | `ios` | 2025-01-22 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250113.0](2025-01-15_1.250113.0.md) | `ios` | 2025-01-15 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.250106.0](2025-01-08_1.250106.0.md) | `ios` | 2025-01-08 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.241216.3](2024-12-19_1.241216.3.md) | `ios` | 2024-12-19 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.241216.0](2024-12-12_1.241216.0.md) | `ios` | 2024-12-12 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.241209.2](2024-12-11_1.241209.2.md) | `ios` | 2024-12-11 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.241202.0](2024-12-07_1.241202.0.md) | `ios` | 2024-12-07 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.241118.3](2024-11-27_1.241118.3.md) | `ios` | 2024-11-27 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.241118.2](2024-11-20_1.241118.2.md) | `ios` | 2024-11-20 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.241111.3](2024-11-16_1.241111.3.md) | `ios` | 2024-11-16 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.241111.2](2024-11-14_1.241111.2.md) | `ios` | 2024-11-14 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.241111.0](2024-11-07_1.241111.0.md) | `ios` | 2024-11-07 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.241104.1](2024-11-06_1.241104.1.md) | `ios` | 2024-11-06 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.241104.0](2024-10-31_1.241104.0.md) | `ios` | 2024-10-31 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.241028.2](2024-10-29_1.241028.2.md) | `ios` | 2024-10-29 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.241021.7](2024-10-23_1.241021.7.md) | `ios`、`android` | 2024-10-23 | `TODO`（`ios`、`android`）— _详细技术差分待补充_ |
| [1.241021.4](2024-10-22_1.241021.4.md) | `ios` | 2024-10-22 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.241021.2](2024-10-18_1.241021.2.md) | `ios` | 2024-10-18 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.241021.0](2024-10-17_1.241021.0.md) | `ios` | 2024-10-17 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.241007.1](2024-10-08_1.241007.1.md) | `ios` | 2024-10-08 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.240930.2](2024-10-02_1.240930.2.md) | `ios` | 2024-10-02 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.240923.1](2024-09-26_1.240923.1.md) | `ios` | 2024-09-26 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.240916.1](2024-09-17_1.240916.1.md) | `ios` | 2024-09-17 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.240909.0](2024-09-10_1.240909.0.md) | `ios` | 2024-09-10 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.240902.2](2024-09-06_1.240902.2.md) | `ios` | 2024-09-06 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.240826.1](2024-09-01_1.240826.1.md) | `ios` | 2024-09-01 | `TODO`（`ios`）— _详细技术差分待补充_ |
