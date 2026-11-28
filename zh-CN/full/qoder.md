# Qoder 最新版本改动

[English](../../full/qoder.md) | 简体中文 · [精简版 (Highlight)](../qoder.md) | **完整详情 (Full Detail)**

> 五端（`mac`、`win`、`ubuntu`、`ios`、`android`）完整 61 个历史版本索引（桌面端 `mac`/`win`/`ubuntu` 最新 `0.5.21`、iOS 最新 `1.46.0`、Android 最新 `2.0.0`；`0.5.13` 至 `0.5.20` 之间的中间桌面版本以及 Android `0.11.0` 从未入仓，Android `2.0.0` 仅覆盖 `0.11.0 → 2.0.0`）见 [qoder/README.md](qoder/README.md)。

## 最新桌面版本：0.5.21（macOS / Windows / Linux，2026-11-27）

详细改动见 [qoder/2026-11-27_0.5.21.md](qoder/2026-11-27_0.5.21.md)。基于相邻对 **`0.5.20 → 0.5.21`** 官方版本化路径 `releases/0.5.21/` 三端包（macOS `arm64` / Windows `x64` / Linux `amd64` `.deb`）的静态对比（官方 changelog `November 27, 2026` — 英文 *"Everyday Polish"*［无独立 `"Qoder 0.5.21"` 标题行，经 HTML 锚点 `id="0.5.21"` / `qoder-0521-everyday-polish`、中文「日常优化」、清单与包内版本绑定］；更新清单 `releaseDate` 为 macOS `2026-11-27T08:03:56.246Z` / Windows `08:14:31.290Z` / Linux `07:54:29.115Z`；三端构建提交同为 `eb36b7b303185facdb2ef70f0eaf9f8199b2c413`，`buildNumber` macOS `94896589` / Windows `94896591`；`.rpm` 仅记清单与 HEAD 散列、`Qoder-mac-x64.zip` 在 CDN 存在但未取未分析、`Qoder-win-arm64-user.exe` 返回 404、NSIS 未反汇编、不涵盖 Android/iOS、未运行客户端）：

- **AppHub 连接器同步与运行时小幅递增（独立核实）**：从 macOS `arm64` 归档及解包元数据（`Info.plist`、`build-manifest.json`、`package.json`）直接核实：Electron 保持 `43.8.4`、`@qoder-ai/qoder-agent-sdk`（`npm:@ali/qoder-agent-sdk-next`）与 `@qoder-ai/qoder-cn-agent-sdk`（`npm:@ali/qodercn-agent-sdk-next`）由 `1.0.62-alpha.9` 升至 `1.0.62-alpha.10`、`qoderCliVersion` 由 `1.1.96-hotfix.8` 升至 `1.1.96-hotfix.9`（依赖集合其余不变）。静态字符串检查证实渲染层新增 `appHubError`、`loadingSyncSources`、`streamable_http`，主进程新增 `cloud-configuration:list-apphub-items`、`cloud-configuration:sync-apphub-vault` 及两条遥测串（`SDK JobToken callback failed`、`SDK JobToken callback returned no credential`）。
- **Worker 字符串表零变化与官方修复静态无法核验**：`0.5.20` 与 `0.5.21` 的 worker 解码字符串表均为 `13,966` 条且完全一致（`+0 / −0`），与静态差分报告记录的“无对应修复/提示新文案”相容；代理设置变更后的诊断重跑提示及四项官方修复（云自动化编辑、设备时钟差、系统代理模型列表加载、Windows OpenSSH 主机校验失败）均**静态无法核验**，未能在二进制中逐条证实。
- **包体积差与报告引述细部统计**：盘上复算四包体积差与完整 SHA-256 均与清单及 `x-oss-meta-sha256` 一致（macOS `arm64` zip `−426` B、Windows `x64` `.exe` `−5,880` B、`app.zip` `+8,652` B、Linux `amd64` `.deb` `+652,764` B）。源自静态差分报告、未单独重新解包复现的细部统计包括：`app.asar` `+13,300` B（`electronMain.js` `+9,814` B）、渲染层 literals `+1,001` 且无修复文案、Windows `1,109` / Linux `1,101` 文件树逐哈希、Windows 签名表维持 `14,832` B、`.deb` `control` 仅变 `Version`/`Installed-Size`、`context-plugin`/`office-xlsx` 换包及 `93` 个同尺寸重签名二进制哈希变化。

