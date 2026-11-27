# Kimi 最新版本改动

[English](../../full/kimi.md) | 简体中文 · [精简版 (Highlight)](../kimi.md) | **完整详情 (Full Detail)**

> 五端（`mac`、`win`、`ubuntu`、`ios`、`android`）完整 186 个历史版本索引（桌面端 `mac`/`win` 最新 `3.2.29`、iOS 最新 `3.1.8`，独立 Linux 端暂未发布；`3.2.25` 至 `3.2.29` 之间的中间桌面版本尚未全部入录或完成解析）见 [kimi/README.md](kimi/README.md)。

## 最新桌面端深度解析版本：3.2.29（2026-11-26，`mac`、`win`）

详细改动见 [kimi/2026-11-26_3.2.29.md](kimi/2026-11-26_3.2.29.md)。基于官方带版本直链的 macOS `arm64`（`com.moonshot.kimichat`，`3.2.28.27 → 3.2.29.35`）与 Windows `x64`（PE `FileVersion` `3.2.28.33 → 3.2.29.38`）双包进行的 **`3.2.28`（2026-11-18）→ `3.2.29`（2026-11-26）** 静态差分（跨端 Sentry 构建指纹 `3.2.28+e69611da7c → 3.2.29+9f88ce6cda`；`3.2.25` 之后的中间桌面版本尚未全部入仓——仓内无 `3.2.28` 条目，`3.2.26`/`3.2.27` 仍为 `win` 端 `TODO` 占位——因此 `3.2.25` **并非**本对对比基线；macOS Intel 未取样；官方无 Linux 包，记为「无」；iOS/Android 不在范围；未运行目标二进制）：

- **官方未提及的本地文件版本历史子系统（基于 `restic`）**：新增 `0 → 13` 个独立 `kimi-agent:file-history-*` IPC 通道（`list`、`read-version`、`image`、`image-cancel`、`diff`、`summary`、`restore`、`status`、`changed`、`attach`、`edit-sessions-ack`、`edit-sessions-freeze`、`edit-sessions-unfreeze`），随包内置 `restic` `0.19.1`（`darwin-arm64/restic` `29,603,376` B / `win32-x64/restic.exe` `31,670,288` B）与 `restic-bsd-2-clause.txt`，`out/main/chunks/` 新增 `18` 个模块前缀（`file-history-client`、`version-diff`、`version-summary`、`restic-resolver`、`repository-key-store`、`maintenance-scheduler`、`process-supervisor`、`lease`、`ab-gate` 等），`out/build-manifest.json` 新增 `flavor.features.fileHistory: true`，解码主进程新增 `file_history_restic`、`ResticCommandError`、`fileHistoryAbEligible`、`isFileHistoryRuntimeEnabled`；`zh-CN` 新增 `113` 个 key 中除 `2` 条全局搜索文案外，其余 `111` 条均为文件/版本历史及版本比对相关。含 A/B 开关标记，不代表对所有用户立即可见。
- **官方 `3.2.29` 条目分层对照**：已坐实——Markdown 预览大纲导航（`obsidianToc` 在 `3.2.28` 为 `0` 次、`3.2.29` 见于双端 `WorkbenchPanel` 与 `en-US`/`zh-CN` 语言包）与全局搜索 UI/交互（新增 `showMoreMatches`、`searchOlderConversations` 及双端 `GlobalSearchModal` JS 更新 + 新增 CSS）。仅模块级（未逐行验证）——工作台文件树展开收起（新增 `WorkbenchFileSurface`）、远程控制权限同步与全自动误弹审批（`preload-permission-flow.mjs`、`permission-flow*`、`RemoteControl*`、`ApprovalPrompt`）、听写误回填（`MessageList`、`ConversationView`）及市场插件授权过期（新增 `use-plugin-install-flow` 及插件页更新）。仅来自官方日志、未独立锁定包内落点——移动端键盘遮挡插件/技能列表、资料刷新侧栏跳动与图片预览缩放错目标（不将 `pinch-zoom` preload 移除作为缩放修复行级证据）。
- **运行时、归档、依赖与签名核验边界**：Electron `43.7.7` / Chromium `150.0.7871.250` 不变；`daimon` 升至 `1.0.15`（`1.0.14 → 1.0.15`）；双端 `app.asar` 增删改计数均为 `+915 / −885 / 44` 且 `44` 个修改路径完全相同（去哈希增删路径集合未独立复现同构结论）；`gateway.asar` 双端各增约 `+6.4` MB；`runtime/npm.asar` 双端逐字节未变；`package.json` 升级 `pnpm` `9.15.0 → 12.21.0`、`@doc-k/embed-sdk` `0.5.0 → 0.6.1`，新增 `geographiclib-mgrs` `1.0.7`，并移除原 `pnpm` overrides/patches 配置段。签名边界：macOS 主二进制 Team ID `2J9472RW75`、`com.moonshot.kimichat`、`Developer ID Application`（分析报告记录 CodeDirectory `3/3` 页哈希吻合，本次核验未重算页哈希，未完成 Apple 根信任与公证验证）；Windows 双包由同一 Sectigo EV 主体（叶证书组织为北京月之暗面科技有限公司）签名并带 RFC3161 时间戳，**未重算 Authenticode PE 摘要**，亦未验证 Sectigo 根信任与时间戳有效性。

