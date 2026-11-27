# Claude Latest Changes

English | [简体中文](../zh-CN/full/claude.md) · [Highlight](../claude.md) | **Full Detail**

> See [claude/README.md](claude/README.md) for the complete five-platform index (`mac`, `win`, `ubuntu`, `ios`, `android`) covering all 534 historical releases (245 Desktop + 289 Mobile).

## Latest Android Release: 1.261124.19 (Android, 2026-11-25 Uptodown Window)

See [claude/2026-11-25_1.261124.19.md](claude/2026-11-25_1.261124.19.md) for full details. Read-only static diff of **Uptodown third-party mirror** Play-split XAPKs (`1.261123.19` [`versionCode` `26112319`] → `1.261124.19` [`versionCode` `26112419`], imprecise `2026-11-25/26` window; not direct Play downloads, no full `apksigner` scheme verify, iOS & `1.261120.19`–`1.261122.*` gap uncovered, APKs not executed):

- **Packaging & Manifest Invariants**: XAPK entries `37 → 30` (`28 → 21` language splits: `+config.te.apk`, `−config.{am,fil,hi,ml,mr,sw,ta,tl}.apk`), `20/20` native `.so` libs byte-identical across `arm64_v8a`/`armeabi_v7a`, base APK `1,241` entries (`META-INF/services` rotation), `resources.arsc` `758,720 → 755,716` B, uncompressed DEX `59,979,864 → 60,997,648` B (`~+1.0` MB; `classes6.dex` `4.59 → 5.71` MB, `classes3.dex` `−0.34` MB), `minSdk`/`targetSdk` `32`/`37`, `66` permissions, and `83` components unchanged.
- **GitHub Integration, Safeguards Copy & Places Panel (`DEX` Pool `171,650 → 173,615`)**: Adds `claudeai.code.connect_github_card.*`, Claude GitHub App install copy, PR/plan/tool-call approval error taxonomy, org connector-approval notice, `CollapsedToolsSheetDestination${HostPage,ProductPage,Viewer}`, cloud-environment setup prompts, ~12 biology/cybersecurity/sensitive-topic safeguards model-switch strings, `claudeai.places_list.*` (`viewed`/`photo_source_opened`/`place_changed`/`sources_info_opened`) + `voice.reachability_checked`, `usage.section.*`, `settings.default_tab.*`, PHI-exclusion project instructions, read-aloud limit, and ~20 sign-in/error strings.
- **Removals & Network Surface**: Retires `claudeai.code.continue_on_cloud.*` (`8 → 1`), `artifacts.ready_made_card.rated`, `claudeai.money.message_box.*`, and legacy artifact errors; **zero API endpoint additions or removals** (only `assets.claude.ai/claude-ai/wb/{file}` and `breville.com` favicon literals).

---

## Latest Desktop Release: 5.11492.5 (2026-11-14)

See [claude/2026-11-14_5.11492.5.md](claude/2026-11-14_5.11492.5.md) for full details. Cross-platform (`mac`, `win`, `ubuntu`) embedded Claude Code engine minor update, Office skill validator hardening, and sandbox/native rotation with zero desktop UI changes over `5.11492.2`:

- **Engine Session Storage Key Schema & Managed File-Read Setting**
  - Expanded `index.chunk-BDY2-Sqh.js` (`739 B` → `21 KB`) into a unified local storage key validation layer covering `transcript`, `sessionJournal`, `agentMemory`, `tasks`, `drafts`, new `jobs-root`, recovery copies, `pluginRegistry`/`pluginAssetCache`, and three-tier `settings` (`user`/`project`/`local`) plus `setSessionArchived`; added managed setting `blockFileToolReadsOutsideWorkingDirectories` alongside `blockWritesOutsideWorkingDirectories`, and updated `ion-dist` `c6f6cf4c2` (`454 KB`) with machine-wide `env.CLAUDE_CODE_AUTO_MODE_MODEL` documentation.
- **Bundled Office Skills (`docx`/`pptx`/`xlsx`) Security Hardening (`agentSkillsRef` `1794527255 → 1794592614`)**
  - Added `names_another_root()` (`PureWindowsPath` drive/root traversal rejection), enforced `os.path.normpath` + `is_relative_to(unpacked_dir)` containment on OOXML relationship targets (`broken_refs`), and replaced `subprocess` `git diff` in `redlining.py` with a work-bounded `SequenceMatcher` (`_WorkSpent`) alongside minor `xlsx` `recalc.py` updates.