---

## 最新 Android 版本：2.0.0（Android，2026-11-27）

详细改动见 [qoder/2026-11-27_2.0.0.md](qoder/2026-11-27_2.0.0.md)。基于官方滚动 CDN 单体 APK **`0.11.0`（`versionCode` `73`，`30,147,702` B）→ `2.0.0`（`versionCode` `75`，`41,738,505` B，`+11,590,803` B）** 的纯双包静态差分（`Last-Modified`：`2026-11-27 14:44:05` UTC / 北京 `22:44:05`；同自签 `CN=Qoder cli` 发布证书 `a54169ccdb9b3898d7395746b2a9963900a7d1c5ab403eaf9eddbac103fe6066`；`gitCommit=01d86bf86b188d5f6204cda8b376f61aab8aa5f4 → f42c8de801f896f74d4ba3db746ce59427f70bdb`；中间版本 `0.11.0` 从未入仓，`0.10.0` **并非**对比基线；官方移动端 changelog 停在 `0.11.0`［`2026-11-25`］且 Google Play 仍为 `0.11.0`，Play 的 `"Updated on Nov 27, 2026"` **不得**当作 `2.0.0` 上架日或发布日；跳过 `74` 与 `1.x` 属官方版本策略；不涵盖 iOS，未安装运行）：

- **QBot 助手形态（`features/qbot`、`31` 条 `/api/v1/qbot*` 路径与 `335` 条 `qbot.*` 文案）**：清单新增 `qbot`/`qbot_list`，DEX 新增 `31` 条 `/api/v1/qbot*` 路径（`0 → 31`，覆盖 `initialize`、`list`、`access`、`avatars` 及 `{bot_id}` 下 artifacts/connectors/environments/events/files/pause/resume/schedules/vm/worker-tasks）、`/signed-artifact-download` 与 `QBOT_*` 事件码；动态文案新增 `335` 条 `qbot.*`（`2,220 → 2,572`，`+352`；domestic 包约 `20 KB → 41 KB`）；新增全套 `qbot_*` 资源、Figma 连接器 SVG（`qbot_connector_figma*.svg`）、`artifact_file_icons.ttf` 与抽屉双模式图标（`drawer_home_mode.png`、`qbot_drawer_mode.png`）。`2.0.0` DEX 未检出 `streamable_http`。
- **生物识别远程控制授权与防休眠（`USE_BIOMETRIC`）**：`AndroidManifest.xml` 新增 `android.permission.USE_BIOMETRIC`，并新增 `device_management.remote_control.*` 盘上原文键（`authentication_reason`、`use_passcode`、`keep_awake`、`keep_awake_description`、`allow`、`authentication_failed`、`authentication_unavailable`）。
- **结构变化、自动化运行延伸与报告引述项**：归档条目 `1,215 → 1,253`（`+43 / −5 / 公共 1,210`；`classes.dex` `+469,940` B、`classes2.dex` `+1,243,880` B、`resources.arsc` `+147,528` B）；DEX 新增 `/api/v1/qcloud/cloud-automation-runs`、`/api/v1/remote/automations`、`/api/v1/remote/automation-runs`（其余不少 `qcloud`/`remote` 路径如 `/api/v1/qcloud/cloud-automations` 在 `0.11.0` 已存在），并新增 `automation_history_empty_pendulum.webp` 与 `home_connect_editor_{en,zh}_{dark,light}.gif`。`"40+"` DTO 全清单、Compose 组件全名、受 R8 重排影响的单 DEX 净增细节与灰度开放状态仅转述自静态差分报告。

---

## 前序桌面版本：0.5.20（macOS / Windows / Linux，2026-11-25）

