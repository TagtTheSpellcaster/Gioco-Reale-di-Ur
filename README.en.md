# Royal Game of Ur

[Versione italiana](README.md)

[![Version](https://img.shields.io/badge/version-1.6-blue)](#versions)
[![License: AGPL v3](https://img.shields.io/badge/license-AGPL--3.0-blue.svg)](https://www.gnu.org/licenses/agpl-3.0)
[![GitHub Pages](https://img.shields.io/badge/demo-GitHub%20Pages-222?logo=github)](#publishing-on-github-pages)
[![HTML5](https://img.shields.io/badge/HTML5-single%20file-E34F26?logo=html5&logoColor=white)](index.html)
[![JavaScript](https://img.shields.io/badge/JavaScript-ES2020-F7DF1E?logo=javascript&logoColor=black)](index.html)
[![Three.js](https://img.shields.io/badge/Three.js-r128-000?logo=threedotjs&logoColor=white)](https://threejs.org/)

A browser-based version of the Royal Game of Ur, a board game played in Mesopotamia from the third millennium BC onwards and documented by boards discovered in the Royal Cemetery of Ur. The project consists of a single HTML page, with no build process or installation required.

## Features

- **Two reconstructed rule sets**: Finkel (4 tetrahedral dice) and Bell (3 dice, with stakes and a bank). Optional variants: the bounce rule and the four-point roll exit rule (Bell).
- **Pieces per player**: 7 (modern rules) or 5 (the tablet analysed by Finkel).
- **Opponent**: computer (heuristic based on capture probabilities) or two players sharing the same screen.
- **Game board**: inspired by examples in the British Museum, drawn in SVG, with the symbols marking the squares.
- **3D tetrahedral dice** (Three.js), with marked vertices; the dice turn red when it is Red's turn. If WebGL or Three.js is unavailable, the page uses 2D SVG dice.
- **Animations**: pieces move one square at a time, and captured pieces return to the board. Animations are disabled when the operating system's reduced-motion setting is enabled.
- **Synthesized audio** using Web Audio, with no external audio files: sound effects (enabled by default) and a Mesopotamian-inspired soundtrack (disabled by default). The settings are saved in the browser.
- **Illustrated rules**: animated tutorials for Finkel (15 screens) and Bell (17 screens), featuring scenarios verified by the game engine.
- **History**: a cinematic-style title sequence about the history of the game, based on the "Royal Game of Ur" Wikipedia entry, accessible via the button at the top of the page.
- **Language**: Italian and English interface, with an IT/EN selector on the page. The selected language is saved in the browser; on first access, the browser's language is used.
- Responsive interface for small screens, with automatic light and dark themes and keyboard navigation for the pieces.

## How to Play

Each player moves their pieces along a path of fourteen squares: four in their own lane, eight in the shared central lane, and two in the final lane. Rosettes are located on squares 4, 8, and 14. The first player to get all their pieces safely off the board wins.

The complete rules for each version are available in the "Rules" panel and in the "Illustrated Rules" tutorial.

## Getting Started

Open `index.html` in a modern browser. No server or installed dependencies are required.

When the page loads, it downloads the following resources from CDNs, if available:

- Three.js r128 from `cdnjs.cloudflare.com` (for 3D dice; 2D dice are used if it is unavailable);
- fonts from Google Fonts (system fonts are used otherwise).

The game also works if neither of these resources can be loaded.

## Publishing on GitHub Pages

1. Copy `index.html` to the root of the repository.
2. In *Settings → Pages*, select the branch (for example, `main`) and the `/ (root)` folder.
3. The page will be available at `https://<username>.github.io/<repository>/`.

## Structure

All the code is contained in `index.html`, divided into three parts:

| Part | Contents |
|---|---|
| Engine | Pure logic, with no DOM access: state, rolls, move generation, Finkel and Bell rules, CPU move selection. |
| Interface | SVG board, pieces, 3D/2D dice, animations, panels, and settings. |
| Content | "Illustrated Rules" tutorial, procedural audio, and history. |

The game engine has been tested through complete game simulations and scenarios covering special situations (captures, occupied central rosette, exact exit rolls, bounce rule, Bell stakes).

## Historical Accuracy

The original rules are unknown: all versions of the game are reconstructions. In particular:

- Sources report either five or seven pieces; the number can be selected.
- In the reconstruction cited by Wikipedia, a player who skips a rosette pays a stake, and a piece on a rosette cannot be captured. This implementation uses modern rules instead (an extra roll under Finkel, a stake paid by the opponent under Bell).
- Murray's longer path, the 16-square variants, and the extended-path variant are not included.

## Versions

| Version | Changes |
|---|---|
| 1.0 | Game with Finkel and Bell rules, SVG board, 2D dice, computer opponent or two-player mode. |
| 1.1 | Board redesigned based on examples in the British Museum; 3D tetrahedral dice. |
| 1.2 | Dice vertices rendered as small white or black pyramids. |
| 1.3 | "Illustrated Rules" tutorials for Finkel and Bell. |
| 1.4 | Piece animations, red dice for Red, sound effects, soundtrack, history, and option to play with 5 or 7 pieces. |
| 1.5 | Compact layout: board and roll controls displayed on the same screen on displays at least 1000 px wide. |
| 1.6 | Italian and English interface with language selector. |

## Sources

- "Royal Game of Ur", Wikipedia.
- Rules reconstructed by Irving Finkel (British Museum) and Robert C. Bell.

## License

Copyright © 2026 Alessandro Valli.

This program is free software: you can redistribute it and modify it under the terms of the GNU Affero General Public License, version 3 or later, published by the Free Software Foundation. In particular, if you provide a modified version as a network service, you must make its source code available to users.

The program is distributed without any warranty. The full text is available in [LICENSE](LICENSE) and at <https://www.gnu.org/licenses/agpl-3.0.html>.

Three.js is distributed under the MIT License.
