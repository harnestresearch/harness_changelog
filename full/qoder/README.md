# Qoder Changelog History

English | [简体中文](../../zh-CN/full/qoder/README.md) · [Highlight](../../qoder/README.md) | **Full Detail**

Complete multi-platform version history covering all **61** unified releases of Qoder from `1.24.1` (2026-07-16) to `0.5.21` Desktop / `2.0.0` Android (2026-11-27) across `mac`, `win`, `ubuntu`, `ios`, and `android` (**31** Desktop/Unified releases + **30** Mobile-only releases; intermediate desktop versions `0.5.14` and `0.5.16`–`0.5.19` and intermediate Android `0.11.0` were never cataloged in this repository—Android `2.0.0` covers strictly `0.11.0 → 2.0.0`).

## Five-Platform Coverage Overview

| Platform | Distribution / Package | Tracked Releases | Version Range | Latest Version |
|---|---|---|---|---|
| `mac` | macOS (`Qoder.app` CDN & Homebrew Cask) | 31 | `0.1.0` → `0.5.21` | [0.5.21](2026-11-27_0.5.21.md) |
| `win` | Windows (`Alibaba.Qoder` Setup CDN & Winget) | 29 | `0.1.0` → `0.5.21` | [0.5.21](2026-11-27_0.5.21.md) |
| `ubuntu` | Ubuntu / Linux (`Qoder-linux-amd64.deb` & `.rpm` CDN) | 29 | `0.1.0` → `0.5.21` | [0.5.21](2026-11-27_0.5.21.md) |
| `ios` | iOS App Store (`com.qoder.mobile` & `com.qoder.app.cn`) | 27 | `1.24.1` → `1.46.0` | [1.46.0](2026-11-12_1.46.0.md) |
| `android` | Android (`com.qoder.mobile` Official APK CDN & Play) | 3 | `0.9.0` → `2.0.0` | [2.0.0](2026-11-27_2.0.0.md) |

## Desktop Version Index (`mac` / `win` / `ubuntu`, Newest → Oldest)