详细改动见 [qoder/2026-11-25_0.5.20.md](qoder/2026-11-25_0.5.20.md)。基于 **`0.5.18 → 0.5.20`** 三端官方包（macOS `arm64` / Windows `x64` / Linux `amd64`）静态对比（官方 changelog `November 25, 2026` — *"Cross-Device Collaboration and Cloud Tasks"*；更新清单 `releaseDate` 为 macOS `2026-11-25T14:26:16.356Z` / Windows `14:34:35.952Z` / Linux `14:13:26.874Z`，三端构建 commit 同为 `aacc1a53…`；中间桌面版 `0.5.14` 与 `0.5.16`–`0.5.19` 尚未入仓，`0.5.13` **并非**对比基线，且刻意跨过无官方 changelog 条目、未下载未分析的 `0.5.19`；macOS `arm64` 全量静态解包分析，Windows `x64` `exe`+`app.zip` 与 Linux `amd64` `.deb` 核验体积与清单 SHA-256、其内部文件树与 Authenticode 核验沿用静态拆包记录且未在此重解包，Windows NSIS 未反汇编，`.rpm` 仅记录清单 SHA-256；未覆盖 macOS `x64`、Windows `arm64`、Android、iOS；未运行客户端）：

- **云端任务、跨设备协作与本地任务恢复（`electronMain.js` `+396,950` B）**：新增 `14` 条 `cloud-session:*` IPC 与 `cloudSessionMainService`、扩展 `automations.*` IPC 与 `+6` 条 `AUTOMATION_TASK_*` 错误码（渲染层 `2 → 8`；`AUTOMATION_UNREADABLE` 与 `automation_heartbeat_run_now`/`scheduled` 在 `0.5.18` 已存在）、`19` 条 `automationPeer.*` 键 + `downloadArtifact` + `automations.read.v1`/`manage.v1` + `chatSession.fileDownload.*` / `Resources/runtime/file-transfer.cjs`（`peerDeviceId` 在 `0.5.18` 已存在），以及 `chat-session-recovery:{changed,decide,get}` / `.recoveryPhase` / `20261119-00-chat-session-restart-resumption.sql`；云端与跨设备授权粒度均依赖服务端，未做运行验证。
- **受管设备登录、归档按组操作、缩放入口与官方修复映射**：新增 `auth.deviceAccountBlocked.{confirm,description}`、`"Device account policy rejected the current login"`、`"Enterprise VPC sign-in"`、worker 浏览器登录迁移文案（`"Qoder PAT sign-in is no longer supported..."`）及三条独立企业/组织插件锁定字符串（`cannot be disabled.` / `cannot be uninstalled.`）；新增 `restoreGroupTasks`/`archivedGroupMore`/`deleteArchiveSearchResults*`（`archived_sessions` 系 `0.5.18` 既有 Codex 历史目录校验，非新增 SQLite 表）与 `fontSizeExtraLarge`/`uiScaleExtraLarge` 入口字符串（无明文排版参数）。官方四项修复按证据界定：自动化断线阻塞（`20261121-00-automation-run-retry-count.sql`、`20261121-01-automation-manual-pending-index.sql`）、Remote Control 消息顺序（`20261123-01-async-question-order-clock`、`.messageOrder`）、迁移后插件安装失败与受限 Windows 后台服务启动（仅局部/间接静态线索：worker 归档/符号链接校验、`pluginHost.js` `+1,487` B、移除 `Resources/plugin-lifecycle/{WindowsPluginJob.cs,windows-job.ps1}`）及有效模型启动会话（仅间接登出/重选引导文案）。
- **未公告运行时、扩展与依赖变化**：Electron 保持 `43.8.4`；`qodercli` / worker 跨 minor 升至 `1.1.96-hotfix.8`（`qoder-worker-runtime.obf.mjs` `−826,457` B，解码串 `14,658 → 13,966`；新增 `dist/_worker/qoder/{agent-creator,skill-creator,hook-config}/SKILL.md` 并保留 `dist/_worker/builtin/*/SKILL.md`）；Agent SDK `1.0.62-alpha.2 → alpha.9`；`@ali/qoder-browser-use-sdk` `0.4.2 → 0.4.3`；新增 `@ali/qoder-text-sdk` `0.5.2`（以 `app/out/qoder-text/` 取代 `Resources/dynamic-text/qoder.json`）与 `@qoder-space/in-app-browser`；内置扩展 `qoder.knowledge.center` 拆为 `qoder.knowledge.wiki`（`0.1.0`）+ `qoder.qmind`（`0.1.1`）（`12 → 13` 个，`catalog.v1.json` `+3,881` B）；另含 Qwen 登录文案、`statusline` Qoder 可选积分提示词拆分、视频交付说明（`mp4`/OSS 签名 URL）、`qoder-security` 引导脚本 JSON/SHA-256 加固、双主题应用图标刷新与 Chrome 连接器 `1.7.7 → 1.7.10`。