- **10-Locale `ion-dist` Catch-Up, `smol-bin` Rotation & Minimal Linux Delta**
  - Added `~48` keys across `10` non-English `ion-dist` locales (browser extension CRX/permission prompts and billing/credit expiration copy) and rotated `smol-bin` VM images across platforms; on Linux `.deb` (`99` members), only `app.asar`, `ion-dist.asar`, and `smol-bin.x64.img` changed while `claude-desktop` and all native modules remained SHA-256 identical (confirming `darwin`'s `26` rebuilt binaries are a re-signing rotation with unchanged Electron `45.2.1`, `eipc` methods, API hosts, and tool rules).

---

## Previous Android Release: 1.261113.19 (Android, 2026-11-14)

See [claude/2026-11-14_1.261113.19.md](claude/2026-11-14_1.261113.19.md) for full details. Static diff of Uptodown Google Play-split XAPKs (`1.261112.18` (`versionCode` `26111218`, Play release date unconfirmed) → `1.261113.19` (`versionCode` `26111319`, Google Play US `"Updated on: Nov 14, 2026"`); iOS not covered, APKs not executed, and prior `assetlinks.json` signer match record `305a1e8a…818b64a0` was not re-fetched):

- **`minSdkVersion` `29` → `32` (Android 10 → 12L) & Split Inventory**: Decoded `AndroidManifest.xml` raises `minSdkVersion` to `32` (`targetSdkVersion` `37` unchanged); total XAPK entries move `37 → 39` with language splits `27 → 30` (`-bho`, `+gu`/`nb`/`ta`/`te`), while the absence of `config.x86_64.apk` applies strictly to this sampled Uptodown Play-split XAPK and does not establish dropped official `x86_64` support.
- **Voice `dictation` / `readaloud` Refactor & Residual `TTSPlaybackService`**: Removes 12 helper/exception classes from `com.anthropic.claude.bell.tts.*` while retaining `TTSPlaybackService`, and adds `com.anthropic.voice.internal.{readaloud,dictation,dictation/offline}` (`189` / `116` / `105` files), `stt.repo` exceptions, `CallHooks.tools`, and `ConversationOptions.newChatPermissionMode` (annotated `"not open yet: the server does not verify it"`).
- **CCR Expansion, Static Promotional-Credits/KYC Code & Event Pruning**: Expands CCR (`code/remote/state/ProjectSheet*`, `GitHubSsoRequiredException`, `CoworkTurnOutcomeWorker`, 49-type `CodeRemoteBottomSheetDestination`, saved-login agent auth prompts, `"Response font"` / `"Anthropic Serif"`, `<files-path name="kept_tmp">`), retires mobile Threads views and `v1/code/sessions/{session_id}/feedback`, removes location event-property scrub keys (`66` permissions and HTTP(S) hosts unchanged), and adds static promotional-to-credits / voice-credit strings plus `organizations/{organization}/kyc_status`, `KycStatus`, and `kyc_required` purchase outcomes on top of `1.261112.18`'s existing credits UI (static client presence does not imply live rollout or enacted billing/policy changes).

---

## Previous Desktop Release: 5.11492.2 (2026-11-13)

See [claude/2026-11-13_5.11492.2.md](claude/2026-11-13_5.11492.2.md) for full details. Cross-platform (`mac`, `win`, `ubuntu`) feature, enterprise-governance, and security hardening update incorporating `5.11492.0`:

- **Enterprise Config Template Export & `SandboxNetworkAccess` Rule**
  - Added `.vite/build/configTemplateWindow.js` + `.vite/renderer/config_template_window/` (~20 files) and eipc `ConfigTemplateExport_$_exportTemplates(selection)` for managed deployment template export; added `SandboxNetworkAccess` to the core tool-permission schema allowlist alongside `WebFetch`.
- **SSH Host Settings, Chunked File Reads & `ion-dist` Surfaces**
  - Added `ssh_host_settings` and SSH host-key verification tri-state diagnostics (`posture`/`redial`/`redial_unverified`), `LocalAgentModeSessions.readOpenedFileChunk(readId)`, `ComputerUseTcc.openMicrophoneSettings`, action-level Claude for Chrome prompts, four MCP connector OAuth credential modes, 12h metered-connection update deferral, credit purchase step-up flows, and Loom/Vimeo/YouTube/Google Drive preview providers.
- **Cross-Platform Security Hardening & Sandbox Rebuilds**
  - Hardened Windows `claude://` launch arguments (`Parameters='-- "%1"'`), tightened Linux `/usr/lib/claude-desktop/claude-desktop` permissions (`04755 → 0755`), aligned Linux Artifact CDN allowlists (`esm.sh`, `cdn.jsdelivr.net`, `cdnjs.cloudflare.com`, `unpkg.com`, `fonts.googleapis.com/gstatic`) with macOS, and rebuilt native MCP binaries and Cowork `smol-bin` VM images across all platforms.

---

## Recent Major Baseline: 5.1231.0 (2026-11-10, `4.x → 5.x`)

See [claude/2026-11-10_5.1231.0.md](claude/2026-11-10_5.1231.0.md) for full details.

- **Built-in Browser Chrome Extension Ecosystem**
  - Added three core main-process bundles (`extensionWindow.js`, `extensionWorker.js`, `webStorePage.js`) integrating `https://chromewebstore.google.com` and Google's CRX distribution/update pipeline to browse, verify, and install Chrome extensions directly inside the built-in browser.
- **Extension Agentic Bridge & 1Password Autofill**
  - Added the `extension-host:agentic-call` bridge protocol (`agenticMode.enable/disable`, `agenticAutofill.fillCredential`), natively supporting Claude for Chrome extension coordination and **1Password Agentic Autofill** login credential authorization.
- **Cowork Plugin Directories & Three.js 3D Artifact Rendering**
  - Added plugin directory controls including `CLAUDE_CODE_USE_COWORK_PLUGINS` and `CLAUDE_CODE_PLUGIN_CACHE_DIR`; introduced a full Three.js WebGL rendering pipeline in the Web UI (`ion-dist.asar`) for 3D Artifacts.
- **Runtime Upgrade**
  - **Upgraded Electron to `45.2.1`** (from `44.9.3`).
