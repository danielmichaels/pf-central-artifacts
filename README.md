# pf-central-artifacts

Public release artifacts for pf-central. The source repository is private;
this repository exists so releases and the server container image can be
downloaded without authentication. It holds no source code — releases are
published here by the pf-central CI pipeline.

Each release carries:

- `pf-central-server-linux-amd64` — central server binary
- `nats-agent-freebsd-amd64` — pfSense agent binary
- `pfSense-pkg-nats-agent.pkg` — pfSense package
- `install.sh` — pfSense installer
- `SHA256SUMS`

Stable download URLs:

```text
https://github.com/danielmichaels/pf-central-artifacts/releases/download/v1.2.3/<asset>
https://github.com/danielmichaels/pf-central-artifacts/releases/latest/download/<asset>
```

`latest` always resolves to the newest stable release; prereleases are only
reachable at their versioned URL.

Install on pfSense:

```sh
fetch -o - https://github.com/danielmichaels/pf-central-artifacts/releases/latest/download/install.sh | sh
```

Server image (distroless, runs as UID 65532, ports 2808 and 24222, persistent
storage at `/data`):

```sh
docker pull ghcr.io/danielmichaels/pf-central:latest
```