---

## 更早入仓桌面版本：0.5.13（macOS，2026-11-16）

详细改动见 [qoder/2026-11-16_0.5.13.md](qoder/2026-11-16_0.5.13.md)。基于官方 macOS `arm64` 双包（`0.5.12` → `0.5.13`，`Qoder-mac-arm64.zip` `342,120,251` → `342,127,454` B，`+7,203` B；日期依据更新清单 `0.5.13.yml` 的 `releaseDate: 2026-11-16T13:05:09.530Z`，其中 `releaseNotes: {}` 为空不表示官方无网页说明且不把文件 `mtime` 当作 `Last-Modified`；Windows/Linux 未逆向，未运行客户端）：

- **渲染层 `ApplicationTransport.subscribe` 达上限等待释放与 30 秒限频日志（`Dta6yTTQ.js` `176,239` B → `BHeyMntc.js` `177,975` B）**：保留单连接 `64` 订阅上限不变（未取消上限），达上限时先等待 `releaseRequested` 在途订阅完成释放（`waitForReleases` / `releaseSubscription`）再复检是否抛 `APPLICATION_RATE_LIMITED`，并新增 `lastLimitLogAt` 30 秒节流 `warn` 日志 `"Application subscription limit reached"`（统计各方法的 `{active, establishing, releasing, releaseFailed, oldestAgeMs}`）；将其对应至官方高频切任务/通知积压打不开任务的说明属静态行为推断，未经动态运行验证。
- **Worker 解码字符串表增量（`14,169 → 14,175`，`+6 / −0`）**：`qoder-worker-runtime.obf.mjs`（`+10,705` B，commit `0b1f085` → `cfef7df`）新增 6 条字符串——审批评估边界提示词、涵盖嵌套 Shell 的 Bash 风险自评指令，以及 `Bash risk input`、`First local Auto gate reason`、`First matching Auto blacklist rule identifier`、`Local Auto approval policy version` 四条遥测/字段说明，仅代表提示词与说明文本变化，不证明审批策略已在运行期生效。
- **SDK `1.0.60-alpha.62`、`qodercli` `1.1.86-hotfix.5.2` 与官方说明分层对照**：`@qoder-ai/qoder-agent-sdk` / `@qoder-ai/qoder-cn-agent-sdk` 由 `1.0.60-alpha.50` 升至 `1.0.60-alpha.62`，`qoderCliVersion` 及 OSS 下载模板由 `1.1.86-hotfix.5` 升至 `1.1.86-hotfix.5.2`（Electron `43.8.4` 不变，`electronMain.js` `+10,751` B 重混淆且明文自然语言串零增删），替换 `qoder-office-xlsx` 归档（`dd2dff0f…` → `9927b58d…`，Rust `xlsx-sidecar` `8,730,592 → 8,730,704` B）；官方其余修复按证据分层：设备信息准备较慢时活动通知超时仅具间接关联，subagent 模型配置、`context-limit` 压缩恢复、切模型用量计算与 fork/恢复压缩消息链接未找到新本地静态证据（不排除位于混淆控制流或远端配置中）。

---

