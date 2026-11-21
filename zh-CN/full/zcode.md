# ZCode Desktop 最新版本改动

[English](../../full/zcode.md) | 简体中文 · [精简版 (Highlight)](../zcode.md) | **完整详情 (Full Detail)**

> 五端（`mac`、`win`、`ubuntu`、`ios`、`android`）完整 123 个历史版本索引（`0.1.7` → `3.18.2`，覆盖桌面三端 `mac` / `win` / `ubuntu`；独立 `ios` / `android` 端暂未发布）见 [zcode/README.md](zcode/README.md)。

## 3.18.2（2026-11-13）

承接上一正式版 [3.17.2](zcode/2026-11-02_3.17.2.md) 的官方正式版（发布于 `2026-11-13`，官方说明累计含预览版 `3.18.0` / `3.18.1`，二进制逆向对比基线为 `3.18.1`）。详细改动见 [zcode/2026-11-13_3.18.2.md](zcode/2026-11-13_3.18.2.md)。

- **数据目录迁移凭据密钥共享（`credential-key-share` IPC）**
  - `updateDataBaseDir` 在完成数据目录拷贝后发起 `credential-key-share-request`，主进程校验 `enc:v2:os:<24hex>:` 内嵌 OS 密钥环指纹与 `credential-source` 绑定状态后，将 `base64url` 密钥写入 `<newRoot>/.zcode/v2/credentials.json.keyring`，实现迁移后免重新登录直接解密。
- **Linux 无系统密钥环私有文件密钥回退（`enablePrivateFileKeyFallback`）**
  - Linux 主进程启动时武装回退钩子，当系统密钥环（Secret Service）不可用时以 `0600` 权限原子创建 `.zcode/v2/credential-secret` 32 字节随机密钥（宿主与 CLI 副本在 `3.18.2` 中未接线、静态不可达）。
- **Start Plan 账号材料独立化与 `zai_cn` → `bigmodel` 映射**
  - 宿主新增无需完整 OAuth `accessToken` 的 `loadStartPlanMaterial` / `loadStartPlanZcodeJwt`、独立 `isStartPlanFamilyCurrent` 与 `identityOf("start-plan")` 判定，以及将 `zai_cn` 归入 `"bigmodel"` 家族的 `resolveStartPlanFamilyFromOAuthProvider`，修复国内未关联 BigModel 账号无法使用 Start 套餐权益的问题。
- **Windows 更新器修复与零重建运行时**
  - 修复 Windows 在受系统限制或路径含特殊字符时检查更新失败的问题；Linux `x64` 包内 Electron `44.7.0` / Chromium `152.0.7977.130` 运行时、依赖树、18 个内置插件与 `7,847` 个多语言键较 `3.18.1` 零变化。

---

## 3.18.1（2026-11-11）

详细改动见 [zcode/2026-11-11_3.18.1.md](zcode/2026-11-11_3.18.1.md)。

- **macOS 麦克风权限重置与字体平滑开关**：新增 `zcode:reset-microphone-access`（调用 `tccutil reset Microphone <bundleId>`）与五语分阶段权限引导弹窗，以及 macOS 桌面专属 `settings.fontSmoothing` 开关。
- **CLI 有界内存诊断与问题修复**：新增 15 秒周期 `zcode-cli-memory-v1` V8 堆内存快照并纳入「导出日志」归档，会话列最小宽度调为 `360px`，同时修复国内用户网站登录失败、内置浏览器点选元素跳完整视图及更新时残留旧进程等问题。

---

## 近期重要版本：3.18.0（2026-11-10）

`3.18.0` 功能主线完整记录见 [zcode/2026-11-10_3.18.0.md](zcode/2026-11-10_3.18.0.md)：

- **桌面与开发工作流**：聊天框语音输入、受管 Git Worktree 并行任务与消息分叉、基于 MCP 的独立扩展（Extensions）宿主子系统、内置 `design` 插件（`v0.7.2`）及内置浏览器可视化点选编辑/设备预设/PNG·PDF 导出。
- **智能体运行时与工具面**：新增 12 个多会话控制工具（`CreateSession` / `ForkSession` / `SendToSession` / `WaitSessions` 等）、`SearchPlugins` / `SuggestPluginInstall` 插件发现工具、`ReadTopicResource` 受管资源工具、子代理 `budget.webSearch` 搜索次数上限与中断后部分输出恢复、系统提示词默认注入 `<total_tokens>` 段，以及下线旧版 `ReadSessionContext`。
- **账号、安全与站点服务**：新增 `zai_cn` OAuth 提供者与多账号切换、凭据迁移至操作系统密钥环（`@napi-rs/keyring`）、更新包 `pkijs` 代码签名证书链校验、`android-emulator` 外部工具路径安全加固、归档会话批量永久删除、分享有效期与分享管理页、日语/韩语/俄语界面，以及 ZCode Sites 访问统计与实例规格翻倍。
