# Acquisition sources and multi-courier supply planning

The planner, recipe requirements and desktop acquisition view combine saved shop offers with stock references used by map search. This applies to all items, not just ethanol. Catalogue variants with the same verified name can share acquisition searches. Owned quantities still require the exact item ID and unit: package sizes and substances measured in grams are never converted automatically.

A wiki reference does not prove current stock or price. Missing values remain unknown. A source must belong to a saved known vendor, a location explored in the EXR mask, or an explicitly enabled spoiler view. Hidden sources must not enter the plan.

## Using the planner

1. Add shopping-list items or create a recipe-based production plan.
2. Select one or more couriers and owned destination hideouts in the planner's logistics panel. On desktop, use Ctrl-click for multiple selections.
3. Calculate the plan. An empty selection allows all eligible saved players and owned hideouts with known coordinates.
4. Show the plan on the map to display courier → shop/owned storage → destination legs and their markers.
5. Double-click a source or use Locate on map. Navigation clears search, category and favorite filters that would conceal the target.

The algorithm first chooses the pickup covering the most unresolved list entries, then assigns an eligible nearby courier and destination using saved positions. A courier's next trip starts at the previous delivery endpoint. Production requirements retain their designated production hideout; another selected endpoint does not override it.

## Accuracy limits

Routes are greedy straight-line estimates, not road navigation or a globally optimal route. Items use `VERIFY_AT_PICKUP`: stock, package-to-gram conversion, obtainable quantity and carrying capacity still need verification. Multiple destinations are supported; manual list entries go to an eligible nearby selected destination rather than being duplicated at every endpoint.

Player positions come from `SavedPlayerLastPosition`. Online presence is unknown. A player with a saved position can appear even with an empty inventory.

## Validation

- `tests/check_supply_chain.cjs`: reference sources, same-name variants, unit separation, saved player positions, selected endpoints, hidden sources and unknown couriers.
- `tests/check_design_workflows.cjs`: desktop/portrait controls, map navigation and pickup/delivery legs.
- `tests/check_widgets.cjs`: actual Windows Qt application, map markers/legend, navigation, save reading and owned-server shutdown.

Map and reference data from [drugdealersim.com](https://drugdealersim.com). No endorsement or affiliation with TGS, ByteRunners or Movie Games SA.
