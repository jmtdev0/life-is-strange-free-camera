# Life Is Strange Free Camera

Modified Cheat Engine tables and input config for a more modern free-camera workflow in *Life Is Strange*.

This work is based on **Life Is Strange - Photographer Mod v1.3 by IDK31**. The original table comments reference:

<http://steamcommunity.com/sharedfiles/filedetails/?id=656832219>

## Current Controls

Load `LIS_PhotoMod1.3/LIS_PhotoMod1.3 - A ver.CT` in Cheat Engine, attach to `LifeIsStrange.exe`, activate `CAMERA CONTROLS`, and press `PageDown` to toggle freecam.

- Gamepad left stick: move freecam.
- Gamepad right stick: look/rotate freecam.
- Hold `X`: slow camera movement and look.
- Hold `Y`: fast camera movement and look.
- Left mouse button: mouse look fallback.
- WASD: keyboard fallback for freecam movement.
- Delete/Supr: toggle HUD and outlines, under `GAME SETTINGS`.
- Arrow keys: move Max in-game, via the included `LifeIsStrangeInput.ini` profile.

## Files

- `LIS_PhotoMod1.3/`: working Cheat Engine tables and backups.
- `config/LifeIsStrangeInput.freecam-current.ini`: current input profile copy.
- `config/LifeIsStrangeInput.before-freecam-gamepad-20260519.ini`: input backup before gamepad freecam changes.
- `config/LifeIsStrangeInput.before-wishlist-20260519.ini`: input backup before the arrow-key/gamepad wishlist changes.

The live game config remains at:

`%USERPROFILE%\Documents\My Games\Life Is Strange\LifeIsStrangeGame\Config\LifeIsStrangeInput.ini`

To use the included profile, copy `config/LifeIsStrangeInput.freecam-current.ini` over that file while the game is closed, then start the game.

## Notes

This is a Cheat Engine workflow for a single-player game. It patches live process memory and can crash the game. Back up saves before experimenting.

