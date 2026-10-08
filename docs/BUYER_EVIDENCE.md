# Vendor purchases and sales

Trade direction always uses the vendor's perspective: **Vendor sells** means the player can buy from the vendor; **Vendor buys** means the vendor accepts the player's item.

Accepted items, owned inventory, price, purchase budget and location are separate facts. An accepted item remains a buyer result when the player owns zero units or its price is unknown. Shop assortment cannot establish buyback. Manual sell quotations are marked `unverified`, not confirmed acceptance.

## Recorded observations

The user supplied an in-game SELL screenshot for **Tom the Tech**, recorded on 2026-10-08. Its visible rows confirm: Hammer 800 B, Crowbar 500 B, Bolt cutter 800 B, Shovel 800 B, Wrench 500 B, Pitchfork 500 B, Knife 800 B, Military knife 1,000 B, Cleaver 800 B, Baseball bat 1,000 B, Metal pipe 100 B and Paddle 100 B per piece. These are observed snapshot prices, not a guarantee of present prices, budget or reputation access. The screenshot is scrolled; the list is not asserted to be exhaustive.

The user also reported that **Alejandro Flores** accepts empty bottles. The four catalogued empty-bottle IDs are recorded as a user report, with unknown prices and unknown purchase budget. The exact variants have not been independently verified by screenshots.

Data lives in `web/data/companion-knowledge.json` under `buyer_observations`. Each observation requires a named vendor, source, date, evidence state and exact known item IDs. Price may be null. Observations are never copied into the vendor's sale assortment.

## Location and coverage

Named observations bind only to a unique matching vendor name/alias in the current model. Otherwise a separate reference entity is created without coordinates. Map results list these unplaced buyers instead of inventing pins or routes. A correctly identified mapped vendor can be given its exact observed name through the existing alias controls.

The map catalogue was inspected for separate buying/acceptance fields; its available inventory entries contain assortment information, not an exhaustive buyer database. The wiki's shop overview and selling tutorial do not specify every vendor's accepted item list. The remaining vendors therefore stay unverified; this update is **not a completed audit of every buyer**. Supporting references: [DDS2 shops](https://drugdealersim.com/wiki/dds2/shops-vendors) and [DDS2 selling tutorial](https://www.drugdealersim.com/wiki/dds2/game-tips-tutorials).

The desktop and web vendor direction views expose both directions, source evidence and unknown location/price. The web Sell valuables entry opens the same buyer catalogue. Game saves remain read only.
