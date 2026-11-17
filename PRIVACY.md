# Privacy Policy — RightFocus Solo

**Last Updated:** November 15, 2026

**RightFocus Solo** (`RightFocus-Solo.exe`) is designed from the ground up with a **100% local-first, zero-network privacy architecture**.

The creators and maintainers of RightFocus (**TreatACookie / RightFocus**) **do not operate any central servers, do not require user accounts, and never collect, receive, store, or have access to your activity data or telemetry.**

---

## 1. Information Recorded Locally on Your Device

When running on your computer, RightFocus Solo records screen-time and application activity locally on that device only:

1. **Foreground Application Activity:**
   - The executable name of the active foreground window (e.g., `chrome.exe`, `Code.exe`, `Minecraft.exe`).
   - The active window title (unless disabled via the **"Don't record window titles"** setting in `Settings`).
   - Timestamps and duration of each activity span.
2. **Idle / AFK (Away From Keyboard) Status:**
   - Seconds since the last mouse or keyboard input (via the standard Windows `GetLastInputInfo` API) to determine whether the user is actively at the computer (`not-afk`) or away (`afk`).
   - **RightFocus Solo never logs keystrokes, mouse coordinates, screenshots, webcam feeds, microphone audio, or clipboard contents.**
3. **Device Metadata:**
   - The local computer's hostname and operating system platform identifier.

### Where Data is Stored Locally
- All local activity is stored exclusively in a local SQLite database at `%APPDATA%\rightfocus-solo\rightfocus.db`.

---

## 2. Built-In Privacy Controls

RightFocus Solo gives you complete control over what is recorded and stored:

- **Title Redaction (`Don't record window titles`):** You can disable window title recording at any time in `Settings → Tracking` so that only application executable names are logged.
- **Excluded Applications (`Exclude apps`):** You can specify executables (such as password managers like `1Password.exe`, `Bitwarden.exe`, `KeePass.exe`) that RightFocus Solo will never record.
- **Full Data Ownership, Export & Wipe:** From the `Data` page, you can inspect the exact SQLite file path on disk, export all data to JSON, or permanently wipe any time range or the entire database.

---

## 3. Zero External Network Requests

RightFocus Solo is a strictly offline application. It makes **zero outbound network connections** of any kind — no cloud sync, no background update checks, no accounts, and no telemetry.

---

## 4. Contact & Questions

If you have questions about this Privacy Policy or RightFocus Solo's privacy architecture, please open an issue on our public repository:
- **GitHub Issues:** [https://github.com/treatacookie/RightFocus-Solo/issues](https://github.com/treatacookie/RightFocus-Solo/issues)
