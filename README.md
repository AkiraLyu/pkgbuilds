# Personal Arch Linux packages

Each package directory contains its PKGBUILD, required support files and `.SRCINFO`.
KDE sources and patches live in [AkiraLyu/kde-plugins](https://github.com/AkiraLyu/kde-plugins).
Third-party packages continue to use their AUR maintainers.

Configure `~/.config/paru/paru.conf`:

```ini
[options]
PgpFetch
Devel
Provides

[bin]
Sudo = run0

[pkgbuilds]
Url = https://github.com/AkiraLyu/pkgbuilds.git
```

```sh
paru --sudo run0 -Sy --pkgbuilds
paru --sudo run0 -S kde-config chatgpt-translucent-bars
kde-config
```

`kde-config` pulls in App Grid, Adjustable Task Manager, Kate translucent bars,
WeChat Glass and the Darkly translucent Plasma theme. `chatgpt-desktop` remains in AUR; `chatgpt-translucent-bars` applies the patch
through a pacman hook after application updates. Rebuild `wechat-glass-live` after KWin ABI changes and log in again.

Other personal packages include `wps-fps-unlock-git`, `zhihu-collection-export-git`,
`gamescope-git` (the Anime4K fork)  and `foxvault-git`.
The diary source remains in the dotfiles repository and is fetched from GitHub.
The archive, Fcitx5, TeX Live and Wine meta packages are maintained only here.

After editing a recipe, regenerate its `.SRCINFO` with `makepkg --printsrcinfo`.
Package sources and build output are not committed.
