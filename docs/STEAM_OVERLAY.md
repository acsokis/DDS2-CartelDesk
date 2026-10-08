# Use CartelDesk in the Steam Overlay

1. Start CartelDesk and leave its local server running.
2. Copy the actual local server address from CartelDesk. With the default port, the desktop web view is `http://127.0.0.1:8765/` and the compact companion view is `http://127.0.0.1:8765/companion`.
3. Start DDS2 through Steam. Open the Steam Overlay with your configured shortcut (normally Shift+Tab), open its web browser and paste either address.
4. Resize the browser to suit your game. Where Steam provides a pin control, pin the browser and adjust its opacity.

The compact companion works inside this browser as well as on a phone. On a phone, use the LAN address shown by CartelDesk, not `127.0.0.1`. Use the actual configured port if it differs from 8765.

The native CartelDesk window remains a separate desktop application; this workflow displays its web interfaces in Steam. Closing CartelDesk or stopping its server makes the overlay page unavailable. Steam Overlay must be enabled for DDS2. This workflow has not been exercised in a running DDS2 Steam session during the current verification.

Valve documents browser pinning in its [Steam client update notes](https://store.steampowered.com/news/posts/?enddate=1687393980).

The native Steam QR button provides the local web link with `?overlay=1`. Paste that link into the Steam browser. The page then offers an always-visible 25?100% content-opacity slider; it controls CartelDesk page content, not the Steam window or desktop application opacity.
