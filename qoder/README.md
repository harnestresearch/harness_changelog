# Qoder Changelog History

English | [简体中文](../zh-CN/qoder/README.md) · **Highlight** | [Full Detail](../full/qoder/README.md)

Complete multi-platform version history covering all **59** unified releases of Qoder from `1.24.1` (2026-07-16) to `0.5.20` (2026-11-25) across `mac`, `win`, `ubuntu`, `ios`, and `android` (**30** Desktop/Unified releases + **29** Mobile-only releases; intermediate desktop versions `0.5.14` and `0.5.16`–`0.5.19` are not yet cataloged).

## Five-Platform Coverage Overview

| Platform | Distribution / Package | Tracked Releases | Version Range | Latest Version |
|---|---|---|---|---|
| `mac` | macOS (`Qoder.app` CDN & Homebrew Cask) | 30 | `0.1.0` → `0.5.20` | [0.5.20](2026-11-25_0.5.20.md) |
| `win` | Windows (`Alibaba.Qoder` Setup CDN & Winget) | 28 | `0.1.0` → `0.5.20` | [0.5.20](2026-11-25_0.5.20.md) |
| `ubuntu` | Ubuntu / Linux (`Qoder-linux-amd64.deb` & `.rpm` CDN) | 28 | `0.1.0` → `0.5.20` | [0.5.20](2026-11-25_0.5.20.md) |
| `ios` | iOS App Store (`com.qoder.mobile` & `com.qoder.app.cn`) | 27 | `1.24.1` → `1.46.0` | [1.46.0](2026-11-12_1.46.0.md) |
| `android` | Android (`com.qoder.mobile` Official APK CDN & Play) | 2 | `0.9.0` → `0.10.0` | [0.10.0](2026-11-15_0.10.0.md) |

## Desktop Version Index (`mac` / `win` / `ubuntu`, Newest → Oldest)

