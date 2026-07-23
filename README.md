# snap-mmctl

Snap packaging for [mmctl](https://github.com/mattermost/mattermost/tree/master/server/cmd/mmctl), the remote CLI tool for [Mattermost](https://mattermost.com).

> **Community project.** This snap is maintained independently and is not
> endorsed by or affiliated with Mattermost, Inc.

## Installation

```
sudo snap install mmctl-bp
```

### Convenient alias

The snap command is `mmctl-bp.mmctl`. To call it as plain `mmctl`, create an
alias:

```
sudo snap alias mmctl-bp.mmctl mmctl
```

## Sandboxing

The snap runs under strict confinement. It has access to the network (to reach
your Mattermost server) and read/write access to files under your `$HOME`
directory — necessary for authentication with token files.

## Configuration

mmctl configuration is stored under:

```
$HOME/snap/mmctl-bp/common/.config/
```

This location is shared across all versions of the snap, so your credentials
and settings survive upgrades and refreshes without any manual migration.

## Source

- Snap recipe: <https://github.com/barryprice/snap-mmctl>
- Upstream mmctl: <https://github.com/mattermost/mattermost/tree/master/server/cmd/mmctl>
- Issues specific to this snap: <https://github.com/barryprice/snap-mmctl/issues>
