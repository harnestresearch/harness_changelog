# Qoder 版本变更历史

[English](../../../full/qoder/README.md) | 简体中文 · [精简版 (Highlight)](../../qoder/README.md) | **完整详情 (Full Detail)**

覆盖 Qoder 自 `1.24.1`（2026-07-16）至 `0.5.20`（2026-11-25）在 `mac`、`win`、`ubuntu`、`ios`、`android` 五端共 **59** 个版本条目的完整演进索引（含 **30** 个桌面/跨端版本与 **29** 个移动端独立版本；中间桌面版本 `0.5.14` 与 `0.5.16`–`0.5.19` 尚未入仓）。

## 五端覆盖概览

| 平台 | 分发渠道 / 包名 | 收录版本数 | 版本范围 | 最新版本 |
|---|---|---|---|---|
| `mac` | macOS（`Qoder.app` 官方 CDN & Homebrew Cask） | 30 | `0.1.0` → `0.5.20` | [0.5.20](2026-11-25_0.5.20.md) |
| `win` | Windows（`Alibaba.Qoder` 官方安装包 & Winget） | 28 | `0.1.0` → `0.5.20` | [0.5.20](2026-11-25_0.5.20.md) |
| `ubuntu` | Ubuntu / Linux（`Qoder-linux-amd64.deb` 与 `.rpm` 官方源） | 28 | `0.1.0` → `0.5.20` | [0.5.20](2026-11-25_0.5.20.md) |
| `ios` | iOS App Store（`com.qoder.mobile` 国际版与 `com.qoder.app.cn` 国内版） | 27 | `1.24.1` → `1.46.0` | [1.46.0](2026-11-12_1.46.0.md) |
| `android` | Android（`com.qoder.mobile` 官方 APK CDN 与 Play） | 2 | `0.9.0` → `0.10.0` | [0.10.0](2026-11-15_0.10.0.md) |

## 桌面端版本索引（`mac` / `win` / `ubuntu`，最新 → 最早）

