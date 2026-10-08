# Map filters and vendor direction

Shops, shopkeepers and vendor records share one **vendor** category. Their names and saved/reference locations remain distinct. Non-trading NPCs retain their NPC category.

Web category and required-item lists support multiple selections. Clicking or tapping an option toggles it without requiring Ctrl. Selected categories and items match any selected value within their group; category, item, text and trade direction must all match together. The All entry clears its group. Clear map filters resets the trade-direction selection too.

The native layer menu stays open while multiple checkboxes are toggled with the mouse or Space/Enter. Escape or a click outside dismisses it. Web expandable panels retain their open/closed state during redraws and local model updates within the current page session.

**Vendor sells** identifies acquisition offers and wiki reference stock. **Vendor buys** identifies separately recorded acceptance evidence or a clearly unverified catalogue sell quotation. Acceptance does not require owned stock or a known price. A Knife in a shop's reference stock does not establish that the shop buys knives back. Knife and Military knife remain separate item IDs. The selected item and direction must match the same offer: a knife seller that buys a different item is not a knife buyer.

Reference prices/stock and manual catalogue quotations are not live availability. Missing buyback information remains unknown. Disabling fog exposes reference pins intentionally; it does not change the game's exploration data.

Observed buyer lists and their evidence limits are documented in [Buyer evidence](BUYER_EVIDENCE.md). Buyers without verified coordinates appear as unplaced results; no map location is invented.
