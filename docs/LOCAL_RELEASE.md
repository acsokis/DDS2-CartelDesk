# Local release

Run `release/CartelDesk.exe`. The release folder is the sole retained local application package. Tests use this folder by default; no preview installation is needed.

The package includes the current asset quotation report, shared shopping-list logistics and directed map legs. The same verified package is distributed by the latest GitHub release. Unpriced assets, liabilities and reference-only shop stock remain unknown.

The map now groups shops and trading NPCs under vendor, distinguishes acquisition from listed buyback quotations, supports multiple category/item selections and retains expanded web panels. The native layer menu stays open for repeated toggles. See [map filters](MAP_FILTERS.md).

Build intermediates may be recreated temporarily by the build tools. They are not required to run the application. Keep the source, third-party dependencies, compiler/Qt SDK and private recovery archives for future development and Windows reinstall recovery.

The browser payload and read-only SQLite catalogue are packed in `runtime/CartelDesk.assets`. Loose `web/` copies and review packages are not needed in the final local release. Guides, LGPL corresponding source archives, font licenses, configuration and source/recovery backups are retained.


## Portable runtime container

The distributed `CartelDesk.exe` contains the DLLs, Qt plugins, backend and verified asset container in a bounded PE overlay. The first launch verifies every entry with SHA-256, writes a fresh staging directory, flushes its files and atomically renames it to `runtime/`. No application DLL loads before this succeeds. An interrupted extraction leaves the previous runtime untouched. Subsequent launches reuse the runtime without repeating extraction or affecting animation frames.

Keep the application in a writable folder. First launch requires approximately 140 MB of additional free space. Qt libraries remain dynamically linked and replaceable in `runtime/` after extraction. `CartelDesk.exe --unpack-runtime` extracts without opening the interface. For an upgrade, close CartelDesk, keep your local configuration, remove the old runtime directory and then launch the new EXE. Do not replace DLLs while the application is running.

This is packaging and integrity checking, not DRM, encryption or a digital publisher signature. SHA-256 checksums distributed with the official release are the external authenticity reference. Native project source and private saves are not distributed.
