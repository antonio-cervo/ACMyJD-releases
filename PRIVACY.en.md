# Privacy Policy — JD Link Sender

*Versione italiana: [PRIVACY.md](PRIVACY.md)*

Last updated: 2026-11-26

JD Link Sender is a browser extension that sends links and encrypted containers to a
JDownloader 2 instance (ClickNLoad2 interface) chosen and configured by the user.

## Data processed

- **Web page content**: when the user explicitly clicks the "Send to JDownloader" context menu
  item (on a link, a text selection, or an area of the page), the extension's toolbar icon, or
  its keyboard shortcut, the extension reads the HTML/DOM
  content of that page or link to detect encrypted CNL2 blocks, link lists and any archive
  password ("Password: …"), which is shown in the popup and only sent to JDownloader. This reading only
  happens on the user's explicit action, never in the background or on unselected pages.
- **Websites' Click'n'Load requests**: when a website sends links to a local JDownloader
  (`http://127.0.0.1:9666/flash/...`), usually because the user pressed its Click'n'Load
  button, the extension reads the data of that request only (links or encrypted container) and
  shows it in the confirmation popup. No other network request is read. This feature can be
  turned off on the Options page.
- **JDownloader configuration**: the JDownloader instance URL (and optional fallback URL) entered by the user on the Options
  page is saved in the browser's synced storage (`chrome.storage.sync`), tied to the user's own
  browser account/profile, so it can be reused across sessions.
- **Temporary popup state**: the links/containers awaiting confirmation are passed from the
  background script to the confirmation popup via the browser's session storage
  (`chrome.storage.session`), and cleared immediately after being read.
- **Send history and hoster preferences**: the addresses of sent links with their package name
  (for encrypted containers only a SHA-256 fingerprint, not their content) and the hosters the user deselected are stored
  in the browser's local storage (`chrome.storage.local`, not synced), to flag already-sent links
  and restore previous choices. History entries expire after 60 days and can be cleared at any
  time from the Options page. This data never leaves the browser.
- **Pending sends**: if JDownloader cannot be reached, the links (or encrypted containers) to be
  sent, with the archive password if any, stay in the browser's local storage (`chrome.storage.local`) until the send succeeds or
  the user removes them on the Options page. They are only ever sent to the configured
  JDownloader instance.

## Where the data goes

The extracted links and containers are sent **exclusively** to the JDownloader instance the
user specified on the Options page (on a local network or remotely, e.g. via a tunnel owned by
the user). No data is ever sent to the extension developers or to third-party servers.

## Data sharing

We do not sell, transfer, or share any user data with third parties. We do not use the data for
advertising, profiling, creditworthiness, or lending purposes.

## Contact

For questions about this policy, open an issue at
https://github.com/antonio-cervo/ACMyJD-releases/issues
