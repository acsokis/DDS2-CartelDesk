# Shared reference database and saved player tracking

The C17 service loads an immutable SQLite reference database from `runtime/CartelDesk.assets`. SQLite is statically linked; users need no database server, Python, Node.js or extra SQLite DLL. Native desktop, localhost web, portrait companion and the Steam overlay consume the same service model.

## Data and relationships

The current catalogue contains 720 item identifiers, 1047 reference places, 187 recipes, 540 ingredient/output relationships, 1981 directional vendor offers and six curated measurement facts. Sources and checked dates are stored separately. Foreign keys, schema version, database identity and integrity are checked before use. A failed build preserves the previous database through a temporary file and atomic replacement.

Item IDs are authoritative. Names are searchable aliases, not permission to convert different pack sizes or grams into pieces. Missing recipe IDs, prices, quantities, coordinates and yields remain NULL. An item seen only as a reference can exist as an explicitly marked stub. Wiki stock establishes `vendor_sells`; independently evidenced acceptance establishes `vendor_buys`. One direction never creates the other. A name-only buyer with ambiguous/no location remains unplaced.

Existing JSON contracts are retained as compatibility documents in the database, generated alongside its normalized tables in one transaction. Existing save-backed ownership and logistics graphs remain disposable runtime models: the immutable reference database never contains a player's campaign, configuration, inventory or personal identifiers. Owned inventory and acquisition sources remain separate.

`GET /api/reference` reports the validated schema, catalogue version and counts. Same-origin `POST /api/reference` with `{"item":"Knife"}` looks up independently sourced buyer/seller offers through bound SQL parameters. `GET /data/knowledge.json` serves the database-backed compatibility catalogue. Raw SQL and unrestricted file access are not exposed.

## Tracking and routes

**Saved player tracking** is one persisted host setting, available in the native map and both web layouts. It also works in `/?overlay=1`, with the existing overlay opacity control. Position updates come from newly read game saves, with the normal 15-second refresh. Save modification time is exposed when known; online presence stays unknown. This is not continuous game-memory telemetry.

Turning tracking off clears player and carried-storage coordinates from the companion graph and map tables, including session snapshots. Ownership and inventory remain available. Turning it on restores saved positions. A courier without a known origin cannot receive a fabricated route.

The shared supply planner covers shopping-list items per pickup, assigns saved couriers, accounts for finite owned stock and routes pickups to selected production hideouts. Multiple couriers and endpoints remain supported. Route legs preserve departure, pickup and destination direction. Distances are straight-line estimates; road/boat navigation, carrying capacity and current shop stock are not guaranteed where the save/reference does not establish them.

## Installed game inspection

A bounded read-only directory-index scan identified 43,464 assets in the installed main IoStore container, including `Content/DataTables/Databases/LootPoolDatabase.uasset`, `ItemDatabase.uasset`, `ShopDatabase.uasset` and `IslaSombra/IS_ShopDatabase.uasset`. Only the roughly 2 MB directory index was read, not the entire 17 GB UCAS. The local scan report is private and excluded from distribution.

The development scanner accepts the observed unencrypted version-5 layout, rejects invalid/cyclic handles and bounds reads. It does not extract DataTable rows, images or package payloads. TOC lookup seeds are not campaign/loot RNG seeds. Direct row decoding and automatic startup ingestion remain unfinished; the current release uses the curated catalogue and supplied buyer evidence. Finding an asset name does not verify its prices or loot probabilities.

## Verification

Database build tests cover foreign keys, exact compatibility export, separate buy/sell evidence, unknown component IDs and preservation after failed import. Runtime tests load SQLite directly from the packed distribution, exercise lookup and SQL-injection rejection, and toggle tracking in desktop web, portrait companion and Steam-overlay mode. Synthetic save positions verify that disabling tracking also removes carried-storage coordinates and sync positions. No user's live save is modified.

Map and reference data from [drugdealersim.com](https://drugdealersim.com). Consult the live site for updated data. No endorsement or affiliation with TGS, ByteRunners or Movie Games SA is implied.

Implementation sources: [SQLite](https://www.sqlite.org/download.html), [CUE4Parse IoStore format definitions](https://github.com/FabianFG/CUE4Parse/tree/master/CUE4Parse/UE4/IO). These sources describe the software/format; they do not license underlying game data.