---

## 更早深度解析桌面版本：3.2.25（2026-11-05，macOS）

详细改动见 [kimi/2026-11-05_3.2.25.md](kimi/2026-11-05_3.2.25.md)。

### 版本概览

Kimi Desktop `3.2.25` 在 Electron `43.7.7` 宿主内整合了五大核心技术子系统：（1）内嵌智能体内核 `daimon-bundle` `v1.0.6`（封装 `kimi-code` `v0.5.1` 并自带独立 Node.js `24.15.0`、CPython `3.12` 与 `uv` 工具链）；（2）覆盖云端网关、本地子进程/HTTP、OAuth 2.1 PKCE、Chromium 150 原生 `WebMCP` CDP 域以及桌面操控 `kimi-cu` 的五路 MCP 集成架构；（3）7 个基于 Rust `napi-rs` + Swift 的 macOS 原生 `.node` 扩展；（4）体积 196 MB 的 `gateway.asar`（基于 OpenClaw 的 Desktop Claw 消息网关与 `kimiim-cli`）；以及（5）用于 LaTeX 编译、生物信息序列处理与 3D CAD 解析的沙箱 WASM 引擎。

### 内嵌智能体内核与独立运行时工具链

- **`daimon-bundle`（`v1.0.6`）与 `kimi-code`（`v0.5.1`）**
  - 随包分发 `resources/daimon-bundle/`（核心入口 `kernel-bundle.mjs`），并内置隔离的 Node.js `24.15.0`、Python `3.12` 与 `uv` 环境，使本地 Shell 执行、Python 数据分析与代码修改无需依赖宿主机全局环境。
  - 提供完整本地工作区原语（`Shell`/`Bash`、文件读写与补丁编辑、Glob/Ripgrep 检索、任务清单管理、子代理派发与网页抓取），通过本地 IPC 与 Electron 主进程协同。
- **随包原生辅助工具**
  - `kimiim-cli`：负责多渠道 IM 机器人绑定与网关生命周期管理的命令行桥接工具。
  - `kimi-slides`：本地演示文稿生成、渲染与导出组件。
  - `kimi-webbridge`（状态目录 `~/.kimi-webbridge`）：本地浏览器与工作区通信桥接守护进程。
- **Desktop Claw 消息网关（`gateway.asar`）**
  - 内置独立的 `196 MB` `gateway.asar`（基于 OpenClaw 定制的 Desktop Claw），负责将外部 IM 渠道会话及移动端远程控制指令路由至本机智能体工作区。

### 五路 MCP 集成架构

- **路径 1 — 云端网关 MCP（`agent-gw.kimi.com`）**：通过带鉴权的 HTTPS/SSE 通道接入 Moonshot 云端托管连接器与远程工具。
- **路径 2 — 本地与远程自定义 MCP Server（`stdio` / `SSE` / `StreamableHTTP`）**：基于 `@modelcontextprotocol/sdk` 在主进程管理用户配置的 MCP 服务，完整支持 `initialize`、`tools/list`、`tools/call`、`resources/*`、`prompts/*` 及 `elicitation/create` 交互式审批弹窗。
- **路径 3 — `MCPOAuthService` 授权服务**：实现 OAuth 2.1 + PKCE 自动元数据发现（`.well-known/oauth-authorization-server` 与 `.well-known/oauth-protected-resource`）、本地回环/自定义协议回调捕获、安全令牌存储与自动续期。
- **路径 4 — Chromium 150 `WebMCP` CDP 域桥接**：通过 Chrome DevTools Protocol 挂载内置浏览器 `WebContents` 并启用 Chromium 150 新增的 `WebMCP` 域，自动发现网页暴露的结构化工具并注入当前对话上下文。
- **路径 5 — `kimi-cu` 桌面操控 MCP**：将底层截图、端侧 OCR 与键鼠事件封装为 `screenshot`、`click`、`double_click`、`move`、`drag`、`scroll`、`type`、`key`、`wait` 等 Computer Use 工具供模型调用。