| 版本 | 覆盖平台 | 发布日期 | 核心变更摘要 |
|---|---|---|---|
| [0.5.20](2026-11-25_0.5.20.md) | `mac`、`win`、`ubuntu` | 2026-11-25 | 官方 `0.5.18 → 0.5.20` 三端静态差分（Electron `43.8.4`；跨过未分析的 `0.5.19`；中间 `0.5.14`/`0.5.16`–`0.5.18` 尚未入仓）：`14` 条 `cloud-session:*` IPC + 扩展 `automations.*` IPC 与 `+6` `AUTOMATION_TASK_*` 错误码（`2 → 8`）、`19` 条 `automationPeer.*` 键 + `automations.read.v1`/`manage.v1` + `file-transfer.cjs`、`chat-session-recovery:*` + `20261119-00-chat-session-restart-resumption.sql`、`auth.deviceAccountBlocked.*` + `"Enterprise VPC sign-in"`、归档按组文案与 `fontSizeExtraLarge`/`uiScaleExtraLarge`、`20261121-00`/`01` 自动化迁移与 `20261123-01-async-question-order-clock`、`qodercli` `1.1.86-hotfix.19 → 1.1.96-hotfix.8`（`−826,457` B）、Agent SDK `1.0.62-alpha.2 → alpha.9`、`qoder.knowledge.center` 拆为 `wiki`+`qmind`、`@ali/qoder-text-sdk` `0.5.2`、`@qoder-space/in-app-browser` 及未公告的 Qwen/`statusline`/图标改动 |
| [0.5.13](2026-11-16_0.5.13.md) | `mac` | 2026-11-16 | 官方 macOS `arm64` 双包静态差分（`0.5.12 → 0.5.13`，Electron `43.8.4`）：`ApplicationTransport.subscribe`（`Dta6yTTQ.js` → `BHeyMntc.js`）在保持 `64` 订阅上限下新增等待 `releaseRequested` 在途释放再复检及 30 秒 `"Application subscription limit reached"` 诊断日志、worker 解码字符串 `14,169 → 14,175`（`+6` 条 Bash 风险自评与 Auto 门控/黑名单/策略版本提示词及说明）、Agent SDK `1.0.60-alpha.50 → 1.0.60-alpha.62`、`qodercli` `1.1.86-hotfix.5 → 1.1.86-hotfix.5.2`、`qoder-office-xlsx` `xlsx-sidecar` 重编及官方其余 5 项分层对照 |
| [0.5.12](2026-11-14_0.5.12.md) | `mac` | 2026-11-14 | 官方 macOS `arm64` 双包静态差分（`0.5.11 → 0.5.12`，Electron `43.8.4`）：Agent SDK `1.0.60-alpha.36 → 1.0.60-alpha.50`、`qodercli` `1.1.86-hotfix.4 → 1.1.86-hotfix.5`、worker 解密表新增 4 条 `transcript.resume.*` 字符串、`qoder-office-xlsx` `xlsx-sidecar` 重编、渲染层零字节变化及官方其余 4 项分栏对照 |
| [0.5.7](2026-11-09_0.5.7.md) | `mac`、`win`、`ubuntu` | 2026-11-09 | `TODO`（`mac`、`win`、`ubuntu`）— _详细技术差分待补充_ |
| [0.5.6](2026-11-06_0.5.6.md) | `mac`、`win`、`ubuntu` | 2026-11-06 | `TODO`（`mac`、`win`、`ubuntu`）— _详细技术差分待补充_ |
| [0.5.5](2026-11-05_0.5.5.md) | `mac`、`win`、`ubuntu` | 2026-11-05 | `TODO`（`mac`、`win`、`ubuntu`）— _详细技术差分待补充_ |
| [0.5.3](2026-11-02_0.5.3.md) | `mac`、`win`、`ubuntu` | 2026-11-02 | `Qoder.app` `0.5.3`（`@qoder-ai/qoder-agent-sdk@1.0.59-alpha.9` / `qodercli` `1.1.79-hotfix.11`，协议 `1.5.0`，MCP SDK `2.0.0`+`1.30.0`）：35+ 核心内置工具 + 4 路 MCP 体系（`qoder-context` 语义索引、`repowiki` 14 + `qoder-qmind` 15 知识工具、`qoder.phone-use` 50 个真机操控工具、`qoder_sites` 33 个全栈建站工具及 `event-stream` 原生录制桥） |
| [0.5.2](2026-11-02_0.5.2.md) | `mac`、`win`、`ubuntu` | 2026-11-02 | `TODO`（`mac`、`win`、`ubuntu`）— _详细技术差分待补充_ |
| [0.5.1](2026-10-30_0.5.1.md) | `mac`、`win`、`ubuntu` | 2026-10-30 | `TODO`（`mac`、`win`、`ubuntu`）— _详细技术差分待补充_ |
| [0.4.11](2026-10-23_0.4.11.md) | `mac`、`win`、`ubuntu` | 2026-10-23 | `TODO`（`mac`、`win`、`ubuntu`）— _详细技术差分待补充_ |
| [0.4.9](2026-10-22_0.4.9.md) | `mac`、`win`、`ubuntu` | 2026-10-22 | `TODO`（`mac`、`win`、`ubuntu`）— _详细技术差分待补充_ |
| [0.4.8](2026-10-14_0.4.8.md) | `mac`、`win`、`ubuntu` | 2026-10-14 | `TODO`（`mac`、`win`、`ubuntu`）— _详细技术差分待补充_ |
| [0.4.7](2026-10-14_0.4.7.md) | `mac`、`win`、`ubuntu` | 2026-10-14 | `TODO`（`mac`、`win`、`ubuntu`）— _详细技术差分待补充_ |
| [0.4.4](2026-10-10_0.4.4.md) | `mac`、`win`、`ubuntu` | 2026-10-10 | `TODO`（`mac`、`win`、`ubuntu`）— _详细技术差分待补充_ |
| [0.4.3](2026-09-24_0.4.3.md) | `mac`、`win`、`ubuntu` | 2026-09-24 | `TODO`（`mac`、`win`、`ubuntu`）— _详细技术差分待补充_ |
| [0.4.2](2026-09-24_0.4.2.md) | `mac`、`win`、`ubuntu` | 2026-09-24 | `TODO`（`mac`、`win`、`ubuntu`）— _详细技术差分待补充_ |
| [0.4.1](2026-09-23_0.4.1.md) | `mac`、`win`、`ubuntu` | 2026-09-23 | `TODO`（`mac`、`win`、`ubuntu`）— _详细技术差分待补充_ |
| [0.3.4](2026-09-18_0.3.4.md) | `mac`、`win`、`ubuntu` | 2026-09-18 | `TODO`（`mac`、`win`、`ubuntu`）— _详细技术差分待补充_ |
| [0.3.3](2026-09-18_0.3.3.md) | `mac`、`win`、`ubuntu` | 2026-09-18 | `TODO`（`mac`、`win`、`ubuntu`）— _详细技术差分待补充_ |
| [0.2.5](2026-09-12_0.2.5.md) | `mac`、`win`、`ubuntu` | 2026-09-12 | `TODO`（`mac`、`win`、`ubuntu`）— _详细技术差分待补充_ |
| [0.2.3](2026-09-10_0.2.3.md) | `mac`、`win`、`ubuntu` | 2026-09-10 | `TODO`（`mac`、`win`、`ubuntu`）— _详细技术差分待补充_ |
| [0.2.2](2026-09-09_0.2.2.md) | `mac`、`win`、`ubuntu` | 2026-09-09 | `TODO`（`mac`、`win`、`ubuntu`）— _详细技术差分待补充_ |
| [0.2.1](2026-09-08_0.2.1.md) | `mac`、`win`、`ubuntu` | 2026-09-08 | `TODO`（`mac`、`win`、`ubuntu`）— _详细技术差分待补充_ |
| [0.1.8](2026-09-05_0.1.8.md) | `mac`、`win`、`ubuntu` | 2026-09-05 | `TODO`（`mac`、`win`、`ubuntu`）— _详细技术差分待补充_ |
| [0.1.6](2026-09-03_0.1.6.md) | `mac`、`win`、`ubuntu` | 2026-09-03 | `TODO`（`mac`、`win`、`ubuntu`）— _详细技术差分待补充_ |
| [0.1.4](2026-09-01_0.1.4.md) | `mac`、`win`、`ubuntu` | 2026-09-01 | `TODO`（`mac`、`win`、`ubuntu`）— _详细技术差分待补充_ |
| [0.1.3](2026-08-31_0.1.3.md) | `mac`、`win`、`ubuntu` | 2026-08-31 | `TODO`（`mac`、`win`、`ubuntu`）— _详细技术差分待补充_ |
| [0.1.2](2026-08-28_0.1.2.md) | `mac`、`win`、`ubuntu` | 2026-08-28 | `TODO`（`mac`、`win`、`ubuntu`）— _详细技术差分待补充_ |
| [0.1.1](2026-08-27_0.1.1.md) | `mac`、`win`、`ubuntu` | 2026-08-27 | `TODO`（`mac`、`win`、`ubuntu`）— _详细技术差分待补充_ |
| [0.1.0](2026-08-27_0.1.0.md) | `mac`、`win`、`ubuntu` | 2026-08-27 | `TODO`（`mac`、`win`、`ubuntu`）— _详细技术差分待补充_ |

