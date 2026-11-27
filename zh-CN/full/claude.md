# Claude 最新版本改动

[English](../../full/claude.md) | 简体中文 · [精简版 (Highlight)](../claude.md) | **完整详情 (Full Detail)**

> 五端（`mac`、`win`、`ubuntu`、`ios`、`android`）完整 534 个历史版本索引（桌面端 245 个 + 移动端 289 个）见 [claude/README.md](claude/README.md)。

## 最新 Android 版本：1.261124.19（Android，2026-11-25 Uptodown 镜像窗口）

详细改动见 [claude/2026-11-25_1.261124.19.md](claude/2026-11-25_1.261124.19.md)。基于两份 **Uptodown 第三方镜像** Play 原签分包 XAPK（`1.261123.19`［`versionCode` `26112319`］→ `1.261124.19`［`versionCode` `26112419`］，发布窗口约 `2026-11-25/26`；非直接来自 Play 官方下载，未做 `apksigner` 全量校验，不含 iOS 与 `1.261120.19`–`1.261122.*` 缺口，未运行 APK）的只读静态差分：

- **打包与清单不变量**：XAPK 条目 `37 → 30`（语言分包 `28 → 21`：`+config.te.apk`、`−config.{am,fil,hi,ml,mr,sw,ta,tl}.apk`）；`arm64_v8a`/`armeabi_v7a` 全部 `20` 个原生 `.so` 库逐字节一致；base APK `1,241` 条目（`META-INF/services` 轮换），`resources.arsc` `758,720 → 755,716` B，未压缩 DEX 总和 `59,979,864 → 60,997,648` B（约 `+1.0` MB；`classes6.dex` `4.59 → 5.71` MB，`classes3.dex` `−0.34` MB）；`minSdk`/`targetSdk` `32`/`37`、`66` 权限与 `83` 组件不变。
- **GitHub 集成、Safeguards 文案与 Places 面板（DEX 池 `171,650 → 173,615`）**：新增 `claudeai.code.connect_github_card.*`、Claude GitHub App 安装提示、PR/plan/工具调用审批失败分类、组织连接器审批提示、`CollapsedToolsSheetDestination${HostPage,ProductPage,Viewer}`、云环境引导、约 12 条 biology/cybersecurity/sensitive topics safeguards 换模型文案、`claudeai.places_list.*`（`viewed`/`photo_source_opened`/`place_changed`/`sources_info_opened`）+ `voice.reachability_checked`、`usage.section.*`、`settings.default_tab.*`、明示排除 PHI 的项目指令、朗读限额及约 20 条登录/错误文案。
- **移除面与网络面**：收缩/下线 `claudeai.code.continue_on_cloud.*`（`8 → 1`），移除 `artifacts.ready_made_card.rated`、`claudeai.money.message_box.*` 与旧 artifact 错误串；**API 端点零增删**（仅新增 `assets.claude.ai/claude-ai/wb/{file}` 与 `breville.com` favicon 字面量）。

---

## 最新桌面版本：5.11492.5（2026-11-14）

详细改动见 [claude/2026-11-14_5.11492.5.md](claude/2026-11-14_5.11492.5.md)。覆盖 `mac`、`win`、`ubuntu` 三端的内嵌 Claude Code 引擎功能小版本、Office 技能安全加固与沙箱/原生件轮换重建（桌面 UI 层较 `5.11492.2` 零新增）：

- **引擎会话存储键 Schema 与受管文件读取配置键**
  - `index.chunk-BDY2-Sqh.js` 由 `739 B` 扩充至 `21 KB`，定义覆盖 `transcript`、`sessionJournal`、`agentMemory`、`tasks`、`drafts`、新 `jobs-root`、恢复副本、`pluginRegistry`/`pluginAssetCache` 及 `user`/`project`/`local` 三层 `settings` 的本地存储键校验层，并整合会话 API、新增 `setSessionArchived`; 新增企业受管键 `blockFileToolReadsOutsideWorkingDirectories`（与 `blockWritesOutsideWorkingDirectories` 并存），并在 `ion-dist` `c6f6cf4c2`（`454 KB`）补全机器级 `env.CLAUDE_CODE_AUTO_MODE_MODEL` 文档指引。
- **内置 Office 技能（`docx`/`pptx`/`xlsx`）校验器安全加固（`agentSkillsRef` `1794527255 → 1794592614`）**
  - 新增 `names_another_root()`（基于 `PureWindowsPath` 拒绝带盘符/根锚路径）、OOXML relationship 目标 `os.path.normpath` + `is_relative_to(unpacked_dir)` 包含校验（越界记入 `broken_refs`），并将 `redlining.py` 外部 `git diff` 子进程替换为带工作量上限（`_WorkSpent`）的 `SequenceMatcher`（附 `xlsx` `recalc.py` 小改）。
- **10 语种翻译追赶、`smol-bin` 再轮换与 Linux 最小增量印证**
  - `ion-dist` 10 个非英语 locale 各补齐约 `48` 键（内置浏览器扩展权限/CRX 校验提示与订阅/积分过期文案），全平台轮换 `smol-bin` 镜像；Linux `.deb`（`99` 成员）仅 `app.asar`、`ion-dist.asar`、`smol-bin.x64.img` 3 个文件变化，主二进制 `claude-desktop` 与全部原生模块逐 SHA-256 未变，反证 `darwin` 端 `26` 个重建二进制属重签轮换（Electron `45.2.1`、`eipc` 桥面、API 端点与权限规则零变化）。

---

## 上一 Android 版本：1.261113.19（Android，2026-11-14）

