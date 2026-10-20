# Server Authority

A Valheim mod by **SterbenDen** that makes the dedicated server the owner of the world.

[Download the installer ZIP](https://github.com/HamzaLayas/Dens_Server_Authority/releases/latest) · [Report a problem](https://github.com/HamzaLayas/Dens_Server_Authority/issues)

## Requirements and installation

Built for **Valheim 1.0.20** and **BepInExPack Valheim 5.4.2351**. Install the same Server Authority version on the dedicated server and every player's PC. Players without the mod cannot join. Listen servers are not supported.

1. Stop the server and close Valheim. Back up your world and characters.
2. Install [BepInExPack Valheim](https://valheim.hexium.gg/mods/denikson/BepInExPack_Valheim) on the server and every client.
3. Download `ServerAuthority-<version>.zip` from Releases and extract it into each Valheim installation. It installs `BepInEx/plugins/ServerAuthority/ServerAuthority.dll`.
4. Remove any older copies of `ServerAuthority.dll` elsewhere in `BepInEx/plugins/`. Keep your configuration and saved data.
5. Start the server once to create `BepInEx/config/sterbenden.ServerAuthority.cfg`. Stop it before editing the configuration, then restart.

The installer ZIP contains only the plugin DLL. Use this ZIP to install the mod. GitHub's automatic source archives contain this public repository's player documentation and icon.

## Features

* The dedicated server simulates zones, creatures, farming, smelters, ships, spawns, and raids around players.
* Persistent objects remain server-owned. Players receive short permissions for actions such as riding, using carts, picking up items, and editing signs.
* Ships remain server-owned while players sail them.
* Chests, ship cargo, cart storage, and tombstones use server-validated inventory sessions. The server records item moves in `BepInEx/config/ServerAuthority/audit/`.
* Characters are stored on the server in `BepInEx/config/ServerAuthority/characters-v2/`, with rotating and daily backups. Offline character edits are ignored. Characters from 0.2.x move there automatically on first login.
* Unauthorized object changes are rejected and resynchronized. Sustained abuse can result in a kick.
* Optional network tuning and client ship prediction are disabled by default.

The mod checks compatibility with the game's methods at startup. A feature that does not match the installed game version disables itself and explains why in the log.

## Configuration

Gameplay settings are controlled by the server and sent to clients when they join.

| Setting | Default | Purpose |
| --- | --- | --- |
| `World.MaxNearSimulationDistance` | `2` | Caps the area simulated around each player. Larger areas increase server CPU use. |
| `World.CreateBudgetMs` | `2` | Per-frame time budget for creating world objects. |
| `World.OwnershipBudgetMs` | `0.3` | Per-frame time budget for updating ownership. |
| `Features.Enforcement` | `Enforce` | Use `LogOnly` initially when checking compatibility with other world mods. |
| `Characters.FirstLogin` | `Import` | Import a character on first join, or choose `Fresh` for new characters. |
| `Characters.SaveIntervalMinutes` | `5` | How often the server requests a character save. |
| `Ships.Prediction` | `false` | Enables client ship prediction. |

`Characters.KeepLocalCopy` controls whether the client keeps a local character copy. Use `sa_stats` in the console for feature status and timings; admins can use `sa_stats server` for server and player statistics.

## Compatibility and updates

Install world-behavior mods on the dedicated server, since it runs the simulation. Mods must support dedicated servers. Mods that change object ownership, container access, networking, or server-side character storage may conflict. Use only one server-side character system.

UI and inventory mods use the normal inventory interface. EquipmentAndQuickSlots' separate character backup restore is disabled while Server Authority stores characters. BetterNetworking disables this mod's network tuning.

Back up data and stop the server and clients before updating. Update every installation together and keep only one copy of the DLL. Version 0.3.0 can't be mixed with 0.2.x on either side.

[Downloads](https://github.com/HamzaLayas/Dens_Server_Authority/releases) · [Help and issues](https://github.com/HamzaLayas/Dens_Server_Authority/issues)
