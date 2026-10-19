# Changelog

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
