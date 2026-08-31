# snap-mmctl

**mmctl as a [Snap](https://snapcraft.io) package.**

[mmctl](https://github.com/mattermost/mattermost/tree/master/server/cmd/mmctl) is the remote CLI tool for [Mattermost](https://mattermost.com). This repo packages it as a strictly-confined Snap, making it a single-command install on any Linux distribution that supports snaps.

## Install

[![Get it from the Snap Store](https://snapcraft.io/en/dark/install.svg)](https://snapcraft.io/mmctl-bp)

```bash
sudo snap install mmctl-bp
```

### Tracks

The Snap is published on two tracks:

| Track | Branch | Description |
|-------|--------|-------------|
| `stable/` | `main` | Latest upstream release |
| `esr/` | `esr` | Latest Extended Support Release |

Install the ESR track with:

```bash
sudo snap install mmctl-bp --channel=esr/stable
```

### Convenient alias

The snap command is `mmctl-bp.mmctl`. To call it as plain `mmctl`, create an alias:

```bash
sudo snap alias mmctl-bp.mmctl mmctl
```

## Usage

Authenticate and manage your Mattermost server:

```bash
mmctl auth login https://mattermost.example.com
mmctl user list
mmctl team list
```

See the [upstream docs](https://docs.mattermost.com/manage/mmctl-command-line-tool.html) for the full command reference.

## How it works

The Snap wraps the latest mmctl release (tracked by the `main` branch) or the latest ESR (tracked by the `esr` branch). Each branch discovers the appropriate upstream tag at build time. A CI workflow verifies every push and PR still builds and passes linting, while [snapcraft.io](https://snapcraft.io) handles publishing to the Snap Store on its own schedule.

## Disclaimer

> **Community project.** This snap is maintained independently and is not
> endorsed by or affiliated with Mattermost, Inc.

## Credits

- **[mattermost/mattermost](https://github.com/mattermost/mattermost)** — the Mattermost platform this Snap packages mmctl from.
- **[barryprice](https://github.com/barryprice)** — Snap packaging and maintenance.