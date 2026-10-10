# nasgoros.github.io

Website of nasgorOS, built with [Hugo](https://gohugo.io/) and published to GitHub
Pages by `.github/workflows/hugo.yml` on every push to `main`. ROM files are hosted on
SourceForge; the site only links to them.

## Adding a device (maintainers)

Each device is a folder `content/device/<codename>/`:

```
content/device/merlinx/
├── _index.md   device page: name, codename, SoC, maintainer, SourceForge folder, kernel source
└── 17.0.md     one page per nasgorOS version: install guide for this device
```

1. Copy `content/device/merlinx/` to `content/device/<codename>/`.
2. In `_index.md` set `title`, `codename`, `soc`, `maintainer`, `maintainer_url`,
   `kernel_source` and `sourceforge_folder` (the folder name under
   `sourceforge.net/projects/nasgoros/files/`).
3. In `<version>.md` (e.g. `17.0.md`) set `title` to the version, `android`, and
   `weight` (version x10, newest first), then write the install steps for the device.
   Download buttons point to `files/<sourceforge_folder>/<version>/` and `.../recovery/`.
4. Preview with `hugo server`, then open a pull request.

`hugo.toml` holds the GitHub, Telegram and SourceForge links and the "Supported by"
list.