| Version | Platforms | Release Date | Highlights |
|---|---|---|---|
| [0.5.20](2026-11-25_0.5.20.md) | `mac`, `win`, `ubuntu` | 2026-11-25 | Official `0.5.18 → 0.5.20` static diff (skipping unanalyzed `0.5.19`; intermediate `0.5.14`/`0.5.16`–`0.5.18` not yet cataloged): desktop Cloud Tasks, Cross-Device Collaboration (`automationPeer.*`, peer workspace downloads, `automations.read.v1`/`manage.v1`), Local Task Recovery, Managed Device Sign-In, archive group restore/delete, extra-large text & `125%` scaling entry strings, 4 official fixes (incl. Remote Control ordering & automation disconnect retry/index, plus partial clues for plugin migration/restricted Windows), and unannounced `qodercli` `1.1.96-hotfix.8`, `knowledge.center` → `wiki`+`qmind` split, `@ali/qoder-text-sdk`, `@qoder-space/in-app-browser`, Qwen sign-in strings, and icon refresh |
| [0.5.13](2026-11-16_0.5.13.md) | `mac` | 2026-11-16 | Official macOS `arm64` static diff (`0.5.12 → 0.5.13`): `ApplicationTransport.subscribe` drain-and-recheck at the `64`-subscription limit with 30s diagnostic logging (static behavioral inference for task-switching hangs), `+6` decoded worker prompt/telemetry strings (`14,169 → 14,175`) for Bash risk self-assessment and Auto gate/blacklist/policy version, Agent SDK `1.0.60-alpha.62` & `qodercli` `1.1.86-hotfix.5.2`, `xlsx-sidecar` rebuild, and tiered notes for 5 remaining official fixes |
| [0.5.12](2026-11-14_0.5.12.md) | `mac` | 2026-11-14 | Official macOS `arm64` static diff (`0.5.11 → 0.5.12`): 4 `transcript.resume.*` session-resume validation strings (static evidence), Agent SDK `1.0.60-alpha.50` & `qodercli` `1.1.86-hotfix.5`, recompiled `qoder-office-xlsx` `xlsx-sidecar`, and separated notes on 4 official changelog items without new local static diff |
| [0.5.7](2026-11-09_0.5.7.md) | `mac`, `win`, `ubuntu` | 2026-11-09 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [0.5.6](2026-11-06_0.5.6.md) | `mac`, `win`, `ubuntu` | 2026-11-06 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [0.5.5](2026-11-05_0.5.5.md) | `mac`, `win`, `ubuntu` | 2026-11-05 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [0.5.3](2026-11-02_0.5.3.md) | `mac`, `win`, `ubuntu` | 2026-11-02 | Standalone agentic workbench with Git Worktrees, Plan/Experts workflows, Repo Wiki & QMind notebooks, full-stack Qoder Sites (DB/Functions/Storage), USB iOS & Android Phone Use automation, Computer/Browser Use with recording, and WeCom/DingTalk channels |
| [0.5.2](2026-11-02_0.5.2.md) | `mac`, `win`, `ubuntu` | 2026-11-02 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [0.5.1](2026-10-30_0.5.1.md) | `mac`, `win`, `ubuntu` | 2026-10-30 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [0.4.11](2026-10-23_0.4.11.md) | `mac`, `win`, `ubuntu` | 2026-10-23 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [0.4.9](2026-10-22_0.4.9.md) | `mac`, `win`, `ubuntu` | 2026-10-22 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [0.4.8](2026-10-14_0.4.8.md) | `mac`, `win`, `ubuntu` | 2026-10-14 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [0.4.7](2026-10-14_0.4.7.md) | `mac`, `win`, `ubuntu` | 2026-10-14 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [0.4.4](2026-10-10_0.4.4.md) | `mac`, `win`, `ubuntu` | 2026-10-10 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [0.4.3](2026-09-24_0.4.3.md) | `mac`, `win`, `ubuntu` | 2026-09-24 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [0.4.2](2026-09-24_0.4.2.md) | `mac`, `win`, `ubuntu` | 2026-09-24 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [0.4.1](2026-09-23_0.4.1.md) | `mac`, `win`, `ubuntu` | 2026-09-23 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [0.3.4](2026-09-18_0.3.4.md) | `mac`, `win`, `ubuntu` | 2026-09-18 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [0.3.3](2026-09-18_0.3.3.md) | `mac`, `win`, `ubuntu` | 2026-09-18 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [0.2.5](2026-09-12_0.2.5.md) | `mac`, `win`, `ubuntu` | 2026-09-12 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [0.2.3](2026-09-10_0.2.3.md) | `mac`, `win`, `ubuntu` | 2026-09-10 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [0.2.2](2026-09-09_0.2.2.md) | `mac`, `win`, `ubuntu` | 2026-09-09 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [0.2.1](2026-09-08_0.2.1.md) | `mac`, `win`, `ubuntu` | 2026-09-08 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [0.1.8](2026-09-05_0.1.8.md) | `mac`, `win`, `ubuntu` | 2026-09-05 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [0.1.6](2026-09-03_0.1.6.md) | `mac`, `win`, `ubuntu` | 2026-09-03 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [0.1.4](2026-09-01_0.1.4.md) | `mac`, `win`, `ubuntu` | 2026-09-01 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [0.1.3](2026-08-31_0.1.3.md) | `mac`, `win`, `ubuntu` | 2026-08-31 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [0.1.2](2026-08-28_0.1.2.md) | `mac`, `win`, `ubuntu` | 2026-08-28 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [0.1.1](2026-08-27_0.1.1.md) | `mac`, `win`, `ubuntu` | 2026-08-27 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |
| [0.1.0](2026-08-27_0.1.0.md) | `mac`, `win`, `ubuntu` | 2026-08-27 | `TODO` (`mac`, `win`, `ubuntu`) — _highlights pending_ |

## Mobile Version Index (`ios` / `android`, Newest → Oldest)

