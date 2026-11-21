# ChatGPT / Codex 最新版本改动

[English](../codex.md) | 简体中文 · **精简版 (Highlight)** | [完整详情 (Full Detail)](full/codex.md)

> 五端（`mac`、`win`、`ubuntu`、`ios`、`android`）完整 418 个统一版本索引（`26.x` 桌面端 211 个 + `1.x` 移动端及早期 macOS 207 个）见 [codex/README.md](codex/README.md)。

## 最新 Android 版：1.2026.314（Android，2026-11-16 APKPure 归档）

核心亮点见 [codex/2026-11-16_android-1.2026.314.md](codex/2026-11-16_android-1.2026.314.md)，完整技术细节见 [full/codex/2026-11-16_android-1.2026.314.md](full/codex/2026-11-16_android-1.2026.314.md)。_（`versionCode 2631431` 的 APKPure 归档日为 `2026-11-16`，对比归档日 `2026-11-10` 的 `1.2026.307` / `2630718`；Google Play 精确发布时间未核实，无官方本版说明。仅限 `base` + `arm64_v8a` + `en` + `mdpi` 四 split 归档样本只读静态对比，不含 iOS 与 `300 → 307`，未运行 APK、未做 `apksigner` 完整密码学验签，客户端静态代码/文案/清单接线不代表功能已放量上线或运行时行为已发生。）_

- **内嵌 `RmcpHttp2Server`、Netty `4.1.140.Final` 与签名 RMCP Grant 字符串（客户端静态接线）**：新增 `RmcpHttp2Server`、打包 Netty `4.1.140.Final` HTTP/2 组件，并引入签名 RMCP 握手/授权字符串（`x-codex-rmcp-grant`、`use_handle_rmcp`、`/mcp`、`/handle-provider-relay`、`Mcp-Session-Id`；`/backend-api/ps/mcp` 与 `http://127.0.0.1:39801/android-executor/mcp` 在 `1.2026.307` 中已存在，静态字面量在场不证明实际监听）。
- **MCP Discovery/Skills 类型、`thread/delete` RPC 与移动端 Codex Remote 界面组件串**：`io.modelcontextprotocol` 新增 `DiscoverRequest*`/`DiscoverResult`、`CacheScope` 与 `mcp/skill` 标识；app-server RPC 新增 `thread/delete`（`+` `thread/deleted`、移除 `thread/realtime/listVoices`），12 项 `codex_app` 工具与模型 slug 集合不变；同步引入手机端 Codex Remote 模型菜单、主机管理/重连、会话删除（`CodexRemoteThreadRemovalDialog`）及双端会话冲突提示文案。
- **清单权限（`CALL_PHONE`、`FOREGROUND_SERVICE_MEDIA_PLAYBACK`）、通知/朗读服务与静态功能模块**：`<uses-permission>` 真正新增仅 `CALL_PHONE` 与 `FOREGROUND_SERVICE_MEDIA_PLAYBACK` 两条；以 `DeviceNotificationListener`（`oai_notifications`）替换 `MediaAccessNotificationListener`，注册 `ReadAloudPlaybackService` / `ReadAloudPauseReceiver` / `NotificationTapActivity`；新增扫码登录文案/资源（`qr_sign_in_available=` 在 `307` 已存在）、Wallet/比价/Learning 模块与 `"dot"` / Gmail OAuth 字符串；本 `2631431` 样本中大部分 3D mesh/runtime 资产未见（DEX 类 `91,702 → 94,565`，仍保留 `assets/orbit-bundled/{descriptor,metadata}.json` 与 `orbit_*` drawable，未见资产去向未证）。

---

## 最新 Windows 桌面版：26.1111.2228.0（Windows，2026-11-14）

核心亮点见 [codex/2026-11-14_26.1111.2228.0.md](codex/2026-11-14_26.1111.2228.0.md)，完整技术细节见 [full/codex/2026-11-14_26.1111.2228.0.md](full/codex/2026-11-14_26.1111.2228.0.md)。_（官方 CDN MSIX `Last-Modified`：`2026-11-14`，Microsoft Store 前台上架时间戳未确认；Store MSIX `26.1106.6628.0 → 26.1111.2228.0` 内部映射跨平台构建线 `26.1106.51428 → 26.1111.21308` / 构建号 `26605 → 27194`。仅限双官方 MSIX 静态解包对比，未安装 Windows 客户端、未做运行时或 MCP 握手验证。）_

