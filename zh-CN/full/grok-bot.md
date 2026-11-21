# Grok Bot 最新版本改动

[English](../../full/grok-bot.md) | 简体中文 · [精简版 (Highlight)](../grok-bot.md) | **完整详情 (Full Detail)**

> 五端（`mac`、`win`、`ubuntu`、`ios`、`android`）完整 115 个历史版本索引（桌面端 92 个 + iOS 端 23 个；独立 Android 端暂未发布）见 [grok-bot/README.md](grok-bot/README.md)。

## 1.2.0（2026-11-17，官方包 `Last-Modified` 北京时间）

详细改动见 [grok-bot/2026-11-17_1.2.0.md](grok-bot/2026-11-17_1.2.0.md)。

- **协议差分、主进程网络栈迁移与核验边界**
  - 官方 update API 与 `HEAD` 元数据确认 `darwin-arm64`、`linux-x64`、`win32-x64-user` 统一为 `1.2.0`（`commitSha: cf0aa5097b8fdfea8f2ecd33ce9f71a72655ef08`），但**逆向静态实证仅覆盖 Linux `x64` `.deb`（经 update API `debUrl` 获取，`aptrepo` `Packages` 当前不再列出 `grok-bot`）与 macOS `arm64` `.dmg` 双包**（Windows `Setup.exe` 仅核对元数据未下载，`darwin-x64` 与 `AppImage` 未分析，未运行被测程序，静态客户端面不代表后端已开放）。
  - `aiserver.v1.GrokBotService` 由 `515` 扩充至 `529` 个方法（`+14 / −0`，新增 14 项均为 `Unary`；全表 `509 → 523` `Unary` + `6` `ServerStreaming`），Protobuf 消息 `3,087 → 3,127`（`+43 / −3`）、枚举 `470 → 476`（`+6 / −0`），出现 **4 处字段删除**（`GetTeamPrepaidBillingResponse.uncovered_spend_cents`、`GetUserPrepaidBillingResponse.uncovered_spend_cents`、`SendMessageArgs.to_main_chat` 及 `ComposerCapabilityContext.GithubPRContext.conflict_resolution` + 3 个嵌套消息）。
  - 主进程网络与代理栈（`undici` / `EnvHttpProxyAgent` / `ProxyAgent`，含 `239` 条迁移长字符串）由 `main-app.cjs`（`−509` KB）迁入 `main-core.cjs`（`+433` KB），新增默认关闭（`default: false`）的开关 `sand_system_proxy_auto` 与 `sand_system_proxy_auto_kill_switch`（`trustSystemRoots`）。
- **Slack 工作区安装、第三方连接、Skill 版本回滚与公开 Changelog**
  - 新增 `Get/Start/UninstallGrokBotSlackWorkspaceInstall`（含 `StartOutcome` / `State` / `UninstallOutcome` 状态机）、`List/DisconnectGrokBotThirdPartyConnection`（`grok_bot_connected_apps_settings`）、`ListGrokBotSkillRevisions` / `RevertGrokBotSkill`（`GrokBotSkillRevisionAuthor`、`chunk-skill-change-diff`、`grok_bot_skill_links_in_chat` 及团队发布提示）、`ListPublicGrokBotChangelog`、内部 `Get/SetGrokBotPaperTermsInternal`（`covered_by_paper_addendum`）、`GetGrokBotShoppingOrderState`、`GetGrokBotMessagingContactPhoto`、`AdminMoveGrokBotMessagingUserLines` 及 `ResolveGrokBotAgentFileReads`（`GrokBotAgentFileStore`、`grok_bot_files_open_preview`、`grok_bot_library_tree/writes`）。
