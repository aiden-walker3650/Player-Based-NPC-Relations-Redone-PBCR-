# Player Based NPC Relations Redone (PBCR)

**A Garry's Mod addon for changing the player's faction and controlling how NPCs and SNPCs perceive them.**

[![Garry's Mod](https://img.shields.io/badge/Game-Garry's%20Mod-blue)](https://store.steampowered.com/app/4000/Garrys_Mod/)
[![License](https://img.shields.io/badge/License-PBCR%20Attribution%201.0-orange)](LICENSE)
[![Steam Workshop](https://img.shields.io/badge/Steam%20Workshop-PBCR-lightgrey)](https://steamcommunity.com/sharedfiles/filedetails/?id=3611618315)

PBCR lets you change your player faction so that supported NPCs react to you according to the selected side. You can switch factions from the dedicated tab in the Garry's Mod Spawn Menu or by using console commands. The addon is designed for both single-player and multiplayer.

**Original creator and developer:** Aiden Walker 3650

[View the Steam Workshop page](https://steamcommunity.com/sharedfiles/filedetails/?id=3611618315)

---

## Features

- **Player faction switching** ”choose a faction through the PBCR tab in the Spawn Menu or use a console command.
- **NPC and SNPC relationship handling** ”supported NPCs respond to the player's selected faction.
- **Broad NPC compatibility** ”designed to work with standard NPCs and SNPCs, with compatibility for **VJ Base** and **ZBase**.
- **Multiplayer support** ”faction selection and administration features are available in multiplayer.
- **No NPC renaming** ”PBCR uses the game's `CLASS_*` classifications and `Classify` function rather than changing NPC names.
- **Admin permissions** ”server administrators can restrict faction switching and set a player's faction.
- **Notifications and hints** ”in-game hints explain faction changes, commands, and errors. Players can disable notifications.
- **Localization** ”includes language support, with English, Russian, Ukrainian, and German examples.
- **Event-based updates** ”PBCR applies the faction when it is changed; it does not need to poll relationships every tick.

## Available factions

The following factions are listed in the Steam Workshop description. Some require the corresponding game or additional content.

| Game / Category | Faction | Console ID | Requirement |
|---|---|---|---|
| Half-Life 2 | The Combine | `combine` | Half-Life 2 |
| Half-Life 2 | Resistance | `rebels` | Half-Life 2 |
| Half-Life 2 | Zombies / Headcrabs | `zombies` | Half-Life 2 |
| Half-Life 2 | Antlions | `antlions` | Half-Life 2 |
| Half-Life: Source / Resurgence | H.E.C.U. | `hecu` | Half-Life: Source or Half-Life: Resurgence |
| Half-Life: Source / Resurgence | Xen | `xen` | Half-Life: Source or Half-Life: Resurgence |
| Half-Life: Resurgence | Race X | `race_x` | Half-Life: Resurgence |
| Half-Life: Resurgence | Black Operations | `blackops` | Half-Life: Resurgence |
| Portal | Aperture Science | `aperture` | Portal |
| Other | Outcast | `outcast` | — |
| Other | Neutral | `neutral` | — |

> **Note:** Factions tied to other games or mods require that content to be installed. Their availability may depend on your setup.

## Installation

1. Download this repository using **Code â†’ Download ZIP**, or clone it with Git.
2. Place the addon's `pbcr` folder in your Garry's Mod addons directory:

   ```text
   garrysmod/addons/pbcr/
   ```

3. Start or restart Garry's Mod / your server.
4. Open the Spawn Menu and use the PBCR faction-selection tab.

For a dedicated server, install PBCR on the server and make sure clients receive the addon as required by your server's addon setup.

## Commands and configuration

Commands can be entered in the developer console. Server-side commands and settings should be configured by the server owner or an administrator.

### Server and admin commands

| Command | Description | Default |
|---|---|---|
| `pbcr_admin_only <0/1>` | Set to `1` to allow only server administrators to change their faction. Set to `0` to allow all players to change their faction. | `0` |
| `pbcr_setfaction_to_player "<player name or SteamID>" <faction>` | Set a specific player's faction. This is an administrator command. Put the player name or SteamID in quotation marks. | â€” |

Example:

```text
pbcr_setfaction_to_player "Player Name" combine
pbcr_setfaction_to_player "STEAM_0:0:000000000" rebels
```

### Player commands

| Command | Description | Default |
|---|---|---|
| `pbcr_setfaction <faction>` | Change your own faction, unless faction switching is restricted by `pbcr_admin_only 1`. | â€” |
| `pbcr_notify <0/1>` | Enable (`1`) or disable (`0`) PBCR notifications on your client. | `1` |

Examples:

```text
pbcr_setfaction combine
pbcr_setfaction rebels
pbcr_notify 0
```

## Compatibility and limitations

- PBCR supports standard NPCs and SNPCs and includes compatibility for **VJ Base** and **ZBase**.
- A custom NPC may not work correctly if its relationship logic is based on the NPC's name and the player instead of the game's classification system.
- Other addons that override NPC relationships or AI behavior may interfere with PBCR. Two addons that both change the player's faction or NPC relationships can conflict; disable or configure the conflicting addon if you encounter issues.
- **NextBots are not supported.**

Compatibility can vary with third-party addons and custom NPC implementations. The points above describe the compatibility and limitations stated in the Workshop description.

## Credits

- **Aiden Walker 3650** ”creator and developer of Player Based NPC Relations Redone (PBCR), including its original code.
- **AHTOXA** ”tested the addon during development.
- **Funni Taco** ”created the original concept that inspired this addon.

## License and attribution

PBCR is distributed under the **PBCR Attribution License 1.0**. You may use, modify, and redistribute the addon, including in other projects, provided that you follow the attribution requirements.

If you use PBCR or incorporate any part of its original code into another addon or project, you must clearly credit **Aiden Walker 3650** as the original creator of PBCR and the author of the reused code. Keep the copyright and license notices, identify your own changes, and do not imply that the original creator endorses your project.

See the separate [`LICENSE`](LICENSE) file for the complete terms.

---

*This repository is the source-code home of PBCR. For the addon page and Workshop updates, visit the [Steam Workshop page](https://steamcommunity.com/sharedfiles/filedetails/?id=3611618315).*