- **MSIX 清单开机自启默认值调整（`Enabled="true"` → `"false"`）**：`AppxManifest.xml` 中 `<uap5:StartupTask TaskId="App">` 声明默认值由 `Enabled="true"` 改为 `Enabled="false"`（仅为清单默认值变化，实际安装/升级行为未经验证）。
- **Codex 引擎 `0.169.0-alpha.11.1`、Chromium `157.0.8103.78` 与 MCP Apps 预加载层**：原生 `codex.exe` 与随包 WSL Linux ELF `codex` 引擎版本串升至 `0.169.0-alpha.11.1`，Chromium 升至 `157.0.8103.78` 并重编原生模块、新增 `shared-texture.node`；扩容 `sandbox-preload.js`（Web Worker RPC 与结构化克隆序列化），新增 `application-websocket-preload.js`、`mcp-app-permission-declarations-v2` 及 `cua_node` Windows `window3` 自动化 API；渲染端 95 个 MCP 工具名与 8 个插件 `.mcp.json` 零增减（未验证全部 95 个接口语义及实时握手）。
- **技能导入、云端预览、Worktree 等门控与字符串同步（静态门控/字符串证据）**：主进程与主 UI bundle 同步引入 `claude-code-local-skills` / `codex-app-synced-skill-import`、`codex_desktop_cloud_previews`、`codex_app_worktrees`、`mcp_lazy_stdio_startup`、自动化收件箱已读操作、停止轮次确认、Spaces 缩略图、2026-11 批次连接器标识、College Plan / Birthday 深链路由、Quartz 图标及内联 SVG 启动流光屏（门控与字符串在场不代表已向用户开放）。

---

## 最新 Linux / macOS 桌面版：26.1111.21308（Linux / macOS，2026-11-13）

核心亮点见 [codex/2026-11-13_26.1111.21308.md](codex/2026-11-13_26.1111.21308.md)，完整技术细节见 [full/codex/2026-11-13_26.1111.21308.md](full/codex/2026-11-13_26.1111.21308.md)。

- **外部技能导入、云端预览与 Git Worktree 升级**：支持自动检测并导入本地 Claude Code 与 Cursor 的自定义技能（`SKILL.md`），在桌面端直接查看与管理云端实时预览（Cloud Previews），并新增 Worktree 设置页、分支初始化弹窗、迁移至 Worktree 对话框及 Git 关联检出挂载。
- **自动化任务收件箱、全局搜索、Spaces 与防误触中断**：上线自动化运行收件箱（支持未读运行计数与一键已读）及停止活跃轮次确认提示；新增全局搜索、Spaces 页面缩略图与自定义侧栏排序、本地项目一键转聊天与侧栏会话速览。
- **交互式 MCP 应用增强、11 月连接器与本地 MCP 懒启动**：MCP 应用小组件支持后台多线程（Web Worker）与按来源细粒度权限控制，支持本地 stdio MCP 服务按需懒启动；更新 DocuSign/HubSpot/Klaviyo（2026-11）连接器，支持恢复 Office 工作簿，新增 Quartz 图标并焕新启动流光界面。

---

## 其他平台近期重点版本

- **Desktop（macOS / Linux）`26.1106.51428`（2026-11-11）** — [精简版](codex/2026-11-11_26.1106.51428.md) · [完整详情](full/codex/2026-11-11_26.1106.51428.md)
  - 支持多账号管理与无缝工作区切换过渡屏、Code Review 置顶与最近 PR 记忆、Pages 多人协作文档、图片内文字直接编辑、宽屏交互图表与 `gpt-5-t-mini` 模型。
- **Desktop（Linux / macOS）`26.1103.60933`（2026-11-09）** — [精简版](codex/2026-11-09_26.1103.60933.md) · [完整详情](full/codex/2026-11-09_26.1103.60933.md)
  - 修复多账号快速切换时的侧栏状态串写问题，细化企业策略禁用输入框原因提示，支持回复文字批注与选中 Page 作为上下文，并为删除会话增加确认提示。
- **Android `1.2026.300`（2026-10-31）** — [精简版](codex/2026-10-31_android-1.2026.300.md) · [完整详情](full/codex/2026-10-31_android-1.2026.300.md)
  - 支持将 Android 手机配对挂载为 Codex 加密远程执行环境并弹出移动端交互式授权确认框，同时上线 Health Connect 健康数据接入、购物助手卡片、浏览器登录接力与 1Password / 验证码自动填充。
