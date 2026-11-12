[Back to All Plugins](../../README.md)

# AerioTV Presets

**Version:** `0.0.7` | **Author:** jonzey231 | **Last Updated:** Nov 09 2026, 21:15 UTC

Preconfigure a user's AerioTV favorites, group order, hidden groups, and settings. Their AerioTV devices offer Dispatcharr Sync on first launch and start from this setup. Requires AerioTV 1.8.45 or newer on Apple devices and AerioTV for Android 0.5.14 or newer.

[![License: AGPL-3.0-or-later](https://img.shields.io/badge/License-AGPL--3.0--or--later-blue?style=flat-square)](https://spdx.org/licenses/AGPL-3.0-or-later.html) [![Repository](https://img.shields.io/badge/GitHub-Repository-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/jonzey231/AerioTVPresets)

![Dispatcharr min](https://img.shields.io/badge/Dispatcharr_min-0.33.0-brightgreen?style=flat-square)

## Downloads

### Latest Release

- **Download:** [`aeriotv-presets-latest.zip`](https://github.com/swvn-dispatch/plugin-repo-dev/releases/download/aeriotv-presets-0.0.7/aeriotv-presets-0.0.7.zip)
- **Built:** Nov 12 2026, 17:16 UTC
- **Source Commit:** [`87c45ef`](https://github.com/swvn-dispatch/plugin-repo-dev/commit/87c45efdc70a7dad3de92882de8afaf876b4cf5b)

**Checksums:**
```
MD5:    9c4016ad744f1ae726b138f4f20bc18b
SHA256: 38aada8e834ceb21b1b99ad3239ccca71852ea11679046a0e5d5cbd093b4bffe
```

### All Versions

| Version | Download | Built | Commit | MD5 | SHA256 |
|---------|----------|-------|--------|-----|--------|
| `0.0.7` | [Download](https://github.com/swvn-dispatch/plugin-repo-dev/releases/download/aeriotv-presets-0.0.7/aeriotv-presets-0.0.7.zip) | Nov 12 2026, 17:16 UTC | [`87c45ef`](https://github.com/swvn-dispatch/plugin-repo-dev/commit/87c45efdc70a7dad3de92882de8afaf876b4cf5b) | 9c4016ad744f1ae726b138f4f20bc18b | 38aada8e834ceb21b1b99ad3239ccca71852ea11679046a0e5d5cbd093b4bffe |

---

**Source:** [Browse Plugin](https://github.com/swvn-dispatch/plugin-repo-dev/tree/main/plugins/aeriotv-presets)

**Metadata:** [View full manifest](./manifest.json)

---

## Plugin README

# AerioTV Presets

Lets a Dispatcharr admin set up a user's AerioTV app before the user signs in: favorite channels,
Live TV group order, hidden groups and categories, and app settings such as theme and mode. The
plugin writes the user's AerioTV Dispatcharr Sync record; their AerioTV devices offer Dispatcharr
Sync on first sign-in and start from that setup.

Use: choose a user, Save, run Refresh Lists, reload the page, make your choices, then run Preview and Apply
(Fill only adds what the record does not have yet; Replace overwrites what you set).

Collapsible sections need a Dispatcharr build with plugin settings sections (dev branch, November
2026); older 0.33.0 builds show Expand switches instead. The plugin makes no network calls.

Requires AerioTV 1.8.45 or newer on iPhone, iPad, and Apple TV, or AerioTV for Android 0.5.14 or
newer on phones, tablets, and Android TV.

Source, docs, and issues: https://github.com/jonzey231/AerioTVPresets
