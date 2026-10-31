# Mirthwood Item Menu

**An AddItemMenu-style inventory browser for Mirthwood, developed by Sarakiel.**

Browse, search, and add items directly to your inventory through an in-game interface. Designed for players who want faster access to weapons, armor, food, crafting materials, seeds, tools, and other items.

**Version:** 1.0.0  
**Author:** Sarakiel  
**Mod Loader:** BepInEx 5.x  
**Tested Game Version:** Mirthwood v1.1.4p2

[Download Latest Release](https://github.com/luthfipratamaps/MirthwoodItemMenu-Sarakiel/releases/latest) | [Nexus Mods Page](https://www.nexusmods.com/mirthwood/mods/14)

---

## Features

- **In-Game Item Browser** — Browse items discovered from Mirthwood's runtime item database.
- **Instant Item Addition** — Add items directly to your inventory.
- **Search and Categories** — Filter weapons, armor, food, materials, seeds, tools, and miscellaneous items.
- **Custom Quantities** — Specify amounts or use quick +1, +10, and +99 buttons.
- **Configurable Hotkey** — Open and close the menu using `F7` by default.
- **Item Information** — Inspect item details, types, internal names, and stack information.
- **Safety Controls** — Hidden quest, debug, and internal items are excluded by default and risky items require confirmation.
- **Optional Gameplay Pause** — Pause gameplay while using the menu.

The mod uses Mirthwood's native inventory functions rather than directly editing save files.

## Requirements

- Mirthwood (Windows)
- BepInEx 5.x (tested with 5.4.23.2)

**BepInEx installation:** [Mirthwood BepInEx Pre-Configured](https://www.nexusmods.com/mirthwood/mods/1)

## Installation

1. Install BepInEx into your Mirthwood game directory.
2. Download the latest release ZIP from [GitHub Releases](https://github.com/luthfipratamaps/MirthwoodItemMenu-Sarakiel/releases).
3. Extract the ZIP into the main Mirthwood directory, preserving the folder structure.
4. Confirm the DLL is located at:

   `Mirthwood\BepInEx\plugins\MirthwoodItemMenu\MirthwoodItemMenu.dll`

5. Start Mirthwood, load your save, and press **F7**.

## Configuration

A configuration file is generated automatically when the mod is launched:

`BepInEx\config\sarakiel.mirthwood.itemmenu.cfg`

Default configuration:

```ini
[General]
MenuKey = F7
DefaultQuantity = 1
ShowHiddenTestQuestItems = false
PauseGameplayWhileMenuOpen = true

[Diagnostics]
VerboseDiscovery = false
```

Close the game before editing configuration values.

## Uninstallation

Delete the following folder:

`BepInEx\plugins\MirthwoodItemMenu\`

Optionally delete the configuration file:

`BepInEx\config\sarakiel.mirthwood.itemmenu.cfg`

## Compatibility and Troubleshooting

This release was tested with **Mirthwood v1.1.4p2** and **BepInEx 5.4.23.2**. Compatibility with newer game versions has not been fully verified.

If the mod stops working, check your BepInEx installation and provide `BepInEx\LogOutput.log` when reporting the problem, after removing any personal or sensitive information.

## Important Notes

This mod can change inventory contents and game progression. Hidden or internal items may affect quests or save stability. Back up important saves before experimenting with those items.

## Credits

Developed by **Sarakiel**.

Built using BepInEx and Harmony.

This is an unofficial community mod and is not affiliated with or endorsed by Bad Ridge Games or V Publishing. Mirthwood and its assets belong to their respective owners.

The mod source code is maintained separately from this public release repository.