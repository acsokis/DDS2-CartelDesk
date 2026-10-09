# Typography and proportion system

CartelDesk uses phi = 1.61803398875 for major spacing and size relationships, and sqrt(phi) for adjacent typography levels. This is a hierarchy system, not uniform scaling of the entire window. Responsive layouts preserve readable text, bounded scroll areas and practical control sizes. Map geometry and chart values are never changed for aesthetic proportions.

The locally bundled Barlow Regular and SemiBold font kit is unmodified and licensed under the SIL Open Font License 1.1. Source: https://github.com/google/fonts/tree/main/ofl/barlow. The license accompanies the font files in assets/fonts/OFL.txt inside the read-only web asset container. Qt embeds both font faces as resources; browsers load them locally without third-party requests. System fonts remain fallback options. The existing wordmark artwork and symbolic icons retain their established rendering.

Body text starts at 15 logical pixels, captions retain a 12 pixel floor, adjacent headings step by sqrt(phi), and major headings by phi. Borders are 1 logical pixel, focus indicators 2 logical pixels with a 3 pixel offset. Holographic sidebar grids stay low contrast behind navigation. Animations remain controlled by the existing motion setting.

Validation: the local release build succeeded. Web animation and asset container tests passed (2 tests). The Windows Widgets integration test passed, including data loading, map/planner controls, ZIP export and owned-server shutdown. The 1280 x 900 native preview was visually inspected. This system does not imply an award or guarantee that every individual legacy control already uses a design token.
