# ZCode Desktop Latest Changes

English | [简体中文](../zh-CN/full/zcode.md) · [Highlight](../zcode.md) | **Full Detail**

> See [zcode/README.md](zcode/README.md) for the complete five-platform index (`mac`, `win`, `ubuntu`, `ios`, `android`) covering all 123 historical releases (`0.1.7` → `3.18.2` across `mac` / `win` / `ubuntu`; standalone `ios` / `android` unreleased).

## 3.18.2 (2026-11-13)

Official public release succeeding [3.17.2](zcode/2026-11-02_3.17.2.md) (`Released Nov 13, 2026`, accumulating preview `3.18.0`/`3.18.1` notes; binary diff baseline `3.18.1`). See [zcode/2026-11-13_3.18.2.md](zcode/2026-11-13_3.18.2.md) for full details.

- **Post-Migration Credential Key Sharing (`credential-key-share` IPC)**
  - `updateDataBaseDir` invokes `shareCredentialKeyWithDataRoot` (`credential-key-share-request` / `credential-key-share-result`) so the main process verifies matching 24-hex OS keyring fingerprints (`enc:v2:os:<24hex>:`) and `credential-source` pin state, writing the `base64url` key to `<newRoot>/.zcode/v2/credentials.json.keyring` without requiring re-login.
- **Linux Secret Service Private-File Key Fallback (`enablePrivateFileKeyFallback`)**
  - Main-process `createSystemCredentialCipher` on Linux registers a fallback hook that atomically publishes an exclusive `0600` 32-byte random `base64url` secret at `.zcode/v2/credential-secret` when OS keyring verification fails (host and CLI copies remain statically unwired in `3.18.2`).
- **Decoupled Start Plan Material & `zai_cn` → `bigmodel` Mapping**
  - Host adds `loadStartPlanMaterial` / `loadStartPlanZcodeJwt` (independent of OAuth `accessToken`), standalone `isStartPlanFamilyCurrent` & `identityOf("start-plan")`, and `resolveStartPlanFamilyFromOAuthProvider` mapping `zai_cn` → `"bigmodel"` so unlinked China accounts can use Start Plan benefits.
- **Windows Updater Fix & Zero-Rebuild Linux Runtime**
  - Fixes Windows update checks failing under system restrictions or special-character paths; Electron `44.7.0` / Chromium `152.0.7977.130` runtime, dependencies, plugins, and `7,847` i18n keys are unchanged from `3.18.1`.

---

## 3.18.1 (2026-11-11)

See [zcode/2026-11-11_3.18.1.md](zcode/2026-11-11_3.18.1.md) for full details.

- **macOS Voice Permission Reset & Font Smoothing**: Added `zcode:reset-microphone-access` (`tccutil reset Microphone <bundleId>`) with a multi-phase composer permission popover across 5 locales, plus a macOS-desktop `settings.fontSmoothing` toggle.
- **Bounded CLI Memory Diagnostics & Bug Fixes**: Added `zcode-cli-memory-v1` 15s V8 heap snapshots bundled into exported logs, widened v4 resource metrics to 8 fields, narrowed minimum session list width to `360px`, and fixed mainland China website login, browser element-picker view jumps, and leftover old processes during updates.

---

## Recent Major Release: 3.18.0 (2026-11-10)

See [zcode/2026-11-10_3.18.0.md](zcode/2026-11-10_3.18.0.md) for the full `3.18.0` feature changelog:

- **Desktop & Developer Workflows**: Composer voice input, managed Git Worktree parallel tasks and message forking, standalone MCP-based Extensions host subsystem, built-in `design` plugin (`v0.7.2`), and built-in browser visual element click-to-edit, device presets, and PNG/PDF export.
- **Agent Runtime & Tool Surface**: Added 12 multi-session control tools (`CreateSession` / `ForkSession` / `SendToSession` / `WaitSessions`, etc.), `SearchPlugins` / `SuggestPluginInstall` marketplace discovery tools, `ReadTopicResource` managed resource download, subagent `budget.webSearch` search caps and partial output recovery on interruption, default `<total_tokens>` budget injection in system prompts, and retirement of legacy `ReadSessionContext`.
- **Accounts, Security & Sites**: Added `zai_cn` OAuth provider and multi-account switching, OS keyring credential migration (`@napi-rs/keyring`), `pkijs` code-signing certificate chain verification for updates, `android-emulator` external binary path hardening, bulk permanent deletion for archived sessions, share expiration & Share Management page, Japanese/Korean/Russian UI locales, and ZCode Sites traffic analytics plus 2× container specs.
