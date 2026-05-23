# Life Is Strange Free Camera

Modified Cheat Engine table and input profiles for a modern free-camera workflow in *Life Is Strange*.

This work is based on **Life Is Strange - Photographer Mod v1.3 by IDK31**. The original table comments reference:

<http://steamcommunity.com/sharedfiles/filedetails/?id=656832219>

## What This Setup Does

- Moves and rotates the free camera with a gamepad.
- Keeps Max controllable with the keyboard arrow keys.
- Uses `WASD` as a keyboard fallback for free-camera movement.
- Blocks the game's normal left-stick input so the same stick can drive the free camera.
- Adds a `Delete` HUD/outlines toggle.
- Adds optional debug logging to `logs/freecam-debug.log`.

## Requirements

- *Life Is Strange* for PC.
- Cheat Engine.
- A controller exposed as XInput. For a DualShock 4, use DS4Windows.
- HidHide is recommended with DS4Windows so the game does not also see the physical DirectInput controller.

For the intended DualShock 4 setup, start DS4Windows before launching the game. DS4Windows should expose the pad as an Xbox/XInput controller.

## Game Config

The game reads its live config from:

`%USERPROFILE%\Documents\My Games\Life Is Strange\LifeIsStrangeGame\Config`

Close the game before changing these files.

Copy these repository files into that live config folder:

- `config/LifeIsStrangeInput.freecam-current.ini` -> `LifeIsStrangeInput.ini`
- `config/LifeIsStrangeUI.freecam-current.ini` -> `LifeIsStrangeUI.ini`

The input profile clears the game's normal `WASD` movement, maps movement actions to the left-stick axes, and keeps arrow-key movement available through the XInput hook in the Cheat Engine table.

The UI profile disables left-stick button emulation in the UI layer so the stick is less likely to leak through as menu/game input.

## Cheat Engine Setup

Recommended table:

`LIS_PhotoMod1.3/LIS_FreeCamera_Gamepad.CT`

Basic flow:

1. Launch *Life Is Strange*.
2. Open the table in Cheat Engine.
3. Attach Cheat Engine to `LifeIsStrange.exe`.
4. Enable `Block game's left stick input - experimental XInput hook`.
5. Enable `>> FREE CAMERA + HUD [F2]` or press `F2`.
6. Press `PageDown` in-game to toggle the free camera.

The XInput hook is part of the intended workflow. It blocks the physical left stick from moving Max while letting the table use that same stick for the free camera. It also turns the arrow keys into a virtual left stick so Max can still move.

`Enable debug logging to logs/freecam-debug.log` is optional and disabled by default. Enable it only when troubleshooting.

## Controls

### Cheat Engine / Camera Mode

- `F2`: initialize the table.
- `PageDown`: toggle free camera on/off.
- `Delete` / `Supr`: toggle HUD and outlines.

### Free Camera

- Gamepad left stick: move the free camera.
- Gamepad right stick: rotate the free camera.
- `WASD`: move the free camera with keyboard.
- Hold left mouse button: rotate the free camera with the mouse.
- Hold Square / Xbox `X`: slow camera movement.
- Hold Triangle / Xbox `Y`: very fast camera movement.

The speed buttons affect camera movement, not camera rotation.

### Max

- Arrow keys: move Max.

With the XInput hook enabled, the game's physical left-stick input is blocked from Max and reused by the free camera.

## Files

- `LIS_PhotoMod1.3/LIS_FreeCamera_Gamepad.CT`: current gamepad-focused table.
- `config/LifeIsStrangeInput.freecam-current.ini`: current gameplay input profile.
- `config/LifeIsStrangeUI.freecam-current.ini`: current UI input profile.
- `config/LifeIsStrangeInput.before-freecam-gamepad-20260519.ini`: older input backup kept for reference.
- `config/LifeIsStrangeInput.before-wishlist-20260519.ini`: older input backup kept for reference.

Runtime logs are written under `logs/` and are ignored by git.

## Notes

This is a Cheat Engine workflow for a single-player game. It patches live process memory and can crash the game while experimenting. Keep a copy of any live `.ini` file you care about before replacing it.
