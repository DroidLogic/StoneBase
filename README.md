<p align="center">
  <img src="https://gostonebase.com/favicon.svg" width="80" alt="StoneBase logo" />
</p>

<h1 align="center">StoneBase</h1>

<p align="center">
  <strong>Understand your games. Explore the alternatives. Play your next one.</strong><br/>
  A Go library, KataGo review workspace and engine playground for Windows, macOS and Linux.<br/>
  Keep everything running on your computer—and review from a phone or tablet on your local network.
</p>

<p align="center">
  <a href="https://github.com/DroidLogic/StoneBase/releases/latest"><strong>Download StoneBase</strong></a>
  · <a href="https://gostonebase.com/blog/katago-setup-guide/">KataGo setup guide</a>
  · <a href="https://discord.gg/BjHzqQCHtX">Join Discord</a>
</p>

<p align="center">
  <a href="https://github.com/DroidLogic/StoneBase/releases/latest"><img src="https://img.shields.io/github/v/release/DroidLogic/StoneBase?style=flat-square&color=blue" alt="Latest release" /></a>
  <img src="https://img.shields.io/badge/desktop-Windows%20%7C%20macOS%20%7C%20Linux-brightgreen?style=flat-square" alt="Desktop platforms" />
  <a href="https://discord.gg/BjHzqQCHtX"><img src="https://img.shields.io/badge/Discord-community-5865F2?style=flat-square&logo=discord&logoColor=white" alt="Discord" /></a>
</p>

**Pro is free during the open beta.** No key, signup or payment is needed. Connect to the internet to activate access automatically and at least every 48 hours to renew it. [How beta access works ↓](#open-beta-access)

![StoneBase live analysis of Shin Jinseo vs KataGo](https://gostonebase.com/images/release/shin-jinseo-live-analysis.png)

*Shin Jinseo vs KataGo — SSEN Math & Hankyung Kishin Match, 21 July 2026. Real game data and KataGo analysis.*

## Start reviewing

1. **[Download the latest release](https://github.com/DroidLogic/StoneBase/releases/latest)** and install the package for your computer.
2. **Open a game.** Import an SGF from your device or bring in a game from OGS. You can browse the board and variations before configuring an engine.
3. **Connect KataGo for AI review.** Install a compatible KataGo executable and neural-network file, then select them and an **analysis configuration** in Settings. The [setup guide](https://gostonebase.com/blog/katago-setup-guide/) walks through this for each platform.

| Windows (x64) | macOS (Apple Silicon) | Debian / Ubuntu (x64) | Other Linux distributions (x64) |
|---|---|---|---|
| `.msi` installer | `.dmg` installer | `.deb` package | `.AppImage` |

The desktop packages include Java. KataGo and other engines are installed separately on the host computer; choose a build and model suited to its hardware. For **Play** mode, add a GTP engine in Settings with its executable, command arguments and GTP configuration.

## Study, play and organize

- **Review with KataGo:** live analysis, candidate moves, variation previews, and an action to add the engine’s suggested next move.
- **See territory and likely dead groups:** ownership markers scale with confidence. Compare current-board territory with predicted final ownership; the estimate is separate from the recorded result.
- **Understand move accuracy:** for games marked as analyzed, compare points lost and move quality across the opening, middle game and endgame. Open the detailed report while keeping the board visible.
- **Play against an engine—or match two engines:** choose any configured GTP engine, pause and resume, swap colors for a rematch, and save the game for review.
- **Navigate comfortably:** compact move controls, a timeline, autoplay, keyboard shortcuts and wheel navigation. A move tree beside the board and collapsible panels keep the position in view.
- **Build a useful library:** SGF and OGS imports, categories, public database downloads, exact and similar position search, duplicate merging, batch analysis and ZIP export.

<details>
<summary>See territory estimation and the accuracy report</summary>

![KataGo territory estimate and likely dead stones](https://gostonebase.com/images/release/territory-estimate.png)

*Territory and dead-stone markers are AI estimates, not a final adjudication.*

![StoneBase move accuracy report beside the board](https://gostonebase.com/images/release/move-accuracy.png)

</details>

The interface is available in **English, Spanish, Korean, Japanese, Simplified Chinese, German, Brazilian Portuguese and French**.

## Review from your phone or tablet

Keep StoneBase running on your computer, connect your other device to the **same trusted local network**, and open the computer’s StoneBase address in its browser. No separate mobile app is needed: your computer runs the engines and serves the shared game library.

The launcher prints the address as `Local network: http://…`. Use the port shown; StoneBase selects an available port when necessary. If the device cannot connect, check that the host firewall allows StoneBase’s frontend port.

**Upload selects files on the device you are holding.** An SGF chosen on your tablet is uploaded to the host’s library for review and analysis. Keep this service on your trusted network; do not forward its port to the public internet.

<details>
<summary>See the phone and tablet layouts</summary>

<img src="https://gostonebase.com/images/release/review-phone.png" width="280" alt="StoneBase phone browser review with move controls below the board" />
<img src="https://gostonebase.com/images/release/review-tablet.png" width="600" alt="StoneBase tablet browser review with the move tree beside the board" />

*The same game, reviewed through the responsive browser interface.*

</details>

## Open beta access

Pro activates automatically after the app verifies a short-lived beta access token. It needs an internet connection at least every **48 hours** to renew access. The beta remains open until we announce its end.

Existing beta-key users can simply update. Once keyless access is verified, StoneBase removes the saved beta key from local settings. Older versions can keep using their keys until the beta ends.

When beta access ends, the app returns to **Free** unless a valid paid license applies. Your games remain on your computer; libraries above the Free limit are preserved, but further imports are limited.

| After beta | Included |
|---|---|
| **Free** | Up to 50 games, single-game KataGo analysis, board review, GTP play, SGF/OGS imports and local-network browser access |
| **Pro** | Unlimited library, batch analysis and ZIP export, position search, duplicate detection and public database downloads |

Supporter and Max are coming soon. Max is planned to add cloud-hosted KataGo analysis without requiring a local GPU. Cloud analysis is not part of the current open beta. See [plan details](https://gostonebase.com/#pricing).

## Your data and feedback

Games and local analysis are stored on your host computer. Optional usage and diagnostic telemetry can be disabled in Settings. Beta/license validation is separate and uses a hashed device identifier; it does not upload your games. Read the [privacy notice](https://gostonebase.com/privacy/).

Found a bug, or have an idea for a better review workflow? [Open an issue](https://github.com/DroidLogic/StoneBase/issues/new) or [join Discord](https://discord.gg/BjHzqQCHtX).

[Website](https://gostonebase.com) · [Study guides](https://gostonebase.com/blog/) · [r/StoneBase](https://www.reddit.com/r/StoneBase/) · [KataGo](https://github.com/lightvector/KataGo)
