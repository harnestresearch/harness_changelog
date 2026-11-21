# ChatGPT / Codex 最新版本改动

[English](../../full/codex.md) | 简体中文 · [精简版 (Highlight)](../codex.md) | **完整详情 (Full Detail)**

> 五端（`mac`、`win`、`ubuntu`、`ios`、`android`）完整 418 个统一版本索引（`26.x` 桌面端 211 个 + `1.x` 移动端及早期 macOS 207 个）见 [codex/README.md](codex/README.md)。

## Android 最新版：1.2026.314（Android，2026-11-16 APKPure 归档）

详细改动见 [codex/2026-11-16_android-1.2026.314.md](codex/2026-11-16_android-1.2026.314.md)。_（`com.openai.chatgpt` `versionCode 2631431` 的 APKPure 归档日为 `2026-11-16`，基线 `1.2026.307` / `2630718` 归档日 `2026-11-10`；Google Play 精确发布时间未核实，无官方说明。仅限四 split 归档 XAPK 样本只读静态差分，未运行 APK、未做 `apksigner` 完整密码学验签，提取证书指纹与已存 `2026-11-07` `chat.openai.com` `assetlinks.json` 记录一致。）_

- **Codex / MCP 客户端传输、SDK 与移动端 Remote UI 静态代码接线**
  - 新增 `com.openai.feature.deviceexecutor.impl.RmcpHttp2Server`（`RmcpHttp2Server$Frame`），首次打包 Netty `4.1.140.Final` HTTP/2 元数据与保留类，并引入签名 RMCP 握手/授权字符串（`x-codex-rmcp-grant`、`use_handle_rmcp`、四类校验错误串及 `/mcp`、`/handle-provider-relay`、`Mcp-Session-Id`；`/backend-api/ps/mcp` 与 `http://127.0.0.1:39801/android-executor/mcp` 在 `1.2026.307` 中已存在，静态串不证明当前实际监听）。
  - `io.modelcontextprotocol` 新增 `DiscoverRequest*`/`DiscoverResult`、`CacheScope` 与 `mcp/skill` 标识（协议日期常量仍为 `2025-03-26` / `2025-06-18` / `2025-11-25`）；app-server RPC 新增 `thread/delete`（`+` `thread/deleted`）并移除 `thread/realtime/listVoices`，12 项 `codex_app` 工具名与模型 slug 集合零增减；新增移动端 Codex Remote Compose 组件串（`CodexRemoteComposerModelMenuPopup`、`CodexRemoteThreadRemovalDialog`、`X-Codex-Surface`、`codex_remote.json`、`chatgpt_codex_web_routing_free_v2_group`）。
- **Android 清单权限、平台 Valdi 模块与打包资产差分（DEX 类 `91,702 → 94,565`）**
  - `<uses-permission>` 真正新增仅 `CALL_PHONE` 与 `FOREGROUND_SERVICE_MEDIA_PLAYBACK`（`+2 / -0`，其余权限 diff 为 XML 重排）；`<application>` 以 `DeviceNotificationListener` 替换 `MediaAccessNotificationListener`，新增 `ReadAloudPlaybackService`、`ReadAloudPauseReceiver`、`NotificationTapActivity` 与 `<meta-data android:name="com.openai.play_features" android:value="orbit"/>`；`<queries>` 新增微信/Viber/Zalo 包可见性及 5 项通知/健康/`http` intent（清单声明不等于实际读通知或拨号）。
  - `assets/*.valdimodule` 由 `118` 增至 `121`（新增 `oai_notifications`、`chatgpt_commerce_reporting`、`chatgpt_learning`），更新 `chatgpt_wallet_core`，并携带扫码登录文案/资源（`qr_sign_in_available=` 在 `307` 已存在）、`"dot"` / Gmail OAuth 字符串（`https://auth.api.openai.org/api/accounts/authorize`）及多项开关字面量（静态代码/文案存在不代表已向用户开放或计费生效）。
  - 本 `2631431` 样本中 `libcapture.so` 缩减 `946` KB（`-35.6%`），`assets/{meshes,fitted,orbit-runtime,orbit-thumbnails,orbit-licenses}/` 与 `assets/native-resources.bin` 下大部分 3D 资产未见（`base.apk` 净增 `+1.07` MB），但仍保留 `assets/orbit-bundled/{descriptor,metadata}.json`、`orbit_*` drawable 与 `liborbit_characters_jni.so`（未见资产去向未证）。

---

## Desktop 最新 Windows 版：26.1111.2228.0（Windows，2026-11-14）

详细改动见 [codex/2026-11-14_26.1111.2228.0.md](codex/2026-11-14_26.1111.2228.0.md)。_（官方 CDN MSIX `Last-Modified`：`2026-11-14`，Microsoft Store 前台上架时间戳未确认；Store MSIX `26.1106.6628.0 → 26.1111.2228.0` 内部映射跨平台构建线 `26.1106.51428 → 26.1111.21308` / 构建号 `26605 → 27194`。仅限双官方 MSIX 静态解包对比，未安装客户端、未做运行时或 MCP 握手验证。）_

- **MSIX 清单默认值翻转、引擎与 Chromium 运行时升级**
  - `AppxManifest.xml` 中 `<uap5:StartupTask TaskId="App">` 由 `Enabled="true"` 改为 `Enabled="false"`（仅为包清单默认值变化，实际系统安装/升级表现未验证）；`windows-store-update.json` 同时给出 Store `buildVersion`（`26.1111.2228.0`）与跨平台线 `releaseVersion`（`26.1111.21308`）。
  - 原生 `resources/codex.exe`（`+8.8` MB）与逐字节同源的 WSL Linux ELF `resources/codex`（`c147ac3b…`；内置工具集与 Linux `21308` 一致系由该 ELF 副本同源**推断**）版本串同步由 `0.167.0-alpha.4.1` 升至 `0.169.0-alpha.11.1`；Chromium 升至 `157.0.8103.78`，全量重编原生模块并新增 `resources/native/shared-texture.node`（`codex-shared-texture-create`）。
