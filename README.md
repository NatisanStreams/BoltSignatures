# BoltSignatures

A Skript addon that lets players sign items with their name and a custom color, leaving a persistent lore entry on the item. Simple, lightweight, no databases.

## Features

- Players sign their held item with `/sign`, adding a colored lore entry
- Per-player signature color, supports named colors and hex codes
- `multiple-signatures` toggle in config — prevent duplicate signatures or allow stacking
- Players can remove their own signature with `/sign remove_self`
- Admins can wipe all BoltSignatures from an item with `/sign remove_all`
- Per-UUID playerdata files, loaded on join and unloaded on quit
- Config and playerdata hot-reload via `/bs reload` and `/bs reloadplayer <player>`
- Full tab completion on all commands and subcommands

## Dependencies

- [Skript](https://github.com/SkriptLang/Skript)
- [skript-yaml](https://github.com/Sashie/skript-yaml)
- [SkBee](https://github.com/ShaneBeee/SkBee)

## Installation

1. Drop all `.sk` files from `main/` into `plugins/Skript/scripts/`
2. Restart the server or run `/skript reload all`
3. A config file will generate at `plugins/BoltSignatures/config.yml`

## Configuration

| Key | Default | Description |
|-----|---------|-------------|
| `config.multiple-signatures` | `false` | Allow the same player to sign an item more than once |

## Commands

| Command | Description |
|---------|-------------|
| `/sign` | Sign your held item |
| `/sign remove_self` | Remove your own signature from the held item |
| `/sign remove_all` | Remove all BoltSignatures from the held item (admin only) |
| `/bs reload` | Reload the config |
| `/bs reloadplayer <player>` | Reload a specific player's data |
| `/bs config color set <color>` | Set your signature color |
| `/bs config color preview` | Preview your current signature color |

Aliases: `/boltsignatures`, `/bsignatures`, `/bs`

## Permissions

| Node | Description |
|------|-------------|
| `boltsignatures.sign` | Access to `/sign` and color config |
| `boltsignatures.admin` | Access to admin commands (`reload`, `reloadplayer`, `remove_all`) |

## Colors

Signature colors accept any Minecraft named color (`red`, `gold`, `light_purple`, etc.) or a hex code. The `#` is required when using hex — `#E096FF` works, `E096FF` alone does not. A full list of named colors is available in the [MiniMessage color reference](https://docs.papermc.io/adventure/minimessage/format/#color). Set yours with:

```
/bs config color set <color or #hex>
```