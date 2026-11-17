# Security Policy & Architecture — RightFocus Solo

**Last Updated:** November 15, 2026

RightFocus takes security and privacy seriously. This document outlines the security architecture of **RightFocus Solo**, as well as instructions for reporting security vulnerabilities.

---

## 1. Security Architecture Overview

### 1.1 Zero Open Local Network Ports
- Unlike traditional localhost-server time trackers, `RightFocus-Solo.exe` **does not open any local TCP/HTTP listening ports**.
- All communication between the React 19 UI and the Rust backend in `RightFocus-Solo.exe` happens over in-process Tauri v2 IPC (`window.__TAURI_INTERNALS__`). Other processes or browser tabs on the machine cannot query your local database over `localhost`.

### 1.2 Zero Outbound Network Surface
- `RightFocus-Solo.exe` is compiled with zero HTTP/network client dependencies (`ureq`, `reqwest`, etc. are completely excluded from the Cargo dependency tree).
- The application never opens outbound connections: no cloud sync, no update server, no telemetry endpoint, and no remote accounts.

### 1.3 Least-Privilege Per-User Installation
- The NSIS installer (`RightFocus-Solo-Setup-<ver>.exe`) installs strictly under `%LOCALAPPDATA%\Programs\rightfocus-solo` with `RequestExecutionLevel user` (no administrator/UAC elevation required).
- Activity data is stored in a local SQLite database under the current user's `%APPDATA%\rightfocus-solo\rightfocus.db` directory.

---

## 2. Supported Versions

| Version | Supported |
| :--- | :--- |
| **`0.8.x` (Latest Release)** | ✅ Supported |
| `0.7.x` | ⚠️ Upgrade Recommended |

---

## 3. Reporting a Vulnerability

If you discover a security vulnerability in RightFocus Solo:

1. **Please do NOT open a public GitHub issue containing exploit details** before a fix has been released.
2. Instead, please report the issue via [GitHub Security Advisories](https://github.com/treatacookie/RightFocus-Solo/security/advisories/new) or open a minimal contact issue on [https://github.com/treatacookie/RightFocus-Solo/issues](https://github.com/treatacookie/RightFocus-Solo/issues) requesting a private communication channel.
3. Include affected versions, reproduction steps, and potential impact. We aim to acknowledge reports within 72 hours and publish a patched release promptly.
