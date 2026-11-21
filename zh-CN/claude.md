# Claude 最新版本改动

[English](../claude.md) | 简体中文 · **精简版 (Highlight)** | [完整详情 (Full Detail)](full/claude.md)

> 五端（`mac`、`win`、`ubuntu`、`ios`、`android`）完整 533 个历史版本索引（桌面端 245 个 + 移动端 288 个）见 [claude/README.md](claude/README.md)。

## 最新桌面版本：5.11492.5（2026-11-14）

核心亮点见 [claude/2026-11-14_5.11492.5.md](claude/2026-11-14_5.11492.5.md)，完整技术细节见 [full/claude/2026-11-14_5.11492.5.md](full/claude/2026-11-14_5.11492.5.md)。

- **企业受管文件读取策略与自动模式说明完善**：新增企业受管配置键 `blockFileToolReadsOutsideWorkingDirectories` 以管控 auto-mode 下工作目录外文件读取授权提示，并在管理设置文档中补充整机级 `env.CLAUDE_CODE_AUTO_MODE_MODEL` 覆盖自动模式审阅模型的说明。
- **内置 Office 文档技能安全加固与大文档比对防耗尽**：加固内置 `docx`、`pptx`、`xlsx` 技能校验器以拦截 Windows 盘符/根路径穿越及越界 OOXML 关系引用，并将修订比对（redlining）改为带工作量上限的序列比对算法以防超大文档耗尽资源。
- **内嵌引擎会话存储键校验层与多语种翻译补齐**：在内嵌 Claude Code 引擎中建立覆盖会话记录、任务、草稿、`jobs-root` 及三层设置的存储键校验体系与 `setSessionArchived` 归档支持，轮换全端 Cowork 沙箱镜像，并为 10 个非英语语种补齐约 48 条扩展与订阅确认文案（桌面英文界面较 `5.11492.2` 无新增变化）。

---

## 最新 Android 版本：1.261113.19（Android，2026-11-14）

核心亮点见 [claude/2026-11-14_1.261113.19.md](claude/2026-11-14_1.261113.19.md)，完整技术细节见 [full/claude/2026-11-14_1.261113.19.md](full/claude/2026-11-14_1.261113.19.md)。_（Google Play 美区 `"Updated on: Nov 14, 2026"` + Uptodown `"Matches the published version"`；基线 `1.261112.18` 官方发布日未确认。仅基于 Uptodown Play-split XAPK 静态分析；不涵盖 iOS，未运行 APK，静态代码与文案在场不代表功能开放或政策/计费已生效。）_

- **最低系统要求升至 Android 12L（`minSdkVersion` `29` → `32`）与 `27 → 30` 语言分包**：解码清单证实最低系统版本由 Android 10（`29`）提升至 Android 12L（`32`，API 32），`targetSdkVersion` `37` 不变；XAPK 总条目 `37 → 39`，语言 split 实际由 `27` 扩至 `30`（移除 `bho`，新增 `gu`、`nb`、`ta`、`te`；该份 Uptodown 分包样本未含 `config.x86_64.apk`，仅属样本现象而非官方停支证据）。
- **独立语音听写（含离线听写）与朗读模块重构**：清理 `com.anthropic.claude.bell.tts.*` 下 12 个旧辅助/异常类（`TTSPlaybackService` 仍保留），在 `com.anthropic.voice.internal` 下新增 `readaloud`、`dictation` 与 `dictation/offline` 模块及 `stt.repo` 听写异常、`CallHooks.tools` 挂载更新。
- **CCR 项目设置、GitHub SSO、底部导航扩充与静态额度迁移/KYC 代码**：新增 Claude Code Remote 项目设置表单、`GitHubSsoRequiredException`、`CoworkTurnOutcomeWorker` 后台完成通知、49 项底部导航目的地、已保存登录凭据授权提示、`"Response font"` / `"Anthropic Serif"` 与 `<files-path name="kept_tmp">`，下线移动端旧 Threads 视图并清理遥测位置事件字段；在 `1.261112.18` 既有 credits UI 基础上新增促销转额度迁移提示、语音额度提示及 `KycStatus` / `organizations/{organization}/kyc_status` 客户端代码（仅限静态代码在场）。

---

## 上一桌面版本：5.11492.2（2026-11-13）

核心亮点见 [claude/2026-11-13_5.11492.2.md](claude/2026-11-13_5.11492.2.md)，完整技术细节见 [full/claude/2026-11-13_5.11492.2.md](full/claude/2026-11-13_5.11492.2.md)。

- **企业受管配置模板导出与计量网络更新控制**：新增企业配置模板导出窗口以便在 macOS 与 Windows 上批量部署受管配置，完善强制更新重启策略与统一管理台指引，并支持在按流量计费网络下最长推迟 12 小时下载更新。
- **独立沙箱网络权限与 Chrome 细粒度动作授权**：将沙箱联网拆分为独立的 `SandboxNetworkAccess` 规则，并在 Claude for Chrome 中新增点击、输入、滚动、截图及读取页面网络请求等逐动作授权确认。
- **SSH 主机设置、大文件分块读取与安全加固**：新增 SSH 主机级配置与密钥校验诊断、本地会话大文件分块续读、MCP 连接器四类 OAuth 凭据模式及 Loom/Vimeo/YouTube/Google Drive 预览；同时加固 Windows `claude://` 参数防注入并补齐 Linux 端 Artifact CDN 白名单。

---

## 近期大版本基线：5.1231.0（2026-11-10，`4.x → 5.x`）

核心亮点见 [claude/2026-11-10_5.1231.0.md](claude/2026-11-10_5.1231.0.md)，完整技术细节见 [full/claude/2026-11-10_5.1231.0.md](full/claude/2026-11-10_5.1231.0.md)。

- **内置浏览器支持安装 Chrome 扩展**：支持在内置浏览器中直接访问 Chrome 应用商店浏览、安装、管理与卸载扩展程序。
- **1Password 登录凭据自动填充**：支持在浏览器自动化操作中授权调用 1Password 完成账号自动填充。
- **交互式 3D Artifact 渲染与运行时升级**：Artifact 新增三维模型与场景渲染能力，支持加载 Cowork 插件，并完成桌面底层运行时大版本升级。
