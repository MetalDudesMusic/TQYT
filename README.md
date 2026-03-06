# Torque Motors Youtube — Kodi 21 Addon

A standalone Kodi 21 (Nexus) addon that plays YouTube playlists, channel videos and direct URLs.  
No separate YouTube addon needed. Self-updating via this GitHub repo.

---

## Install

1. Download the latest zip from [Releases](https://github.com/MetalDudesMusic/TQYT/releases/latest)
2. In Kodi: **Add-ons → Install from zip file** → select the downloaded zip

---

## Features

- ▶️ YouTube playlists, channel videos, streams and channel playlist pages
- 🔁 Auto-play next video
- ➕ Add/remove custom YouTube URLs from within Kodi
- 🗑 Clear Cache button on home menu
- 🔄 Auto-update system — checks this repo on startup, one tap to install

---

## How auto-update works

On each Kodi startup the addon silently fetches `version.json` from this repo.  
If the version number is higher than the installed one, a notification appears.  
Tap **🔔 Update Available** on the home menu (or **🔄 Check for Updates**) to install.

The update downloads the zip from GitHub Releases, replaces the addon files,  
and preserves your custom `icon.png` / `fanart.jpg` images.

---

## Releasing an update

1. Make your changes to `plugin.video.torquemotors/`
2. Bump the version in **both** `version.json` AND `plugin.video.torquemotors/addon.xml`  
   (e.g. `1.0.0` → `1.0.1`)
3. Update the `changelog` field in `version.json`
4. Commit and push to `main`

GitHub Actions will automatically build the zip and publish a new Release.  
Users will be notified on their next Kodi startup.

---

## Custom images

Replace these placeholder files in `plugin.video.torquemotors/resources/images/`:

| File | Size |
|------|------|
| `icon.png` | 256×256 px |
| `fanart.jpg` | 1920×1080 px |

---

## Repo layout

```
TQYT/
├── version.json                         ← version check file (read by addon)
├── plugin.video.torquemotors/           ← the addon itself
│   ├── addon.xml
│   ├── addon.py
│   └── resources/
│       ├── settings.xml
│       ├── images/
│       │   ├── icon.png
│       │   └── fanart.jpg
│       └── language/resource.language.en_gb/
│           └── strings.po
└── .github/workflows/
    └── release.yml                      ← auto-builds zip on push
```
