<p align="center">
  <img src="assets/go-sound.png" width="200" alt="soundcloud-dl logo">
</p>

<h1 align="center">soundcloud-dl</h1>

<p align="center"><strong>Fork of AYehia0/soundcloud-dl, re-pathed as a Go library for Space Disco tooling.</strong></p>

<p align="center"><em>"We are going to space and we are bringing a disco."</em> 🚀🪩</p>

> **Status:** Fork, 5 commits ahead of upstream for library use. · **Visibility:** public · **Language:** Go · **History:** 2022-09-17 → 2023-11-19, 58 commits

## 🪩 What this is

Fork of the open-source `AYehia0/soundcloud-dl` CLI (download SoundCloud tracks and playlists with search, quality selection and ID3 tagging). Space Disco's 5 commits export a `Download` function and move the module path to `github.com/spacedisco/soundcloud-dl` so `spacedisco/cli` can import it.

## 🎛️ Stack

- Go 1.19
- cobra/pflag
- goquery (scrapes the public client id)
- grafov/m3u8 (HLS)
- bogem/id3v2 tagging
- promptui, progressbar

## 🗺️ Layout

| Path | What it does |
| --- | --- |
| `main.go, cmd/soundcloud-dl` | CLI entry |
| `pkg/soundcloud` | API calls, search, playlists, download |
| `pkg/client` | HTTP client |
| `internal/core.go` | download orchestration |
| `testdata/` | mocked API responses and sample audio |
| `Makefile` | run/build helpers |

## 🚀 Launch sequence (local setup)

```bash
go install github.com/spacedisco/soundcloud-dl@latest
soundcloud-dl <url> --best --download-path ./download
```

## 🛸 Deploy

Library + CLI. No release workflow.

## 🔌 Integrations

SoundCloud public web API (`api-v2.soundcloud.com`) using a scraped client id.

## 🧪 Tests & CI

Go tests for URL parsing and download qualities with testdata. No CI.

## 🛰️ Current state

Fork, 5 commits ahead of upstream for library use. Issues are disabled on this repo (typical for forks), so improvements are tracked in the PR description and docs instead.

## 🎚️ Usage (from the upstream README)

Make sure to read the help menu.

```
Usage:
  sc <url> [flags]

Flags:
  -b, --best                   Download with the best available quality.
  -p, --download-path string   The download path where tracks are stored. (default "/home/none/Things/github/soundcloud-dl")
  -h, --help                   help for sc
  -s, --search-and-download    Search for tracks by title and prompt one for download 
  -v, --version                version for sc
```

Notes : `-s` can't work with a `url` passed.

- **Download through a given URL**
<p align="center">
    <img src="assets/soundcloud-dl-github.gif" style="border-radius:8px" alt="goandsoundcloud">
</p>

- **Download through search**

Note: search is limited to 6 results of type `track`, later on maybe `playlist` will be added. Also pagination may be add!.

<p align="center">
    <img src="assets/download-search-short.gif" style="border-radius:8px" alt="goandsoundcloud">
</p>

- **Download a playlist**

Note : when downloading a playlist, it uses the flag `--best` to grab the best quality.

<p align="center">
    <img src="assets/playlist-download.gif" style="border-radius:8px" alt="goandsoundcloud">
</p>

## 🌌 How it connects

Imported as a Go library by Space Disco's internal track-import tooling.

## 🙏 Credits

Original project by [AYehia0](https://github.com/AYehia0/soundcloud-dl). Space Disco's changes export `Download` as a library function and move the module path.

---

<p align="center"><sub>Space Disco · Orbital Lounge and House Music Club · Deep, Minimal, Tech House &amp; Soulful, Groovy, Funky, Disco House.<br>Documentation refreshed November 2026 from a read of the code and history.</sub></p>
