# StoneBase Privacy Notice

Updated September 6, 2026.

Your game library, SGF files, analyses, comments and configuration are stored
on the computer running the StoneBase server. If you connect from a phone,
tablet or another computer, those devices communicate with your server.
They do not upload your library to StoneBase's hosted services.

This notice describes optional app telemetry, license validation, update
checks and the external services you choose to use.

## 1. Optional usage and reliability statistics (telemetry)

**Off by default.** On first launch you are asked to choose. You can change
your choice at any time in **Settings → Privacy**. The preference applies
to the server installation and browsers connected to it. Declining does not
prevent you from using the app.

When enabled, the app sends signed HTTPS events through its backend to
`https://license.gostonebase.com/telemetry`. We use them to find broken
features, understand operation outcomes and improve the app:

- App startup and shutdown, plus a heartbeat every **30 minutes** while
  the server is running. Heartbeats indicate server uptime, not active use.
- Feature use and onboarding steps, such as opening a game or configuring
  an engine. These are fixed categories, not a recording of your actions.
- Operations requested, started, completed, failed, cancelled or blocked,
  with elapsed time and counts where available. Examples include imports,
  analysis and engine matches. Pausing a match is not reported as completion.
- Errors described by fixed reason codes, the affected feature, operation
  stage, HTTP status where relevant, and a diagnostic fingerprint used to
  group similar failures. Automatic events do not contain exception messages
  or stack traces. The backend fingerprint hashes exception type and a
  limited number of StoneBase code symbols; it excludes message contents.
- Browser startup, rendering, loading, network and connection failures.
  Browser events include only a browser family and a broad viewport category
  (`mobile`, `tablet` or `desktop`), not the full user-agent string or URL.

Older app versions send a smaller set of events, including completed
analysis with a move-count bucket rather than operation outcomes.

### Event identifiers and context

| Field | Purpose |
|-------|---------|
| Installation ID (`anonInstallId`) | A truncated, salted hash of the machine fingerprint, stable across sessions. It lets us count reporting installations and returning usage. Despite its historical field name, this is **pseudonymous**, not a guarantee of anonymity. It does not directly contain your name or license key. |
| Backend session ID | A random UUID generated each time the server starts. |
| Browser session ID | A separate random identifier for a browser app session. Several devices can connect to one server installation. |
| Event and operation IDs | Random identifiers for correlating operation outcomes and recognizing repeated deliveries. No game ID is included. |
| App context | App version, operating system, locale, frontend/backend origin, and fixed feature/stage categories. |
| Engine and entitlement context | Fixed engine category, version when available, tier and entitlement source when available. No engine command, configuration path, license key or account identifier. |
| Country | Cloudflare derives a country code from the network request. StoneBase does not write the raw IP address to its telemetry events or Analytics Engine datasets. |

### What automatic telemetry does not contain

- Names, email addresses, usernames or account identifiers
- File names, file paths, SGF content or your game library
- Moves, board positions, winrates, variations or comments
- Engine commands, engine output, KataGo queries or responses
- Keystrokes, mouse recordings or window titles
- Error messages or stack traces
- Raw IP addresses

Cloudflare receives the connecting IP address as part of handling HTTPS
traffic. Its processing of network and security information is separate
from the fields StoneBase writes to Analytics Engine; we do not claim that
an IP address is never processed by the hosting provider.

### Delivery, withdrawal and retention

Telemetry uses bounded in-memory queues and limited retries. Events can be
dropped during outages or when a queue is full; game operations do not wait
for telemetry delivery. Queued events are cleared when telemetry is disabled,
and consent is checked before sending. Requests already sent cannot be
recalled. Disabling telemetry stops future collection; it does not delete
previously received events.

Events are stored in Cloudflare Workers Analytics Engine, whose documented
[data retention period is three months](https://developers.cloudflare.com/analytics/analytics-engine/limits/).
The HMAC signature discourages forged events; it does not make the data
anonymous. Reporting can use sampling, so counts may be estimates.

### Error reports you choose to share

The app may show an error report that you can review and copy. That report
can contain messages and stack traces, unlike automatic telemetry, and may
contain private details. Copying it places it on your clipboard; it does not
send it to us. Review and remove private information before posting it in an
issue, chat or support request.

## 2. License and beta access validation

If you activate a license key, StoneBase contacts
`https://license.gostonebase.com` to validate and periodically revalidate it.
That request contains the key and a stable machine fingerprint to enforce
the license's device limit. License validation is separate from optional
telemetry and is not disabled by the telemetry preference. Activating a beta
key also requires validation; this is not limited to paid licenses.

During the open beta, StoneBase automatically contacts the same service to
request temporary Pro access without a key. The request contains only a
hashed machine fingerprint. The service signs a device-bound token valid
for at most 48 hours; no account, license row or device activation is created
for this request. The token is cached on your StoneBase server and renewed
periodically while it runs. This functional access check is separate from
optional analytics and still runs when telemetry is disabled. No game
contents or raw device name are sent in the keyless beta request.

## 3. Update checks

StoneBase fetches release metadata from GitHub to show when a newer version
is available. GitHub receives the connecting IP address, as with any web
request, but no StoneBase-specific installation identifier in that request.

## 4. Features you choose to use

Features such as importing OGS games, downloading public databases or
starting Paddle checkout contact their respective providers. Their privacy
policies apply to those requests. Configured GTP engines run the commands
you supply on your StoneBase server; third-party engine software may make
its own network requests.

## Contact

For privacy questions or requests concerning your data, contact
[contact@gostonebase.com](mailto:contact@gostonebase.com).
