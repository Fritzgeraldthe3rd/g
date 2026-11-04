# Game Vault

A merged browser game collection. The original six game folders are preserved,
with their broken entry points repaired, plus a root launcher, Cookie Umpire's
cookie clicker, and the Cookie Arcade classics.

No build step. No package manager. Serve the folder over HTTP and play.

## Games

| Game | Path | State |
| --- | --- | --- |
| 1v1.LOL | [`1v1-lol/`](1v1-lol/) | Local Unity entry point added; local Firebase helpers wired in |
| 2048 | [`2048/`](2048/) | Existing game retained; analytics call removed |
| Awesome Tanks | [`awesome-tanks/`](awesome-tanks/) | Existing entry retained |
| Awesome Tanks 2 | [`awesome-tanks-2/`](awesome-tanks-2/) | Existing entry retained |
| Bad Piggies | [`badpiggies/`](badpiggies/) | Entry point repaired for local hosting |
| Baldi's Basics | [`baldibasic/`](baldibasic/) | Entry point repaired for local hosting |
| Cookie Umpire | [`cookie-umpire/`](cookie-umpire/) | Local wrapper embedding the published clicker build |
| Snake | [`arcade/snake/`](arcade/snake/) | Added locally |
| Pong | [`arcade/pong/`](arcade/pong/) | Added locally |
| Breakout | [`arcade/breakout/`](arcade/breakout/) | Added locally |

The launcher is [`index.html`](index.html). It links each game and embeds the
Cookie Umpire build in a local wrapper page. The Cookie Arcade hub at
[`arcade/`](arcade/) links 2048 and the three added classics.

## What changed in this merge

- Added a responsive root launcher with the full ten-game collection.
- Added `cookie-umpire/`, a full-screen wrapper around the canonical published
  Cookie Umpire build at <https://hrw233.github.io/cookieumpire/>.
- Added `arcade/` with local copies of Snake, Pong and Breakout, plus a shared
  CC0 license and the Cookie Arcade hub.
- Added `1v1-lol/index.html`, with the build pointed at local Firebase helper
  files; `1v1-lol/2.7.json` now loads its data and WebAssembly from the repo
  instead of jsDelivr.
- Repaired the install/start pages for Bad Piggies and Baldi's Basics so they
  load from a subdirectory instead of the site root.
- Removed a Google Analytics call from the 2048 page.
- Added `.nojekyll` so the folder layout works on GitHub Pages.
- Added [third-party notices](THIRD-PARTY-NOTICES.md).

Cookie Umpire's 421 KB source tree is intentionally not duplicated: its published
build is embedded, so this merge stays reviewable and the app keeps one canonical
copy. The wrapper has an "Open standalone" link for browsers that block iframes.

## Run locally

The Unity games need real HTTP headers, not `file://`.

```sh
python3 -m http.server 8000
```

Then open <http://127.0.0.1:8000/>. Use a server from the repository root so the
entry pages resolve their relative asset paths correctly.

## Layout

```text
.
├── index.html              # launcher
├── arcade/
│   ├── index.html          # Cookie Arcade hub
│   ├── LICENSE-CC0.txt
│   ├── snake/
│   ├── pong/
│   └── breakout/
├── cookie-umpire/
│   └── index.html          # wrapper for the published clicker
├── 2048/
├── 1v1-lol/
├── awesome-tanks/
├── awesome-tanks-2/
├── badpiggies/
├── baldibasic/
├── README.md
└── THIRD-PARTY-NOTICES.md
```

## Licensing and attribution

- 2048 is MIT; its license is [`2048/LICENSE.txt`](2048/LICENSE.txt).
- Snake, Pong and Breakout are CC0; the shared text is
  [`arcade/LICENSE-CC0.txt`](arcade/LICENSE-CC0.txt).
- No license was supplied for 1v1.LOL, Bad Piggies, Awesome Tanks, Awesome
  Tanks 2 or Baldi's Basics. Those games remain under their respective owners'
  terms and are not relicensed by this repository.
- Cookie Umpire is embedded from its published build. No license was supplied
  for it; the source is not copied here.
- See [THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md) for provenance and source
  links.

This merge adds launcher and wrapper code; it does not relicense any upstream
game or asset.
