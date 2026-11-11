<div align="center">

<img src="assets/logo.png" width="132" alt="ColorCC logo">

# ColorCC

**A ColorOS-inspired Control Centre for Samsung One UI 9 & One UI 8.5**

Real-time background blur, refractive glass surfaces, and responsive spring physics for One UI's quick panel—delivered seamlessly as a systemless LSPosed module.

<p align="center">
  <a href="../../releases"><img src="https://img.shields.io/badge/version-0.99.8-c0405e?style=for-the-badge" alt="Version 0.99.8"></a>
  <img src="https://img.shields.io/badge/One%20UI-9%20%7C%208.5-1428a0?style=for-the-badge&logo=samsung&logoColor=white" alt="One UI 9 and 8.5">
  <img src="https://img.shields.io/badge/LSPosed-module-6a45d6?style=for-the-badge" alt="LSPosed module">
  <img src="https://img.shields.io/badge/root-required-2b2b33?style=for-the-badge" alt="Root required">
</p>

[**Overview**](#overview) · [**Features**](#features) · [**Requirements**](#requirements) · [**Installation**](#installation) · [**Usage**](#usage) · [**Troubleshooting**](#troubleshooting)

<br>

<img src="assets/banner.png" alt="ColorCC: the control centre, the media player and the editor" width="100%">

</div>

## Overview

**ColorCC** replaces Samsung One UI's stock quick panel with a modern control centre modelled after ColorOS. It introduces large glassmorphic cards, vertical and horizontal sliders, circular quick tiles, and an expandable media player. Every surface renders over a live, real-time blur of the underlying screen, paired with gesture-driven spring animations that track your finger.

ColorCC hooks directly into `SystemUI` at runtime via **LSPosed**. No system partitions or files are modified on disk—simply disable the module at any time to restore the stock One UI quick panel.

> [!NOTE]
> This repository hosts the prebuilt release APK, issue tracker, and user documentation only.

## Screenshots

<div align="center">
<table>
  <tr>
    <td align="center"><img src="assets/screenshots/panel.png" width="250" alt="The control centre"></td>
    <td align="center"><img src="assets/screenshots/player.png" width="250" alt="The media player"></td>
    <td align="center"><img src="assets/screenshots/editor.png" width="250" alt="The editor"></td>
  </tr>
  <tr>
    <td align="center"><b>Control Centre</b></td>
    <td align="center"><b>Media Player</b></td>
    <td align="center"><b>Layout Editor</b></td>
  </tr>
</table>
</div>

## Features

### Glass & Visual Effects
- **Four Material Presets:**
  - **Liquid:** Clear refractive glass that subtly bends background details along card edges.
  - **Frosted:** Diffused milky glass with a fine surface grain.
  - **Opaque:** High-contrast glossy dark glass.
  - **None:** Disables shader effects for clean, flat translucent shapes.
- **Real-Time Live Blur:** Dynamically blurs live content behind the shade (including active video playback) with **Light**, **Normal**, and **Strong** intensity levels.
- **Dynamic Reflections:** Card, tile, and slider surfaces reflect colour shifts from the underlying screen in real time.
- **Gyroscopic Tilt Highlights:** Specular edge highlights shift naturally as you tilt your device.

### Customizable Layout
- **Modular Grid:** Combines dedicated control cards (Wi-Fi, Bluetooth, Mobile Data, Media, Brightness, Volume, and Sound Mode) with quick-setting tiles.
- **Freeform Drag & Drop:** Long-press and drag any element to reorder. Quick tiles can be placed directly alongside control cards—such as next to sliders or above the media player.
- **Resizable Cards & Sliders:** Drag the corner handle of any card or slider to resize it. Resizing a slider into a wide, short aspect ratio automatically switches it to horizontal operation.
- **Adjustable Tile Density:** Configure **2, 3, or 4 rows** of quick tiles per page.
- **Adaptive Icon Theming:** Choose between signature ColorOS per-tile accent colours or your system's dynamic theme palette.
- **Quick Management:** Remove tiles or cards with <kbd>−</kbd> and restore them anytime with <kbd>+</kbd>.

### Interactive Controls
- **Quick Submenus:** Long-press **Wi-Fi** or **Bluetooth** to switch networks or paired devices without leaving the shade.
- **Expanded Brightness Control:** Long-press the brightness slider for a full-screen view featuring Auto Brightness, Dark Mode, and Extra Brightness toggles.
- **Live Brightness Preview:** While dragging the brightness slider, the surrounding panel fades out so you can accurately judge display luminance.
- **Multi-Channel Volume:** Long-press the volume slider to independently adjust Media, Ringtone, Notification, and System streams.
- **Variable Torch Intensity:** Long-press the Flashlight tile to fine-tune beam brightness.
- **Active VPN Indicator:** Displays the active VPN client in the header and links directly to system VPN settings.
- **Predictive Back Navigation:** Pressing back (or swiping back) closes any active submenu first before dismissing the panel.

### Media Player
- **Expandable View:** Tap the media card to expand a full-featured player with album artwork blended into the glass backdrop and a corner app badge.
- **Adaptive Seek Bar:** Automatically samples its accent colour from the current album art.
- **Extended Controls:** Supports app-specific custom actions, per-app volume control, and quick media output switching.

### Physics & Motion
- **Velocity-Aware Springs:** Panel expansion tracks your swipe velocity—slow pulls ease into place, while fast flicks overshoot slightly before springing back.
- **Staggered Page Transitions:** Swiping horizontally between the Control Centre and Notification Shade moves elements in a responsive, cascaded sequence.
- **Overscroll Stretch:** Pulling past the bottom of the panel produces a natural rubber-band stretch and rebound.
- **Morphing Menus:** Submenus expand smoothly out of the originating tile or card and collapse back into it when dismissed.

### Performance & Reliability
- **Cached Surface Rendering:** Moving elements are rasterized once and hardware-transformed during animations, ensuring smooth frame rates even on budget devices.
- **Automatic Crash Protection:** If an unhandled exception occurs, ColorCC immediately falls back to the stock One UI panel. After three consecutive crashes, the module automatically disables itself to prevent bootloops or UI lockups.

## Requirements

| Component | Requirement |
| :--- | :--- |
| **Device** | Samsung Galaxy smartphone running **One UI 9** or **One UI 8.5** *(Tablets and unfolded foldables retain the stock panel)* |
| **Root Solution** | Magisk or KernelSU |
| **Zygisk** | Built-in Zygisk or ReZygisk |
| **Framework** | LSPosed |

> [!IMPORTANT]
> Earlier One UI versions are not supported. If installed on an unsupported version, ColorCC safely remains inactive and leaves the stock panel untouched.

## Installation

1. Download **`ColorCC-v0.99.8.apk`** from the [Releases](../../releases) page and install it on your device.
2. Open **LSPosed Manager**, navigate to **Modules**, enable **ColorCC**, and ensure **System UI** (`com.android.systemui`) is checked in the module scope.
3. Restart System UI by rebooting your phone or running the following command in a root terminal:
   ```sh
   su -c pkill -f com.android.systemui
