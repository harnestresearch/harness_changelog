# DSH (DeepSeek Harness) 最新版本改动

[English](../../full/dsh.md) | 简体中文 · [精简版 (Highlight)](../dsh.md) | **完整详情 (Full Detail)**

> 五端（`mac`、`win`、`ubuntu`、`ios`、`android`）技术版本索引（当前收录预发布版 `0.2.3-alpha.2`）见 [dsh/README.md](dsh/README.md)。

## 0.2.3-alpha.2 — 预发布版 Prerelease（2026-11-22）

详细改动见 [dsh/2026-11-22_0.2.3-alpha.2.md](dsh/2026-11-22_0.2.3-alpha.2.md)。

### 版本概览

`dsh-v0.2.3-alpha.2`（官方 GitHub Release `published_at` `2026-11-22 19:00:39 UTC+8` / `2026-11-22T11:00:39Z` UTC；早先 git 合并提交 `4b399c39a6d` 于 `2026-11-22 16:50:28 +0800`）是承接 `dsh-v0.2.3-alpha.1`（`d98f5d68519`，官方发布于 `2026-11-22 11:19:36 UTC+8`）的运行时下限与依赖安全对齐 **Alpha 预发布版**，涵盖 `5` 个提交（主线 `3` 个 first-parent 合并：PR #8837、PR #8960、PR #8961）与 `488` 个改动文件（新增 `3`、修改 `485`；`+806 / -707` 行；含 `413` 个 `package.json` 与 `75` 个非清单文件；严格基于只读 git 标签对象与官方 Release 元数据核验，未执行动态运行）。

### Node.js 下限 `^24.22.3 || >=26.13.1`、检查位置与内置运行时对齐

- **精确 semver 范围与检查位置（`package.json:9`、`apps/cli/package.json:191`，PR #8837）**：将 `>=24.9.0` 替换为 `^24.22.3 || >=26.13.1`（等价 `>=24.22.3 <25.0.0-0 || >=26.13.1`）——允许 `24.x` 中 `>=24.22.3`（非严格相等）及 `>=26.13.1`（semver 语义包含 `27.x+`，但 CI 仅覆盖 `24.22.3`、最新 `24` 与浮动 `26`），排除 `<24.22.3`、全部 `25.x` 及 `26.0.0`–`26.13.0`。仓库无 `.npmrc` / `engineStrict`，CLI 启动链路（`apps/cli/src/{bin,installed-bin,profile-boot}.ts`）无运行时 `process.versions.node` 拦截，Python 开发载体（`python/sdk-runtime/src/deepseek_harness_runtime/__init__.py:14,147-152`）亦只改缺 `node` 提示而不查版本；严格 `=== '24.22.3'` 仅作用于 `scripts/run-gates.ts:113,496-501`（设 `DSH_NODE_COMPAT_BUILD=1` 时）、`scripts/primary-runtime/lock.json:2` + `prepare.ts:278` 与 `scripts/build-exe-for-python-sdk.ts:33-35,112-114,127-129,412-417`（`pkg --sea --targets node24.22.3-...`；`scripts/build-exe-for-ssh-helper.ts` 仍用浮动 `node24`）。
- **安全依赖、Electron `^44.11.5`、Vendor 版本号与升级指南（PR #8837、PR #8960、PR #8961）**：在 `pnpm-workspace.yaml:19-23` 新增 `undici` `overrides`（`6.29.1` / `7.30.2` / `8.12.4`）并将 4 个直接依赖升至 `8.12.4`；桌面端 Electron 由 `^44.7.0` 升至 `^44.11.5`（`apps/desktop/package.json:76`、`verified-versions.json:3,8`），`node-addon-require-builtin` 由 `^0.1.9` 升至 `^0.1.10`（4 个清单及 `minimumReleaseAgeExclude`）；更新 `27` 个 `.github/workflows/*.yml`、`scripts/wine-windows-gates.sh` 及 3 个仅改注释的 TS 文件（`packages/boot/{app-boot,hmr}`、`packages/ptc-runtime/ptc-runtime-node`）；新增 `docs/upgrade-guide/v0.2.3-alpha.1/node-24-22-3/guide.{md,zh.md,i18n.yaml}`；PR #8960 将 `9` 个 `vendor/*` 包升至 `*-alpha.1`，PR #8961 将 `404` 个工作区清单升至 `0.2.3-alpha.2`。相较 `alpha.1` 零产品、UI、CLI、协议或插件业务逻辑改动。

