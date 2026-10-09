# v1.1.4 verification

Windows x64 release verified on 9 October 2026.

- Packed portable EXE: 307 runtime files embedded; first launch extracts through a fresh staging directory and atomic rename.
- Per-entry SHA-256 validation; damaged bytes, traversal, reserved Windows device paths, truncated footer and stale runtime marker rejected.
- Final launcher suite: 4/4 passed, including real Windows Qt 6.12 native startup, Widgets/QML pages, map filters, QR behavior, export and owned-backend shutdown.
- Combined packaged suite before the final cache-version guard: 12/12 passed; final launcher changes independently retested afterward.
- Reference database builder: 4/4 passed. SQLite catalogue integrity and foreign-key checks passed.
- Actual browser reference/tracking checks passed on desktop, portrait companion and Steam-overlay routes; vendor direction and unknown prices retained.
- Visual/media audit: 46 captures, no detected JavaScript errors, horizontal overflow or automated accessibility violations within that audit.

These are the checks performed, not a claim that every possible state or all historical acceptance points were tested. Automated accessibility checks do not replace manual accessibility review. Physical HDR luminance, phone hardware and NVIDIA overlay performance were not certified.

Installed game index confirms ItemDatabase, ShopDatabase and LootPoolDatabase asset names. Their table rows remain undecoded. Saved-player tracking updates from save snapshots; unsaved live position and online presence remain unknown. Routing remains an estimate where road topology, stock or capacity is unavailable.

Native project source, private recovery files, live saves and user configuration are excluded from the public release.
