# Third-party notices

This repository is a merged collection of browser games. The launcher and the
wrapper pages are original to this merge. The games and their assets remain the
property of their respective authors and are provided under the terms below or,
where no license was supplied, under their owners' terms.

## Cookie Umpire

- **Path:** [`cookie-umpire/`](cookie-umpire/)
- **What this repo contains:** a wrapper page only. It embeds the canonical
  published build at <https://hrw233.github.io/cookieumpire/>.
- **Source/build:** not duplicated in this repository.
- **License:** no license was supplied for Cookie Umpire. It is not relicensed
  here. The canonical build contains its own third-party dependencies and
  notices.

The wrapper provides a standalone link to the same build for browsers or
embeds that block iframe content. The clicker needs network access to load.

## Cookie Arcade classics

### 2048

- **Path:** [`2048/`](2048/)
- **Author:** Gabriele Cirulli
- **Source:** <https://github.com/gabrielecirulli/2048>
- **License:** MIT, reproduced in [`2048/LICENSE.txt`](2048/LICENSE.txt)

The only change to the game page is the removal of a Google Analytics call.

### Snake, Pong and Breakout

- **Paths:** [`arcade/snake/`](arcade/snake/),
  [`arcade/pong/`](arcade/pong/), [`arcade/breakout/`](arcade/breakout/)
- **Author:** Steven Lambert (Straker)
- **Source:** <https://github.com/straker/arcade> (the classic arcade games
  collection)
- **License:** CC0 1.0 Universal, reproduced in
  [`arcade/LICENSE-CC0.txt`](arcade/LICENSE-CC0.txt)

The games are included as standalone pages with local relative assets.

## Unity WebGL games from the original collection

The following folders and assets were already present in
`Fritzgeraldthe3rd/g` and are retained as-is, apart from the entry-point repairs
described in the README:

| Game | Path | License status |
| --- | --- | --- |
| 1v1.LOL | [`1v1-lol/`](1v1-lol/) | No license supplied |
| Bad Piggies | [`badpiggies/`](badpiggies/) | No license supplied |
| Awesome Tanks | [`awesome-tanks/`](awesome-tanks/) | No license supplied |
| Awesome Tanks 2 | [`awesome-tanks-2/`](awesome-tanks-2/) | No license supplied |
| Baldi's Basics | [`baldibasic/`](baldibasic/) | No license supplied |

These are fan/ported WebGL builds. Their names, characters, art, audio, code and
other assets belong to their respective rights holders. No license text was
included with the original folders, so this repository does not relicense them.
Anyone redistributing or reusing those assets should obtain permission from the
rights holder.

### Entry-point changes

- `1v1-lol/index.html` was added as a local entry page. The existing Unity build
  files and the original `2.7.json` data are used, with the data and WebAssembly
  URLs changed from jsDelivr to local paths.
- `badpiggies/index.html` and `baldibasic/index.html` were replaced with local
  install/start pages. The Unity build payloads are unchanged.
- The 2048 page no longer sends a page-view event to Google Analytics.

## Added code

The root launcher, Cookie Umpire wrapper, Cookie Arcade hub and the repository
documentation are additions made for this merge. They may be reused with this
collection; the upstream games keep their own terms.
