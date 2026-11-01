# Installation Guide — Mirthwood Item Menu

This guide explains how to install **Mirthwood Item Menu by Sarakiel** on Windows and verify that it loads correctly.

> **Compatibility note:** Release **1.0.0** is documented as tested with **Mirthwood v1.1.4p2** and **BepInEx 5.4.23.2 (5.x)**. Other game or loader versions have not been verified here.

## Requirements

- Mirthwood for Windows
- BepInEx 5.x installed in the Mirthwood game directory (the project README reports testing with **5.4.23.2**)
- The latest release package from [GitHub Releases](https://github.com/sarakiel-id/MirthwoodItemMenu-Sarakiel/releases/latest)

If you do not yet have BepInEx, the project README links to [Mirthwood BepInEx Pre-Configured on Nexus Mods](https://www.nexusmods.com/mirthwood/mods/1). Follow that package's installation instructions, or install a compatible BepInEx 5.x distribution appropriate for your game.

## 1. Locate the game directory

In Steam, open **Library → Mirthwood → Properties → Installed Files → Browse**.

The folder opened by Steam is your **Mirthwood game directory**. The paths below are relative to this folder; its absolute location varies by system.

## 2. Check BepInEx installation

Before installing the mod:

1. Confirm that the game directory contains a `BepInEx` folder.
2. Launch Mirthwood once with BepInEx installed, then exit the game.
3. If available, check `BepInEx/LogOutput.log` for startup information. Some installations may configure logging differently.

If BepInEx fails to initialize, resolve that problem before proceeding with the Item Menu mod.

## 3. Install Mirthwood Item Menu

1. Download the latest release ZIP from [GitHub Releases](https://github.com/sarakiel-id/MirthwoodItemMenu-Sarakiel/releases/latest).
2. Open the ZIP and inspect its folders.
3. If the package contains a top-level `BepInEx` folder, extract that folder into the **Mirthwood game directory**, preserving its internal structure. Merge folders if Windows prompts you.
4. Otherwise, place `MirthwoodItemMenu.dll` in the plugin folder shown below. Create the `MirthwoodItemMenu` subfolder if needed.

The final layout should be:

```text
Mirthwood/
└── BepInEx/
    ├── plugins/
    │   └── MirthwoodItemMenu/
    │       └── MirthwoodItemMenu.dll
    └── config/
        └── sarakiel.mirthwood.itemmenu.cfg   # generated on first successful launch
```

> **Common mistake:** Do not accidentally create `Mirthwood/BepInEx/BepInEx/plugins/...` by extracting the ZIP into an existing `BepInEx` folder instead of into the game directory.

## 4. Verify the installation

1. Start Mirthwood and load a save.
2. Press **F7** (the default menu hotkey).
3. Confirm that the item browser opens.
4. Try a harmless search or category filter. For a cautious first test, avoid adding quest or internal items.
5. Close the menu and confirm that gameplay resumes normally.

If the menu does not open, confirm the DLL path, inspect the BepInEx log, and check whether the hotkey was changed.

## 5. Optional configuration

After the mod has launched successfully, it should create:

```text
BepInEx/config/sarakiel.mirthwood.itemmenu.cfg
```

Example settings documented by the project:

```ini
[General]
MenuKey = F7
DefaultQuantity = 1
ShowHiddenTestQuestItems = false
PauseGameplayWhileMenuOpen = true

[Diagnostics]
VerboseDiscovery = false
```

Close Mirthwood before editing the configuration file, then restart the game to apply changes. Keep `ShowHiddenTestQuestItems = false` unless you understand the risks of internal/quest items.

## Updating

1. Exit Mirthwood.
2. Back up your existing configuration if you customized it.
3. Download the new release and replace the old mod DLL while keeping the expected folder structure.
4. Launch the game and verify the menu opens; review release notes for any configuration changes.

## Uninstalling

1. Exit Mirthwood.
2. Delete `BepInEx/plugins/MirthwoodItemMenu/`.
3. Optionally delete `BepInEx/config/sarakiel.mirthwood.itemmenu.cfg`.

Uninstalling the plugin does **not** automatically reverse inventory changes made while using it.

## If something goes wrong

- **F7 does nothing:** Confirm the DLL location, BepInEx startup, and current `MenuKey` value.
- **The game fails to start:** Test BepInEx independently and check for conflicts or incompatible game/loader versions.
- **The menu opens but an item behaves unexpectedly:** Avoid further changes, keep a backup of your save, and report reproducible details.
- **Need assistance?** Open an [Issue](https://github.com/sarakiel-id/MirthwoodItemMenu-Sarakiel/issues) with the game version, mod version, BepInEx version, steps to reproduce, and a relevant excerpt from `BepInEx/LogOutput.log` (remove any personal or sensitive data first).

For structured release checks, see [TESTING.md](TESTING.md).