| Version | Platforms | Release Date | Highlights |
|---|---|---|---|
| [0.10.0](2026-11-15_0.10.0.md) | `android` | 2026-11-15 | Cross-channel static diff (`0.9.0` (`67`) → `0.10.0` (`70`)): expanded `features/credits` Benefits Center models & `qoder_web_fetch.js` bridge, `ModelManagementValue` & thinking-effort/context UI copy (with preview/simulation strings), streamlined homepage/drawer copy, and `OtlpTelemetryClient` technical batch API |
| [1.46.0](2026-11-12_1.46.0.md) | `ios` | 2026-11-12 | `TODO` (`ios`) — _highlights pending_ |
| [1.45.1](2026-11-11_1.45.1.md) | `ios` | 2026-11-11 | `TODO` (`ios`) — _highlights pending_ |
| [1.45.0](2026-11-09_1.45.0.md) | `ios` | 2026-11-09 | `TODO` (`ios`) — _highlights pending_ |
| [0.9.0](2026-11-08_0.9.0.md) | `android` | 2026-11-08 | `TODO` (`android`) — _highlights pending_ |
| [1.44.0](2026-11-03_1.44.0.md) | `ios` | 2026-11-03 | `TODO` (`ios`) — _highlights pending_ |
| [1.43.1](2026-10-31_1.43.1.md) | `ios` | 2026-10-31 | `TODO` (`ios`) — _highlights pending_ |
| [1.43.0](2026-10-29_1.43.0.md) | `ios` | 2026-10-29 | `TODO` (`ios`) — _highlights pending_ |
| [1.42.1](2026-10-24_1.42.1.md) | `ios` | 2026-10-24 | `TODO` (`ios`) — _highlights pending_ |
| [1.42.0](2026-10-21_1.42.0.md) | `ios` | 2026-10-21 | `TODO` (`ios`) — _highlights pending_ |
| [1.41.0](2026-10-15_1.41.0.md) | `ios` | 2026-10-15 | `TODO` (`ios`) — _highlights pending_ |
| [1.40.0](2026-09-30_1.40.0.md) | `ios` | 2026-09-30 | `TODO` (`ios`) — _highlights pending_ |
| [1.39.0](2026-09-27_1.39.0.md) | `ios` | 2026-09-27 | `TODO` (`ios`) — _highlights pending_ |
| [1.38.0](2026-09-20_1.38.0.md) | `ios` | 2026-09-20 | `TODO` (`ios`) — _highlights pending_ |
| [1.37.0](2026-09-18_1.37.0.md) | `ios` | 2026-09-18 | `TODO` (`ios`) — _highlights pending_ |
| [1.36.0](2026-09-10_1.36.0.md) | `ios` | 2026-09-10 | `TODO` (`ios`) — _highlights pending_ |
| [1.35.0](2026-09-08_1.35.0.md) | `ios` | 2026-09-08 | `TODO` (`ios`) — _highlights pending_ |
| [1.34.0](2026-09-05_1.34.0.md) | `ios` | 2026-09-05 | `TODO` (`ios`) — _highlights pending_ |
| [1.33.0](2026-08-29_1.33.0.md) | `ios` | 2026-08-29 | `TODO` (`ios`) — _highlights pending_ |
| [1.32.0](2026-08-25_1.32.0.md) | `ios` | 2026-08-25 | `TODO` (`ios`) — _highlights pending_ |
| [1.31.0](2026-08-22_1.31.0.md) | `ios` | 2026-08-22 | `TODO` (`ios`) — _highlights pending_ |
| [1.30.0](2026-08-17_1.30.0.md) | `ios` | 2026-08-17 | `TODO` (`ios`) — _highlights pending_ |
| [1.29.0](2026-08-09_1.29.0.md) | `ios` | 2026-08-09 | `TODO` (`ios`) — _highlights pending_ |
| [1.28.0](2026-08-05_1.28.0.md) | `ios` | 2026-08-05 | `TODO` (`ios`) — _highlights pending_ |
| [1.27.0](2026-08-03_1.27.0.md) | `ios` | 2026-08-03 | `TODO` (`ios`) — _highlights pending_ |
| [1.26.0](2026-07-31_1.26.0.md) | `ios` | 2026-07-31 | `TODO` (`ios`) — _highlights pending_ |
| [1.25.2](2026-07-25_1.25.2.md) | `ios` | 2026-07-25 | `TODO` (`ios`) — _highlights pending_ |
| [1.25.1](2026-07-24_1.25.1.md) | `ios` | 2026-07-24 | `TODO` (`ios`) — _highlights pending_ |
| [1.24.1](2026-07-16_1.24.1.md) | `ios` | 2026-07-16 | `TODO` (`ios`) — _highlights pending_ |
