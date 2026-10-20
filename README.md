<p align="center">
  <a href="https://pfcentral.danielms.site">
    <img src="https://pfcentral.danielms.site/apple-touch-icon.png" alt="pfCentral" width="96" height="96">
  </a>
</p>

<h1 align="center">pf-central-artifacts</h1>

<p align="center">
  Download binaries, the pfSense package and the server image for
  <a href="https://pfcentral.danielms.site"><strong>pfCentral</strong></a>.
</p>

<p align="center">
  <a href="https://pfcentral.danielms.site"><strong>Documentation</strong></a>
  ·
  <a href="https://pfcentral.danielms.site/docs/onboard/enroll/">Install guide</a>
  ·
  <a href="https://pfcentral.danielms.site/docs/operate/upgrade-agents/">Upgrade agents</a>
</p>

The source repository is private; this repository exists so releases and the
server container image can be downloaded without authentication. It holds no
source code — releases are published here by the pf-central CI pipeline.

Each release carries:

- `pf-central-server-linux-amd64` — central server binary
- `pfcentral-agent-freebsd-amd64` — pfSense agent binary
- `pfSense-pkg-pfcentral-agent.pkg` — pfSense package
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
