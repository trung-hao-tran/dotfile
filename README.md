# dotfile

Personal dotfiles and nerd fonts.

## Contents

- `config/mimeapps.list` — default apps (Firefox as default browser)
- `config/otter-launcher/config.toml` — otter-launcher config
- `fonts/` — Nerd Fonts (DepartureMono, Hack, AnonymousPro, FiraCode, GeistMono)

## Install

```sh
cp config/mimeapps.list ~/.config/mimeapps.list
cp -r config/otter-launcher ~/.config/
mkdir -p ~/.local/share/fonts
cp -r fonts/. ~/.local/share/fonts/
fc-cache -f
```

## Dependencies (Fedora/dnf)

Required by `config/otter-launcher/config.toml` modules:

```sh
sudo dnf install firefox foot flatpak sqlite NetworkManager \
  procps-ng findutils util-linux systemd sudo fontconfig \
  yt-dlp mpv
```

- `firefox` — default browser (`br`, `mimeapps.list`). **Not installed on this machine yet** — install before using the `br` module or opening links.
- `foot` — terminal spawned by `k`, `cl`, `i`, `p`, `yt`, `wifi` modules
- `flatpak` — `sr` (search) / `i` (install) modules
- `sqlite` (`sqlite3` cli) — `cl` clipboard module, reads cclip's db
- `NetworkManager` (`nmcli`) — `wifi` module
- `procps-ng` (`ps`, `pkill`, `free`), `findutils` (`xargs`), `util-linux` (`setsid`, `stty`) — used across modules and the header
- `systemd` (`loginctl`, `systemctl`) — `p` power menu module
- `yt-dlp`, `mpv` — `yt` module (via `yt.sh`)
- `fontconfig` (`fc-cache`) — needed after installing fonts

Not distro packages — build/install separately, referenced at `~/.local/bin/`:

- `fsel` — used by `k`, `a`, `app`, `cl`, `p`, `wifi` modules and `yt.sh`
- `cclipd` — clipboard history daemon backing the `cl` module (must be running in your session; its db lives at `~/.local/share/cclip/db.sqlite3`)
- `otter-launcher` itself
