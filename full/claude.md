# Claude Latest Changes

English | [简体中文](../zh-CN/full/claude.md) · [Highlight](../claude.md) | **Full Detail**

> See [claude/README.md](claude/README.md) for the complete five-platform index (`mac`, `win`, `ubuntu`, `ios`, `android`) covering all 535 historical releases (245 Desktop + 290 Mobile).

## Latest Android Release: 1.261125.19 (Android, 2026-11-27 Uptodown Window)

See [claude/2026-11-27_1.261125.19.md](claude/2026-11-27_1.261125.19.md) for full details. Read-only static diff of archived **Uptodown third-party mirror** Play-split XAPKs (`1.261124.19` [`versionCode` `26112419`] → `1.261125.19` [`versionCode` `26112519`], `2026-11-26/27` window: Uptodown `"Nov 27, 2026"`, Google Play US `"Updated on Nov 26, 2026"` with embedded unix `1795755160` [`2026-11-26 20:52:40` PST / `2026-11-27 12:52:40` UTC+8]; archived sample XAPK SHA-256 `801b77ee…` does **not** match current live Uptodown `44.03 MB` / `39662257…` rotated container; 8th archived Play-split release with signer `305a1e8a…818b64a0` / MD5 `2e746b8a2e01023c55ed06b2945690c6`; no full `apksigner` verify, iOS uncovered, APKs not executed):

- **Packaging & Manifest Invariants**: XAPK members `30 → 30` with `config.x86_64.apk` (`6,628,240` B, `10` `.so` libs) returning after absence since `1.261113` and language splits shifting `21 → 20` (`+gu`, `+hi`, `−da`, `−nb`, `−te`); `arm64-v8a` / `armeabi-v7a` (`20/20` `.so`) unchanged across `1.261123.19` / `1.261124.19` / `1.261125.19`; base APK `1,241` entries (`META-INF/services/p22.b3,p23.b → p23.b3,p24.b`), `resources.arsc` `755,716 → 758,616` B, `aboutlibraries.json` `332,597 → 336,112` B; `classes6.dex` `5.71 → 7.11` MB offset by `classes3.dex` `−1.44` MB for net DEX `+286,852` B (`60,997,648 → 61,284,500` B); `minSdk`/`targetSdk` `32`/`37`, `66` `uses-permission` entries (+ `1` declared `DYNAMIC_RECEIVER_NOT_EXPORTED_PERMISSION`), and `83` components unchanged.
- **Usage Credits Auto-Reload, IAP Identity Check, Reflect & GitHub Creation (Unique DEX Pool `170,384 → 170,870`)**: Adds usage-credits auto-reload copy + `claudeai.usage_credits.code_limit_offer.step`; IAP government photo ID capture checklist + Google Play update/account notice + `claudeai.iap.identity_check.{,verify_opened}` + `PurchaseCancellation`; incremental Reflect (`cardinal`) background-notification, memory-prerequisite, and delete-all copy + `claudeai.cardinal.{notify.{offered,answered},recap.read,wait.left}`; and GitHub repo-creation copy + `claudeai.code.repository_picker.new_repository.{shown,opened,finished}` + name/SSO/permission/indeterminate error taxonomy.
- **Media, Removals & Network Surface**: Adds `<1`-minute video limit copy, `"Pause/Play %1$s preview"`, and DEX literal `https://kept.invalid/` (initial diffing reported no API endpoint changes; full-corpus endpoint diff not independently re-run), while removing `"Conversation outline (Ant only)"` and legacy feedback form category strings (`Bug report` / `Feature request` / `General feedback`).

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

## Previous Android Release: 1.261124.19 (Android, 2026-11-25 Uptodown Window)

See [claude/2026-11-25_1.261124.19.md](claude/2026-11-25_1.261124.19.md) for full details. Read-only static diff of **Uptodown third-party mirror** Play-split XAPKs (`1.261123.19` [`versionCode` `26112319`] → `1.261124.19` [`versionCode` `26112419`], imprecise `2026-11-25/26` window; not direct Play downloads, no full `apksigner` scheme verify, iOS & `1.261120.19`–`1.261122.*` gap uncovered, APKs not executed):

- **Packaging & Manifest Invariants**: XAPK entries `37 → 30` (`28 → 21` language splits: `+config.te.apk`, `−config.{am,fil,hi,ml,mr,sw,ta,tl}.apk`), `20/20` native `.so` libs byte-identical across `arm64_v8a`/`armeabi_v7a`, base APK `1,241` entries (`META-INF/services` rotation), `resources.arsc` `758,720 → 755,716` B, uncompressed DEX `59,979,864 → 60,997,648` B (`~+1.0` MB; `classes6.dex` `4.59 → 5.71` MB, `classes3.dex` `−0.34` MB), `minSdk`/`targetSdk` `32`/`37`, `66` permissions, and `83` components unchanged.
- **GitHub Integration, Safeguards Copy & Places Panel (`DEX` Pool `171,650 → 173,615`)**: Adds `claudeai.code.connect_github_card.*`, Claude GitHub App install copy, PR/plan/tool-call approval error taxonomy, org connector-approval notice, `CollapsedToolsSheetDestination${HostPage,ProductPage,Viewer}`, cloud-environment setup prompts, ~12 biology/cybersecurity/sensitive-topic safeguards model-switch strings, `claudeai.places_list.*` (`viewed`/`photo_source_opened`/`place_changed`/`sources_info_opened`) + `voice.reachability_checked`, `usage.section.*`, `settings.default_tab.*`, PHI-exclusion project instructions, read-aloud limit, and ~20 sign-in/error strings.
- **Removals & Network Surface**: Retires `claudeai.code.continue_on_cloud.*` (`8 → 1`), `artifacts.ready_made_card.rated`, `claudeai.money.message_box.*`, and legacy artifact errors; **zero API endpoint additions or removals** (only `assets.claude.ai/claude-ai/wb/{file}` and `breville.com` favicon literals).

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
