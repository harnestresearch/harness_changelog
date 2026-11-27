# Qoder 最新版本改动

[English](../qoder.md) | 简体中文 · **精简版 (Highlight)** | [完整详情 (Full Detail)](full/qoder.md)

> 五端（`mac`、`win`、`ubuntu`、`ios`、`android`）完整 59 个历史版本索引（桌面端 `mac`/`win`/`ubuntu` 最新 `0.5.20`、iOS 最新 `1.46.0`、Android 最新 `0.10.0`；`0.5.13` 至 `0.5.20` 之间的中间桌面版本尚未入仓）见 [qoder/README.md](qoder/README.md)。

## 最新桌面版本：0.5.20（macOS / Windows / Linux，2026-11-25）

核心亮点见 [qoder/2026-11-25_0.5.20.md](qoder/2026-11-25_0.5.20.md)，完整技术细节见 [full/qoder/2026-11-25_0.5.20.md](full/qoder/2026-11-25_0.5.20.md)。_（官方标题日期 `November 25, 2026` — "Cross-Device Collaboration and Cloud Tasks"；三端更新清单 `releaseDate` 为 macOS `2026-11-25T14:26:16.356Z` / Windows `14:34:35.952Z` / Linux `14:13:26.874Z`。中间桌面版本 `0.5.14` 与 `0.5.16`–`0.5.19` 尚未入仓，`0.5.13` **并非**本对基线——本篇仅覆盖 `0.5.18 → 0.5.20` 静态对比，并刻意跨过无官方 changelog 条目、未下载未分析的 `0.5.19`。macOS `arm64` 全量静态分析；Windows `x64` `exe`+`app.zip` 与 Linux `amd64` `.deb` 核验包体积/SHA-256，内部文件账与 Authenticode 核验沿用静态拆包记录、未在此重解包，NSIS 未反汇编，`.rpm` 仅记清单 SHA-256；未覆盖 macOS `x64`、Windows `arm64`、Android、iOS；未运行验证。）_

### 核心亮点

- **云端任务、跨设备协作与本地任务恢复**：官方说明引入桌面端云端任务、从已连接设备工作区下载文件及按权限管理自动化、退出/更新后恢复未完成本地任务。静态差分证实新增 `14` 条 `cloud-session:*` IPC、`automations.*` IPC 与 `+6` 条 `AUTOMATION_TASK_*` 错误码（`2 → 8`）、`19` 条 `automationPeer.*` 渲染键、`automations.read.v1`/`manage.v1`、`chatSession.fileDownload.*` / `Resources/runtime/file-transfer.cjs`，以及 `chat-session-recovery:*` / `.recoveryPhase` / `20261119-00-chat-session-restart-resumption.sql`（云端与跨设备均依赖服务端，未动态验证）。
- **受管设备登录限制、归档按组操作、超大字体与 125% 缩放**：官方说明支持企业管理员限制受管设备仅用批准组织企业账号登录、归档本地任务按组恢复/删除（搜索结果批量删除仅影响匹配项）、超大字体与 `125%` 独立缩放。静态证实新增 `auth.deviceAccountBlocked.{confirm,description}`、`"Device account policy rejected the current login"`、`"Enterprise VPC sign-in"`、`restoreGroupTasks`/`archivedGroupMore`/`deleteArchiveSearchResults*`，以及 `fontSizeExtraLarge`/`uiScaleExtraLarge` 入口串（未见明文排版参数，企业策略依赖服务端）。
- **问题修复与未公告运行时/扩展改动**：官方修复涵盖数据目录迁移后插件安装失败及受限 Windows 插件后台服务无法启动（仅局部/间接静态线索：worker 归档安全校验、`pluginHost.js` `+1,487` B、移除 `WindowsPluginJob.cs`/`windows-job.ps1`，无法逐条归因）、后台断线阻塞下一轮自动化（`20261121-00-automation-run-retry-count.sql` 与 `20261121-01-automation-manual-pending-index.sql`）、有效模型无法开始会话（仅间接登出/重选提示）与 Remote Control 消息乱序（`20261123-01-async-question-order-clock` 与 `.messageOrder`）。未公告改动包括 Electron 维持 `43.8.4`、`qodercli` 跨 minor 升至 `1.1.96-hotfix.8`（`−826,457` B）、Agent SDK `1.0.62-alpha.9`、`qoder.knowledge.center` 拆为 `qoder.knowledge.wiki` + `qoder.qmind`、`@ali/qoder-text-sdk` `0.5.2`、`@qoder-space/in-app-browser`、Qwen 登录文案、`statusline` 提示拆分及应用图标刷新。