### macOS 原生 NAPI 模块与沙箱 WASM 引擎

- **7 个原生 `.node` 模块（Rust `napi-rs` + Swift/Objective-C 系统框架）**：
  - `kimi-darwin.node`：macOS 窗口控制、辅助功能/屏幕录制 TCC 权限检测以及系统外观与电源状态钩子。
  - `kimi-screen-capture.node`：基于 ScreenCaptureKit / CGWindowList 的高性能屏幕与窗口采集。
  - `kimi-ocr.node`：调用 Apple Vision 框架（`VNRecognizeTextRequest`）实现端侧离线文字识别。
  - `kimi-scroll-input.node` 与 `kimi-global-input.node`：合成 CGEvent 平滑滚动、指针轨迹、键盘输入及全局快捷键监听。
  - `kimi-file-manager-selection.node`：读取当前 Finder 激活窗口路径与选中文件列表，实现「直接针对访达选中文件提问」。
  - `kimi-keyboard-environment.node`：检测当前输入法（IME）与键盘布局状态，避免中文输入法激活时合成按键串码。
- **领域专用沙箱 WASM 模块**：
  - `tectonic.wasm`：端侧沙箱化 TeX/LaTeX 排版编译引擎，直接在本地将 `.tex` 编译为 PDF。
  - `samtools.wasm`：端侧生物信息学 BAM/SAM/CRAM 序列比对分析模块。
  - `occt-import-js.wasm`：OpenCASCADE WebAssembly 几何内核，支持在客户端直接解析并三维预览 STEP/IGES/BREP 工业 CAD 模型。

---

## 近期 Android 端深度解析版本：3.1.5（2026-10-23）

详细改动见 [kimi/2026-10-23_android-3.1.5.md](kimi/2026-10-23_android-3.1.5.md)。

### 版本概览

Kimi Android `3.1.5`（`versionCode 382`）在移动端完整落地了面向桌面工作区的远程控制客户端协议栈、基于 ConnectRPC 的 `/apiv2/kimi.gateway.*` 多渠道认证矩阵、面向 Kimi Claw 的跨应用授权入口（`AuthActivity3`），以及结合设备风控签名的双令牌续期机制。

### 远程控制（Remote Control）协议与实时媒体链路

- **远控指令与状态协议（`i00.*` 包族）**：
  - 实现结构化 JSON 远控消息通道，围绕 6 类核心动作驱动远端桌面工作区：`pick`（远端文件/目标点选）、`read`（读取远端文件与工作区状态）、`upload`（将手机相册/文件上传至桌面会话）、`preview`（预览远端产物）、`release`（释放远控控制权）与 `status`（主机在线与运行状态同步）。
  - 新增 `RcReadOnlyImageActivity` 只读图像预览 Activity，专用于在手机端安全查看远端桌面截图与生成图表。
- **TRTC 实时音视频管线**：
  - 集成腾讯云实时音视频（`TRTC`）原生 SDK，承载实时语音通话及远控场景下的低延迟媒体流传输。

### 认证矩阵与会话安全续期

- **ConnectRPC 网关登录矩阵（`/apiv2/kimi.gateway.*`）**：
  - 统一通过 `/apiv2/kimi.gateway.*` ConnectRPC 服务承载短信验证码登录、运营商本机号码一键登录、微信 OpenSDK 授权登录与邮箱登录。
  - 提供 `AuthActivity3` 外部拉起授权页，专门处理 **Kimi Claw** 跨应用绑定与第三方伴生工具的 OAuth 授权确认。
- **`AccountSessionManager`、MMKV 存储与风控令牌刷新**：
  - 由 `AccountSessionManager` 将登录凭据与用户缓存持久化至 MMKV 实例 `kimi_cache_user_info`。
  - 通过 `POST /api/account.gateway.v1.AuthService/RefreshToken` 执行前置续期与 401 拦截重放，请求头强制携带设备风控载荷 `X-Msh-Shield-Data` 及 `X-Msh-Device-Id`、`X-Msh-Platform`、`X-Msh-Version`。
