> **Development / Not accepted.** This review records implementation and verification evidence. Explicit user design acceptance is pending.

# Interactive design and animation review - 2026-10-09

## Current scope and evidence

This review covers shared desktop/web interaction motion and display performance. Earlier requirement-by-requirement records in DESIGN_REVIEW_HU.md remain historical evidence; passing this review does not certify every multiplayer, trading or installed-asset requirement.

The packaged local application is `release/CartelDesk.exe` (v1.1.4). Publishing a tested release does not mark this design review as accepted. Source control now has a private local Git baseline with no remote. Subsequent edits have normal VS Code diffs; changes predating that baseline cannot be reconstructed from it.

## Interaction coverage

| Surface | Interaction and motion | Verification |
| --- | --- | --- |
| Navigation and all pages | Native 190 ms top-edge transition; web 190 ms opacity entrance, triggered by navigation only | Windows navigation smoke and desktop/portrait workflow audit |
| Qt Quick buttons | 100 ms hover/selection colour and shallow pressed background scale; hit target stays fixed | QML render and native navigation checks |
| Widgets buttons and form controls | 150 ms input-transparent border pulse on hover, focus or press | Five control types, real text/key dispatch and button signal probe |
| Native popup menus | Short opening ribbon; menu input passes through | Shared event-filter coverage; no delayed actions |
| Web buttons, fields, summaries and rows | 100 ms colour/border feedback; visible focus; disclosure content fades once | Browser interaction, reduced-motion and all-page checks |
| Scrollbars and bounded lists | Native Damascus thumb colour changes; no easing on scroll position | Native/portrait bounded-panel checks |
| Map | Coordinate geometry and gestures remain direct; no global transform/width transition | Legend, filtering, locate, finance, ping and empty-state workflows |
| Production display | Real elapsed-time phases, bounded 60 Canvas paints/sec; measured values remain save-derived | 60-sample graph at simulated 60/120/144/240 Hz |
| Game clock and liquid edges | Existing original cartoon dial/flush/drip effects; motion preference retained | Chord, round trip, wash phases, gravity and eight-drop cap |
| Motion preference | Disables CSS/WAAPI/QML/native transient motion, clears active pulses and droplets | Explicit toggle and OS reduced-motion tests |

## Performance design

Full-page QGraphicsOpacityEffect capture was removed from native navigation. Transient feedback has at most six native/browser animations, input-transparent painting, no input consumption and no idle repaint loop. The web avoids canvas size/layout reads each frame: ResizeObserver maintains logical dimensions. Rendering has a fractional-time tolerance, so a nominal 60 Hz source does not drop alternating frames due to floating-point rounding. Time accumulation never depends on frame count.

Native HDR caches D3D shader-resource and render-target views until texture/size/device reset. Its presentation remains nonblocking and falls back to SDR on failure. Border effects invalidate only their small visible regions, not the whole window; detached droplets update their masks only when geometry changes. Automatic web refresh is postponed while a form field is focused or a pointer gesture is held. Explicit refresh remains available.

The expensive decorative Canvas rasterization is capped at 60 Hz even on higher-refresh displays. This is a workload bound, not a claim of native 240 FPS rendering. Physical input-to-photon delay, NVIDIA-overlay interaction and HDR luminance require a separate hardware observation.

## Accessibility and visual review

Local Barlow Regular/SemiBold, SIL OFL, use the shared phi/sqrt(phi) type hierarchy. Captions have a 12 px minimum. Hairline borders are 1 logical pixel and focus outlines 2 pixels. Decorative jungle/holographic mesh stays behind navigation; the sidebar remains fixed to viewport height and scrolls independently. Map reference lists and production job lists are keyboard-focusable named regions. Corporate hint text uses the readable muted palette.

The actual 1280 x 900 EXE preview is `media/screenshots/desktop-interaction-review.png`. Desktop and portrait layouts were checked for horizontal overflow. This is a design review, not an award claim or a guarantee of handmade cartoon-production quality.

## Results

- Targeted animation/HDR/interaction suite: 7 passed, 0 failed, 0 skipped.
- Native observed maximum input dispatch: 15 ms; maximum event-loop gap: 33 ms during simultaneous effects. These measure dispatch, not photon latency.
- Browser 60-point graph: 121 paints over a simulated two-second interval at each tested refresh rate, including the initial paint; maximum measured draw call 1.5 ms in the headless probe.
- Accessibility/layout audit: 46 desktop/portrait workflow screens, 0 axe violation groups, no JavaScript errors or horizontal overflow.
- Windows Widgets smoke: data, navigation, maps, planner controls, export and managed-server shutdown passed.

## Shared reference and tracking update

The shared read-only SQLite catalogue and persisted saved-player tracking preference are implemented. [Database, provenance, routing and verification](../REFERENCE_DATABASE.md) describes their exact scope. Native desktop and both browser layouts use the same service and 15-second save refresh. Disabling tracking withholds player and carried-storage coordinates while retaining ownership.

Installed IoStore index inspection confirmed the Item, Shop, Isla Sombra Shop and Loot Pool database assets. DataTable row extraction and automatic startup ingestion remain incomplete. Exhaustive buyer coverage, road navigation and continuous unsaved player telemetry are not claimed.
