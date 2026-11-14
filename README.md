<div align="center">

<img src="assets/logo.png" width="132" alt="ColorCC logo">

# ColorCC

**A ColorOS-style control centre for Samsung One UI 9 and One UI 8.5**

Glass surfaces, live blur and spring-based motion, in place of One UI's quick panel — delivered as an LSPosed module.

<img src="https://img.shields.io/badge/version-0.99.58-c0405e?style=for-the-badge" alt="Version 0.99.58">
<img src="https://img.shields.io/badge/One%20UI-9%20%7C%208.5-1428a0?style=for-the-badge&logo=samsung&logoColor=white" alt="One UI 9 and 8.5">
<img src="https://img.shields.io/badge/LSPosed-module-6a45d6?style=for-the-badge" alt="LSPosed module">
<img src="https://img.shields.io/badge/root-required-2b2b33?style=for-the-badge" alt="Root required">
<br>
<img src="https://img.shields.io/badge/Telegram-join%20for%20leaks-26A5E4?style=for-the-badge&logo=telegram&logoColor=white" alt="Join the Telegram">

<br><br>

<img src="assets/banner.png" alt="ColorCC: the control centre, the media player and the editor" width="100%">

</div>

<br>

## Overview

I love what ColorOS does with its control centre, and I missed it every time I picked up a Samsung phone — so I built ColorCC to bring that feel over. Big glass cards, tall sliders, round tiles and a full media player, all sitting on top of a live blur of whatever's behind the shade. Everything moves on springs that follow your finger instead of just fading in and out.

ColorCC runs inside System UI as an LSPosed module, so nothing on your phone is actually modified. Turn the module off and the stock panel is right back where you left it.

> This repository holds the APK and its docs only — no source, sorry.

<br>

## Get leaks before anyone else

I post early looks at upcoming ColorCC updates — and whatever I build after it — in my Telegram channel before any of it is public. If you want a heads-up on what's coming instead of waiting for a release, that's where to be.