| Version | Platforms | Release Date | Key Changes |
|---|---|---|---|
| [0.5.21](2026-11-27_0.5.21.md) | `mac`, `win`, `ubuntu` | 2026-11-27 | Official `0.5.20 → 0.5.21` static diff (Electron `43.8.4`, commit `eb36b7b303185facdb2ef70f0eaf9f8199b2c413`): renderer `appHubError`/`loadingSyncSources`/`streamable_http`, main `cloud-configuration:{list-apphub-items,sync-apphub-vault}` + 2 `SDK JobToken` telemetry strings, Agent SDK `1.0.62-alpha.9 → alpha.10`, `qoderCliVersion` `1.1.96-hotfix.8 → hotfix.9`, identical `13,966`-entry worker string table (`+0 / −0`); static report notes `app.asar` `+13,300` B (`electronMain.js` `+9,814` B) & `context-plugin`/`office-xlsx` swaps; proxy diagnostic prompt and 4 official fixes statically unverifiable |
| [0.5.20](2026-11-25_0.5.20.md) | `mac`, `win`, `ubuntu` | 2026-11-25 | Official `0.5.18 → 0.5.20` static diff (Electron `43.8.4`; skipping unanalyzed `0.5.19`; intermediate `0.5.14`/`0.5.16`–`0.5.18` not yet cataloged): `14` `cloud-session:*` IPC channels + expanded `automations.*` IPC & `+6` `AUTOMATION_TASK_*` codes (`2 → 8`), `19` `automationPeer.*` keys + `automations.read.v1`/`manage.v1` + `file-transfer.cjs`, `chat-session-recovery:*` + `20261119-00-chat-session-restart-resumption.sql`, `auth.deviceAccountBlocked.*` + `"Enterprise VPC sign-in"`, archive group UI & `fontSizeExtraLarge`/`uiScaleExtraLarge`, `20261121-00`/`01` automation migrations & `20261123-01-async-question-order-clock`, `qodercli` `1.1.86-hotfix.19 → 1.1.96-hotfix.8` (`−826,457` B), Agent SDK `1.0.62-alpha.2 → alpha.9`, `qoder.knowledge.center` → `wiki`+`qmind` split, `@ali/qoder-text-sdk` `0.5.2`, `@qoder-space/in-app-browser`, and unannounced Qwen/`statusline`/icon changes |
| [0.5.13](2026-11-16_0.5.13.md) | `mac` | 2026-11-16 | Official macOS `arm64` static diff (`0.5.12 → 0.5.13`, Electron `43.8.4`): `ApplicationTransport.subscribe` (`Dta6yTTQ.js` → `BHeyMntc.js`) awaits `releaseRequested` releases at the unchanged `64`-subscription cap with 30s `"Application subscription limit reached"` diagnostics, worker strings `14,169 → 14,175` (`+6` Bash risk / Auto gate / blacklist / policy-version prompt & telemetry strings), Agent SDK `1.0.60-alpha.50 → 1.0.60-alpha.62`, `qodercli` `1.1.86-hotfix.5 → 1.1.86-hotfix.5.2`, `qoder-office-xlsx` `xlsx-sidecar` rebuild, and tiered stratification for 5 remaining official fix notes |
| [0.5.12](2026-11-14_0.5.12.md) | `mac` | 2026-11-14 | Official macOS `arm64` static diff (`0.5.11 → 0.5.12`, Electron `43.8.4`): Agent SDK `1.0.60-alpha.36 → 1.0.60-alpha.50`, `qodercli` `1.1.86-hotfix.4 → 1.1.86-hotfix.5`, 4 new `transcript.resume.*` decoded worker strings, `qoder-office-xlsx` `xlsx-sidecar` rebuild, byte-identical renderer, and separated comparison for 4 official changelog items |
| [0.5.7](2026-11-09_0.5.7.md) | `mac`, `win`, `ubuntu` | 2026-11-09 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [0.5.6](2026-11-06_0.5.6.md) | `mac`, `win`, `ubuntu` | 2026-11-06 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [0.5.5](2026-11-05_0.5.5.md) | `mac`, `win`, `ubuntu` | 2026-11-05 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [0.5.3](2026-11-02_0.5.3.md) | `mac`, `win`, `ubuntu` | 2026-11-02 | `Qoder.app` `0.5.3` (`@qoder-ai/qoder-agent-sdk@1.0.59-alpha.9` / `qodercli` `1.1.79-hotfix.11`, wire `1.5.0`, MCP SDK `2.0.0`+`1.30.0`): 35+ core tools + 4 MCP channels (`qoder-context` `mtree`+`rg`, `repowiki` 14 + `qoder-qmind` 15, `qoder.phone-use` 50 `ios_*`/`android_*`/`mobile_*` tools, `qoder_sites` 33 tools, `event-stream` CUA bridge) |
| [0.5.2](2026-11-02_0.5.2.md) | `mac`, `win`, `ubuntu` | 2026-11-02 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [0.5.1](2026-10-30_0.5.1.md) | `mac`, `win`, `ubuntu` | 2026-10-30 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [0.4.11](2026-10-23_0.4.11.md) | `mac`, `win`, `ubuntu` | 2026-10-23 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [0.4.9](2026-10-22_0.4.9.md) | `mac`, `win`, `ubuntu` | 2026-10-22 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [0.4.8](2026-10-14_0.4.8.md) | `mac`, `win`, `ubuntu` | 2026-10-14 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [0.4.7](2026-10-14_0.4.7.md) | `mac`, `win`, `ubuntu` | 2026-10-14 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [0.4.4](2026-10-10_0.4.4.md) | `mac`, `win`, `ubuntu` | 2026-10-10 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [0.4.3](2026-09-24_0.4.3.md) | `mac`, `win`, `ubuntu` | 2026-09-24 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [0.4.2](2026-09-24_0.4.2.md) | `mac`, `win`, `ubuntu` | 2026-09-24 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [0.4.1](2026-09-23_0.4.1.md) | `mac`, `win`, `ubuntu` | 2026-09-23 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [0.3.4](2026-09-18_0.3.4.md) | `mac`, `win`, `ubuntu` | 2026-09-18 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [0.3.3](2026-09-18_0.3.3.md) | `mac`, `win`, `ubuntu` | 2026-09-18 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [0.2.5](2026-09-12_0.2.5.md) | `mac`, `win`, `ubuntu` | 2026-09-12 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [0.2.3](2026-09-10_0.2.3.md) | `mac`, `win`, `ubuntu` | 2026-09-10 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [0.2.2](2026-09-09_0.2.2.md) | `mac`, `win`, `ubuntu` | 2026-09-09 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [0.2.1](2026-09-08_0.2.1.md) | `mac`, `win`, `ubuntu` | 2026-09-08 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [0.1.8](2026-09-05_0.1.8.md) | `mac`, `win`, `ubuntu` | 2026-09-05 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [0.1.6](2026-09-03_0.1.6.md) | `mac`, `win`, `ubuntu` | 2026-09-03 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [0.1.4](2026-09-01_0.1.4.md) | `mac`, `win`, `ubuntu` | 2026-09-01 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [0.1.3](2026-08-31_0.1.3.md) | `mac`, `win`, `ubuntu` | 2026-08-31 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [0.1.2](2026-08-28_0.1.2.md) | `mac`, `win`, `ubuntu` | 2026-08-28 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [0.1.1](2026-08-27_0.1.1.md) | `mac`, `win`, `ubuntu` | 2026-08-27 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |
| [0.1.0](2026-08-27_0.1.0.md) | `mac`, `win`, `ubuntu` | 2026-08-27 | `TODO` (`mac`, `win`, `ubuntu`) — _detailed diff pending_ |