- **MCP 安全治理、`AppSecrets` Preload 接线、`AndroidControlDevice` 与客户端面收缩**
  - 新增 MCP `grok_sso_sign_in` 与 `blocked_reason_text`、团队 `mcp_allowlist_*` 设置、`grok_connectors_only_*`（`grokConnectorsOnly`）、内置连接器 `mcp.squarespace.com` 以及 5 个 Microsoft 365 SVG 图标与租户 `adminConsentUrl` 引导文案；移除 `grok_bot_mcp_app_unsafe_eval_desktop` 与 preload `allowEval`。
  - 具名接线 **5 个 `CloudAgentAppSecret*` preload 方法**（`createCloudAgentAppSecret`、`getCloudAgentAppSecrets`、`listCloudAgentAvailableAppSecrets`、`declineCloudAgentAppSecrets`、`widenCloudAgentAppSecretScope`；静态提取的 preload 标识符为 `701 → 709` / `+14 / −6`，含属性键名而非 14 个方法）、`dismissUpdateRestart`、`logoutCursor(..., switchToAccountId)`、企业席位授权（`TeamEnterpriseGrantState`）与 `DESIGNATED` 指定共享人、Castle 邀请令牌及 5 条航班检索文案。
  - `node-agent-coordinator` 静态工具注册表 `201 → 198`（`+AndroidControlDevice`，`−CreateTask` / `ReadTask` / `UpdateTask` / `DeleteTrackedTasks`，`UpdateTrackedTaskTags` 保留）；收缩客户端侧 Factory 资产（移除 `grok_bot_factories`、4 个 preload 遥测方法、`chunk-factory-layout` / `chunk-automation-run-rows`，`main-app` 中 `factory` 字符串 `84 → 14`，底层 Factory RPC/Protobuf 保留）；重组独立 `telegram.png` / `whatsapp.png` 图标文件；静态检查记录 6 个抽检 RPC（`0` 处不匹配）与 `UserComputer` / `lexec` 帧描述符一致（`.deb` 与 `.dmg` 的 `proto.cjs` / `preload.cjs` / `lexec` 逐字节一致；静态一致不证明运行兼容）。

---

## 上一版本：1.1.0（2026-11-14）

详细改动见 [grok-bot/2026-11-14_1.1.0.md](grok-bot/2026-11-14_1.1.0.md)。

- **纯加法协议演进与桌面运行时升级**
  - `aiserver.v1.GrokBotService` 由 `493` 扩充至 `515` 个方法（`+22 / −0`），ConnectRPC 服务定义由 `7` 增至 `11` 个（新增 `AppPublishService`、`UnifiedDashboardService`、`XaiAccountClosurePartnerService`、`XaiUnificationPartnerService`），Protobuf 消息 `2,829 → 3,087`（`+258 / −0`）、枚举 `411 → 470`（`+59 / −0`），全量零字段/枚举删除（`proto.cjs` `1,589,070 → 1,730,908` B；`UserComputer` 帧协议逐字节不变）。
  - **Electron 升级至 `43.8.9`**（自 `43.8.4` 升级，Chromium `150.0.7871.250`）；新增 `local-meeting-recorder.cjs`（`135,396` B）、`preload-spotlight-element-pick-overlay.cjs`（`17,989` B）、`sand_notification_settings.node` 触控板抬指监听 `watch_scroll_finger_lift`、AppImage 更新签名校验 `verifySignature` 以及 `@anysphere/cursor-icons`。
- **Factories 流水线、Cloud Agent 应用托管与页面发布审查**
  - 上线 YAML 声明式 **Factories** 流水线（`List/Save/Run/DeleteGrokBotFactory`、`UpdateFactory` 工具、步骤与定时表达式校验、`chunk-factory-layout`、开关 `grok_bot_factories`）。
  - 新增 Cloud Agent 应用托管（`PublishApp`/`UnpublishApp`、`AppDeployment`、`AppAccessList` 及 8 个 preload `CloudAgentPublish*` 方法）、**`AppSecrets`** 密钥绑定生命周期（`Create/List/Set/Delete/Bind/Unbind/Widen/Sync/Decline/Request/ApplyAppSecrets`）以及 **Page 页面发布、安全审查与组织受众分享**（`ProposePublish`、`PublishReview`/`PublishReviewOverride`、`Get/UpdatePublishedPageShare`、`PublishMerge`）。