- **MCP Apps 预加载层、工具名集合与 `cua_node` Windows `window3` API**
  - 引入与 Linux `26.1111.21308` 逐字节相同的 `sandbox-preload.js`（`+115,494` B，`workers-module` Web Worker RPC 与 `structured-clone` 序列化器）及新文件 `application-websocket-preload.js`（`55,745` B），在 `early-bootstrap.js` 新增 `mcp-app-permission-declarations-v2` 持久化 Schema，并在 `cua_node` 新增 36 文件 Windows `window3` 桌面自动化 API。
  - 渲染端提取的 95 个 `snake_case` MCP 工具名、8 个插件 `.mcp.json`、`codex-app-tools/server.mjs`（`f0f5230d…`）及 26 项 `codex_desktop:*` IPC 通道均零增减（未对全部 95 个接口语义与实时 MCP 握手做运行时核验）。
- **主进程与渲染端门控及字符串集合更新（静态门控/字符串证据）**
  - 新增与 `26.1111.21308` 同集的 6 项字面量 gate（`codex-app-synced-skill-import`、`codex_desktop_cloud_previews`、`codex_app_worktrees`、`codex-app-serial-number`、`codex-default-environment-server-settings`、`lenovo_preload_reward_device_serial`）及 `mcp_lazy_stdio_startup`、`claude-code-local-skills`、云端预览/Worktree/SSH Portal 字符串、Protobuf 事件 `+19`（`1,280 → 1,299`）、自动化收件箱/停止轮次确认/Spaces/`2026-11` 连接器串、College Plan 与 Birthday 深链路由、Quartz 图标与内联 SVG 流光屏（移除 `gpt-instant-fallback` slug 与 `aeon-*` 串；门控与字符串在场不等于已向用户开放）。

---

## Desktop 最新 Linux / macOS 版：26.1111.21308（Linux / macOS，2026-11-13）

详细改动见 [codex/2026-11-13_26.1111.21308.md](codex/2026-11-13_26.1111.21308.md)。

- **引擎与运行时跨代升级**
  - 内置 Codex CLI 引擎连跨两个 minor 升级至 `0.169.0-alpha.11.1`（`resources/codex` 缩减 `26.3` MB、`codex-code-mode-host` 缩减 `9.2` MB，新增 `mcp_lazy_stdio_startup`、`websocket_upgrade`、`skill_namespace`、`execution_scope` 与 `approved_plan`）。
  - Chromium 运行时升级至 `157.0.8103.78`，并新增 `desktop:native:shared-texture` 原生工作区包（`codex-shared-texture-create`）。
- **MCP Apps Web Worker 沙箱与 Application WebSocket 预加载层**
  - `sandbox-preload.js` 扩容 `+115` KB，引入 `workers-module` Web Worker RPC 与完整流/Fetch 对象结构化克隆序列化；新增 `application-websocket-preload.js`（`55.7` KB）提供帧校验与 `admission_cancelled` 关闭处理；新增按来源持久化的 `mcp-app-permission-declarations-v2` 权限模型。
- **外部技能导入、云端预览与 Worktree 扩展**
  - 新增对 `claude-code` 与 `cursor` 的两级 `SKILL.md` 扫描与同步技能导入（`codex-app-synced-skill-import`）、云端预览控制（`codex_desktop_cloud_previews`）、Worktree 设置页/弹窗流（`codex_app_worktrees`）与 Git 关联检出附件、stdio MCP 懒启动，以及 Windows Store / MSIX 自更新接管遥测枚举。
- **自动化任务收件箱、全局搜索、Spaces 与内置插件**
  - 新增自动化运行收件箱、停止活跃轮次确认、`chatgpt-global-search`、Spaces 持久化、2026-11 批次 DocuSign/HubSpot/Klaviyo 连接器、43 项新 Protobuf 分析事件（`1,256 → 1,299`），以及 `cua_node` Windows `window3` 窗口自动化 API。

---

## 其他平台近期最新版本

- **Desktop（macOS）`26.1106.51428`（2026-11-11）** — 详见 [codex/2026-11-11_26.1106.51428.md](codex/2026-11-11_26.1106.51428.md)
  - Codex CLI 升至 `0.167.0-alpha.4.1`、Chromium 升至 `157.0.8103.51`；上线多账号切换与 `desktop-switch-loader`、云端 SSH Portal 响应式状态机、主进程 `automation_update` 处理器、Code Review PR 持久化、Pages 协作文档（DIL）、图片文字编辑与 `gpt-5-t-mini`。
- **Desktop（Linux）`26.1103.60933`（2026-11-09）** — 详见 [codex/2026-11-09_26.1103.60933.md](codex/2026-11-09_26.1103.60933.md)
  - 账号状态持久化引入世代计数器防切号串写，新增 `codex_desktop:network-online` 通道、`active_turn_mismatch` 错误映射、6 类策略禁用提示、页面批注模块及 `delete_thread` 弹窗确认配置。
- **Android `1.2026.300`（2026-10-31）** — 详见 [codex/2026-10-31_android-1.2026.300.md](codex/2026-10-31_android-1.2026.300.md)
  - 首次内建 MCP Kotlin SDK 与本地 Streamable-HTTP MCP 服务器（`android executor`），可将手机自身挂载为 Codex 执行环境；新增 `exec-server` Noise 加密分块中继、Elicitation 作答闭环、Health Connect 集成与移除旧对外 Token 服务。
