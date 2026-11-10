# What's new

## v0.9.97 · November 10, 2026

### New-game Pokémon-menu hotfix

Fixes a freeze when opening the Pokémon menu after receiving your starter on a new game. The starter's walking-path buffer overlapped memory used by the menu controller. Older states could bypass that scene and conceal the problem.

The path now uses a temporary allocation, released when the scene ends. The same repair is included in **Black 2 and White 2**, with no permanent memory increase. Existing backgrounds, dialogue, sprites, features and battery-save data are preserved.

The old overwrite was reproduced. Regressions now run the complete starter sequence, check that menu code survives, and enter the captured native White 2 menu afterward in the same memory session. Paired party-utility, field-move, stats-redraw and application-load checks also pass. Both xdelta patches reconstruct the full expected ROMs by SHA-256. These checks do not constitute a fresh complete live playthrough.

**Updating:** apply the new patch to the matching original ROM, retain your battery save, and boot normally. Older emulator states restore old code/memory.

[Download v0.9.97](https://github.com/omgkai/Following-Black-White-2/releases/tag/v0.9.97)

## v0.9.96 · Initial community release

The main-story build brought following Pokémon, context-aware dialogue, expressive battle backgrounds in supported areas, optional quality-of-life settings, manual rematches, free party-menu RELEARN, BOX access and IV/EV viewing together in both editions.

The Black 2 party-selection crash was corrected by fixing two edition-specific native calls. A paired offline audit and full patch-reconstruction checks were completed. The later v0.9.97 starter-to-menu regression exposed an additional memory overlap missed by that audit; use v0.9.97 or later for new games.

Further area backgrounds and postgame additions remain unfinished.
