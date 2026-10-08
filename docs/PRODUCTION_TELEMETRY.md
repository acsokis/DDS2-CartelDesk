# Corporate operations and production flow

Operations places a compact production instrument and phone-pairing card in one top row. Corporate cash, inventory mass, trash mass and asset quotations use the full width below it. Workforce/estate counts use a compact grid. Inventory, location, attention and production lists have bounded scroll areas. Compact windows expose phone pairing through the Phone QR button, including IP selection, and return the card to its normal place after closing.

## Game-time measurements

The saved WorldTimeManager exposes CurDayInt and CurDayPercent. Valid day/percentage values map to elapsed game minutes as `day * 1440 + percentage * 14.4`. This is game time, not wall-clock time or the application's polling interval.

The instrument shows active saved jobs and known queued quantities; tracked queue reduction per game minute; new queue/increases per game minute; and per-job quantities, raw timers and signed raw-timer changes per game minute. Up to 60 session samples plot queued units in amber and observed reduction rate in green, on independent vertical scales and a shared game-time axis.

A rate requires two comparable saves with advancing game time. First samples, paused/invalid clocks, ambiguous IDs and unknown quantities stay unresolved. Repeated UI redraws do not add samples. Loading earlier game time or changing campaign resets history.

Disappeared jobs are counted separately and excluded from the reduction rate. Queue depletion and raw-timer movement do not prove completed output: cancellation or edits can affect data. The raw timer's physical unit remains unverified. The instrument does not invent output kg/min, completion percentages or completion times.

The app remains save-only and read-only. The display changes when the game writes another save; polling an unchanged save cannot provide live in-game telemetry. Optional scanner and brand motion remain decorative and follow the Animations preference.

Operations detail panels use three equal columns for owned inventory, saved locations and data warnings, each with an independent bounded scroll area. Very narrow content below 600 pixels stacks the panels. Unchanged production samples show explicit states (no queue reduction, no new work, or timers changing) instead of a misleading zero-per-minute readout. Numeric zero remains available to the measurement logic; positive observed rates retain their game-minute units. A green reduction curve appears only after a positive reduction is recorded.

## Cartoon game clock

The desktop production instrument includes a scalable circular sun/moon character. Daytime is 06:00?18:00. A daily sun break starts at 16:20 and a moon break at 04:20, lasting 20 saved game minutes: two minutes of comic ignition, sixteen of smoking with drifting embers, and two of stubbing out. These are decorative scenes; their stage follows saved game time without inventing live clock progress. Animation preferences disable movement, leaving a static time-appropriate illustration. Missing game time shows an unresolved clock. Drawing uses a small vector canvas with a 15 FPS timer active only on the visible Operations page.

The cartoon clock adds elastic squash/stretch, blinking and expressive eyebrows, exaggerated puffed cheeks, drifting smoke rings, ignition sparks and a comic stub-out impact. Its original sun/moon characters retain the existing colour palette, saved-time schedule and animation-off behaviour.

The sun uses a gold dial and the moon a silver dial, each with a light-to-dark metallic gradient, hour ticks and slowly rotating radial decoration. Rotation follows the animation preference.

The animated dial sits directly beside the saved day/time label in the production header, with the timer observation status on a separate line. The sun and moon switch with saved daytime/nighttime.

When saved game time is unavailable, a decorative sun/moon coin-spin and trick handoff runs after a random 7?13 minutes spent on the visible Operations page with animations enabled. Each eight-second scene alternates the recipient: sun to moon, then moon to sun. Disabling animation or leaving the page cancels an active scene and pauses its waiting countdown. The clock label stays unavailable; this does not invent game time.

An observed advancing saved-time day/night change triggers a 32-second decorative coin-spin and trick handoff (moon to sun at dawn, sun to moon at dusk). Daytime boundaries remain 06:00 and 18:00; the 04:20/16:20 scenes remain unchanged. Missing clocks, repeated saves and time rollback do not trigger this transition. The game-time label is not extrapolated; only the decorative scene uses a 30 FPS presentation timer on the visible Operations page. Unknown-clock fallback remains separately scheduled.
