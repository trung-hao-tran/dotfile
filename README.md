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
