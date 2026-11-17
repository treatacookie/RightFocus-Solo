# RightFocus Solo

**Local-First Screen-Time Analytics for Windows.**

[![Latest Release](https://img.shields.io/github/v/release/treatacookie/RightFocus-Solo?label=Latest%20Release&color=2b7fff)](https://github.com/treatacookie/RightFocus-Solo/releases/latest)
[![Platform: Windows 10/11](https://img.shields.io/badge/Platform-Windows%2010%20%2F%2011%20(x64)-0078D6)](https://github.com/treatacookie/RightFocus-Solo/releases/latest)
[![License: MIT](https://img.shields.io/badge/License-MIT-22c55e)](LICENSE)

---

## Overview

**RightFocus Solo** is a lightweight, high-precision desktop activity tracker and screen-time
dashboard built with **Rust**, **Tauri v2**, and **React 19**.

RightFocus Solo is the **standalone edition** of RightFocus: it runs entirely on a single Windows
computer and makes **no network connections whatsoever** — no child-device pairing, no Cloudflare
relay, no accounts, no telemetry, and no remote servers. Core local activity tracking is inspired by
[ActivityWatch](https://activitywatch.net/).

*(Looking for multi-device parental monitoring and child synchronization? See [**RightFocus Parent**](https://github.com/treatacookie/RightFocus-Parent).)*

---

## Key Features

- **Ultra-Lightweight Native Binary:**
  - **`RightFocus-Solo-Setup.exe` (~2.1 MB):** Full local analytics dashboard for your Windows PC with system tray support and automatic local SQLite storage (`%APPDATA%\rightfocus-solo\rightfocus.db`).
- **Rich Screen-Time Insights:**
  - **Dashboard:** Daily active-time summaries, category breakdowns, and top apps/window titles.
  - **Timeline:** Zoomable, interactive multi-day visual timeline of active (`not-afk`), idle
    (`afk`), and application usage spans.
  - **Calendar:** Day, Week, and Month activity block views.
  - **Top Apps & Categories:** Custom date ranges, regex-based category hierarchy with priority
    ordering, and historical retrospective recategorization.
  - **Raw Events & Data Management:** Full JSON export, backup import, and selective time-range or
    full database wipe.
- **100% Local-First & Private:** All activity data stays in a local SQLite database with no central
  servers, no external databases, zero telemetry, and zero third-party analytics. Unlimited history retention.

---

## Downloads & Installation

Download the latest installer from [**GitHub Releases**](https://github.com/treatacookie/RightFocus-Solo/releases/latest):

| Installer | Target PC | Size | Description |
| :--- | :--- | :--- | :--- |
| **`RightFocus-Solo-Setup-<ver>.exe`** | Your Windows PC | ~2.1 MB | Full local dashboard + activity tracker |

The installer is per-user (no admin/UAC prompt required) and adds a Startup shortcut so tracking
begins automatically on login.

---

## Development

```bash
npm install            # install frontend dependencies
npm run typecheck      # validate TypeScript types
cargo check --workspace # validate Rust workspace
npm run build:binaries # compile release binaries into target/release/
npm run dist           # build the NSIS installer
```

---

## Legal, Privacy & Security Documentation

- [**License (`MIT`)**](LICENSE) — Open-source MIT License terms.
- [**Privacy Policy (`PRIVACY.md`)**](PRIVACY.md) — Local-first storage architecture.
- [**Terms of Use (`TERMS.md`)**](TERMS.md) — Device-owner use mandate and warranty disclaimers.
- [**Security Policy (`SECURITY.md`)**](SECURITY.md) — Local data handling and vulnerability disclosure.
- [**Third-Party Notices (`THIRD_PARTY_NOTICES.md`)**](THIRD_PARTY_NOTICES.md) — Attributions for
  ActivityWatch inspiration, Tauri, React, SQLite, Rust crates, and Microsoft WebView2.
- [**Changelog (`CHANGELOG.md`)**](CHANGELOG.md) — Version history and release notes.