详细改动见 [claude/2026-11-14_1.261113.19.md](claude/2026-11-14_1.261113.19.md)。基于两份 Uptodown Google Play 分包 XAPK（`1.261112.18`（`versionCode` `26111218`，Play 发布日未确认）→ `1.261113.19`（`versionCode` `26111319`，Google Play 美区 `"Updated on: Nov 14, 2026"`））的静态反编译与资源/字符串差分（不涵盖 iOS，未运行 APK；签名指纹 `305a1e8a…818b64a0` 与 `assetlinks.json` 匹配依据先前快照记录，未重新联网复验）：

- **`minSdkVersion` `29` → `32`（Android 10 → 12L）与分包修正**：解码 `AndroidManifest.xml` 证实 `minSdkVersion` 升至 `32`（`targetSdkVersion` `37` 不变）；XAPK 总条目 `37 → 39`，其中语言 split 实际 `27 → 30`（去 `bho`，增 `gu`/`nb`/`ta`/`te`）；该份 Uptodown Play-split XAPK 样本不含 `config.x86_64.apk`，仅代表样本构成，绝不构成官方停止支持 `x86_64` 的依据。
- **语音 `dictation` / `readaloud` 重构与残留 `TTSPlaybackService`**：`com.anthropic.claude.bell.tts` 移除 12 个辅助/异常类但仍保留 `TTSPlaybackService`，新增 `com.anthropic.voice.internal.{readaloud,dictation,dictation/offline}`（`189` / `116` / `105` 文件）、`stt.repo` 异常、`CallHooks.tools` 及注释明示 `"not open yet: the server does not verify it"` 的 `ConversationOptions.newChatPermissionMode`。
- **CCR 扩展、静态促销转额度/KYC 代码与遥测收缩**：新增 CCR `code/remote/state/ProjectSheet*`、`GitHubSsoRequiredException`、`CoworkTurnOutcomeWorker`、49 项 `CodeRemoteBottomSheetDestination`、已保存登录凭据授权提示、`"Response font"` / `"Anthropic Serif"` 与 `<files-path name="kept_tmp">`，移除旧 Threads 界面、`v1/code/sessions/{session_id}/feedback` 及位置事件属性字段（`66` 项系统权限与 HTTP(S) 域名集合零增删）；在 `1.261112.18` 既有 credits UI 之上新增促销转额度迁移提示、语音额度提示及 `organizations/{organization}/kyc_status`、`KycStatus`、`kyc_required` 购买结果枚举（静态在场不代表功能开放或计费/政策生效）。

---

## 上一桌面版本：5.11492.2（2026-11-13）

详细改动见 [claude/2026-11-13_5.11492.2.md](claude/2026-11-13_5.11492.2.md)。覆盖 `mac`、`win`、`ubuntu` 三端的功能演进、企业治理扩面与安全加固版本（并入 `5.11492.0`）：

- **企业配置模板导出与 `SandboxNetworkAccess` 权限规则**
  - 全平台新增 `.vite/build/configTemplateWindow.js` + `.vite/renderer/config_template_window/`（约 20 文件）与 eipc `ConfigTemplateExport_$_exportTemplates(selection)`；工具权限 schema 核心白名单新增 `SandboxNetworkAccess`，将沙箱联网从 `WebFetch` 中独立拆出。
- **SSH 主机级设置、大文件分块续读与 `ion-dist` 新增面**
  - 新增 `ssh_host_settings` 与 host-key 校验豁免三态（`posture`/`redial`/`redial_unverified`）、`LocalAgentModeSessions.readOpenedFileChunk(readId)`、`ComputerUseTcc.openMicrophoneSettings`、Claude for Chrome 逐动作授权文案、MCP 连接器四类 OAuth 客户端凭据模式、按流量计费网络 12 小时推迟更新、积分购买二次核验及 Loom/Vimeo/YouTube/Google Drive 预览支持。
- **三端安全加固与沙箱镜像重建**
  - Windows `AppxManifest.xml.in` 加固 `claude://` 参数分隔（`Parameters='-- "%1"'`）；Linux `.deb` 主程序 `claude-desktop` 权限位由 `04755` 收紧为 `0755` 并补齐 `esm.sh`、`cdn.jsdelivr.net`、`cdnjs.cloudflare.com`、`unpkg.com`、`fonts.googleapis.com/gstatic` 等 Artifact CDN 白名单；全平台重建原生 MCP 组件与 Cowork `smol-bin` 虚拟机镜像。

---

## 近期主版本基线：5.1231.0（2026-11-10，`4.x → 5.x`）

详细改动见 [claude/2026-11-10_5.1231.0.md](claude/2026-11-10_5.1231.0.md)。

- **内置浏览器 Chrome 扩展生态**
  - 主进程新增 `extensionWindow.js`、`extensionWorker.js`、`webStorePage.js` 三个核心 Bundle，接入 `https://chromewebstore.google.com` 与 Google CRX 分发更新管线，支持在内置浏览器中直接浏览、校验并安装 Chrome 扩展。
- **扩展 Agentic 桥与 1Password 自动填充**
  - 新增 `extension-host:agentic-call` 桥接协议（`agenticMode.enable/disable`、`agenticAutofill.fillCredential`），原生支持 Claude for Chrome 扩展联动与 **1Password Agentic Autofill** 登录凭据自动填充授权。
- **Cowork 插件目录与 Three.js 3D Artifact 渲染**
  - 新增 `CLAUDE_CODE_USE_COWORK_PLUGINS`、`CLAUDE_CODE_PLUGIN_CACHE_DIR` 等插件目录控制项；Web UI（`ion-dist.asar`）引入完整 Three.js WebGL 渲染管线，支持 3D Artifact 渲染。
- **运行时升级**
  - **Electron 升级至 `45.2.1`**（自 `44.9.3` 升级）。