**[Join @coloredmodules on Telegram](https://t.me/coloredmodules)**

<br>

## Screenshots

<table>
  <tr>
    <td align="center"><img src="assets/screenshots/panel.png" width="250" alt="The control centre"></td>
    <td align="center"><img src="assets/screenshots/player.png" width="250" alt="The media player"></td>
    <td align="center"><img src="assets/screenshots/editor.png" width="250" alt="The editor"></td>
  </tr>
  <tr>
    <td align="center"><b>Control centre</b></td>
    <td align="center"><b>Media player</b></td>
    <td align="center"><b>Editor</b></td>
  </tr>
</table>

<br>

## Features

### Glass
- **Four looks.** Liquid is clear glass that bends the background at its edge. Frosted is milky glass with the colours behind it glowing through. Opaque is glossy black glass. None strips the glass effect away entirely, for flat, see-through shapes.
- **Live blur** of whatever's behind the panel, so a video playing underneath keeps moving through it. Pick Light, Normal or Strong.
- **Live reflections** — the glass on cards, tiles and sliders follows the screen behind it as it changes.
- **Tilt highlights.** The shine along each edge shifts as you tilt the phone in your hand.

### Layout
- Wi-Fi, Bluetooth, mobile data, media, brightness, volume and sound-mode cards up top, your tiles below.
- **Move anything.** Hold an item and drag it wherever you want. Tiles can even sit among the cards — next to a slider, above the media card, wherever.
- **Resize cards, sliders and tiles** by dragging a corner. Make a slider wide and short and it starts working sideways. A tile tucked among the cards can grow to 2x1, 2x2 and beyond, picking up a name label like the Wi-Fi card once it does.
- **Two, three or four rows** of tiles, your choice.
- **Icon colours** either in ColorOS's per-tile colours or your system theme colour.
- Pull something out with **−**, bring it back with **+**.

### Controls
- **Hold Wi-Fi or Bluetooth** to see nearby networks or paired devices, **mobile data** to pick which SIM handles data, **hotspot** for its name and password, and **Do Not Disturb** to lock it on for 1, 2 or 8 hours. Everything else opens its settings, same as ColorOS.
- **Hold the brightness slider** for a full-screen brightness view with auto brightness and dark mode baked in.
- **Hold the volume slider** for a full-screen volume view — drag it all the way down for silent mode.
- **Hold the torch** and drag up or down to set how bright it is.
- **Drag the brightness slider** and the rest of the panel fades out, so you can actually judge how the screen looks without the clutter.
- A VPN indicator in the header names whatever VPN app is active and jumps straight to its settings.
- Back button or back gesture closes an open menu first, then the panel — never both at once.

### Media player
- Tap the media card and it opens into a full player, artwork fading into the glass with the app's own icon tucked in the corner.
- The seek bar pulls its colour straight from the album art.
- You still get the app's own extra buttons, per-app volume, and a media output switcher.

### Motion
- Every card, slider and tile has its own spring and follows the shade as it opens: pull slowly and they pour in under your finger row by row, flick it and they get thrown in. Each one curves in toward the middle, stretches as it falls, lands a little past its spot with a squash, then settles back. Closing works the same way in reverse, lowest item first.
- Swipe between the control centre and notifications and the whole sheet moves like a liquid — the front edge follows your finger, the back edge trails behind, so it stretches a bit mid-swipe and wobbles together when it stops.
- Pull past the end and the panel stretches like rubber before snapping back.
- Menus grow out of whatever you held to open them, and shrink back into it when they close.

### Reliability
- Anything that moves is drawn once and then just repositioned, so it stays smooth even on budget phones.
- If something goes wrong, the stock panel takes over automatically. After three crashes in a row, ColorCC switches itself off so it doesn't keep bothering you.

<br>

## Requirements

| | |
|---|---|
| **Language** | English, Turkish, Italian, Indonesian and French. Everything else falls back to English. |
| **Phone** | Samsung Galaxy on **One UI 9** or **One UI 8.5**. Fold's inner screen works but is still being tested. Tablets keep the stock panel for now. |
| **Root** | Magisk or KernelSU |
| **Zygisk** | Zygisk or ReZygisk |
| **Framework** | LSPosed |

Any other One UI version isn't supported yet — ColorCC just leaves the stock panel alone on those.

<br>

## Installation

1. Grab **`ColorCC.apk`** from the [Releases](../../releases) page and install it.
2. Open **LSPosed > Modules**, enable **ColorCC**, and tick **System UI** in its scope.
3. Restart System UI — reboot, or run this in a root terminal:
   ```sh
   su -c pkill -f com.android.systemui
   ```
4. Pull down the quick panel and you're set.

**Updating?** Just install the new APK over the old one and restart System UI again.

<br>

## Usage

| Action | Result |
|---|---|
| Tap a tile or card | Turns it on or off |
| Hold a tile or card | Opens its menu, or its settings if it doesn't have one |
| Hold the brightness slider | Opens the brightness view |
| Hold the volume slider | Opens the volume view |
| Tap the media card | Opens the full media player |
| Pencil, top left | Opens the editor |
| Power button, top right | Opens the power menu |
| Gear, top right | Opens Settings |

**Inside the editor:** the **Layout** tab shows everything currently in your control centre plus what you can add — tap − or + to remove or add an item, hold and drag to move it, drag a corner to resize it. The **Look** tab is where you set the glass style, blur strength, number of tile rows and icon colours, all previewed live as you change them. Turn the phone sideways and both tabs sit next to each other. **Reset to default**, under Layout, puts the layout, tiles and look back to how they started. **Done** saves your changes; the cross or Back throws them away.

<br>

## Troubleshooting

<details>
<summary><b>The stock panel shows instead of ColorCC</b></summary>
<br>

- Make sure ColorCC is enabled in LSPosed with **System UI** checked in its scope, then restart System UI.
- ColorCC only runs on One UI 9 and One UI 8.5. Anywhere else, it leaves the stock panel alone on purpose.
- After three crashes, ColorCC turns itself off automatically. To switch it back on, run:
  ```sh
  su -c rm /data/user_de/0/com.android.systemui/files/colorcc_crashes
  ```
  Then restart System UI.
</details>

<details>
<summary><b>System UI keeps crashing or the screen is stuck</b></summary>
<br>

Uninstall the module from a root shell:

```sh
su -c "pm uninstall dev.colorcc"
```

No shell handy? Boot into your root manager's safe mode (Magisk or KernelSU) — that disables all modules at once.
</details>

<br>

## Reporting a bug

Find me as **gtsw1** on Discord or **[@Guestoss](https://t.me/Guestoss)** on Telegram. It helps a lot if you include:

- the lines starting with `ColorCC:` from **LSPosed Manager > Logs**,
- your phone model and One UI version,
- a short screen recording, if you're able to grab one.

<br>

## Uninstalling

Disable ColorCC in LSPosed or just uninstall the app, then restart System UI. Nothing gets left behind.

<br>

## Acknowledgements

Big thanks to everyone who tested ColorCC and suggested features along the way:

- [**Kzrxe.7z**](https://www.tiktok.com/@nxt_nix2)
- [**Namphet**](https://www.tiktok.com/@namphet_.s23)
- [**Murat**](https://github.com/murat4747k-blip)
- [**Xezjk**](https://github.com/xezjk)
- **希望**
- **Alizabp**
- **Kil**
- **Hayachi**
- **Hari**

<br>

## Disclaimer

ColorCC modifies System UI on a rooted phone. It's provided as is, with no warranty, and you use it at your own risk. Before installing any System UI module, make sure you've got a way back — your root manager's safe mode is a good one to know.

Samsung, Galaxy and One UI are trademarks of Samsung Electronics. ColorOS is a trademark of OPPO. ColorCC is an independent project and isn't affiliated with or endorsed by either.

<br>

## Copyright

© 2026 Guest. All rights reserved.

ColorCC is free to download and use. Please share a link to this page rather than re-uploading the APK or images, and don't pass off modified copies as your own.

<br>

<div align="center">

Made by **Guest** · © 2026 · Inspired by ColorOS and iOS

</div>
