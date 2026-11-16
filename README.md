# Dead Sector

Top-down zombie survival shooter. One self-contained HTML file, Canvas2D, built for a phone held sideways. Installable as a PWA: add it to your home screen and it opens full screen, landscape, and keeps working offline.

**Play:** https://michaellearns30-ship-it.github.io/dead-sector/

## Files

| File | What it is |
| --- | --- |
| `index.html` | The whole game: rendering, level generation, audio, UI. No external assets, no build step. |
| `manifest.json` | PWA manifest: full screen, landscape, icons, theme colour. |
| `sw.js` | Service worker. Network-first with a cache fallback, so a new build is picked up on the next launch and the game still opens with no signal. |
| `icons/` | Home-screen icons (192, 512, maskable, Apple touch). |

## How updates land here

`.github/workflows/sync.yml` copies the current build from the live preview into this repository's root and commits it. Run it from the Actions tab ("Sync game build" -> Run workflow) after a new build is published, or it runs on its own when the workflow file changes. GitHub Pages republishes within a minute, and the service worker fetches the new `index.html` the next time the app is opened with a connection.

## Controls

Left thumb moves. Right thumb aims and fires. Buttons in the corners: survivor ability, grenade, trap. Pause button top-left.
