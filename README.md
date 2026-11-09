[简体中文](README.zh_CN.md) · **English**

# PPT Pager · Color edition

> **This project is for personal study and research only. Commercial use is strictly prohibited.**
> Project-specific contributions use PolyForm Noncommercial 1.0.0; see [LICENSE](LICENSE)
> and [NOTICE](NOTICE). Upstream MIT, third-party licenses and earlier grants remain in effect.

Keep your presentation in hand: see a live color preview on the device, move
between slides and adjust your Mac's volume. Walk around within your local
network's coverage rather than staying beside the computer. Network coverage
and isolation settings determine reachability. No Bluetooth pairing is needed.
Tested with WPS presentations; macOS only. This is a screen preview, not video.

## v1.1 downloads

- [Color Mac companion](https://github.com/khemis8866-dotcom/ai-passport-ppt-pager/releases/download/v1.1/ppt-pager-mac.zip): Python 3.9 or newer, no extra Python packages.
- [Complete firmware](https://github.com/khemis8866-dotcom/ai-passport-ppt-pager/releases/download/v1.1/FoloToy-AI-Passport-full.bin): merged image for offset 0x0; a merged flash may reset saved Wi-Fi.
- [Current source snapshot](https://github.com/khemis8866-dotcom/ai-passport-ppt-pager/releases/download/v1.1/ppt-pager-source.zip): application, companion, tests, font materials and engineering docs.

## Get started

1. Extract the companion ZIP. Open Terminal with Command+Space. Run `python3 --version`; install a compatible Python 3 from [python.org](https://www.python.org/downloads/macos/) if needed.
2. When the device asks for Wi-Fi setup, use an iPhone to join the `PPTPager-xxxx` hotspot shown on its screen, using the displayed hotspot password. Open http://192.168.4.1 in Safari, select the venue's 2.4 GHz Wi-Fi, enter its password, and tap Connect PPT Pager. Wait until the device indicates it is waiting for the computer. Connect the Mac to the same LAN; the iPhone can return to its usual Wi-Fi.
3. Stop an older companion with Control+C. In Terminal type `cd` plus one space, drag the extracted `PPT-Pager-Mac` folder from Finder into Terminal, and press Return. Run `python3 ppt_pager_companion.py --code 123456`, replacing 123456 with the device's current six-digit pairing code. Keep Terminal running.
4. Grant Terminal Screen Recording, Accessibility, and any requested System Events automation permission. Restart Terminal if requested and repeat step 3. Otherwise restart the companion after granting permission. Wait for the device to indicate connection.
5. Keep the WPS slideshow in the foreground. UP: previous; DOWN: next; short OK: volume up; long OK: volume down. Control+C stops the companion. After a device restart, stop the old companion and rerun with the new pairing code. For setup failure rejoin its hotspot and choose Choose Wi-Fi again; double-press UP only to clear saved Wi-Fi and change networks.

The new companion is required for color. Older companions remain compatible but
send monochrome previews. Native color is 240 x 135 with aspect-preserving
filtered resizing; tiny desktop text is still limited by the display size.

## Validation and earlier release

Build and host checks passed, including 14 companion tests. The user confirmed
color preview, WPS previous/next and both volume controls on the flashed v1.1
image. Extended operation and network-active heap measurements remain unverified.
The complete-image SHA-256 is
`167ba37a191d376fc0a9da282998d8ddca9185bfb105fa59d665babf42450d3b`.

The [frozen v1.0 release](https://github.com/khemis8866-dotcom/ai-passport-ppt-pager/releases/tag/v1.0)
remains available. Current source is in the v1.1 source snapshot linked above;
the repository is maintained as a release-download index. The top-level
`ppt-pager-source.zip` is the legacy v1.0 snapshot; use the v1.1 release link for
the current source. Distribution excludes
private credentials, device identities, machine paths, logs and debugging files.