---

## 前序预发布版：0.2.3-alpha.1（2026-11-22）

详细改动见 [dsh/2026-11-22_0.2.3-alpha.1.md](dsh/2026-11-22_0.2.3-alpha.1.md)。

### 版本概览

`dsh-v0.2.3-alpha.1`（官方 GitHub Release `published_at` `2026-11-22 11:19:36 UTC+8` / `2026-11-22T03:19:36Z` UTC；早先 git 合并提交 `d98f5d68519` 于 `2026-11-22 00:45:52 +0800`；对应 `alpha.1`，不含后续 npm `alpha.2`）是承接祖先标签 `dsh-v0.2.2-rc.5`（`9c2670d3bce`，官方发布于 `2026-11-18 20:51:39 UTC+8`）的首个 `0.2.3` **Alpha 预发布版**，涵盖 `2,343` 个提交（主线 `240` 个 first-parent 合并）与 `7,260` 个改动文件（`+302,202 / -83,093` 行；新增 `25` 个生产包及 `apps/desktop-publisher`，移除 `2` 个包，新增 `55` 条并更新 `2` 条 `docs/upgrade-guide`；严格基于只读 git 标签对象与官方 Release 元数据核验，未执行动态运行）。

### 连接器生态、远程鉴权、会话界面、实验组合包与安全迁移

