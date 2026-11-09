<div align="center">

<img src="assets/logo.png" width="132" alt="ColorCC logo">

# ColorCC

**A ColorOS 16-style control centre for Samsung One UI 9**

Liquid glass, live blur and spring physics in place of One UI's quick panel, as an LSPosed module.

<img src="https://img.shields.io/badge/version-0.86-c0405e?style=for-the-badge" alt="Version 0.86">
<img src="https://img.shields.io/badge/One%20UI-9-1428a0?style=for-the-badge&logo=samsung&logoColor=white" alt="One UI 9">
<img src="https://img.shields.io/badge/LSPosed-module-6a45d6?style=for-the-badge" alt="LSPosed module">
<img src="https://img.shields.io/badge/root-required-2b2b33?style=for-the-badge" alt="Root required">

<br><br>

<img src="assets/banner.png" alt="ColorCC: the control centre, the media player and the editor" width="100%">

</div>

<br>

## ✨ What it is

ColorCC swaps One UI's quick panel for a control centre in the style of ColorOS 16: big glass cards, tall liquid sliders, round tiles and a full media player. Everything is drawn as real glass over a live blur of whatever is behind it, and everything moves on springs.

It is an LSPosed module that runs inside System UI. Nothing is replaced on disk: turn the module off and the stock panel is back.

> This repository ships the APK and documentation only.

<br>

## 📸 Screenshots

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

## 🌟 Features

### 🫧 Glass that looks like glass
- **Three looks:** *Liquid* (clear, with the background bending at the rim), *Frosted* (milky with a fine grain) and *Opaque* (glossy black glass).
- **Live blur** of what is behind the panel, so a playing video keeps moving through it. Choose *Light*, *Normal* or *Strong*.
- **Tilt highlights:** the shine on every edge slides round the glass as you tilt the phone.
- Sunk slider tracks, raised cards and a soft sheen give every surface depth.

### 🧩 Your layout, your way
- Wi-Fi, Bluetooth, mobile data, media, brightness, volume and sound-mode cards, plus all your tiles.
- **Hold and drag** anything to move it. Everything else stays where it is.
- **Drag a card's corner** to resize it freely. Make a slider wide and short and it slides sideways.
- Remove anything with **−** and bring it back with **+**.

### 🎛️ Controls that go deeper
- **Hold Wi-Fi or Bluetooth** for nearby networks or paired devices.
- **Hold the volume slider** for media, ringtone, notification and system volume. Muted ones are crossed out.
- **Hold the torch** for its brightness.
- The sound-mode pill switches between sound, vibrate and silent in one tap.

### 🎵 A real media player
- Tap the media card and it grows into a full player. The artwork fades into glass, with the app's own icon in the corner.
- The seek bar takes its colour from the album art, with a glowing head that breathes while music plays.
- The app's own extra buttons (like, shuffle and so on), per-app volume and a **Media output** switcher.

### 🌊 Motion that responds to you
- The opening follows your swipe. A slow pull eases in and a fast flick lands with a bounce.
- Pull past the end and the whole panel stretches like rubber, then springs back.
- Liquid sliders, springy presses and Samsung's own icon animations when a tile toggles.
- Menus grow out of what you held and fold back into it when they close.

### ⚡ Smooth and safe
- Moving parts are drawn once and only moved, so budget phones keep up.
- If anything goes wrong, the stock panel comes straight back. After three crashes ColorCC switches itself off.

<br>

## 📋 Requirements

| | |
|---|---|
| 📱 **Phone** | Samsung Galaxy on **One UI 9**. Tablets keep the stock panel. |
| 🔓 **Root** | Magisk or KernelSU |
| 🧬 **Zygisk** | Zygisk or ReZygisk |
| 🧩 **Framework** | LSPosed |

ColorCC is built against One UI 9's System UI. Other One UI versions are not supported and will most likely show the stock panel.

<br>

## 🚀 Installation

1. Download **`ColorCC-v0.86.apk`** from the [Releases](../../releases) page and install it.
2. Open **LSPosed → Modules**, enable **ColorCC** and tick **System UI** in its scope.
3. Restart System UI. Either reboot, or run this in a root terminal:
   ```sh
   su -c pkill -f com.android.systemui
   ```
4. Pull down the quick panel. That's it.

**To update,** install the new APK over the old one and restart System UI again.

<br>

## 🕹️ How to use it

| Do this | To get |
|---|---|
| Tap a tile or card | Turn it on or off |
| Hold a tile or card | Its menu: networks, devices, torch brightness and more |
| Hold the volume slider | Every volume, one slider each |
| Tap the media card | The full media player |
| ✏️ Pencil (top left) | The editor |
| Power button (top right) | The power menu |
| ⚙️ Gear | Settings |

**In the editor:** hold and drag to move, drag the corner arrow to resize, and tap − or + to remove or add. Pick a **Look** (Liquid, Frosted or Opaque) and a **Blur** (Light, Normal or Strong); both preview straight away. Tap **Done** to keep your changes.

<br>

## 🛟 Troubleshooting

<details>
<summary><b>The stock panel shows instead of ColorCC</b></summary>
<br>

- Check that ColorCC is enabled in LSPosed with **System UI** in its scope, then restart System UI.
- ColorCC only runs on One UI 9 phones. On anything else it leaves the stock panel alone on purpose.
- After three crashes ColorCC turns itself off. To turn it back on:
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

No shell? Boot into your root manager's safe mode (Magisk or KernelSU), which disables all modules.
</details>

<details>
<summary><b>Reporting a problem</b></summary>
<br>

Open **LSPosed Manager → Logs**. Every line from ColorCC starts with `ColorCC:`. Attach those lines, your phone model and your One UI version to an issue. A short screen recording helps a lot.
</details>

<br>

## 🗑️ Uninstalling

Disable ColorCC in LSPosed, or uninstall the app, then restart System UI. Nothing else is left behind.

<br>

## 💖 Special thanks

To the people who tested ColorCC and suggested features for it:

- [**Namphet**](https://www.tiktok.com/@namphet_.s23)
- **白夜执**
- **Kzrxe.7z**
- **Kil**
- **Hayachi**
- **Alizabp**

<br>

## ⚠️ Disclaimer

ColorCC modifies System UI on a rooted phone. It is provided as is, without warranty, and you use it at your own risk. Keep a way back, such as root manager safe mode, before you install any System UI module.

Samsung, Galaxy and One UI are trademarks of Samsung Electronics. ColorOS is a trademark of OPPO. ColorCC is an independent project and is not affiliated with or endorsed by either.

<br>

## 📜 Copyright

© 2026 Guest. All rights reserved.

ColorCC is free to download and use. Please share a link to this page instead of re-uploading the APK or the images, and do not publish modified copies as your own.

<br>

<div align="center">

Made by **Guest** · © 2026 · Inspired by ColorOS 16 and iOS

</div>
