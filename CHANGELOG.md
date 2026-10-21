# Changelog

## 0.3.1

Fixes for players. Works with 0.3.0 servers and clients; updating the server is not required for these fixes.

* After reconnecting with a save that hadn't been confirmed, you now always get the server's latest character. Before, you could get an older copy and be disconnected at the next save.
* If the server doesn't answer a character save, your game now sends it again after 15 seconds instead of waiting until you reconnect.

## 0.3.0

Major update. The server and every player must update to 0.3.0 together; older versions can't join a 0.3.0 server and are told which version to install. Back up the server before updating (see the update guide).

* Joining is checked step by step: your character is only loaded after the server has accepted you, and the server tells you clearly if your installation is missing something it needs.
* Characters are stored more safely. A save is confirmed only once it is on disk, a repeated save is never applied twice, and a damaged or unreadable character is never replaced by a new or imported one.
* Existing characters move to the new storage automatically the first time each player joins. The old files stay untouched, and a backup copy is made first. In rare cases where an old record could belong to two different character names, the server asks the admin to confirm it before that character can join.
* Saves your game couldn't deliver (for example after a disconnect) are kept and sent again when you reconnect, including several saves in a row. A save the server can't accept is kept on your PC instead of being deleted.
* If your character from the server can't be loaded, you are returned to the menu with a message and your local character is left as it was.
* Fixed: a modified client could freeze a world object for every player by sending an extreme update. Such updates are now ignored.
* Players exploring at the same time get new areas loaded fairly, and the per-frame limit on ownership changes is exact.
* More reliable compatibility checks after game updates.

## 0.2.3

* Expanded the player guide with installation, configuration, backup, update, compatibility, and troubleshooting help.
* Added 13 FAQ pages covering server setup, characters, saves, performance, updates, and support.
* Added the full release history to the Hexium changelog. Gameplay behavior is unchanged.

## 0.2.2

* Public downloads and support now use Den's Server Authority on GitHub.
* Added the DLL-only installer and Hexium package. Gameplay behavior is unchanged.

## 0.2.1

* Fixed rejection of unauthorized object destruction.
* Raids now remain active while players are inside the raid area.
* Improved ownership updates in crowded areas to respect the server's per-frame time budget.

## 0.2.0

* Weather-dependent spawns use the weather at each player's location.
* Character saves that cannot reach the server are kept locally and retried after reconnecting or restarting.
* Characters save immediately after death.
* Added optional client ship prediction and more detailed server statistics.
* Prevented EquipmentAndQuickSlots backup restores from duplicating server-stored characters.

## 0.1.0

* Initial release for Valheim 1.0.20.
* Dedicated-server world simulation, spawning, raids, object ownership, ships, containers, and character storage.
* Version checks, rejection of unauthorized writes, optional network tuning, and feature diagnostics.
