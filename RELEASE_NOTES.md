# DDS2 CartelDesk v1.1.1

- Actual FOW_Target.exr RGB exploration in native desktop, localhost and optional LAN companion sharing. Circle/hull discovery estimates removed; invalid or missing masks fail closed. Fog has its own view toggle.
- Visible map legend, counts, empty state and reset. Ingredient search considers recorded stock and acquisition sources. Saved locations and reviewed map references use distinct marker shapes.
- Map movement preserves marker DOM. Native map/background and source terms are cached; typed filters coalesce for 120 ms and number formatters are reused. Resizable native and modern portrait layouts retain sharp text.
- External red triangle pings: sets, bulk add, multi-remove, 1–86400-second lifetime, common-host LAN polling and explicit cross-host JSON export/import. Manual route stops remain separate from verified supply facts.
- Current/named planning lists, quantities, favorites, filtering, reset and separate production plan removal; recipe inputs/equipment with independent owned/acquisition evidence.
- C17/C++17 retained with Qt 6.12 navigation and Operations views, native controls, Start/Stop, owned-process cleanup and companion QR/IP selector. One root launcher; libraries in runtime/.
- Updated 11-language labels, README, actual screenshots and Steam/LinkedIn/Nexus media. Map and reference data from drugdealersim.com. No affiliation or endorsement.

The 131 unique acceptance points are the current scope catalog. The standalone Windows chunked-save transaction passes parser, verification, backup and atomic-replace tests; its network send/receive UI and crash recovery remain pending. WebRTC peer-session UI/wire integration, physical-phone testing and hardware-specific FPS verification also remain pending. The released UI does not transfer or replace a campaign. Source code remains private; only the latest release is public.

## Procurement and courier planning preview — 2026-10-08

Planner and recipe requirements now include map reference acquisition sources, with general same-name item variant matching. Reference stock and prices remain unknown; owned quantities retain exact IDs and units. Saved player positions support selectable couriers and multiple owned hideout endpoints. The map displays pickup/delivery legs. This is a greedy straight-line planning estimate requiring stock verification, not road pathfinding or confirmed availability. Details: [supply planning](docs/SUPPLY_CHAIN.md). Included in v1.1.1.


Latest update (v1.1.1): independent viewport scrolling in desktop navigation and content; readable recipe rows and wrapping action controls; visible source-to-target network arrows outside the fog mask; acquisition references matched across same-name item variants; saved courier positions and selectable hideout destinations for pickup/delivery planning. Quantities and prices absent from the reference remain unknown. Courier routes are greedy straight-line estimates, not road navigation or confirmed live player positions. Map and reference data from drugdealersim.com (https://drugdealersim.com). No endorsement or affiliation with TGS, ByteRunners or Movie Games SA.

Validation for v1.1.1: 26/26 native, Windows desktop and browser regression tests passed on 2026-10-08. Actual desktop/web/portrait screenshots regenerated without JavaScript errors or horizontal overflow.