- **连接器账号、MCP OAuth、按需加载与 7 个独立连接器**：在 `dsh-base`/`dsh-web-app` 默认挂载 `@deepseek-ai/dsh-client-ui-connector-account`、`@deepseek-ai/dsh-mcp-account`、`@deepseek-ai/dsh-cli-account` 与 `@deepseek-ai/dsh-upstream-skills`，新增显式 MCP OAuth 授权/后台刷新与可选 `toolLoading: 'on-demand'`（经 `mcp__<server>__load_tools` 加载；普通服务默认仍为 `'eager'`）；新增 7 个未入 `OPTIONAL_BUNDLES` 的独立可选连接器：MCP OAuth 类 `@deepseek-ai/dsh-{linear,notion,tencent-docs}`（默认 `'on-demand'`）及 CLI 封装类 `@deepseek-ai/dsh-{feishu,wecom,tencent-meeting,dingtalk}`（**飞书**与**企业微信**仅支持 macOS 与 Windows `x64`，`@larksuite/cli` 安装脚本需 pnpm 审批）。
- **Web 远程登录、可插拔鉴权与会话状态组件**：`dsh-web-app` 默认启用 `@deepseek-ai/dsh-client-remote-connection`（一次性二维码、私有登录链接与审批配对；桌面端窗口隐藏）、拆分后的 `@deepseek-ai/dsh-host-authentication-{token,desktop}`（桌面端私有 IPC Cookie、单主机 17 端口 Cookie 上限防 HTTP 431）、默认 `auth: 'required'` 的 `webServer` 路由、可停靠拖拽的 `@deepseek-ai/dsh-client-ui-session-panel` 与独立 `@deepseek-ai/dsh-client-ui-session-status`（Host 共享已读/未读 + `completionFailed`，插件须声明 `inject: ['uiSession.sessionStatus']`）。
- **可选实验组合包（均默认关闭）**：`@deepseek-ai/dsh-experimental-plugin-market-bundle` 新增 Git 仓库插件索引（裸部分克隆复用宿主 Git/SSH 凭据）；新增 `@deepseek-ai/dsh-timeline`（任务树、阻塞项、可点击进度条、`/timeline`、`.timeline.json`、独立模型计费定时报告、「跟随对话」语言）；`@deepseek-ai/dsh-experimental-forge-bundle` 新增 **代码审阅页面**（目前仅 `forge-github` 经本机 `gh` 实现全局列表）、扩展 API（自定义视图、行注解、槽位、`forge/review-changed`）及 `@deepseek-ai/dsh-forge-gitlab`（经本机 `glab` 支持会话关联 GitLab MR，不含全局审阅列表）；`@deepseek-ai/dsh-cua-bundle` 扩至 `["darwin", "win32"]`，新增 `@deepseek-ai/dsh-cua-windows`（暂无 `systemInput`）、更名 `@deepseek-ai/dsh-cua-macos`（`useSystemInput`）、新增隐藏可选 `@deepseek-ai/dsh-cua-mcp`，并在启用 CUA 提供方后为标准模式/SDK/headless 默认提供 `cua_run_code`。
- **安全、运行时与契约迁移（新增 `55` 条、更新 `2` 条升级指南）**：移除 `working_directory` 与子代理 `cwd`，`workspace-write` 随会话实时 `cwd` 移动（工作树 `.git` 写操作需额外审批或 `additionalWritableRoots`，Windows 忽略该项），工作树改用 `enter_worktree`/`exit_worktree`，归档清理工作树在沙箱外执行；新增 `ctx.deepseekAuth`（API 密钥提供方更名 **DeepSeek API**，并完整保留 `rc.5` 路由自动搜索与计费边界——免按次调用费但每次搜索仍额外消耗 `deepseek-v4-flash` 模型 token）；Cordis Core 升至 `4.0.0-rc.12`、Loader `1.0.0-rc.9`、Include `1.2.0`（YAML 1.2 与严格校验），新增 `dsh-client-config`、HMR `--patch` 热重载与标准模式默认 `cordis_inspect`；Node PTC 默认切为 `persistent-in-memory` 作用域 REPL 并彻底移除 `@deepseek-ai/dsh-experimental-ptc-runtime-python`；退役 `@deepseek-ai/dsh-personalized-recommendations` 并由 `dsh-web-app`/`dsh-sdk-app` 默认挂载；合并 `/office` 并内置 `pypdf`；恢复持久终端入口（默认关闭）；新增需手动配置的实验性 `@deepseek-ai/dsh-session-persistence-sqlite`（默认仍为 JSONL）。

---

## 前序预发布版：0.2.2-rc.5（2026-11-18）

详细改动见 [dsh/2026-11-18_0.2.2-rc.5.md](dsh/2026-11-18_0.2.2-rc.5.md)。

### 版本概览

`dsh-v0.2.2-rc.5`（官方 GitHub Release `published_at` `2026-11-18 20:51:39 UTC+8` / `2026-11-18T12:51:39Z` UTC；早先 git 合并提交 `9c2670d3bce` 于 `2026-11-18 17:45:47 +0800`）是承接 `dsh-v0.2.2-rc.4`（`3f321d32bfe`，官方发布于 `2026-11-18 01:53:41 UTC+8`）的 **预发布候选版本（Prerelease）**，共 `5` 个提交、改动 `433` 个文件（`+917 / -594` 行：含 PR #8707 的 `53` 个非清单源码/文档/升级指南/测试/快照文件 `+537 / -214` 行、`380` 个仅升级版本号的工作区 `package.json`，以及相对 `rc.4` 净 diff 为 `0` 的重复时钟单测分支合并 PR #8595；严格基于只读 git 标签对象与官方 Release 元数据核验，未做运行时或真实账单验证）。

### 按路由自动分流搜索提供方、内联摘要提取与迁移边界

