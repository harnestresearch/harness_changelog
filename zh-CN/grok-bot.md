# Grok Bot 最新版本改动

[English](../grok-bot.md) | 简体中文 · **精简版 (Highlight)** | [完整详情 (Full Detail)](full/grok-bot.md)

> 五端（`mac`、`win`、`ubuntu`、`ios`、`android`）完整 115 个历史版本索引（桌面端 92 个 + iOS 端 23 个；独立 Android 端暂未发布）见 [grok-bot/README.md](grok-bot/README.md)。

## 1.2.0（2026-11-17，官方包 `Last-Modified` 北京时间）

核心亮点见 [grok-bot/2026-11-17_1.2.0.md](grok-bot/2026-11-17_1.2.0.md)，完整技术细节见 [full/grok-bot/2026-11-17_1.2.0.md](full/grok-bot/2026-11-17_1.2.0.md)。

> **核验范围**：官方 update API 与 `HEAD` 元数据覆盖 `mac`、`ubuntu`、`win` 统一 `1.2.0`，但**逆向静态实证仅覆盖 Linux `x64` `.deb` 与 macOS `arm64` `.dmg` 双包**（Windows 安装包仅核对元数据未下载，`darwin-x64` 与 `AppImage` 未分析，且未运行被测程序——客户端协议、preload、开关与文案存在不代表后端已开放或线上可用）。

- **Slack 工作区安装状态机与第三方连接管理**：新增团队级 Slack 工作区查询、安装与卸载状态机及 `"Connect Slack"` / `"Return to Slack"` 文案，并支持按 Bot 维度列出或断开已授权第三方应用（配 `grok_bot_connected_apps_settings` 开关）。
- **技能版本回滚、公开 Changelog、订单状态、文件预览与航班文案**：新增 Skill 历史版本查询/回滚接口、变更对比视图与团队发布提示，上线面向客户端的公开只读 Changelog 接口、购物订单状态与消息联系人头像查询、区分 Bot 与用户存储的 Agent 文件读取解析与预览/资料库开关、5 条航班检索进度文案，并将状态兜底文案更新为 `"Grok's servers did not report a status"`。
- **MCP 安全治理、Microsoft 365 管理员审批与 Squarespace 连接器**：为 MCP 服务补充 Grok SSO 登录标记与组织拦截原因文案，落地团队 MCP 白名单字段与“仅连接器”（`grokConnectorsOnly`）受限模式，内置连接器目录新增 Squarespace（`mcp.squarespace.com`），补充 Microsoft 365 五件套图标与租户管理员审批（admin consent）引导文案，同时移除桌面端 MCP 应用 iframe `unsafe-eval` 开关与 `allowEval`。
- **Cloud Agent App Secrets 客户端接线、登出切号与安全管控**：将 `1.1.0` 协议层 **App Secrets** 子系统的 5 个方法首次接线至桌面端 preload，`logoutCursor` 支持登出后直切目标账号（`switchToAccountId`），新增可关闭的更新重启提示、团队“指定共享人”模式与企业席位授权状态、更严格的本地工具审批目标提示，以及默认关闭的沙箱系统代理自动跟随开关（`sand_system_proxy_auto`）。
- **Android 设备控制工具位与客户端资产调整**：静态代理工具注册表与本地审批枚举新增 `AndroidControlDevice`，同时从该注册表移除 `CreateTask`、`ReadTask`、`UpdateTask`、`DeleteTrackedTasks` 四个任务 CRUD 工具项（`UpdateTrackedTaskTags` 与任务状态描述字段保留，非产品全部任务功能下线）；客户端移除 `grok_bot_factories` 开关、4 个 Factory preload 遥测方法及相关前端分块（底层 Factory RPC/Protobuf 保留）；移除独立 `telegram.png` / `whatsapp.png` 图标文件但保留包内平台字符串，属静态资源重组。

---

## 上一版本：1.1.0（2026-11-14）

核心亮点见 [grok-bot/2026-11-14_1.1.0.md](grok-bot/2026-11-14_1.1.0.md)，完整技术细节见 [full/grok-bot/2026-11-14_1.1.0.md](full/grok-bot/2026-11-14_1.1.0.md)。

- **Factories 多步骤流水线**：上线基于 YAML 声明式定义的 **Factories** 自动化流水线，支持创建、定时调度、立即运行与管理多步骤 Agent 工作流。
- **Cloud Agent 应用托管与页面发布分享**：推出云端应用（Cloud Agent Apps）与页面（Page）完整发布体系，支持带作用域的 **App Secrets** 密钥管理、发布前安全审查与豁免审批、实时预览及按团队/组织受众精细配置分享权限。
- **Spotlight 元素拾取器、本地会议录制与说话人分离**：为 Spotlight 新增屏幕元素拾取覆盖层，引入桌面本地会议录制模块与 **Local Pitman** 本地会议助手流程，并为实时语音转写（STT）新增按说话人分段（Speaker Diarization）能力。
- **消费自动批准、额度上限与 X 应用内审批**：新增消费自动批准开关与按币种消费限额控制，支持 X Money 消费验证挑战、**“在 X 应用中批准”（Approve in the X app）**确认提示，并扩充商品、外卖订单动态与地点卡片推送。
- **账户手机验证、扫码配对、GitHub 接入与企业安全强化**：新增账户短信验证码绑定与短信表单认证、手机扫码配对桌面面板、原生 GitHub/SCM 代码仓连接、Cursor ↔ xAI 账号与团队合并向导、组织级网络封禁名单、团队统一 Tailscale 出口节点、策略强制沙箱模式、任务与会话记录双向关联及话题线程回复。

---

## 近期主版本基线：1.0.1（2026-11-11）

核心亮点见 [grok-bot/2026-11-11_1.0.1.md](grok-bot/2026-11-11_1.0.1.md)，完整技术细节见 [full/grok-bot/2026-11-11_1.0.1.md](full/grok-bot/2026-11-11_1.0.1.md)。

- **Spotlight 快捷输入面板与桌面体验升级**：新增 Spotlight 式全局快捷输入栏、窗口位置与最大化状态记忆、聊天代码块语法高亮、语言选择器国旗图标，并完成桌面底层运行时首次大版本升级。
- **状态提示音（Status Chimes）与语音连通性诊断**：支持在任务发送、结果返回、等待确认与出错时播放轻柔提示音，并在语音通话受网络、区域或证书阻断时给出明确原因诊断。
- **iMessage 群聊、电商结账与出行卡片**：支持读取与退出 iMessage 群聊、手机号短信验证码绑定，新增购物车发起/取消结账、租车卡片、机票点击预订以及虚拟试穿照片管理。
- **隐私模式、Passkey 登录、Agent Store 与团队治理合入正式版**：全面合入用户隐私模式与训练数据授权开关、Passkey 通行密钥登录、1Password 凭据接入、日历/会议与交互式审批消息卡、Agent Store 应用市场及企业消费限额与连接器管控能力。
