# Map, fog of war and companion pings

Explored terrain comes exclusively from the selected cartel's `FOW_Target.exr` RGB mask. Alpha is constant and is not exploration data. Circle, bridge and hull estimates have been removed. A missing, corrupt or unsupported EXR leaves terrain covered. Fog can be disabled as a separate view preference. LAN sharing of exploration is optional and off by default. Saved owned-location markers remain usable; unknown contents never become confirmed stock.

External red triangle pings support up to 30 sets and 200 active markers, lifetimes of 1–86400 seconds, individual or batch addition of up to 100 markers, multiple selection/removal and set filtering. Clients using the same LAN host poll shared state every two seconds. Independent hosts use explicit JSON export/import; this is not a WebRTC peer session. Recipe/planner maps can show manual ping stops and straight segments separately from verified inventory and acquisition evidence.

Dragging changes the web SVG viewBox without rebuilding markers or the result list. Zoom updates marker size. The native map and fog background are cached; typing does not rebuild them. Search coalesces input for 120 ms and uses indexed stock/source names. Legend, counts, empty state and reset remain available. Number formatters are reused per language. Performance evidence, when regenerated, is stored under `.build/map-verification`.

Saved network connections point from source to destination. Arrowheads appear at the segment midpoint and the connection layer sits outside the terrain fog mask. These lines represent saved relationships, not confirmed live deliveries. Animation can be disabled; reduced-motion preferences suppress it.

## Files beside the campaign save

- `CartelDefaults.sav`: Unreal GVAS cartel settings, XP, version, DLC and player/character assignments.
- `CartelLocalData.sav`: GVAS hints, read-hint state and FavMap favorites.
- `FOW_Target.exr`: exploration image, not a loot database.

The inspected files do not contain a `LootPoolDatabase` table. The wiki identifies that name as a game DataTable source; this does not imply that the full table is in a save. `Progress.save` can contain dynamic loot state, which differs from static build loot definitions. Missing loot probabilities, quantities and prices remain unknown.

The inspected EXR is 512×512 with HALF A/B/G/R channels and ZIP compression. Alpha is 1; RGB carries exploration. The C17 decoder follows the OpenEXR file layout. Input files are read only.

Map and reference data from [drugdealersim.com](https://drugdealersim.com).