- **Cursor ↔ xAI 统一、手机/消费管控与企业网络安全**
  - 新增 Cursor ↔ xAI 账号与团队合并结账（`Start/Get/CancelCursorTeamMerge`、`Prepare/FinalizeCursorTeamMergeCheckout`、`CreateUnifiedDashboardTeam`、`CompleteXaiUnificationAfterPurchase`、`XaiCloseAccount`/`XaiReopenAccount`）、账户手机验证码绑定与短信表单提交（`Send/ConfirmGrokBotAccountPhoneCode`、`StartFormLinkOwnerCode`、`SubmitTextedFormLink`）、手机扫码配对（`getPhoneAppQrUrl`）、消费自动批准与限额（`Get/SetGrokBotPurchaseAutoApprove`、`SetGrokBotPurchaseSpendLimit` 及 37 语言 `"Approve in the X app"`）、`TeamOrganizationNetworkBlocklist` 组织网络黑名单、团队级 `TeamTailnetExitNode` 出口节点、`SandboxingMode.ENFORCED` 强制沙箱、`MintSandBoxPluginSyncGitToken`、STT 说话人分离（`SttConfig.diarize`、`SttSpeakerTurn`）、`StartGrokBotLocalPitman`、GitHub SCM 连接流程、任务↔转写关联、`+8` 个代理工具（`194 → 202`）以及 Statsig 门控白名单 `168 → 184`（`+17 / −1`）。

---

## 近期主版本基线：1.0.1（2026-11-11）

详细改动见 [grok-bot/2026-11-11_1.0.1.md](grok-bot/2026-11-11_1.0.1.md)。

- **双线合并与运行时升级**
  - 将 `0.78.2 – 0.79.4` 功能分支完整合入 `1.0` 正式通道，`GrokBotService` 由 `1.0.0` 的 414 个方法扩展至 **493 个方法**（含 30 个全新方法）。
  - **Electron 升级至 `43.8.4`**（自 `42.11.16` 首次升级），同步重编译全部 13 个原生模块。
- **桌面体验与代码渲染**
  - 新增 Spotlight 式快捷输入面板（含焦点宽限与回退策略）、窗口几何状态持久化、基于 `tree-sitter` 的聊天代码语法高亮（`CodeTokenizerProvider`）以及 `country-flag-icons` 语言旗帜图标。
- **语音探测与状态提示音**
  - 新增 `api.x.ai/v1/realtime` 可达性探测与阻断原因细分（区域拒绝、隧道拒绝、证书异常等）；新增 **Status Chimes 状态提示音**（任务发送、结果返回、等待决策、出错四类事件提示音）。
- **iMessage 群聊、电商结账与租车卡片**
  - 新增 iMessage 群聊记录读取与退群接口、手机号验证码绑定流程。
  - 新增购物车结账与取消接口（`Start/CancelGrokBotCartCheckout`）、租车业务卡片（`car_rentals` / `car_rental_locations` / `car_rental_detail`）、航司图标资源、礼品送达日期校验与机票点击预订。
- **Agent 偏好层与团队治理**
  - 新增多层 Agent 偏好配置、自动审查开关、文件/技能私有化、Slack 分享治理、自动化立即运行与卡片重跑。
  - 新增管理端双模型并行对比评测（`ModelComparison`）、团队沙盒部署自检、企业消费限额、连接器封禁策略门控，以及 QuickBooks MCP 与 Tailscale 集成回归。
- **随 0.79.x 分支同步进入正式版的能力**
  - 用户隐私模式与训练数据授权弹窗、Passkey 登录仪式、日历与服务端会议协议、iMessage 交互式审批消息卡、全文转写搜索（`SearchGrokBotTranscripts`）、Agent Store 市场及 1Password 服务账户保险库连接器。
