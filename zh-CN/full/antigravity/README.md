# Antigravity 版本变更历史

[English](../../../full/antigravity/README.md) | 简体中文 · [精简版 (Highlight)](../../antigravity/README.md) | **完整详情 (Full Detail)**

覆盖 Google **Antigravity**（`https://antigravity.google`）在 `mac`、`win`、`ubuntu`、`ios`、`android` 五端的技术版本演进索引，当前共收录 **7** 个深度逆向版本，分属两条独立桌面产品线：
- **Antigravity Desktop（`antigravity-hub`）**：内置单体 Go `language_server` 的独立 Electron `44.9.1` 客户端（`2.31.2` → `2.35.2`，覆盖 `mac`、`win`、`ubuntu`，最新 2026-11-25 包 `Last-Modified`；`2.31.2`–`2.32.1` 以 `linux-x64` 为锚点，`2.32.2`/`2.35.1`/`2.35.2` 采用官方 `darwin-arm` 主分析并配合跨端同构建核对）。
- **Antigravity IDE（`Antigravity IDE`）**：基于 Code OSS `1.107.0` / Electron `39.2.3`、按需下载拉起 `~/.gemini/bin/agy --hub` 的 IDE 产品线（覆盖 `mac`、`win`、`ubuntu` 的 `2.7.0`，对比基线 `2.6.0`；发布时间未确认——`product.json` 中的北京时间 `2026-11-11 12:46` 是构建时间而非发布时间）。

## 五端覆盖概览

| 平台 | 分发渠道 / 包名 | 收录版本数 | 版本范围 | 最新版本 |
|---|---|---|---|---|
| `mac` | macOS（`Antigravity.dmg` Hub 官方 GCS 源与 `Antigravity IDE.app` `darwin-arm` 官方 edgedl 源） | 6 | `2.32.0` → `2.35.2`（Hub）/ `ide-2.7.0`（IDE） | [2.35.2](2026-11-25_2.35.2.md) / [IDE 2.7.0](2026-11-11_ide-2.7.0.md) |
| `win` | Windows（`Antigravity` Hub 安装包与 `Antigravity IDE.exe` `windows-x64` Inno Setup `6.4.0.1`） | 6 | `2.32.0` → `2.35.2`（Hub）/ `ide-2.7.0`（IDE） | [2.35.2](2026-11-25_2.35.2.md) / [IDE 2.7.0](2026-11-11_ide-2.7.0.md) |
| `ubuntu` | Ubuntu / Linux（`Antigravity.tar.gz` Hub 与 `Antigravity IDE.tar.gz` `linux-x64`） | 7 | `2.31.2` → `2.35.2`（Hub）/ `ide-2.7.0`（IDE） | [2.35.2](2026-11-25_2.35.2.md) / [IDE 2.7.0](2026-11-11_ide-2.7.0.md) |
| `ios` | 独立 Antigravity iOS 客户端 | 0 | _暂无独立移动端版本_ | — |
| `android` | 独立 Antigravity Android 客户端 | 0 | _暂无独立移动端版本_ | — |

## 桌面端版本索引（`mac` / `win` / `ubuntu`，最新 → 最早）

