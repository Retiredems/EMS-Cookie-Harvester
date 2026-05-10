<p align="center">
  <img width="820" height="571" alt="IMG_5717" src="https://github.com/user-attachments/assets/5e71c117-bc01-4b9d-85f7-93004811ba7c" />

</p>

<h1 align="center">EMS Cookie Harvester</h1>

<p align="center">
  <strong>Harvest Sessions. Own the Inbox.</strong><br/>
  A professional desktop tool that extracts email addresses from Office 365 session cookies — instantly, reliably, at scale.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Windows%20%7C%20macOS-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/Auth-IMAP%20XOAUTH2-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/Modes-Cookie%20Files%20%7C%20System%20Browser-purple?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-Commercial-orange?style=flat-square"/>
  <img src="https://img.shields.io/github/v/release/Retiredems/EMS-Cookie-Harvester?style=flat-square"/>
</p>

---

## What Is EMS Cookie Harvester?

EMS Cookie Harvester is a native desktop application that takes Office 365 session cookies and extracts every email address tied to the account — automatically. It exchanges live session tokens for IMAP XOAUTH2 access, scans the mailbox, pulls every valid address from headers and message bodies, and writes clean per-account result files to disk.

Built for **email marketers**, **list managers**, and **bulk operators** who need to recover and validate large volumes of session-bound mailboxes — on any Windows or macOS machine, fully offline-capable apart from the IMAP connection itself.

---

## Screenshots

<img width="1062" height="666" alt="Screenshot 2026-05-11 at 00 40 08" src="https://github.com/user-attachments/assets/287a5ef9-537b-4217-865d-88bab2a9d653" />

<img width="1061" height="673" alt="Screenshot 2026-05-11 at 00 43 57" src="https://github.com/user-attachments/assets/b81f3a80-083e-428d-b43c-e5f76fe89ef1" />



---

## Key Features

### Two Harvest Modes
| Mode | What It Does |
|------|--------------|
| **Cookie Files Login** | Point at a folder of `email@domain.com.txt` cookie jars — every file is auto-validated, exchanged for IMAP tokens, and harvested in parallel |
| **System Browser Login** | Load a flat list of email addresses and harvest using cookies already present in the system browser session |

### Multi-Threaded Harvesting
- Configurable thread count (1–10) for tuning speed vs. resource use
- Live status per row: `loaded → connecting → token → scanning → finished`
- Per-account isolation — one bad cookie never stalls the queue
- SOCKS5 proxy support — load a `host:port` list to route every connection

### Live Account Table
- Every account visible at a glance — `#`, `Mail`, `Server`, `Type`, `Status`
- Color-coded statuses: idle / running / OAuth / error / finished
- Server and protocol auto-detected per account (IMAP / Exchange)
- Double-click any finished row to open its result file directly

### Search Filters (Exchange Only)
- Optional keyword filter that scans subject and/or body
- Date range filter — bound the harvest window with `From` / `To` dates
- Filters apply only to Exchange accounts; IMAP accounts always full-scan

### Output
- One result file per account: `email@domain.com.txt` with extracted addresses
- Optional consolidated output — all addresses in one file
- Configurable: save correct accounts list, save attachments, save run logs
- Results folder opens with a single keystroke (`F2`)

### Premium Desktop UI
- Dark UI (default) with EMS-green accents and glowing wordmark
- Clean light theme — toggle from the toolbar
- Fixed 1060×640 window, no awkward resizing or layout breakage
- Splash on launch, in-app activation, sidebar with cross-product links

---

## Installation

### Windows

1. Download `EMS-Cookie-Harvester-Setup.exe` from the [latest release](../../releases/latest)
2. Run the installer — follow the setup wizard
3. A desktop shortcut is created automatically
4. Enter your license key on first launch

> Installs per-user (no admin required). Works on any Windows 10 / 11 desktop, laptop, VPS, or RDP environment.

### macOS

