# StoneBase Privacy Notice

StoneBase runs entirely on your computer. Your games, SGF files, analyses,
comments, and configuration never leave your device unless you explicitly
import from or export to a third-party service.

This document describes the **only** network traffic StoneBase initiates on
its own, and exactly what each call contains.

## 1. Optional anonymous usage statistics (telemetry)

**Off by default.** On first launch you are asked to choose. You can change
your choice at any time in **Settings → Privacy**.

When enabled, StoneBase sends a small signed HTTPS payload to
`https://license.gostonebase.com/telemetry` at the following times:

- Once when the app starts (`app_start`)
- Once every 5 minutes while the app is running (`heartbeat`)
- Once when the app exits (`app_exit`)
- When you run an analysis (`analysis_run`) — includes engine name and a move-count bucket (e.g. `100-200`), never the game itself
- When you use a feature (`feature_use`) — includes a feature key from a fixed list
- When a caught error occurs (`error`) — includes an error category from a fixed list; **no error messages, no stack traces, no file paths**

### Every event contains

| Field            | Value                                                                 |
|------------------|-----------------------------------------------------------------------|
| `event`          | One of the event names above                                          |
| `timestamp`      | Unix milliseconds                                                     |
| `sessionId`      | A random UUID regenerated every app launch                            |
| `anonInstallId`  | 16 hex characters: a salted SHA-256 of your machine fingerprint, truncated. Stable across sessions so we can count daily active users — but it **cannot be reversed** to identify your machine, and the salt is different from the one used by the license system, so the two IDs cannot be linked. |
| `appVersion`     | e.g. `1.0.36`                                                         |
| `os`             | One of `windows`, `darwin`, `linux`                                   |
| `locale`         | e.g. `en-US`, `es-ES`                                                 |
| `countryCode`    | Derived by Cloudflare from your request IP (country only, e.g. `ES`). Your IP address is **never stored** in the analytics database. |

### What we **never** send

- Your name, email, username, or any account identifier
- File names, file paths, or SGF content
- Game moves, positions, winrates, variations, or comments
- Engine output, KataGo queries, or KataGo responses
- Keystrokes, mouse activity, or window titles
- Contents of errors or stack traces (only a fixed category label)
- Your IP address (used by Cloudflare to derive country, then discarded)

The payload is signed with HMAC-SHA256 to discourage forgery. Data is written
to Cloudflare Workers Analytics Engine and retained for **3 months**, then
deleted automatically.

## 2. License validation (if you have a paid license)

If you activate a license key, StoneBase contacts
`https://license.gostonebase.com` to validate and periodically re-validate
the key. That request contains your license key and a stable per-machine
fingerprint so that the license system can enforce the 3-device limit. This
traffic exists only when you own a license; the free tier never contacts the
license server.

## 3. Update check

On launch StoneBase fetches the latest release metadata from GitHub to show
you when a newer version is available. GitHub receives your IP (as with any
web request) but no StoneBase-specific identifiers.

## 4. Features you opt into

Features you explicitly invoke — e.g. importing OGS games, KataGo cloud
analysis, or Paddle checkout — make network requests to the relevant third
party. Those calls only happen when you use those features.

## Contact

Questions: open an issue at
<https://github.com/DroidLogic/StoneBase> or email the address shown on
<https://gostonebase.com>.