## 移动端版本索引（`ios` / `android`，最新 → 最早）

| 版本 | 覆盖平台 | 发布日期 | 核心变更摘要 |
|---|---|---|---|
| [0.10.0](2026-11-15_0.10.0.md) | `android` | 2026-11-15 | 跨渠道静态差分（`0.9.0`（`versionCode` `67` APKPure Play XAPK）→ `0.10.0`（`versionCode` `70` 官方单 APK））：扩充 +11 组 `features/credits` 活动/奖励模型与 `assets/qoder_web_fetch.js`、`ModelManagementValue` + 23 条 `composer.model_management.*` 词条（含预览/模拟文案）、首页/抽屉/远程控制词条（`+79 / -3`）及 `OtlpTelemetryClient.exportTechnicalBatch` / `TechnicalSnapshot` / `recordScrollWindow` |
| [1.46.0](2026-11-12_1.46.0.md) | `ios` | 2026-11-12 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.45.1](2026-11-11_1.45.1.md) | `ios` | 2026-11-11 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.45.0](2026-11-09_1.45.0.md) | `ios` | 2026-11-09 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [0.9.0](2026-11-08_0.9.0.md) | `android` | 2026-11-08 | `TODO`（`android`）— _详细技术差分待补充_ |
| [1.44.0](2026-11-03_1.44.0.md) | `ios` | 2026-11-03 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.43.1](2026-10-31_1.43.1.md) | `ios` | 2026-10-31 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.43.0](2026-10-29_1.43.0.md) | `ios` | 2026-10-29 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.42.1](2026-10-24_1.42.1.md) | `ios` | 2026-10-24 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.42.0](2026-10-21_1.42.0.md) | `ios` | 2026-10-21 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.41.0](2026-10-15_1.41.0.md) | `ios` | 2026-10-15 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.40.0](2026-09-30_1.40.0.md) | `ios` | 2026-09-30 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.39.0](2026-09-27_1.39.0.md) | `ios` | 2026-09-27 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.38.0](2026-09-20_1.38.0.md) | `ios` | 2026-09-20 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.37.0](2026-09-18_1.37.0.md) | `ios` | 2026-09-18 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.36.0](2026-09-10_1.36.0.md) | `ios` | 2026-09-10 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.35.0](2026-09-08_1.35.0.md) | `ios` | 2026-09-08 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.34.0](2026-09-05_1.34.0.md) | `ios` | 2026-09-05 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.33.0](2026-08-29_1.33.0.md) | `ios` | 2026-08-29 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.32.0](2026-08-25_1.32.0.md) | `ios` | 2026-08-25 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.31.0](2026-08-22_1.31.0.md) | `ios` | 2026-08-22 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.30.0](2026-08-17_1.30.0.md) | `ios` | 2026-08-17 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.29.0](2026-08-09_1.29.0.md) | `ios` | 2026-08-09 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.28.0](2026-08-05_1.28.0.md) | `ios` | 2026-08-05 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.27.0](2026-08-03_1.27.0.md) | `ios` | 2026-08-03 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.26.0](2026-07-31_1.26.0.md) | `ios` | 2026-07-31 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.25.2](2026-07-25_1.25.2.md) | `ios` | 2026-07-25 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.25.1](2026-07-24_1.25.1.md) | `ios` | 2026-07-24 | `TODO`（`ios`）— _详细技术差分待补充_ |
| [1.24.1](2026-07-16_1.24.1.md) | `ios` | 2026-07-16 | `TODO`（`ios`）— _详细技术差分待补充_ |
