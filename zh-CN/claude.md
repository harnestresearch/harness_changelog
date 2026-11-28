# Claude 最新版本改动

[English](../claude.md) | 简体中文 · **精简版 (Highlight)** | [完整详情 (Full Detail)](full/claude.md)

> 五端（`mac`、`win`、`ubuntu`、`ios`、`android`）完整 535 个历史版本索引（桌面端 245 个 + 移动端 290 个）见 [claude/README.md](claude/README.md)。

## 最新 Android 版本：1.261125.19（Android，2026-11-27 Uptodown 镜像窗口）

核心亮点见 [claude/2026-11-27_1.261125.19.md](claude/2026-11-27_1.261125.19.md)，完整技术细节见 [full/claude/2026-11-27_1.261125.19.md](full/claude/2026-11-27_1.261125.19.md)。_（发布窗口 `2026-11-26/27`：Uptodown 标注 `"Nov 27, 2026"` + `"Matches the published version"`；Google Play 美区可见 `"Updated on Nov 26, 2026"`［无版本号］，源码将 `1.261125.19` 与 unix `1795755160`［美西 `2026-11-26 20:52:40` / 北京 `2026-11-27 12:52:40`］同簇。基于已归档 **Uptodown 第三方镜像** Play 原签分包 XAPK `1.261124.19 → 1.261125.19`［样本 `801b77ee…`］静态对比；当前 Uptodown 源页已轮换为另一份 `44.03 MB` / `39662257…` 容器且未分析。未做 `apksigner` 全量校验，不涵盖 iOS，未运行 APK，静态在场不代表已放量。）_

- **Usage Credits 自动续费与 IAP 身份核验指引**：新增用量额度开启与自动扣款文案（`"Turn on usage credits?"`、`"Auto-reload will charge your card when your credits run low."`）及 `claudeai.usage_credits.code_limit_offer.step`；新增政府照片证件采集前置指引（`"Before you start"`、`"An unexpired government photo ID"`、可选自拍）、Google Play 环境检查提示、`claudeai.iap.identity_check.*` 遥测与 `PurchaseCancellation`（仅静态在场）。
- **Reflect（`cardinal`）增强与 GitHub 代建仓库**：在 `1.261124.19` 既有 Reflect 基础上新增后台撰写通知、记忆前提提示、`"Delete all reflections?"` 与 `claudeai.cardinal.{notify.{offered,answered},recap.read,wait.left}`；新增 `"Create on GitHub"` / `"New repository"` / `"Approve on GitHub"`、`claudeai.code.repository_picker.new_repository.{shown,opened,finished}` 及重名/SSO/权限/结果不确定态错误分类。
- **短视频限制、旧反馈下线与打包变化**：新增 1 分钟以内视频限制提示与 `"Pause/Play %1$s preview"` 控件文案，移除 `"Conversation outline (Ant only)"` 与旧反馈表单分类文案；已归档 XAPK 维持 `30` 成员，`config.x86_64.apk`（`10` 个 `.so`）自 `1.261113` 时代移除后回归，语言分包 `21 → 20`（`+gu`、`+hi`，`−da`、`−nb`、`−te`），`arm64-v8a`/`armeabi-v7a` 共 `20` 个原生库在 `1.261123.19`–`1.261125.19` 三版未重建，总 DEX 仅增 `+286,852` B（约 `+0.29` MB），`minSdk`/`targetSdk` `32`/`37`、`66` 项 `uses-permission` 权限与 `83` 个组件不变。

---

## 最新桌面版本：5.11492.5（2026-11-14）

核心亮点见 [claude/2026-11-14_5.11492.5.md](claude/2026-11-14_5.11492.5.md)，完整技术细节见 [full/claude/2026-11-14_5.11492.5.md](full/claude/2026-11-14_5.11492.5.md)。

- **企业受管文件读取策略与自动模式说明完善**：新增企业受管配置键 `blockFileToolReadsOutsideWorkingDirectories` 以管控 auto-mode 下工作目录外文件读取授权提示，并在管理设置文档中补充整机级 `env.CLAUDE_CODE_AUTO_MODE_MODEL` 覆盖自动模式审阅模型的说明。
- **内置 Office 文档技能安全加固与大文档比对防耗尽**：加固内置 `docx`、`pptx`、`xlsx` 技能校验器以拦截 Windows 盘符/根路径穿越及越界 OOXML 关系引用，并将修订比对（redlining）改为带工作量上限的序列比对算法以防超大文档耗尽资源。
- **内嵌引擎会话存储键校验层与多语种翻译补齐**：在内嵌 Claude Code 引擎中建立覆盖会话记录、任务、草稿、`jobs-root` 及三层设置的存储键校验体系与 `setSessionArchived` 归档支持，轮换全端 Cowork 沙箱镜像，并为 10 个非英语语种补齐约 48 条扩展与订阅确认文案（桌面英文界面较 `5.11492.2` 无新增变化）。

---

## 上一 Android 版本：1.261124.19（Android，2026-11-25 Uptodown 镜像窗口）

核心亮点见 [claude/2026-11-25_1.261124.19.md](claude/2026-11-25_1.261124.19.md)，完整技术细节见 [full/claude/2026-11-25_1.261124.19.md](full/claude/2026-11-25_1.261124.19.md)。_（发布窗口约 `2026-11-25/26`，不精确：Uptodown 标注 `Nov 25, 2026` 且附 `"Matches the published version"`，而 `2026-11-26` Play 美区快照仍停留 `"Updated on: Nov 24, 2026"` 且无版本号。基于 **Uptodown 第三方镜像** Play 原签分包 XAPK `1.261123.19 → 1.261124.19` 静态对比，非直接来自 Play 官方下载；未做 `apksigner` 全量校验，不涵盖 iOS 与 `1.261120.19`–`1.261122.*` 缺口，未运行 APK，静态在场不代表已放量。）_

- **GitHub 深度集成与 PR / Plan / 工具调用审批流**：新增 `claudeai.code.connect_github_card.*` 遥测、Claude GitHub App 安装引导、PR/plan/工具调用审批失败分类、组织连接器审批提示、`CollapsedToolsSheetDestination${HostPage,ProductPage,Viewer}` 及云环境配置引导。
- **Safeguards 换模型文案与 Places 面板**：移动端新增约 12 条面向 biology/cybersecurity/sensitive topics 的 safeguards 自动换模型文案、新增 `claudeai.places_list.*` Places 面板与 `voice.reachability_checked`，并新增 usage 分区、`Default tab` 设置、明示排除 PHI 的项目指令编辑、共享会话链接提示、朗读限额及约 20 条登录/维护/限额错误文案，同时收缩/移除 `continue_on_cloud.*`（`8 → 1`）、`ready_made_card.rated` 与 `money.message_box.*`。
- **分包与不变量**：XAPK 总条目 `37 → 30`（语言分包 `28 → 21`：`+te`、`−am/fil/hi/ml/mr/sw/ta/tl`），全部 `20` 个原生 `.so` 库逐字节一致，`minSdk`/`targetSdk` `32`/`37`、`66` 项权限与 `83` 个组件不变，**网络 API 端点零增删**。

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