## 更早入仓 Android 版本：0.10.0（Android，2026-11-15）

详细改动见 [qoder/2026-11-15_0.10.0.md](qoder/2026-11-15_0.10.0.md)。基于 APKPure Google Play 拆分包 `0.9.0`（`versionCode` `67`，`minSdkVersion` `28`，`targetSdkVersion` `36`）与官方单体通用包 `0.10.0`（`versionCode` `70`；Play 日期 `2026-11-15` 无精确时刻，官方 CDN `Last-Modified`：`2026-11-15 10:56:40` UTC）的跨渠道静态差分（不涵盖 iOS，未运行 APK；`lib/`/`res/`/`resources.arsc` 及壳层清单受拆分包 vs 单体包影响不可直接比，签名密钥 `ddf5ab4a…` vs `a54169cc…` 差异原因仅属推测）：

- **扩充既有 `features/credits` 与 `qoder_web_fetch.js` 原生桥**：在 `0.9.0` 既有 `ChannelValidity`、`UserPlanResponse` 之上新增 11 组活动/奖励/领取模型（及 `JsonAdapter`）、`assets/qoder_web_fetch.js`（`5,397` B，经 `window.qoderBenefits` 桥接 WebView `window.fetch`）及“套餐与用量”“权益中心”与系统 WebView 升级动态词条（`1,852 → 1,928`，`+79 / -3`）。
- **`ModelManagementValue` 与按证据分级的思考强度/上下文文案**：新增 `ModelManagementValue`（及 `JsonAdapter`）与 `ModelManagement{Binding,Configuration,Directory,Editor}`（扩充 `AvailableModelDTO` / `EnvironmentAvailableModelDTO`，`AvailableModelPromotionDTO` 仍保留），新增 23 条 `composer.model_management.*` 词条（6 档思考强度与上下文窗口），同时携带 `"模型管理（预览）"`、`"仅预览，不会修改 Desktop 配置。"` 与 `"模拟*"` 文案。
- **首页/抽屉文案更新与既有 `OtlpTelemetryClient` 技术批处理扩充**：删除 `ic_home_all_tasks_guidance(.dark).png`，新增空状态、抽屉项、远程控制 CLI/桌面端/云端、语音输入（`assets/qoduck_voice/*.webp`）及“智能眼镜/主题”词条，并在 `0.9.0` 既有 `OtlpTelemetryClient` 上新增 `exportTechnicalBatch`、`TechnicalSnapshot`、`TechnicalScalarValues`、`TechnicalEvent` 与 `recordScrollWindow(TechnicalScrollWindow)`。

---

## 前序桌面版本：0.5.12（macOS，2026-11-14）

详细改动见 [qoder/2026-11-14_0.5.12.md](qoder/2026-11-14_0.5.12.md)。基于官方 macOS `arm64` 双包（`0.5.11` → `0.5.12`，`Qoder-mac-arm64.zip` `342,109,501` B → `342,120,251` B）的静态解包差分（Windows/Linux 未逆向，未运行客户端）：