---

## 更早入仓桌面版本：0.5.13（macOS，2026-11-16）

核心亮点见 [qoder/2026-11-16_0.5.13.md](qoder/2026-11-16_0.5.13.md)，完整技术细节见 [full/qoder/2026-11-16_0.5.13.md](full/qoder/2026-11-16_0.5.13.md)。_（发布日期依据更新清单 `0.5.13.yml` 的 `releaseDate: 2026-11-16T13:05:09.530Z`；仅基于官方 macOS `arm64` 双包 `0.5.12 → 0.5.13` 静态解包对比，未逆向 Windows 与 Linux 安装包，未运行被测程序。）_

### 核心亮点

- **渲染层 `ApplicationTransport` 触及 64 订阅上限时等待在途释放再复检**：`BHeyMntc.js` 保持单连接 `64` 订阅上限不变（未取消上限），触顶时先等待 `releaseRequested` 在途订阅释放（`waitForReleases`）并复检，仍超限才抛 `APPLICATION_RATE_LIMITED`，同时新增 30 秒节流的 `"Application subscription limit reached"` 诊断日志；对应官方“频繁切任务或通知积压后任务打不开”修复属静态行为推断，未经动态运行验证。
- **Worker 解码字符串表新增 6 条 Bash 风险自评与本地 Auto 审批词条（`14,169 → 14,175`）**：`qoder-worker-runtime.obf.mjs` 新增审批评估边界提示词、涵盖嵌套 Shell 的 Bash 风险自评指令，以及 `Bash risk input`、`First local Auto gate reason`、`First matching Auto blacklist rule identifier`、`Local Auto approval policy version` 四条遥测/字段说明——仅证明提示词与说明文本变化，不单独证明审批策略已在运行期生效。
- **Agent SDK `1.0.60-alpha.62`、`qodercli` `1.1.86-hotfix.5.2` 与官方其余说明分层对照**：`@qoder-ai/qoder-agent-sdk` / `@qoder-ai/qoder-cn-agent-sdk` 升至 `1.0.60-alpha.62`、`qoderCliVersion` 升至 `1.1.86-hotfix.5.2`（Electron `43.8.4`），并重建 `qoder-office-xlsx` 的 `xlsx-sidecar`；官方其余五项说明中，设备信息慢导致活动通知超时仅具间接关联，subagent 模型配置、`context-limit` 压缩恢复识别、切模型后用量计算及 fork/恢复压缩消息链接未找到新本地静态证据（不等于功能不存在）。

---

## 最新 Android 版本：0.10.0（Android，2026-11-15）

核心亮点见 [qoder/2026-11-15_0.10.0.md](qoder/2026-11-15_0.10.0.md)，完整技术细节见 [full/qoder/2026-11-15_0.10.0.md](full/qoder/2026-11-15_0.10.0.md)。_（Google Play 显示日期 `2026-11-15`，精确发布时刻未公开；官方 CDN `qoder.apk` `Last-Modified`：`2026-11-15 10:56:40` UTC。基于 APKPure Play-split XAPK `0.9.0`（`versionCode` `67`）与官方单体 APK `0.10.0`（`versionCode` `70`）静态对比；不涵盖 iOS，未安装运行，且 `lib/`/`res/` 与签名证书差异受跨渠道/跨形态限制。）_

### 核心亮点

- **权益中心活动模型扩充与混合 WebView 桥**：在 `0.9.0` 已含 `ChannelValidity` 与 `UserPlanResponse` 的基础上，扩充 11 组 `features/credits` 活动/奖励/领取模型、新增 `assets/qoder_web_fetch.js`（`window.qoderBenefits` 原生请求桥）及“套餐与用量”“权益中心”抽屉与设置文案。
- **模型管理文案与 `ModelManagementValue` 模型（含预览/模拟提示）**：新增 `ModelManagementValue` 与 23 条 `composer.model_management.*` 文案（思考开关、6 档思考强度与上下文窗口），同时包含 `"模型管理（预览）"`、`"仅预览，不会修改 Desktop 配置。"` 与 `"模拟成功/部分成功/失败"` 词条（线上持久化范围未经动态验证）。
- **首页引导图清理、导航抽屉与 OTLP 技术批处理接口**：移除首页引导图 `ic_home_all_tasks_guidance(.dark).png`，新增空状态、导航抽屉（定时任务/已归档/设备管理/邀请好友）、远程控制、语音输入与“智能眼镜/主题”设置文案，并在既有 `OtlpTelemetryClient` 上新增 `exportTechnicalBatch`、`TechnicalSnapshot`、`TechnicalEvent` 与 `recordScrollWindow`。