| 版本 | 覆盖平台 | 发布日期 | 核心变更摘要 |
|---|---|---|---|
| [2.35.2 (Hub)](2026-11-25_2.35.2.md) | `mac`、`win`、`ubuntu` | 2026-11-25（包 Last-Modified） | 相对 `2.35.1` 的纯维护版（`2.35.2-4585983447007232`；`darwin-arm` 主分析 + 五端同构建点测，首次覆盖 `darwin-x64` 与 `linux-arm`［`Antigravity-arm64/`］，Win LS PE/CL 未覆盖）：`app.asar`（`e0571155…`，五端一致）仅 `package.json` 版本号更新；Go `language_server` 同大小重编译（mac `197,343,440` B / linux-x64 `230,003,400` B，同基线 `1027784732`，`cl/1029194470 → cl/1029311855`，`strings` `+6,466/−6,307` 噪声，RPC `338`/开关 `225`/模型 `44`/ToolConfig `65`/CUA `19` 零 diff）；官方唯一修复「Switch models while a turn is running」属 Hub webapp，包内静态不可证 |
| [2.35.1 (Hub)](2026-11-25_2.35.1.md) | `mac`、`win`、`ubuntu` | 2026-11-25（包 Last-Modified） | 两段分列 `darwin-arm` 主静态 diff（`2.34.0 → 2.35.0` 与 `2.35.0 → 2.35.1`，构建号 `6394266482769920` / `4615540875067392`；`linux-x64` asar/LS CL 与 `windows-x64` 内嵌 asar 核对，Win LS PE 与 `darwin-x64` 未覆盖）：段二（`2.35.1`）仅 `app.asar`（`9f0aad72…`）version 变更 + 同基线（`1027784732`）LS 重编译（`cl/1029194470`，`+16.5` KB，五口径零 diff，官方 `2.35.1` 三条无静态落点）；段一（`2.35.0`）LS rebase（`cl/1028447422`，`+428` KB，`strings` `+30,776/−29,097`，RPC `380 → 338`，`AgentRemoteSession` CRUD、`openai/openai_go` `10,475` 符号、开关 `204 → 225`、模型 `42 → 44`），新增 `agy-desktop-rtc`/`customWindowControls.js`/`permissionGuide.js`，撤除壳层 HUD（3 文件） |
| [2.32.2 (Hub)](2026-11-17_2.32.2.md) | `mac`、`win`、`ubuntu` | 2026-11-17（包 Last-Modified） | 官方 `darwin-arm` 双 DMG 主静态 diff（构建号 `4665802025205760`，配合 `linux-x64` 同构建/LS 点测与 `windows-x64` 点测）：`app.asar`（`1,068` 文件、`18,668,119` B，SHA-256 `056ba838…`）仅 `package.json` 版本号更新为 `2.32.2`，`chrome-devtools-mcp` `1.9.0` 零差异；重编译 Go `language_server`（`cl/1021296516 → cl/1022991777`，`darwin-arm` `−32` B / 去重 `strings` `+765 / −703`）仅检出 `cel.withDefaultCELHTTPTimeout` 改名与 `Shutdown` 闭包符号变化，静态抽取的 RPC（`376`）、特性开关对（`189`）、`*ToolConfig`（`65`）与 `gemini-4-*`（`9` 档）文本清单零变化 |
| [2.32.1 (Hub)](2026-11-14_2.32.1.md) | `mac`、`win`、`ubuntu` | 2026-11-14 | Go `language_server` 同体积重编译（`239,952,296` B，`cl/1020489536 → cl/1021296516`，去重 `strings` `+1,085 / −1,115`）：默认模型目录新增 `gemini-4-hydrogen-{low,medium,high}`（`defaultmodels.Gemini4Hydrogen`、`gemini-4-hydrogenaicode_latency_ms`）；`app.asar`（`dist/` + `node_modules/`，`1,068` 文件）与 `chrome-devtools-mcp` `1.9.0` 相对 `2.32.0` 逐字节一致，RPC（`375`）、特性开关（`112`）与 `*ToolConfig`（`49`）零漂移 |
| [2.32.0 (Hub)](2026-11-13_2.32.0.md) | `mac`、`win`、`ubuntu` | 2026-11-13 | Electron `44.9.1`，Go `language_server` `206.8 → 240.0` MB（`cl/1020489536`，`.noptrdata` `+29.6` MB）：新增 `30` 文件 `dist/remote/` SSH 远程栈（`--ssh-host`、`27` 通道 IPC 白名单）、Catcher 三层访客视图、`guestCrossSiteCredentials.js` 与 `stripGuestElectronUserAgentToken`、移除 `shell-env`（依赖 `8 → 7`）、受门控 `cortex/ext/plugins/computer`（`ComputerViewerService`、`18` 动作）、`CloneGitHubRepo` RPC（`374 → 375`）、`+58` 特性开关（`54 → 112`）、`AgentRemoteSessionMessages`、`openaiResponsesConverter`，并开放 Dynamic Workflows 与 Everforest 主题（`11` 项改进、`13` 项修复） |
| [2.31.2 (Hub)](2026-11-12_2.31.2.md) | `ubuntu` | 2026-11-12 | Electron `44.5.1 → 44.9.1`，Go `language_server` `195.9 → 206.8` MB（原生工具 `~50 → ~60`）：新增 CDP `WebMCP.*` Guest WebMCP 桥（`64` KiB 上限、`PROTECTED_PAYMENT_HOSTS` 黑名单）、`0o600` `DevToolsActivePort` 权限收紧、`native_swarm` 四工具（`manage_swarm`/`post_message`/`read_board`/`swarm_wait`）、`planexecute` `enter`/`exit`、`RunPersistent` 持久终端、`notebook_execution`、`oneharness`（14 工具）、`sir_flash_lite`（`mode: LOG`）及 `StartMcpOAuthSignIn` RPC（`365 → 374`） |
| [IDE 2.7.0](2026-11-11_ide-2.7.0.md) | `mac`、`win`、`ubuntu` | 未确认 _（构建于 2026-11-11）_ | Code OSS `1.107.0`（`71bedb45`，`languageServerCL` `1018779249`）：全部实质变更集中于 `extensions/agy` `0.0.1 → 1.11.0`（`vscode/extension.js` `+90,987` B、`bridge.js` `+9,333` B）——三态登录状态栏、`authSync`、回环 `POST .../GetAuthStatus`、命令 `25 → 33`、`+35` iframe Schema（`ManageTask`、媒体、浏览器录制）、`isAntigravityIde`（`productId` `5372208`）、CDE `/usr/bin/agy` 优先路径及 `canRetryPortCollision`（`out/` 与 `jetskiAgent` 零代码差异） |
