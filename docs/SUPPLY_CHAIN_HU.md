# Beszerzési források és többjátékos ellátási terv

A planner, a receptigények és a desktop Beszerzés és telepítés nézet a mentett bolti ajánlatok mellett a térképes kereső wiki-készletlistáját is használja. Ez általános termékfeloldás: a tudásbázis azonos nevű termékváltozatai lehetséges beszerzési forrásként együtt kereshetők. A csomagméretet és az alapanyag grammban tárolt változatát nem alakítjuk egymásba. A saját készlet elszámolása továbbra is pontos item ID és egység alapján történik.

A wiki-referencia nem bizonyít aktuális bolti készletet vagy árat. Ezek null/Ismeretlen értékek maradnak. A forrásnak mentésből ismert bolthoz, EXR szerint felfedezett helyhez kell tartoznia, vagy a felhasználónak kifejezetten engedélyeznie kell a spoilereket. A rejtett helyek nem kerülhetnek a tervbe.

## Használat

1. Adj hozzá tételeket a tervezési listához, vagy készíts receptalapú gyártási tervet.
2. A Tervező Szállítási logisztika paneljén válassz egy vagy több beszerzőt és célbúvóhelyet. Desktopon Ctrl/kattintás használható több kijelöléshez.
3. Számítsd ki a tervet. Üres kijelölés esetén az ismert, mentett koordinátával rendelkező játékosok és saját búvóhelyek használhatók.
4. A Terv megjelenítése a térképen a beszerző → bolt/saját tároló → célbúvóhely lábakat és az érintett jelölőket mutatja.
5. A forrássorra dupla kattintással vagy a térképi paranccsal ugorhatsz. A navigáció törli a találatot elrejtő keresési/kategória/kedvencszűrést.

Az algoritmus először a legtöbb még megoldatlan listatételt lefedő megállót választja. Ezután a mentett pozíciók alapján legközelebbi beszerző és cél kerül hozzá. A beszerző következő feladata az előző kiszállítás céljáról indul. A gyártási tervhez tartozó szükséglet a saját kijelölt gyártási búvóhelyére kerül; más kiválasztott endpoint nem írja ezt felül.

## Pontossági korlátok

Ez heurisztikus, légvonalbeli ellátási terv. Nem játékbeli útgráf vagy globálisan optimális útvonalkereső. A terv tételeinek állapota `VERIFY_AT_PICKUP`: a bolti készlet, csomag–gramm átváltás, tényleges felvehető mennyiség és játékos teherbírás ellenőrzése még szükséges. A több célpont választása lehetséges; a manuális listatételek a megfelelő legközelebbi kiválasztott célhoz kerülnek, nem kerülnek automatikusan minden célhoz duplikálva.

A játékos helye a `SavedPlayerLastPosition` mentett pillanatképe. Az online jelenlét ismeretlen. A pozícióval rendelkező, de üres inventoryjú játékos is megjelenhet.

## Ellenőrzések

- `tests/check_supply_chain.cjs`: referenciaforrás, általános termékváltozat-feloldás, egységek szétválasztása, mentett játékospozíció, kijelölt endpoint, rejtett forrás és ismeretlen beszerző.
- `tests/check_design_workflows.cjs`: desktop/portrait supply UI, térképre váltás és két útvonalláb; képek `.build/supply-verification` alatt.
- `tests/check_widgets.cjs`: tényleges Windows Qt alkalmazás, térképi jelölők/legenda, nézetváltás, mentés-olvasás és szerverleállás.

Map and reference data from [drugdealersim.com](https://drugdealersim.com).
