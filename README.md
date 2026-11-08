[简体中文](README.zh_CN.md) · **English**

# PPT Pager

A Mac presentation remote with previous/next slide controls, output-volume adjustment, and a live monochrome screen preview. Tested with WPS presentations using FoloToy AI Passport.

## Downloads

- [Mac companion ZIP](https://github.com/khemis8866-dotcom/ai-passport-ppt-pager/raw/refs/heads/main/ppt-pager-mac.zip) — required; install Python 3 on macOS, then extract the ZIP.
- [Current firmware source ZIP](https://github.com/khemis8866-dotcom/ai-passport-ppt-pager/raw/refs/heads/main/ppt-pager-source.zip) — contains this application's source, dependencies, tests, and development documentation. It is not a flashable image.

## Start

1. When the device shows IPHONE WI-FI SETUP, connect an iPhone to the PPTPager-xxxx hotspot shown after JOIN. The hotspot password appears after AP. Open http://192.168.4.1 in Safari, select your venue's 2.4 GHz Wi-Fi, enter its password, and tap Connect PPT Pager. LOOKING FOR MAC means setup succeeded. Put the Mac on the same LAN and return the iPhone to its normal Wi-Fi.
2. In Mac Terminal, enter the extracted companion folder and run `python3 ppt_pager_companion.py --code 123456`, replacing 123456 with the six digits after PAIR. Give Terminal Screen Recording and Accessibility permissions; approve System Events automation if requested. Wait for CONNECTED.
3. Start your slideshow and keep it in the foreground. UP goes back; DOWN advances; short OK raises the Mac volume; long OK lowers it. The device shows a monochrome screen thumbnail.
4. If setup fails, use Choose Wi-Fi again. Double-press UP to change networks. A device restart generates a new PAIR code: restart the companion with that code. Ctrl+C stops the companion.

## Validation and source

The user confirmed screen preview, WPS previous/next, and both volume controls on 2026-11-09. Restart/reconnect, Wi-Fi reset, and extended operation remain unverified.

The source ZIP includes this app's changes to the [upstream FoloToy baseline](https://gitee.com/FoloToy/ai-passport), not just an unmodified template. The community full-image SHA-256 is `825a14d514b7dc94b1d2c94449a3364b60669b507302e5b8b5d8317e5f7fb0fb`. The preserved upstream MIT license is in LICENSE and the source archive. No private credentials or runtime logs are included.

The Mac companion uses only Python's standard library and built-in macOS tools. Use it on a trusted LAN. Windows is not supported.
