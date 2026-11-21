# Antigravity 最新版本改动

[English](../antigravity.md) | 简体中文 · **精简版 (Highlight)** | [完整详情 (Full Detail)](full/antigravity.md)

> 五端（`mac`、`win`、`ubuntu`、`ios`、`android`）版本索引（覆盖 **Antigravity Desktop / Hub `2.32.2`** 与 **Antigravity IDE `2.7.0`** 两条独立桌面产品线）见 [antigravity/README.md](antigravity/README.md)。

## Antigravity Desktop（Hub）2.32.2（2026-11-17，包 `Last-Modified`）

核心亮点见 [antigravity/2026-11-17_2.32.2.md](antigravity/2026-11-17_2.32.2.md)，完整技术细节见 [full/antigravity/2026-11-17_2.32.2.md](full/antigravity/2026-11-17_2.32.2.md)。

### 核心亮点

- **桌面壳层与内置 MCP 零功能变动的维护补丁构建**：Electron `44.9.1` 桌面壳层（`app.asar` 全量提取 `1,068` 个文件、`18,668,119` B）仅 `package.json` 版本号由 `2.32.1` 升至 `2.32.2`，随包 `chrome-devtools-mcp` `1.9.0`（`app.asar.unpacked`）零差异，完整继承下方 [2.32.1](antigravity/2026-11-14_2.32.1.md) 与 [2.32.0](antigravity/2026-11-13_2.32.0.md) 既有功能与修复。
- **后端重编译与内部遥测符号级微调**：基于官方 `darwin-arm` 双 DMG 主分析（配合 `linux-x64` 同构建及 LS 点测、`windows-x64` 点测，非三端全量提取树 diff），重编译 Go `language_server`（`cl/1021296516` → `cl/1022991777`）未检出新增 UI 话术、且静态抽取的 `9` 档 `gemini-4-*` 模型预设、`376` 条 RPC 前缀、`189` 对特性开关及 `65` 项 `*ToolConfig` 清单均无变化；仅检出内部遥测 CEL 超时函数改名及 `Shutdown` 闭包符号串变化（仅属静态重编译证据，不声称功能修复或全量放量）。

---

## 前序补丁构建（Hub）：2.32.1（2026-11-14）

核心亮点见 [antigravity/2026-11-14_2.32.1.md](antigravity/2026-11-14_2.32.1.md)，完整技术细节见 [full/antigravity/2026-11-14_2.32.1.md](full/antigravity/2026-11-14_2.32.1.md)。

### 核心亮点

- **默认模型目录新增 `Gemini 4 Hydrogen` 档位**：在内置默认模型目录中新增 **Gemini 4 Hydrogen** 的低、中、高三档推理强度预设（如 `Gemini 4 Hydrogen (High)`），与既有 `Gemini 4 Argon`、`Gemini 4 Carbon` 档位并列提供。
- **延续 `2.32.0` 全量能力的次日补丁构建**：保持 Electron `44.9.1` 桌面壳层与内置浏览器 MCP 工具集与 `2.32.0` 逐字节一致，同步更新后端核心构建，完整继承下方 [2.32.0](antigravity/2026-11-13_2.32.0.md) 全部改进与修复。

---

## 近期主版本基线（Hub）：2.32.0（2026-11-13）

核心亮点见 [antigravity/2026-11-13_2.32.0.md](antigravity/2026-11-13_2.32.0.md)，完整技术细节见 [full/antigravity/2026-11-13_2.32.0.md](full/antigravity/2026-11-13_2.32.0.md)。

### 核心亮点

- **Dynamic Workflows 动态工作流上线**：正式开放 **Dynamic Workflows**，支持智能体直接借助随包内置的独立 Python 运行时编写并编排多步骤任务与并行子代理（Subagents）工作流。
- **Everforest 亮/暗主题与提示词跳转快捷键**：在 `Settings > Appearance` 中新增低对比度护眼配色的 **Everforest Light** 与 **Everforest Dark** 主题；支持在输入框或阅读视图中通过快捷键跳转上/下一条提示词，支持在 `Settings > Shortcuts` 中绑定可选的 **Submit Prompt** 发送快捷键，并修复 Linux 下固定会话快捷键与 Chrome 标签组的冲突。
- **内置浏览器标签页隔离加固与站点兼容修复**：智能体控制的浏览器标签页中跨站子框架（Cross-site Frames）默认以未登录态加载（剥离跨站凭据），且在未经显式允许与指定前对智能体截图和页面快照保持隐藏；导航拦截范围由支付页扩展至受保护登录页；文件类型受阻的下载会通知智能体并在下载抽屉显示拦截状态；同时移除内置浏览器 User-Agent 中的 `Electron` 标识（保留 Google 登录兼容特判），解决部分外部网站拦截内置浏览器的问题。
- **授权码登录兜底、云端 GitHub 仓库克隆与交互改进**：新增浏览器自动回跳失败时复制登录链接或粘贴一次性授权码的登录方式；使用远程智能体时支持从工作区选择器将云端 GitHub 仓库克隆至本地并在应用内直接登录 PR 链接；模型选择菜单支持自适应屏幕高度并在加载失败时提供 **Refresh** 重试按钮；插件卡片与详情页直接展示 MCP Server 启动报错，权限菜单在宿主不支持终端沙箱时说明隐藏 Default / Auto 模式的原因。
- **退出残留进程清理、中日韩粗体渲染等 13 项修复与底层基建**：重写登录 Shell 环境变量读取逻辑以确保退出桌面端时正常关闭后台进程，增强设置保存对临时文件锁的容错，修复 CJK 粗体字重退化、长对话上滚卡顿、回退对话工具栏闪烁、草稿/排队消息列表扁平化、插件更新后全屏视图空白及 Google Drive `@` 提及登录；同时随包合入受实验开关门控的 SSH 远程主机栈（`--ssh-host`）、桌面控制（Computer Use）子代理插件与三层访客视图手势栈。

