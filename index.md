---
title: Home
---

# Privacy Policy - POP

**Last updated:** June 2026

## Summary

POP does not collect, store, transmit, or share any personal data. Everything the extension needs to function is stored locally in your own browser, using Chrome's built-in `storage.local` API. No data ever leaves your device.

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

## Remote code

This extension does not execute any remotely hosted code. All JavaScript - including the bundled Chart.js library used to render the analytics page - ships inside the extension package itself and is reviewed as part of the Chrome Web Store submission. No scripts are fetched from external URLs at runtime.

## Single purpose

This extension has a single purpose: to periodically remind users to take short breaks from their screen by displaying a brief, dismissible overlay. It does not perform any function unrelated to this purpose.

## Chrome Web Store dashboard — field-by-field justifications

The Chrome Web Store "Privacy practices" tab asks for a plain-language justification for each requested permission. Use the text below directly in those fields.

**Single purpose description:**
> POP periodically displays a brief, dismissible overlay to remind users to take short breaks from their screen — for example, to drink water, stretch, walk, or rest their eyes. This is the extension's only function.

**`alarms` justification:**
> Used to reliably schedule break reminders at a user-configured interval (default 30 minutes), even when the service worker has been unloaded. The Alarms API is the only mechanism that guarantees this timing persists across browser idle periods and service worker restarts under Manifest V3.

**`storage` justification:**
> Used to save the user's chosen settings (work interval, break duration) and a local log of completed/skipped breaks, so the extension remembers preferences between sessions and can power the optional in-extension analytics view. All data is stored locally via `chrome.storage.local` and never transmitted anywhere.

**`tabs` justification:**
> Used to enumerate open tabs so the break overlay can be displayed across all of them simultaneously when a break starts, and to skip injecting into restricted pages (e.g. `chrome://` URLs) where content scripts cannot run.

**`scripting` justification:**
> Used to inject the break overlay (a self-contained Shadow DOM UI) into the active page when a break begins. This is the only use of the scripting permission — no page content is read, modified, or extracted.

**`host_permissions` (`<all_urls>`) justification:**
> The break overlay must be able to appear regardless of which website the user is currently viewing, since breaks are time-based and not tied to any specific site. Broad host access is required so the reminder works consistently across all of a user's normal browsing, not just an allow-listed set of domains. No page content is read or transmitted; the permission is used solely to display the extension's own overlay UI.

**`remote code` justification:**
> This extension does not use remote code. All scripts, including the bundled Chart.js library for the analytics page, are packaged locally within the extension and contain no calls to external script sources at runtime.

**Data usage checklist (Privacy practices tab):**
> All toggles for "Personally identifiable information," "Health information," "Financial and payment information," "Authentication information," "Personal communications," "Location," "Web history," and "User activity" should be left **unselected / No** — none of these categories are collected, because the extension does not transmit any data off the user's device.

## Changes to this policy

If this policy changes in the future, the updated version will be posted at this same location, with a revised "Last updated" date.

## Contact

If you have questions about this privacy policy, please open an issue on the project's GitHub repository.