- **按模型路由 ID 自动选择搜索提供方与上下文透传（`dsh-base`、`dsh-web`、`dsh-tool-web`，PR #8707；官方说明：「DeepSeek 模型使用 DeepSeek 服务端搜索，搜索不按次收费；其他模型默认使用 DeepSeek Search API」）**：
  - 从 `packages/bundle/base/cordis.patch.yml` 移除 `searchProvider: deepseek-search-api`（`fetchProvider: http` 不变），并为 `WebSearchRequest`（`packages/web/web/src/types.ts`）新增可选 `llmProvider?: string`。未显式配置时，`WebRuntime.selectSearchProvider(llmProvider)`（`packages/web/web/src/index.ts`）仅在 `llmProvider` 命中 `DEEPSEEK_MODEL_ROUTES`（`'deepseek-official'`、`'deepseek-account'`）时优先选用 `'deepseek-official'`，其余所有路由（含经 `llm-pi-ai` 自定义路由接入的 DeepSeek 模型）及无模型请求上下文调用均优先选用 `'deepseek-search-api'`，并保持 `searchReady(modelSelection.provider)` 与 `applyWebSearchTool`（`session.requestContext()?.provider`）严格一致。
  - **回退与计费边界**：显式配置 `web.searchProvider` / `$DSH_WEB_SEARCH_PROVIDER` 对所有路由强制生效且零回退；未配置 `Automatic` 时仅在偏好 ID 未注册或本地 `available() === false` 且剩余可用项恰好为 `1` 个时顺延选用（多于 `1` 个抛 `WEB_PROVIDER_AMBIGUOUS`、`0` 个抛 `WEB_PROVIDER_UNAVAILABLE`），执行期遇到 HTTP/鉴权错误**绝不回退**。官方声明仅免除 `deepseek-official` 按次调用费，**不可泛化为搜索免费**（每次查询仍发起按模型 token 计费的 `deepseek-v4-flash` 辅助 Messages 请求，`deepseek-search-api` 仍按次计费；源码不证明远端真实账单）。
- **设置页「自动选择」、8 语种更名与内联 `snippet` 提取（`ui-settings-web-search`、`web-search-deepseek`，PR #8707）**：
  - `WebSearchCard.tsx` 与 `locales.ts` 将搜索下拉框默认项切为 **自动选择**（展示 `searchAutoHint` 与指南链接，隐藏提供方面板），并将全 8 语种 `providerLegacy` 由 `DeepSeek (legacy)` / `DeepSeek（旧版）` 更名为 `DeepSeek server-side search` / `DeepSeek 服务端搜索`；`mapAnthropicResponse()`（`packages/web/web-search-deepseek/src/provider.ts`）优先提取非空 `WebSearchResultItem.snippet`，缺失时回退文本块 `citations[].cited_text`。
- **破坏性变化（`1` 条 `docs/upgrade-guide` 记录）**：`docs/upgrade-guide/v0.2.2-rc.4/web-search-deepseek-model-default/guide.{md,zh.md}` 说明未配置搜索的 DeepSeek 路由会话切换至 `/anthropic/v1/messages`（追加 `web/deepseek-search-llm-request` 事件），且因 `web-search-deepseek` 的端点（`web-search-deepseek.baseURL` → `$DEEPSEEK_SEARCH_BASE_URL` → `https://api.deepseek.com/anthropic/v1`）不跟随聊天路由 `baseURL`，指向自定义网关的部署需同步设置 `web-search-deepseek.baseURL` / `$DEEPSEEK_SEARCH_BASE_URL` 或固定 `searchProvider: deepseek-search-api`，否则搜索将失败。

---

## 前序预发布版：0.2.2-rc.4（2026-11-18，UTC+8）

详细改动见 [dsh/2026-11-18_0.2.2-rc.4.md](dsh/2026-11-18_0.2.2-rc.4.md)。

### 版本概览

