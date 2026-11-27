# Security Policy & Architecture — RightFocus Solo

**Last Updated:** November 26, 2026

RightFocus takes security and privacy seriously. This document outlines the security architecture of **RightFocus Solo**, as well as instructions for reporting security vulnerabilities.

---

## 1. Security Architecture Overview

### 1.1 Zero Open Local Network Ports
- Unlike traditional localhost-server time trackers, `RightFocus-Solo.exe` **does not open any local TCP/HTTP listening ports**.
- All communication between the React 19 UI and the Rust backend in `RightFocus-Solo.exe` happens over in-process Tauri v2 IPC (`window.__TAURI_INTERNALS__`). Other processes or browser tabs on the machine cannot query your local database over `localhost`.

### 1.2 Zero Telemetry & Cryptographically Verified Updates (`SHA-512`)
- `RightFocus-Solo.exe` contains **zero telemetry, analytics SDKs, cloud sync, or third-party HTTP/TLS crates** (`ureq`, `reqwest`, etc. are excluded from the Cargo dependency tree).
- Every release publishes a `latest.yml` manifest containing the exact Base64 `sha512` digest of `RightFocus-Solo-Setup-<ver>.exe`.
- When checking for updates (automatically every 6 hours if enabled, or manually via **Check for Updates**), `RightFocus-Solo.exe` fetches `latest.yml` strictly over HTTPS via Windows native WinHTTP (`winhttp.dll`), verifies the downloaded installer's SHA-512 digest using Windows CNG (`bcrypt.dll`), and aborts immediately without writing or executing the file if the digest is missing or does not match.
- Background auto-installs are smart idle-gated (requiring the window to be hidden/unfocused, ≥ 2 min app cooldown, and ≥ 60 s OS-wide inactivity via `GetLastInputInfo`) and can be disabled anytime in **Settings → Software Updates** for 100% offline operation.

### 1.3 Least-Privilege Per-User Installation
- The NSIS installer (`RightFocus-Solo-Setup-<ver>.exe`) installs strictly under `%LOCALAPPDATA%\Programs\rightfocus-solo` with `RequestExecutionLevel user` (no administrator/UAC elevation required).
- Activity data is stored in a local SQLite database under the current user's `%APPDATA%\rightfocus-solo\rightfocus.db` directory.

---

## 2. Supported Versions

| Version | Supported |
| :--- | :--- |
| **`0.9.x` (Latest Release)** | ✅ Supported |
| `< 0.9.0` | ❌ Please upgrade to the latest release |

---

## 3. Reporting a Vulnerability

If you discover a security vulnerability in RightFocus Solo:

1. **Please do NOT open a public GitHub issue containing exploit details** before a fix has been released.
2. Instead, please report the issue via [GitHub Security Advisories](https://github.com/treatacookie/RightFocus-Solo/security/advisories/new) or open a minimal contact issue on [https://github.com/treatacookie/RightFocus-Solo/issues](https://github.com/treatacookie/RightFocus-Solo/issues) requesting a private communication channel.
3. Include affected versions, reproduction steps, and potential impact. We aim to acknowledge reports within 72 hours and publish a patched release promptly.
