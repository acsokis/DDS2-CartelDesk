# Golden-ratio responsive layout

The local release uses a shared proportional rhythm across native widgets, desktop QML, browser pages and the phone companion. Existing colors, brand effects and animations are retained.

- Layout reference: phi = 1.61803398875. Large split views use the practical 5:3 / 3:5 approximation. The desktop companion card targets 38.2% of the upper instrument row, bounded to 300-460 pixels. Corporate metrics use the full width below it; narrow windows move pairing into a dialog.
- Type hierarchy: successive levels use sqrt(phi), about 1.272. Body, subheading, heading, title and large metrics form the scale. Captions remain at least 12 CSS/device-independent pixels. Body text remains at least 14 pixels in compact native windows, 15 on desktop web and 16 on the phone.
- Spacing: an 8-pixel base grows by phi into medium and large gaps. Responsive spacing and main padding use these tokens.
- Window scaling: native presentation scales within 0.93-1.13; web typography uses bounded fluid viewport sizes. DPI scaling remains handled by Qt/the browser. Text stays sharp and layouts reflow instead of stretching a screenshot.
- Usability limits: touch controls stay at least 44 pixels high. Icons, hairline borders, map coordinates, QR geometry, scrollbar grips and minimum panel sizes retain functional limits rather than forcing every measurement into a ratio.

The existing Segoe UI/system body and Bahnschrift/Impact display families remain in use, with system fallbacks. No downloaded font, font service or additional font license is needed for this change.

Native style updates are coalesced during resize and only repolish widgets when the rounded body size changes. QML and CSS use shared size tokens. Existing motion-off and reduced-motion behavior is preserved.

Operations detail panels use three equal columns for owned inventory, saved locations and data warnings, each with an independent bounded scroll area. Very narrow content below 600 pixels stacks the panels. Unchanged production samples show explicit states (no queue reduction, no new work, or timers changing) instead of a misleading zero-per-minute readout. Numeric zero remains available to the measurement logic; positive observed rates retain their game-minute units. A green reduction curve appears only after a positive reduction is recorded.

Operations vertical allocation now follows available window height instead of fixed 350/660 pixel rows. Production is bounded at 460?620 pixels, and the report fills remaining space with a 550 pixel minimum; smaller windows scroll. Executive metrics use a two-column/three-row grid alongside three detail columns when content width is at least 950 pixels. Connection QR content stays hidden until requested.