## Mobile Version Index (`ios` / `android`, Newest → Oldest)

| Version | Platforms | Release Date | Key Changes |
|---|---|---|---|
| [2.0.0](2026-11-27_2.0.0.md) | `android` | 2026-11-27 | Official rolling-CDN static diff (`0.11.0` (`versionCode` `73`) → `2.0.0` (`versionCode` `75`, `+11,590,803` B, `gitCommit=f42c8de801f896f74d4ba3db746ce59427f70bdb`); intermediate `0.11.0` never cataloged; mobile changelog stops at `0.11.0` and Play still serves `0.11.0`): `31` `/api/v1/qbot*` DEX paths (`0 → 31`), `335` `qbot.*` keys (`2,220 → 2,572`), `features/qbot` + `QBOT_*` event codes, `/signed-artifact-download`, `android.permission.USE_BIOMETRIC` + `device_management.remote_control.*`, Figma connector SVGs, `artifact_file_icons.ttf`, dual-mode drawer & `qbot_*` assets (`streamable_http` absent in `2.0.0` DEX) |
| [0.10.0](2026-11-15_0.10.0.md) | `android` | 2026-11-15 | Cross-channel static diff (`0.9.0` (`versionCode` `67` APKPure Play XAPK) → `0.10.0` (`versionCode` `70` official universal APK)): +11 `features/credits` campaign/reward models & `assets/qoder_web_fetch.js`, `ModelManagementValue` + 23 `composer.model_management.*` keys (including preview/simulate strings), homepage/drawer/Remote Control copy (`+79 / -3` keys), and `OtlpTelemetryClient.exportTechnicalBatch` / `TechnicalSnapshot` / `recordScrollWindow` |
| [1.46.0](2026-11-12_1.46.0.md) | `ios` | 2026-11-12 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.45.1](2026-11-11_1.45.1.md) | `ios` | 2026-11-11 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.45.0](2026-11-09_1.45.0.md) | `ios` | 2026-11-09 | `TODO` (`ios`) — _detailed diff pending_ |
| [0.9.0](2026-11-08_0.9.0.md) | `android` | 2026-11-08 | `TODO` (`android`) — _detailed diff pending_ |
| [1.44.0](2026-11-03_1.44.0.md) | `ios` | 2026-11-03 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.43.1](2026-10-31_1.43.1.md) | `ios` | 2026-10-31 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.43.0](2026-10-29_1.43.0.md) | `ios` | 2026-10-29 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.42.1](2026-10-24_1.42.1.md) | `ios` | 2026-10-24 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.42.0](2026-10-21_1.42.0.md) | `ios` | 2026-10-21 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.41.0](2026-10-15_1.41.0.md) | `ios` | 2026-10-15 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.40.0](2026-09-30_1.40.0.md) | `ios` | 2026-09-30 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.39.0](2026-09-27_1.39.0.md) | `ios` | 2026-09-27 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.38.0](2026-09-20_1.38.0.md) | `ios` | 2026-09-20 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.37.0](2026-09-18_1.37.0.md) | `ios` | 2026-09-18 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.36.0](2026-09-10_1.36.0.md) | `ios` | 2026-09-10 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.35.0](2026-09-08_1.35.0.md) | `ios` | 2026-09-08 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.34.0](2026-09-05_1.34.0.md) | `ios` | 2026-09-05 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.33.0](2026-08-29_1.33.0.md) | `ios` | 2026-08-29 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.32.0](2026-08-25_1.32.0.md) | `ios` | 2026-08-25 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.31.0](2026-08-22_1.31.0.md) | `ios` | 2026-08-22 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.30.0](2026-08-17_1.30.0.md) | `ios` | 2026-08-17 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.29.0](2026-08-09_1.29.0.md) | `ios` | 2026-08-09 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.28.0](2026-08-05_1.28.0.md) | `ios` | 2026-08-05 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.27.0](2026-08-03_1.27.0.md) | `ios` | 2026-08-03 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.26.0](2026-07-31_1.26.0.md) | `ios` | 2026-07-31 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.25.2](2026-07-25_1.25.2.md) | `ios` | 2026-07-25 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.25.1](2026-07-24_1.25.1.md) | `ios` | 2026-07-24 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.24.1](2026-07-16_1.24.1.md) | `ios` | 2026-07-16 | `TODO` (`ios`) — _detailed diff pending_ |
