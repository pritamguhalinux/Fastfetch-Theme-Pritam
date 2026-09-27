# Lord Pritam's Workstation Fetch

A custom [fastfetch](https://github.com/fastfetch-cli/fastfetch) theme inspired by Catnap — built for a clean, boxed hardware/software split-panel layout with custom logo support and per-module color-coding.

![preview](preview.png)
<!-- Replace preview.png with an actual screenshot of your fastfetch output -->

## Features

- 🖼️ Custom logo support — swap in your own PNG/JPG with configurable size and accent color
- 🧩 Two clearly separated sections:
  - **Hardware** — CPU, GPU, display, disks (`/` and `/home` shown separately), memory, swap
  - **Software** — OS, kernel, display manager, desktop environment, window manager, theme, icons, fonts (system + terminal), terminal emulator, shell
- 🎨 Per-module color-coding so each stat is visually distinct at a glance
- 📦 Custom Unicode box-drawing borders (`┌─┐` / `└─┘`) framing each section
- ✨ Bold custom header banner for that personal-workstation touch
- 🧹 Minimal, no-clutter layout — only the specs that matter

## Installation

1. Install `fastfetch` if you haven't already:
   ```bash
   # Arch
   sudo pacman -S fastfetch

   # Debian/Ubuntu
   sudo apt install fastfetch

   # NixOS / home-manager
   # add `fastfetch` to home.packages / environment.systemPackages
   ```

2. Clone this repo or copy the config:
   ```bash
   mkdir -p ~/.config/fastfetch
   cp config.jsonc ~/.config/fastfetch/config.jsonc
   ```

3. Copy your logo image into the same directory and update the path:
   ```jsonc
   "logo": {
       "source": "/home/YOUR_USERNAME/.config/fastfetch/your-logo.png",
       "height": 18,
       "width": 30
   }
   ```

4. Run it:
   ```bash
   fastfetch
   ```

## Customization

| What to change          | Where                                      |
|--------------------------|---------------------------------------------|
| Logo image                | `logo.source`                              |
| Logo size                 | `logo.height`, `logo.width`                |
| Logo accent color          | `logo.color.1`                             |
| Header text                | First `custom` module's `format`            |
| Section colors            | `keyColor` on each module                  |
| Section border style       | `format` strings on the `custom` divider modules |
| Which stats are shown       | Add/remove modules from the `modules` array |

Full list of available module types and options: [fastfetch JSON schema docs](https://github.com/fastfetch-cli/fastfetch/blob/dev/doc/json_schema.md)

## Notes

- This config is `.jsonc` (JSON with comments) — standard `jq`/JSON validators will choke on the comments. Use a JSONC-aware linter (VS Code's built-in JSON language server handles this fine) to catch syntax errors before running `fastfetch`.
- Tested with fastfetch's schema version referenced at the top of `config.jsonc` — if you're on a much newer/older fastfetch release, check the schema link for breaking changes to module options.

## Credits

Inspired by the **Catnap** fastfetch theme. Customized and maintained by Pritam.

## License

MIT — do whatever you want with it.
