# Manual Test Plan — Mirthwood Item Menu

This checklist supports repeatable validation of **Mirthwood Item Menu by Sarakiel**, especially after updating Mirthwood, BepInEx, the mod DLL, or its documentation.

**This is a test procedure, not a report of completed tests.** Mark results only after running them on a real installation.

## Test environment

Complete the following before testing:

| Field | Value |
| --- | --- |
| Tester / GitHub username | _To fill in_ |
| Date | _YYYY-MM-DD_ |
| Operating system | _e.g. Windows 11_ |
| Mirthwood version | _To fill in_ |
| Mod release / DLL version | _To fill in_ |
| BepInEx version | _To fill in_ |
| Installation method | _Release ZIP / manual DLL copy_ |
| Other installed mods | _List or `None`_ |
| Test save / backup created | _Yes / No_ |

**Reference combination:** The project README states that release 1.0.0 was tested with **Mirthwood v1.1.4p2** and **BepInEx 5.4.23.2**. Record the *actual* versions used; do not assume newer versions work.

## Safety before testing

- [ ] Back up an important save, or use a disposable test save.
- [ ] Exit the game before replacing DLLs or editing configuration files.
- [ ] Keep hidden, test, and quest items disabled (`ShowHiddenTestQuestItems = false`) for routine checks.
- [ ] Record any other mods that might affect inventory or input handling.

## Test cases

Use **Pass**, **Fail**, **Blocked**, or **Not tested** for each case. Capture an issue reference and log excerpt when a case fails.

| ID | Test | Procedure | Expected result | Result |
| --- | --- | --- | --- | --- |
| INST-01 | Plugin file placement | Check `BepInEx/plugins/MirthwoodItemMenu/MirthwoodItemMenu.dll` | DLL exists at the expected location | Not tested |
| INST-02 | Startup | Launch the game with BepInEx | Game starts without a new mod-related startup error | Not tested |
| INST-03 | Default hotkey | Load a save and press `F7` | Item menu opens | Not tested |
| UI-01 | Close menu | Open and then close the item menu | Menu closes and normal gameplay is restored | Not tested |
| UI-02 | Search | Search for a known available item | Relevant item results appear | Not tested |
| UI-03 | Categories | Switch between available item categories | List updates to match the selected category | Not tested |
| ITEM-01 | Add one item | Add quantity `1` of a safe test item | Inventory gains one item, accounting for any existing stack | Not tested |
| ITEM-02 | Add multiple items | Add quantity `10` of a safe stackable item | Inventory change matches requested quantity, subject to game limits | Not tested |
| ITEM-03 | Quick quantity control | Use a visible quantity shortcut, such as `+1`, `+10`, or `+99` | Selected quantity or added quantity behaves as documented | Not tested |
| SAFE-01 | Hidden items excluded | Leave `ShowHiddenTestQuestItems = false` and browse/search | Hidden, debug, and quest items are not shown by default | Not tested |
| SAFE-02 | Risky item confirmation | Only if a safe reproducible scenario exists, inspect a guarded item action | Confirmation appears when the mod marks an action as risky | Not tested |
| CFG-01 | Config generation | Start the mod once and inspect `BepInEx/config/` | `sarakiel.mirthwood.itemmenu.cfg` is generated | Not tested |
| CFG-02 | Hotkey customization | Exit game, change `MenuKey` to another supported key, restart | New key opens the menu; restore `F7` afterward | Not tested |
| CFG-03 | Gameplay pause | With `PauseGameplayWhileMenuOpen = true`, open the menu during a safe situation | Game pauses if this setting is supported in that context | Not tested |
| LOG-01 | Log inspection | Inspect `BepInEx/LogOutput.log` after the session | No new relevant errors or exceptions are introduced | Not tested |
| REMOVE-01 | Uninstall smoke test | Exit game, remove only the mod plugin folder, relaunch | Plugin menu no longer opens; game still starts | Not tested |

> **Testing note:** Some cases depend on available game items, menu controls, or runtime behavior. Mark them **Blocked** or **Not tested** rather than claiming a pass when the scenario cannot be safely reproduced.

## Suggested test sequence

1. Confirm the installation path and record the versions.
2. Perform startup and menu smoke tests (`INST-*`, `UI-*`).
3. Validate search and categories.
4. Back up the save and perform controlled inventory tests (`ITEM-*`).
5. Check default safety settings (`SAFE-*`).
6. Test configuration generation and hotkey customization (`CFG-*`).
7. Inspect logs (`LOG-01`) and restore any changed settings.
8. If appropriate for the release cycle, perform the uninstall test (`REMOVE-01`) and reinstall afterward.

## Defect reporting template

```markdown
### Summary
Short description of the issue.

### Environment
- Mirthwood version:
- Item Menu version:
- BepInEx version:
- OS:
- Other mods:

### Steps to reproduce
1.
2.
3.

### Expected behavior

### Actual behavior

### Test case ID

### Logs / screenshots
Attach only relevant evidence. Remove personal or sensitive information.
```

Create a report in the [repository Issues](https://github.com/sarakiel-id/MirthwoodItemMenu-Sarakiel/issues) if the failure is reproducible.

## Sign-off

| Role | GitHub username | Date | Notes |
| --- | --- | --- | --- |
| Technical reviewer | _To fill in_ | _To fill in_ | |
| Validation tester | _To fill in_ | _To fill in_ | |

**Release decision:** _Pass / Pass with known issues / Blocked / Fail_

**Known issues / follow-up links:** _To fill in_

For setup details, see [INSTALLATION.md](INSTALLATION.md).