1. Download `EMS_Cookie_Harvester_macOS.zip` from the [latest release](../../releases/latest)
2. Unzip and drag `EMS Cookie Harvester.app` to your Applications folder
3. Right-click → Open on first launch (Gatekeeper bypass for unsigned builds)
4. Enter your license key

---

## Getting a License

EMS Cookie Harvester is a **commercial product**. Licenses are hardware-tied — no cloud check-in required after activation.

👉 **Telegram: [@retiredems](https://t.me/retiredems)**
🤖 **Bot: [@emsmailerbot](https://t.me/emsmailerbot)**

**Pricing — single tier, lifetime only:**

| Plan | Price | Devices |
|------|-------|---------|
| Lifetime | **$100** | Up to 3 PCs |

No monthly. No yearly. One payment, three machines, forever.

---

## How to Get a License Key

1. Open EMS Cookie Harvester — your Hardware ID (HWID) is shown on the Activation screen
2. Tap **Copy** to copy the HWID
3. Open Telegram → [@emsmailerbot](https://t.me/emsmailerbot)
4. Select **🍪 EMS Cookie Harvester** → submit your HWID and name
5. Complete payment → receive your key → paste it into the app

Your license is tied to your machine hardware. Up to **3 PCs per key** are accepted automatically. To move beyond that, contact [@retiredems](https://t.me/retiredems) for a transfer.

---

## Input Formats

### Mode 1 — Cookie Files Folder

Drop a folder of `.txt` files, one per account, named after the email address:

```
cookies/
├── alice@example.com.txt
├── bob@contoso.onmicrosoft.com.txt
├── carol@acme.org.txt
└── ...
```

Each file holds the raw session cookie payload (JSON or header format). Cookie Harvester auto-detects the format and validates every jar before launching workers.

### Mode 2 — Mail List File

A plain `.txt` file, one email address per line. Cookie Harvester pairs each address with the cookies already loaded in your system browser session and harvests against that.

```
alice@example.com
bob@contoso.onmicrosoft.com
carol@acme.org
```

Duplicates are removed before harvesting begins.

---

## System Requirements

| | Windows | macOS |
|-|---------|-------|
| OS | Windows 10 / 11 (64-bit) | macOS 11+ (Intel or Apple Silicon) |
| RAM | 256 MB minimum | 256 MB minimum |
| Disk | 200 MB | 200 MB |
| Network | Required (IMAP / Exchange access) | Required (IMAP / Exchange access) |

> Outbound HTTPS and IMAP are required to exchange session tokens and read mailboxes. Optional SOCKS5 proxy support for routing.

---

## Changelog

### v1.0.0 — May 2026

- Initial public release
- Two harvest modes: Cookie Files Login + System Browser Login
- IMAP XOAUTH2 token exchange — Office 365 session cookies → live IMAP access
- Multi-threaded worker pool (1–10 threads), configurable per run
- Live status table with color-coded statuses and double-click-to-open results
- Auto server / protocol detection (IMAP, Exchange)
- Optional Exchange filters: keyword search (subject / body), date range
- Per-account or consolidated result output, optional attachment / log saving
- SOCKS5 proxy list support
- Hardware-tied lifetime license — up to 3 PCs per key
- Dark / light theme, premium PyQt6 UI
- Splash screen on launch with in-app activation flow

---

## Other EMS Tools

| Tool | Description |
|------|-------------|
| [EMS Mailer](https://github.com/Retiredems/Ems-Mailer) | Bulk email sending — SMTP, rotating accounts, templates |
| [EMS Mail Fetcher](https://github.com/Retiredems/EMS-Mail-Fetcher) | Bulk IMAP / POP3 / OAuth account tester and email archiver |
| [EMS Country Sorter](https://github.com/Retiredems/EMS-Country-Sorter) | Sort bulk email lists by country — TLD + DNS + GeoIP detection |

---

## Support

Open an issue on GitHub for bug reports and feature requests. For licensing or transfers, message [@retiredems](https://t.me/retiredems) on Telegram.

---

<p align="center">
  Built with precision by <strong>Retiredems</strong> &nbsp;·&nbsp; Powered by PyQt6
</p>
