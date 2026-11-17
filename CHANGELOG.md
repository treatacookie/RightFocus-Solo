# Changelog

All notable public release changes to **RightFocus Solo** are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [0.8.2] - 2026-11-17

### Initial Public Release
- **RightFocus Solo (`RightFocus-Solo-Setup-0.8.2.exe`):**
  - Local-first Windows desktop activity and screen-time dashboard built with Rust, Tauri v2, and React 19.
  - 100% offline and standalone: no child-device pairing, no cloud relay, no telemetry, and no outbound network calls.
  - Comprehensive tracking: Dashboard, Timeline, Calendar, Top Apps, Categories, Raw Events, and Data management.
  - Smart **Categories** rule builder with 16 starter categories, 280+ curated Windows applications, app-first auto-correlation, and 1-click **Suggested Uncategorized Apps**.
  - Unlimited local SQLite activity history stored in `%APPDATA%\rightfocus-solo\rightfocus.db`.