---

## Antigravity IDE 2.7.0（发布时间未确认；构建于 2026-11-11）

核心亮点见 [antigravity/2026-11-11_ide-2.7.0.md](antigravity/2026-11-11_ide-2.7.0.md)，完整技术细节见 [full/antigravity/2026-11-11_ide-2.7.0.md](full/antigravity/2026-11-11_ide-2.7.0.md)。_（发布时间未确认；`product.json` 中的北京时间 `2026-11-11 12:46` 是构建时间，不是发布时间。）_

### 核心亮点

- **登录态感知状态栏与多窗口认证同步**：底部状态栏升级为登录态三态按钮（未登录时点击直接触发登录，已登录时展开快捷状态菜单），新增登录/登出命令、跨窗口登录态自动同步及 Google Cloud / 企业服务条款状态识别。
- **区分「当前文件」与「全部文件」差异操作及新快捷键**：将行内与并排 Diff 审阅标题明确为「当前文件」，拆出独立的「接受/拒绝全部文件改动」命令，新增新建对话、切换聊天焦点与插入终端输出命令，并细化终端 `Ctrl+L` / `Ctrl+Alt+L` 快捷键分工。
- **后台任务与录制桥接及云工作站预装 CLI 识别**：扩展智能体界面桥接以支持后台任务（`ManageTask`）、多媒体处理与浏览器录制；在 Google Cloud Workstations / Cloud Shell 中自动复用预装 `/usr/bin/agy`、支持本地服务端口冲突重试，并在一键反馈中标识 Antigravity IDE。

---

## Antigravity Desktop（Hub）2.31.2（2026-11-12）

核心亮点见 [antigravity/2026-11-12_2.31.2.md](antigravity/2026-11-12_2.31.2.md)，完整技术细节见 [full/antigravity/2026-11-12_2.31.2.md](full/antigravity/2026-11-12_2.31.2.md)。

### 核心亮点

- **内置浏览器页面级 WebMCP 工具桥接**：新增 Guest WebMCP 桥，支持在内置浏览器中发现、调用与取消由网页自身通过 Chromium WebMCP 暴露的结构化工具（不向页面注入额外脚本），仅限 HTTPS 与本地回环地址，内置 30 秒默认超时（1–120 秒范围）、64 KiB 结果上限，并自动拦截 Stripe、PayPal、Adyen、Google Pay 等支付与身份认证域名。
- **原生多智能体 Swarm 看板协同**：移除旧版单一静态模板，上线原生 Swarm 协同工具族，支持管理并行工作节点、向共享看板投递消息、按未读或提及筛选读取看板以及等待/汇合多节点任务。
- **远程 MCP 服务器直连 OAuth 登录**：新增面向 MCP 服务器的独立 OAuth 登录入口，与现有插件授权体系及 `~/.gemini/config/mcp_config.json` 本地/远程自定义 MCP 配置并存。
- **规划—执行门控、持久终端与 Notebook 执行**：新增规划模式进入/退出门控工具与焦点追踪，终端命令执行支持持久会话（跨轮次保留环境变量与 Shell 变量）及通知超时配置，并新增独立的 Jupyter Notebook 单元格编辑与运行工具。
- **本地调试端口权限加固与安全预筛**：收紧本地应用数据目录（`0700`）与浏览器调试端口文件（`0600`）访问权限，升级 Electron 桌面运行时，放宽内置浏览器 MCP 回退启动器的 Node 版本匹配，并在 30 项工具 / 43 条命令只读安全白名单旁新增轻量模型威胁预筛器（日志模式）。