`dsh-v0.2.2-rc.4`（官方 GitHub Release `published_at` `2026-11-18 01:53:41 UTC+8` / `2026-11-17T17:53:41Z` UTC；早先 git 合并提交 `3f321d32bfe` 于 `2026-11-17 21:30:09 +0800`）是承接 `dsh-v0.2.2-rc.3`（`38a6a5c965a`，官方发布于 `2026-11-13 15:56:55 UTC+8`）的定向修复 **预发布候选版本（Prerelease）**，共 `8` 个提交、改动 `395` 个文件（`+579 / -429` 行：含 `15` 个非清单源码/文档/测试/快照文件 `+199 / -49` 行与 `380` 个仅升级版本号的工作区 `package.json`；严格基于只读 git 标签对象与官方 Release 元数据核验，未执行动态运行）。

### 流式拒答错误码分类、桌面端 LiveShare 工作进程修复与契约变更

- **DeepSeek SSE `stop_reason: "refusal"` → `CONTENT_REFUSED`（`@deepseek-ai/dsh-llm` 与 `@deepseek-ai/dsh-llm-deepseek`，PR #8584；官方说明：「优化模型请求收到异常消息响应时的表现」）**：
  - 在 `LLM_FAILURE_CODES`（`packages/llm/llm/src/error.ts`）新增不含 `retryChoice: true` 的 `CONTENT_REFUSED: {}`，并在 `translate()`（`packages/llm/llm-deepseek/src/translate.ts`）中捕获 `delta.stop_reason === 'refusal'` 及 `stop_details.explanation`，待 `message_stop` 先 yield 汇总后的计费 `{ type: 'usage', usage }` 再抛 `LlmError(..., 'CONTENT_REFUSED')`，取代原先在 `message_delta` 直接抛 `MALFORMED_RESPONSE` 并丢弃用量的行为。请求序列化层净 diff 为 `0`（不发送 `safety_check` 字段），Web 撤回流式草稿，Session 将其保留于模型历史之外的 `assistant/attempt`（`snapshots/session/deepseek-content-refusal/`）。
- **桌面端 LiveShare `ELECTRON_RUN_AS_NODE` 透传与时钟单测修复（`@deepseek-ai/dsh-experimental-liveshare`，PR #8634 & PR #8638；官方说明：「修复 LiveShare 在桌面端无法创建分享的问题」）**：
  - `TunnelWorker.start()`（`packages/experimental/liveshare/src/host/tunnel-worker.ts`）通过新增 `workerNodeModeEnv(process.env)` 在启动 `process.execPath`（`owner-gateway/cli.js`）时转发 `ELECTRON_RUN_AS_NODE`，消除 Electron 桌面端（`mac` / `win`）子进程作为第二个 GUI 实例被 `acquireDesktopSingleInstance()` 以退出码 `0` 终止的问题，且不影响纯 Node 宿主；`owner-credential-horizon.host.spec.ts` 将已过期的硬编码 `2026-11-14` 时间界限改为基于 `Date.now()` 的相对偏移。
- **破坏性变化（`1` 条 `docs/upgrade-guide` 记录）**：`docs/upgrade-guide/v0.2.2-rc.3/deepseek-refusal-code/guide.{md,zh.md}` 声明 DeepSeek 流式 `stop_reason: "refusal"` 在 LLM 错误终止块与失败 `turn/end` 中的错误码由 `MALFORMED_RESPONSE` 改为 `CONTENT_REFUSED`（无 Session v4 JSONL、`cordis.yml` 或 CLI 破坏性变更）。

---

## 前序预发布版：0.2.2-rc.3（2026-11-13）

详细改动见 [dsh/2026-11-13_0.2.2-rc.3.md](dsh/2026-11-13_0.2.2-rc.3.md)。

### 版本概览

`dsh-v0.2.2-rc.3`（`2026-11-13 13:26:07 +0800`，提交 `38a6a5c965a`）是承接 `dsh-v0.2.2-rc.2`（`2026-11-11 10:32:18 +0800`，提交 `ddac96760b6`）的 **预发布候选版本（Prerelease）**，共 `6` 个提交、改动 `515` 个文件（`+10,988 / -669` 行；含 `135` 个源码/测试/文档/CI 文件与 `380` 个工作区清单）。