- **Worker `transcript.resume.*` 静态字符串证据**：`qoder-worker-runtime.obf.mjs`（`+2,423` B，commit `2c8933e` → `0b1f085`）解密字符串表新增且仅新增 4 条记录（`transcript.resume.invalid_file_snapshot_skipped`、`transcript.resume.invalid_replacements_skipped`、`transcript.resume.invalid_selected_message`、`Transcript resume failed: unsafe (`），与官方会话快照/内容替换记录异常中断修复说明对应（具体运行期行为未经动态实测）。
- **SDK `1.0.60-alpha.50`、`qodercli` `1.1.86-hotfix.5` 与 `qoder-office-xlsx` 重建**：`@qoder-ai/qoder-agent-sdk` / `@qoder-ai/qoder-cn-agent-sdk`（`npm:@ali/qoder{,cn}-agent-sdk-next`）由 `1.0.60-alpha.36` 升至 `1.0.60-alpha.50`，`qoderCliVersion` 及按需下载 OSS 模板由 `1.1.86-hotfix.4` 升至 `1.1.86-hotfix.5`（Electron `43.8.4` 不变，`electronMain.js` `+4,898` B 整文件重混淆且明文自然语言串零增删），同时替换 `qoder-office-xlsx` 归档（`0ed5a5ea…` → `dd2dff0f…`，Rust `xlsx-sidecar` `8,730,672` → `8,730,592` B 重编并刷新 `catalog.v1.json` 哈希）。
- **官方说明与静态证据分栏对照**：官方日志列出的改进自动任务标题、文件变更预览 diff 摘要/增删行数、设备标识缺失初始化修复及自定义模型目录 `reasoning effort`/关闭 reasoning 识别四项，在本地 macOS `arm64` 包中未见新增静态证据（`app/out/renderer` 逐字节零变化，`device`/`umid` 字符串集合未变，既有 reasoning 提示语在 `0.5.11` 与 `0.5.12` 中均已存在）；未发现新静态证据不代表相关改动不存在于混淆主进程、远端配置或按需拉取的 `qodercli` `1.1.86-hotfix.5` 中。

---

## 近期架构基线：0.5.3（2026-11-02）

详细改动见 [qoder/2026-11-02_0.5.3.md](qoder/2026-11-02_0.5.3.md)。

### 版本概览

Qoder Desktop `0.5.3` 由 Electron 主进程（`out/main/electronMain.js`、`out/main/pluginHost.js` 及 11 个内置 `.qoder-app-plugin` 扩展）与 `@qoder-ai/qoder-agent-sdk@1.0.59-alpha.9`（`qoder-worker-runtime.obf.mjs` / Go 编写的 `qodercli` `1.1.79-hotfix.11`，线协议 `1.5.0`，基于 `proto/chat.proto` 流式承载 OpenAI 风格函数调用）组成，通过 **35+ 核心运行时内置工具** 与 **四路并行 MCP 注册通道**（覆盖 `stdio`、`StreamableHTTP`/`SSE` 及零子进程开销的 `mcp.registerInProcessServer` 进程内传输）构建完整智能体工作台。

### 核心运行时内置工具注册表（`qoder-worker-runtime`）

- **文件编辑、代码检索与交互式 PTY 终端**：内置 `Read`、`Write`、`Edit`、`Glob`、`Grep`、`GrepRipgrep`、`Bash`（配对交互式伪终端 `BashInput`、`BashOutput`、`BashResize` 与后台进程 `Monitor`）、`WebFetch` 与 `WebSearch`。
- **规划模式、Git Worktree、目标/定时任务与多专家编排**：
  - 提供 `TodoWrite`、`AskUserQuestion`、`EnterPlanMode` / `ExitPlanMode`、`EnterWorktree` / `ExitWorktree`、`CreateGoal` / `UpdateGoal`、`CronCreate` / `CronList` / `CronDelete`、`Skill` 与 `Workflow`。
  - 支持 `Agent`（含会话 `fork` 及兼容读取 `.claude` 目录的 `loadAgentsFromClaudeCodeProject()`）、`SendMessage` 与 `Task` / `TaskList` / `TaskUpdate` 多代理协同，内置 8 类专家角色枚举（`researcher`、`frontend-dev`、`backend-dev`、`qa`、`ux-designer`、`code-reviewer`、`operations`、`general-engineer`）及支持 13 种调用/继承关系查询的 `Codebase` 符号检索工具。
- **多模态生成与按需 MCP 懒加载**：
  - 内置 `ImageSearch`、`ImageGen`、`VideoGen`，以及用于大规模工具集按需发现与调用的 `mcp_list`、`mcp_get`、`mcp_call`（权限粒度 `mcp__<server>__<tool>`，支持 `always_allow | always_ask | always_deny`）。

### 四路内置 MCP 与扩展子系统架构

