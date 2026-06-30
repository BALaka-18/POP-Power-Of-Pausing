# Privacy Policy — Break Reminder

**Last updated:** June 2026 - v1.0.0

## Summary

Break Reminder does not collect, store, transmit, or share any personal data. Everything the extension needs to function is stored locally in your own browser, using Chrome's built-in `storage.local` API. No data ever leaves your device.

## What data is stored locally

The extension stores the following information, entirely within your browser:

- **Settings** — your chosen work interval and break duration
- **Break activity** — a randomly selected activity (drink water, stretch, walk, rest eyes) shown during each break
- **Skip log** — timestamps of breaks you've skipped, used only to power the optional analytics page within the extension
- **Break log** — timestamps and durations of completed breaks, used only to power the optional analytics page within the extension

This data is stored using `chrome.storage.local`, which means:

- It is saved only on your own computer, inside your Chrome profile
- It is never transmitted to any server, including ours — we don't operate a server
- It is automatically deleted if you uninstall the extension
- No other website, extension, or third party can access it

## What we do NOT do

- We do not collect any personally identifiable information (name, email, IP address, etc.)
- We do not use analytics or tracking services (no Google Analytics, no third-party trackers)
- We do not sell, rent, or share any data with anyone, because no data ever leaves your browser
- We do not require account creation or sign-in of any kind
- We do not display ads

## Permissions explained

The extension requests the following Chrome permissions, used strictly as described:

| Permission | Why it's needed |
|---|---|
| `storage` | Save your settings and break history locally |
| `alarms` | Reliably trigger break reminders on a schedule, even if the browser is idle |
| `tabs` | Detect open tabs so the break overlay can be displayed |
| `scripting` | Inject the break reminder overlay into web pages |
| `host_permissions` (`<all_urls>`) | Allow the break overlay to appear on any website you're browsing, regardless of domain |

None of these permissions are used to read, log, or transmit the content of the pages you visit. The extension only interacts with the page to display its own break overlay UI.

## Changes to this policy

If this policy changes in the future, the updated version will be posted at this same location, with a revised "Last updated" date.

## Contact

If you have questions about this privacy policy, please open an issue on the project's GitHub repository.
