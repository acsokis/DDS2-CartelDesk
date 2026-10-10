# DDS2 CartelDesk

![CartelDesk desktop and phone views](media/cover-wide.png)

An unofficial Windows companion for Drug Dealer Simulator 2. Inspect saved stock, look up ingredient sources, and plan shopping and deliveries without changing your game save.

**[Download the latest Windows ZIP](https://github.com/acsokis/DDS2-CartelDesk/releases/latest)** · [Screenshots](media/README.md)

## Quick start

1. Download the Windows x64 ZIP and extract the complete folder to a writable location.
2. Run **CartelDesk.exe**. First launch extracts its bundled runtime. Keep the included licenses with the app.
3. In **Settings**, select your cartel folder and Progress save. The usual folder is `%LOCALAPPDATA%\DrugDealerSimulator2\Saved\SaveGames\Cartels`.
4. Open **Operations overview**, **Inventory**, or **Isla Sombra map**. Refresh after DDS2 finishes saving.
5. Use **Start** and **Stop** to control the companion server. Closing CartelDesk stops its server too.

## Find where to buy or sell

Search the map for an item name or identifier. Suggestions help find matching entries. Use map layers and trade filters to narrow results, then select a marker for details.

Labels use the **vendor's perspective**: **Vendor sells** means you can buy from that vendor; **Vendor buys** means they accept the item from you. Owned stock and acquisition sources are separate. Missing prices, quantities, positions or offers remain unknown. Reference offers do not guarantee current in-game stock.

Fog-of-war reads the campaign's available `FOW_Target.exr`; map controls let you change its display preference. Player positions reflect the latest save, not continuous live tracking.

## Recipes and shopping plans

Choose a recipe and batch count to inspect ingredients and equipment. Use **Locate on map** for available location links. In **Planner**, add quantities, save named lists, load favourites, remove entries or reset the current plan.

Use **Shopping and deployment** and **Delivery logistics** to inspect sources and plan couriers and destination hideouts. Plans are reminders: the app does not buy items, move inventory, deliver supplies or start production inside DDS2.

## Phone, browser and Steam overlay

The desktop's **Web QR**, **Phone QR** and **Steam QR** actions provide their respective links.

For a phone, enable **Enable phone companion on LAN**, select your PC's local IP and scan the phone QR. Both devices need the same trusted network. Click the QR to enlarge it. Keep CartelDesk running. If blocked, use the supplied network helper for the app's port on a private network.

For Steam, enable the game's overlay and open the supplied Steam URL in its browser. The overlay page has an opacity control. Availability depends on your Steam overlay/browser setup.

## Another CartelDesk user

Player pairing is a preview. Exchange the host invitation and player's answer privately, compare the complete verification code through a trusted channel, then approve. Disconnect to end the session. **Pairing does not yet synchronize inventory or transfer saves.** Do not post invitations publicly.

## Settings and troubleshooting

- Change language and animations in **Settings**. Animation-off also hides the visual worm.
- Old data? Save in DDS2, wait for saving to finish, refresh and check the selected campaign.
- Phone cannot connect? Check the PC address, port, LAN option and firewall. `localhost` on a phone means the phone itself.
- No item location? Its position or reference offer may be unknown. Try the map search and compare the live wiki.
- HDR depends on the display and renderer; unsupported output uses the supported mode.

## Privacy and credits

Game saves are read-only. Plans and preferences are local. Exports may contain campaign information: review them before sharing. Source code remains private; this repository contains downloads, documentation and media. Older releases are private drafts.

Map and reference data from [drugdealersim.com](https://drugdealersim.com/). This app is unofficial and is not endorsed by or affiliated with TGS, ByteRunners or Movie Games SA. Underlying game data belongs to its developers. Consult the live wiki for current values. Keep the supplied third-party licenses and notices with the application.

[GitHub](https://github.com/acsokis) · [Instagram](https://www.instagram.com/gabor_carter/) · [LinkedIn](https://www.linkedin.com/in/gabor-web/)