### 实验性官网对话导入包与客户端 UI 扩展接缝

- **`@deepseek-ai/dsh-deepseek-chat-import`（`packages/experimental/deepseek-chat-import`，PR #8342）**：
  - 作为默认关闭的可选实验性 bundle（注册于 `OPTIONAL_BUNDLES`、`MORE_BUNDLES`、`EXPERIMENTAL_BUNDLES`，含 `cordis.patch.yml`、`ctx.deepseekChatImport` / `@Remote limits()` 及 8 语种元数据）提供仅限 owner 的上传路由 `POST /api/deepseek-chat-import/archive?workspaceId=…`，支持 `XMLHttpRequest` 上传进度与无 HTTP 服务环境下的 `__DSH_TRANSPORT__.fetch` 传输回退，并以 `application/x-ndjson` 流式推送进度与结果。
  - 基于 `fflate` 在内存中校验并解析 `deepseek_data-*.zip`（`export_format_version: 3`，面向 `2026-11-12` 导出结构；默认上限 `maxSessions = 1000`、`maxUploadBytes = 512 MiB`、`maxEntryBytes = 256 MiB`、`maxTitleBytes = 80`），拦截重复中央目录名与 `ZIP_STORED` 大小失配；通过两遍流式流程完成图片附件预存、按 `current_message_id` 选择分支、首轮注入受保护空 `system/message` 表面头节点 `0`（避免恢复会话触发 `SessionPersistenceCorruptionError`）、`stage_id` 步骤切分、`web_search` / `web_fetch` / Markdown `READ_LINK` / 合成文件卡片映射，并剔除 `CONTENT_FILTER` 撤回轮次。
- **客户端 UI 槽位与图标（`ui-sidebar`、`ui-workspace`、`ui-directory-picker-*`、`ui-primitives`）**：
  - 新增包裹 `.newSessionRow` 的 root 作用域 HOC 槽位 `sidebar.session.action`，发布声明 `workspace.picker.directoryFlow` 子槽的 `workspace.picker` 组件工厂（`-browse` 与 `-native` 目录选择器同步完成三槽位事务注入），并导出 `IconUploadOutlineRegular` / `IconUploadOutlineMedium`。

### 桌面端安装器、会话导出与 CI 修复（无破坏性变化）

- **Windows 重启状态窗工作目录修复（`apps/desktop/installer/restart-status.h`，PR #8385）**：NSIS 更新重启提示窗 `rundll32.exe` 改为以 `GetSystemDirectoryW` 作为 `lpCurrentDirectory` 启动，防止更新替换期间锁定应用安装目录。
- **会话日志 ZIP 导出容错（`@deepseek-ai/dsh-session-log-export`，PR #8342）**：新增 `headOf()` 预读文件首块，将 `ATTACHMENT_NOT_FOUND` 与 `INVALID_ATTACHMENT_REF` 记入 `attachments-missing.txt` 而不中断 `/api/session.export`，并在提前中止时经 `Promise.allSettled` 关闭所有打开的文件流。
- **CI 已校验 Bubblewrap 缓存（`scripts/ci-verified-download.sh`，PR #8383）**：在托管 Linux CI/E2E 任务中缓存经 SHA-256 校验的 `bubblewrap_0.12.0-1_amd64.deb`（`~/.cache/dsh-ci/bubblewrap`）并收紧 `curl` 超时与重试边界。
- **破坏性变化**：无面向用户、持久化会话或配置文件的破坏性变化（`docs/upgrade-guide/` 新增条目为 `0`；仅外部客户端插件类型 `DirectoryFlowSlotName` 扩展 `'workspace.picker.directoryFlow'`、`SidebarRootComponentProps` 扩展 `'sidebar.session.action'`）。