---

## 前序桌面版本：0.5.12（macOS，2026-11-14）

核心亮点见 [qoder/2026-11-14_0.5.12.md](qoder/2026-11-14_0.5.12.md)，完整技术细节见 [full/qoder/2026-11-14_0.5.12.md](full/qoder/2026-11-14_0.5.12.md)。_（仅基于官方 macOS `arm64` 双包 `0.5.11 → 0.5.12` 静态解包对比；未逆向 Windows 与 Linux 包，未做运行时动态验证。）_

### 核心亮点

- **会话恢复（`transcript.resume`）新增 4 条校验字符串（静态证据）**：内置 worker 运行时解密字符串表新增 `transcript.resume.invalid_file_snapshot_skipped`、`transcript.resume.invalid_replacements_skipped`、`transcript.resume.invalid_selected_message` 与 `Transcript resume failed: unsafe (`，构成对应官方“修复会话快照/内容替换记录异常导致对话中断”说明的静态字符串证据（运行期行为未经动态验证）。
- **Agent SDK 升至 `1.0.60-alpha.50`、`qodercli` `1.1.86-hotfix.5` 与 `xlsx-sidecar` 重打包**：`@qoder-ai/qoder-agent-sdk` / `@qoder-ai/qoder-cn-agent-sdk` 由 `1.0.60-alpha.36` 升至 `1.0.60-alpha.50`，`qoderCliVersion` 及按需下载 OSS 模板由 `1.1.86-hotfix.4` 升至 `1.1.86-hotfix.5`（Electron `43.8.4`），并重编译打包 `qoder-office-xlsx` 中的 Rust `xlsx-sidecar`。
- **官方其余 4 项更新说明与本地静态证据分栏**：官方 `0.5.12` 列出的改进自动任务标题、文件变更预览 diff 摘要与增删行数、设备标识缺失初始化修复及自定义模型目录 `reasoning effort`/关闭 reasoning 识别四项，在本地 macOS `arm64` 包中未见新增静态差分（`app/out/renderer` 逐字节一致，既有 reasoning 校验提示在 `0.5.11` 与 `0.5.12` 两版中均已存在）；未检出本地新静态证据不等于不存在相关功能或修复。

---

## 近期架构基线：0.5.3（2026-11-02）

核心亮点见 [qoder/2026-11-02_0.5.3.md](qoder/2026-11-02_0.5.3.md)，完整技术细节见 [full/qoder/2026-11-02_0.5.3.md](full/qoder/2026-11-02_0.5.3.md)。

### 核心亮点

- **智能体编码工作台、Git Worktree 并行开发与多角色专家协同**：集成交互式终端、Plan 规划模式、目标（Goal）与定时任务编排、隔离式 Git Worktree 并行分支与会话分叉，并内置研究员、前后端开发、测试、UX 设计、代码审查与运维等多角色专家子代理协同。
- **跨本地/远程工作区语义检索、Repo Wiki 与 QMind 知识库**：自动为本地及 SSH/WSL 远程工作区建立语义代码索引，支持生成与可视化编辑项目 Repo Wiki 及架构知识卡片，并内置 QMind 知识笔记本（支持导入网页/本地文件与定时整理任务）。
- **Qoder Sites 全栈应用托管（数据库、云函数、对象存储与流量统计）**：支持构建并发布 `.qoder.site` 在线应用，提供受管 SQL 数据库表迁移与单行安全读写、Serverless 云函数日志诊断、对象存储、按邮箱/账号精细化访问权限控制及 24h/7d/30d 访问统计。
- **USB 连接 iOS 与 Android 真机自动化操控（Phone Use）**：支持在本机任务中自动发现、签名部署、实时预览并操控连接的 iPhone 与 Android 真机/模拟器，支持最多 20 步批处理手势编排，并在遇到人脸/指纹认证、验证码或密码输入时自动安全暂停交由人工接管。
- **桌面录制回放、外部浏览器连接器与 `0.5.3` 列表稳定性修复**：提供桌面自动操控与操作录制回放、Chrome/Edge 外部浏览器扩展连接、交互式 Canvas 可视化画布、PPTX/XLSX/CSV 原生办公预览、三级安全扫描开关及企业微信/钉钉机器人通道；同时在 `0.5.3` 中修复高频更新下工作区与近期任务列表卡在加载态的问题，以及部分历史会话缺失来源会话信息导致的任务列表加载失败。
