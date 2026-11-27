# Privacy Policy — RightFocus Solo

**Last Updated:** November 26, 2026

**RightFocus Solo** (`RightFocus-Solo.exe`) is designed from the ground up with a **100% local-first privacy architecture**.

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

## 3. Optional External Network Requests

RightFocus Solo never transmits your activity data or telemetry anywhere. It makes external network requests **only** in one optional, toggleable circumstance:

- **SHA-512 Verified Update Checks (`GitHub Releases`, toggleable):**
  - When **"Auto-download & install updates"** is enabled in `Settings → Software Updates` (or when you manually click **Check for Updates** in Settings or the system tray), `RightFocus-Solo.exe` queries `https://github.com/treatacookie/RightFocus-Solo/releases/latest/download/latest.yml` over HTTPS using Windows' built-in WinHTTP stack and verifies downloaded installers via Windows CNG SHA-512 before installation.
  - Standard HTTP request metadata (IP address, User-Agent `RightFocus-Solo/<version>`) is handled directly by GitHub under [GitHub's Privacy Statement](https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement).
  - You can disable automatic update checks at any time in `Settings → Software Updates` for 100% offline operation.

---

## 4. Contact & Questions

If you have questions about this Privacy Policy or RightFocus Solo's privacy architecture, please open an issue on our public repository:
- **GitHub Issues:** [https://github.com/treatacookie/RightFocus-Solo/issues](https://github.com/treatacookie/RightFocus-Solo/issues)
