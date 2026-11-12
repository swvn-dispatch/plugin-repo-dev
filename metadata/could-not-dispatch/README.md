[Back to All Plugins](../../README.md)

# Could Not Dispatch

**Version:** `0.7.5` | **Author:** PilaScat | **Last Updated:** Nov 09 2026, 13:27 UTC

Plays a looping image or video when every stream on a channel has failed, so viewers see a message instead of an error. It can show a second card when the provider is full, list the channels in use, and send channels back to their stream.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue?style=flat-square)](https://spdx.org/licenses/MIT.html) [![Repository](https://img.shields.io/badge/GitHub-Repository-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/PilaScat/could-not-dispatch)

## Downloads

### Latest Release

- **Download:** [`could-not-dispatch-latest.zip`](https://github.com/swvn-dispatch/plugin-repo-dev/releases/download/could-not-dispatch-0.7.5/could-not-dispatch-0.7.5.zip)
- **Built:** Nov 12 2026, 17:16 UTC
- **Source Commit:** [`ae0d954`](https://github.com/swvn-dispatch/plugin-repo-dev/commit/ae0d9547db04897d15f60bb617932f892d02b718)

**Checksums:**
```
MD5:    e7183971f9f7eb4a8f1560b566a4ff5a
SHA256: 7d8569a8cf69caeccace92019e3965062b060bef8769aabea06f25e053947b6c
```

### All Versions

| Version | Download | Built | Commit | MD5 | SHA256 |
|---------|----------|-------|--------|-----|--------|
| `0.7.5` | [Download](https://github.com/swvn-dispatch/plugin-repo-dev/releases/download/could-not-dispatch-0.7.5/could-not-dispatch-0.7.5.zip) | Nov 12 2026, 17:16 UTC | [`ae0d954`](https://github.com/swvn-dispatch/plugin-repo-dev/commit/ae0d9547db04897d15f60bb617932f892d02b718) | e7183971f9f7eb4a8f1560b566a4ff5a | 7d8569a8cf69caeccace92019e3965062b060bef8769aabea06f25e053947b6c |
| `0.6.0` | [Download](https://github.com/swvn-dispatch/plugin-repo-dev/releases/download/could-not-dispatch-0.6.0/could-not-dispatch-0.6.0.zip) | Oct 28 2026, 13:34 UTC | [`a137c8a`](https://github.com/swvn-dispatch/plugin-repo-dev/commit/a137c8a20c712352f11477ed6251fdfdbd025bee) | c1834c471dc81cb08f40e710a486af24 | 097a6a6337a556bea054c63608267b3f0d17ec7e3bfea88dbc0088f43de2d89b |

---

**Source:** [Browse Plugin](https://github.com/swvn-dispatch/plugin-repo-dev/tree/main/plugins/could-not-dispatch)

**Metadata:** [View full manifest](./manifest.json)

---

## Plugin README

# Could Not Dispatch

A Dispatcharr plugin that plays a looping image or video when every stream on a channel has
failed, so viewers see a message instead of an error. It can show a second card when the
provider is full, list the channels in use, and send channels back to their stream.

| Every stream failed | Provider full, with the channels in use |
|---|---|
| ![Card for a channel whose streams failed](https://raw.githubusercontent.com/PilaScat/could-not-dispatch/v0.7.3/docs/images/card-offline.png) | ![Card for a full provider, listing the channels in use](https://raw.githubusercontent.com/PilaScat/could-not-dispatch/v0.7.3/docs/images/card-full.png) |

The message is part of your picture. The plugin writes only the channels in use.

## Requirements

Dispatcharr with the Plugins page, and `ffmpeg` and `ffprobe`, already in its image.

## Install

From the Plugin Hub, or unzip the release into `/data/plugins` and press refresh on the
Plugins page. Enable the plugin, fill in the settings, press **Apply**.

## Settings

| Setting | What it does |
|---|---|
| Image or video | A path in the data volume, outside `/data/plugins/could_not_dispatch/`, which an update replaces, or an `http(s)` link |
| Image or video when the provider is full | Optional second card, for channels that found no free connection. Needs the API key |
| Show the channels in use | Writes them on the second card, with the programme on now |
| Height of the channels in use (%) | Where the first line starts, from the top. 58.5 by default |
| Font for the channels in use | Optional `.ttf`, `.otf` or `.ttc`. Empty: the container's sans-serif |
| Local port | Change it only on a conflict |
| Width, Height | Both at 0 to match the picture, up to 1920x1080 |
| Frames per second | 25 by default. Keep your channels' rate: Jellyfin keeps a session's first one |
| Stream bitrate | kbit/s, 2000 by default |
| Excluded groups, Excluded channels | One group, or one channel number or name, per line |
| Cover new channels automatically | Covers the channels an M3U refresh adds |
| API key | A Dispatcharr API key, needed to send channels back |

## Actions

| Action | What it does |
|---|---|
| Apply settings | Starts the card and adds it, last, to every channel not excluded |
| Check status | Says whether the card runs and how many channels carry it |
| Cover new channels | Covers channels that lack it. Runs after every M3U refresh |
| Restart fallback | Restarts the card if it is down. Runs when a channel starts |
| Remove fallback | Detaches the card and deletes its streams |

## What to expect

- **Each channel gets one more stream**, last in its failover list, which Dispatcharr counts
  as an HDHomeRun tuner. Your provider's limit is unchanged.
- **With an API key, channels go back.** After 30 seconds on the card, then after 1, 2 and
  every 5 minutes, the plugin opens the channel's streams in order and switches it to the first
  that sends data, so a dead stream does not interrupt the viewer. The check uses a free
  connection, counted like any other, or waits for one.
- **A full provider gets the second card**, for a channel whose streams are all on accounts at
  their limit, and the channel goes back as soon as a connection frees up.
- **The channels in use** are centred lines, 50 px high on a 1080p card, in grey `#606469`:
  leave that part of the picture empty.
- **Jellyfin can stall after a switch** with the `FFmpeg` stream profile, which starts the
  timestamps again near zero
  ([Dispatcharr#1946](https://github.com/Dispatcharr/Dispatcharr/issues/1946)). A
  [Reservoarr](https://github.com/PilaScat/reservoarr) profile with
  `RESV_TS_CHANNEL={channelId}` keeps them going forwards.
- **A card costs CPU only while watched**: about 0.4 core for a 1080p picture and 0.55 for a
  1080p video, under a 1 CPU limit.
- **A channel on the card never reports as down**: watch the `channel_failover` events.

## Development

```sh
python3 -m venv .venv
.venv/bin/pip install -e '.[dev]'
.venv/bin/python -m pytest
.venv/bin/python -m mypy could_not_dispatch plugin.py
.venv/bin/python -m ruff check .
.venv/bin/python scripts/build_zip.py
```

Decisions, traps and the release routine are in
[docs/MEMORY.md](https://github.com/PilaScat/could-not-dispatch/blob/master/docs/MEMORY.md).

## Licence

MIT. See [LICENSE](https://github.com/PilaScat/could-not-dispatch/blob/master/LICENSE).