1. **通道 1 — 原生工作区语义检索引擎（`qoder-context` `1.0.91.b22f2d0a`）**：
   - 以对用户隐藏的强制内置插件（`qoder-context@qoderapp-bundler`）分发，本地通过 `ELECTRON_RUN_AS_NODE` 启动 `qoder-search.bundle.mjs mcp-bridge`，SSH/WSL 远程工作区则由主进程自动重写为 `${QODER_REMOTE_RUNTIME_ROOT}/bin/node` 远端启动；底层结合 NAPI 原生模块 `mtree.node`、内嵌 `rg` 及会话生命周期钩子，默认常驻暴露 `SearchWorkspace` 与 `SearchKnowledge`。
2. **通道 2 — 知识中心双服务（进程内 `repowiki` + 子进程 `qoder-qmind`，共 29 个工具）**：
   - 进程内 `repowiki`（14 个工具）：含只读 `ListWiki` / `ReadWiki` 以及 12 个受生成状态门控的 Wiki 页面与架构知识卡片读写/关联工具（`list/read/edit/write/delete_wiki`、`reset_wiki_update_commit`、`list/read/edit/write/delete/link/unlink_knowledge`）。
   - 子进程 `qoder-qmind`（契约版本 `5.4.0`，15 个严格校验的 `qmind.*` 工具）：覆盖 Notebook 增删查、语义证据检索 `qmind.retrieve`、HTTPS 网页/本地文件 Source 导入与目录移动，以及支持显式时区 Cron 的 5 类知识维护定时任务（`compilation`、`condensation`、`lint`、`source_refresh`、`source_binding_sync`）。
3. **通道 3 — 全栈建站与 Serverless 托管（进程内 `qoder_sites`，共 33 个工具）**：
   - 注册 `qoder_sites`（`v0.1.0`），所有写操作强制校验宿主签发的封印不透明引用（`siteRef`/`backendRef`/`schemaRef`/`planRef`/`secretRef`/`accessRef`）与 `confirm: true`：涵盖站点准备/预览确认/发布恢复/子域名检测（`prepare_site`、`show_publish_confirmation`、`publish_site`、`check_subdomain`）、细粒度邮箱/UID 访问控制、托管数据库增量迁移与单主键行级增删改查、云函数日志（`get_function_logs`）、`10 MiB` 上限对象存储以及 `24h/7d/30d` PV/UV 统计。
4. **通道 4 — iOS/Android 真机控制（进程内 `qoder.phone-use`，共 50 个工具）与桌面/IM 桥接**：
   - 注册三个仅限本机任务（`executionLocation === "local"`）调用的进程内 MCP 服务：`mobile`（`mobile_list_devices`）、`ios`（`v0.4.0`，**28 个 `ios_*` 工具**，内置 `wda/QoderControl.ipa` WebDriverAgent Runner，支持 Xcode 自动签名安装、控件树/图像观测、长按拖拽、列表滚动采集、生物识别/验证码 `ios_pause` 人工接管及最多 20 步 `ios_batch` 批处理）与 `android`（`v0.5.2`，**21 个 `android_*` 工具**，内置带 SHA-256 校验的 `QoderControl.apk` 与 `scrcpy-server.jar`，且 `android_press_key` 刻意剔除回车提交键以防误触）。
   - `qoder.computer-control`：拉起原生 `QoderComputerUseBridge` 暴露 `event-stream` 录制回放 MCP（`event_stream_start/status/stop`）；`qoder.communication` 通过进程内代理将企业微信与钉钉市场插件接入会话。
   - **外部浏览器、原生辅助组件与 `0.5.3` 修复项**：随包附带 Chrome 扩展 `v1.7.6` 与 Native Messaging 宿主转发页面级 `webmcp_list_tools` / `webmcp_invoke_tool`、办公表格原生 `xlsx-sidecar`、`@ali/qoder-collab-cli@0.1.7`，以及 `Resources/bin/` 下的 `dji_mic_button.node`（大疆麦克风物理按键接入）、`hosted_presentation_host.node`、`native_clipboard.node` 等 6 个原生辅助模块；`0.5.3` 同时修复了工作区与近期任务列表在连续高频更新下卡在加载态的问题，以及历史会话缺失来源会话字段导致的任务列表加载失败。
