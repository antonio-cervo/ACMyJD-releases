# Privacy Policy — JD Link Sender

*Versione italiana: [PRIVACY.md](PRIVACY.md)*

Last updated: 2026-07-08

JD Link Sender is a browser extension that sends links and encrypted containers to a
JDownloader 2 instance (ClickNLoad2 interface) chosen and configured by the user.

## Data processed

- **Web page content**: when the user explicitly clicks the "Send to JDownloader" context menu
  item (on a link, a text selection, or an area of the page), the extension reads the HTML/DOM
  content of that page or link to detect encrypted CNL2 blocks or link lists. This reading only
  happens on the user's explicit action, never in the background or on unselected pages.
- **JDownloader configuration**: the JDownloader instance URL entered by the user on the Options
  page is saved in the browser's synced storage (`chrome.storage.sync`), tied to the user's own
  browser account/profile, so it can be reused across sessions.
- **Temporary popup state**: the links/containers awaiting confirmation are passed from the
  background script to the confirmation popup via the browser's session storage
  (`chrome.storage.session`), and cleared immediately after being read.

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
