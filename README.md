# Privacy Policy — QR CCCD Scanner

**Effective date:** 2026-04-20
## TL;DR

**This extension does not collect, transmit, or sell any of your data.** Everything runs locally in your browser. QR codes and any parsed information (including Vietnamese CCCD details) are processed entirely on your device and never sent to any server — not ours, not anyone else's.

---

## What data the extension processes

When you use the extension, the following data is processed **locally in your browser**:

| Data | When processed | Where it goes |
|---|---|---|
| QR code image | When you right-click an image or capture an area | Decoded in-browser, discarded from memory after decode |
| QR code raw text | After decoding | Saved to `chrome.storage.local` (your device only) |
| Parsed CCCD fields (ID number, name, date of birth, address, gender, etc.) | When QR content matches Vietnamese CCCD format | Displayed in side panel; saved to `chrome.storage.local` |
| Screenshot of the current tab | Only during the "Capture QR Area" flow | Held in memory just long enough to crop to the selection and decode; then discarded |

## What data we do NOT collect

- ❌ **No telemetry** — no analytics, no crash reports, no usage statistics
- ❌ **No network transmission** — the extension makes zero HTTP, WebSocket, or any network call to any server
- ❌ **No cookies / no tracking** — we do not set any cookies or tracking identifiers
- ❌ **No cloud sync** — data is stored in `chrome.storage.local`, which is NOT synced across your devices
- ❌ **No third-party services** — all code runs inside your browser; no CDN fetches at runtime
- ❌ **No account / no login** — the extension requires no registration

## What permissions the extension uses and why

| Permission | Purpose |
|---|---|
| `activeTab` | Access the currently-focused tab only when you invoke the extension (right-click, keyboard shortcut, or action icon) |
| `scripting` | Inject the QR decoding library (`jsQR`) into the active tab on demand |
| `contextMenus` | Add the "Scan QR CCCD" option to the right-click menu on images |
| `storage` | Save your latest scan result so you can view it in the side panel |
| `sidePanel` | Display scanned results in Chrome's built-in side panel |
| `clipboardWrite` | Copy fields to clipboard when you click a "Copy" button |
| `<all_urls>` (optional) | Scan QR codes on any website — **requested only when you use the feature on a new site, per user gesture** |

## How scanned data is stored

- Scanned results are stored via `chrome.storage.local`, which keeps data **only on your computer**
- The extension keeps the **latest scan** and up to **10 recent scans** in local history
- You can **clear all data** at any time by clicking the "Clear" button in the side panel, or by removing the extension

## How to clear your data

1. Open the extension side panel
2. Click **"Clear"** to remove all stored scan data
3. Alternatively, go to `chrome://extensions` → remove the extension to wipe everything

## Third-party libraries

The extension bundles the following open-source libraries **locally** (no CDN, no runtime fetch):

- **jsQR** (Apache-2.0 License) — QR code decoder
- **React** (MIT License) — UI framework
- **IBM Plex Sans** (OFL-1.1 License) — typography

None of these libraries make network calls in the way they're used here.

## Children's privacy

This extension does not target children under 13 and does not knowingly process data from children.

## Changes to this policy

Any changes to this policy will be reflected in the extension's repository. The "Effective date" above will be updated accordingly.

## Contact

Questions about privacy? Open an issue on the repository or email `linhnn61@vnggames.com`.

---

## Why does a zero-collection extension need a Privacy Policy?

Per Chrome Web Store policy, **any extension that requests a permission giving it potential access to user data** (including `storage`, `clipboardWrite`, `<all_urls>`, `activeTab`) must publish a privacy policy — even if the extension never transmits data anywhere. This policy exists to **transparently disclose that we don't collect anything**, so users can verify before installing.
