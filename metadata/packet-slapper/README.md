[Back to All Plugins](../../README.md)

# Packet Slapper

**Version:** `1.3.0` | **Author:** write-erase | **Last Updated:** Nov 14 2026, 21:09 UTC

Runs scheduled or on-demand Ookla Speedtests through Dispatcharr to measure speed and latency.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue?style=flat-square)](https://spdx.org/licenses/MIT.html) [![Repository](https://img.shields.io/badge/GitHub-Repository-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/write-erase/packet-slapper)

## Downloads

### Latest Release

- **Download:** [`packet-slapper-latest.zip`](https://github.com/swvn-dispatch/plugin-repo-dev/releases/download/packet-slapper-1.3.0/packet-slapper-1.3.0.zip)
- **Built:** Nov 16 2026, 16:34 UTC
- **Source Commit:** [`df29445`](https://github.com/swvn-dispatch/plugin-repo-dev/commit/df29445f1f4d13be10c82d62d942a885c6421456)

**Checksums:**
```
MD5:    375776049f0fe8b893eaf581796b94cf
SHA256: a026df44c50a39e5e0bb188e4834d09cdb06612729e40077886f8ad2fb2c88cb
```

### All Versions

| Version | Download | Built | Commit | MD5 | SHA256 |
|---------|----------|-------|--------|-----|--------|
| `1.3.0` | [Download](https://github.com/swvn-dispatch/plugin-repo-dev/releases/download/packet-slapper-1.3.0/packet-slapper-1.3.0.zip) | Nov 16 2026, 16:34 UTC | [`df29445`](https://github.com/swvn-dispatch/plugin-repo-dev/commit/df29445f1f4d13be10c82d62d942a885c6421456) | 375776049f0fe8b893eaf581796b94cf | a026df44c50a39e5e0bb188e4834d09cdb06612729e40077886f8ad2fb2c88cb |
| `1.1.0` | [Download](https://github.com/swvn-dispatch/plugin-repo-dev/releases/download/packet-slapper-1.1.0/packet-slapper-1.1.0.zip) | Oct 28 2026, 14:58 UTC | [`74d1275`](https://github.com/swvn-dispatch/plugin-repo-dev/commit/74d1275ed7cc80b37e8cbf6152d4563789007108) | 97b7f1293f574e5b6db622fd5f74d5cb | 0464043954e3a51f4ea34c4bdf66b7983d34cbee0da7dffbc128eab3df9ce410 |
| `1.0.4` | [Download](https://github.com/swvn-dispatch/plugin-repo-dev/releases/download/packet-slapper-1.0.4/packet-slapper-1.0.4.zip) | Oct 28 2026, 13:35 UTC | [`172f4b4`](https://github.com/swvn-dispatch/plugin-repo-dev/commit/172f4b44d3b7063dca5a8fc1ccb005be67ab2611) | 2be84dbd3f27df76bf6a281d423891ac | dae9f339c9b4ef100e8e1996921a8d89fe9de5078ad05cca466a2254f9b25c9a |

---

**Source:** [Browse Plugin](https://github.com/swvn-dispatch/plugin-repo-dev/tree/main/plugins/packet-slapper)

**Metadata:** [View full manifest](./manifest.json)

---

## Plugin README

# packet-slapper
Packet Slapper runs an official Ookla speedtest directly from inside Dispatcharr, so it measures whatever network path Dispatcharr itself uses, VPN included, without needing a separate container or docker socket.

Run it on demand or on a schedule. Click Run Now for a one-off test, or turn on the scheduler. Scheduled runs skip themselves automatically if anyone's watching live TV, VOD, or catch-up, since a speedtest eats real bandwidth.

Results show right in Dispatcharr, no external service required. You get download, upload, latency, jitter, packet loss, and which server it hit. Add a Discord webhook if you want, and every result also posts there, either as a plain text message or a colored embed card.

A few extras, too. You can pin tests to one specific Ookla server ID so results stay comparable over time, pick your display timezone from a dropdown, and use Check Active Streams or Scheduler Status any time to see what the plugin is doing right now and when the next run is due.
