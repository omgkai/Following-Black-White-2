# What's new

## v0.9.99 · November 11, 2026

### Pokéstar & Name Rater hotfix

- Fix the mandatory Pokéstar Studios tutorial movie and Name Rater Pokémon-selection crashes in both games. Relocate the added field helpers and preserve the native boundaries of the field and Summary modules.
- Add **NICKNAME** to the party menu with the original naming keyboard.
- Award **EXP and EVs on successful catches** through the existing reward/settings pipeline.
- Correct wild shiny boosts after native personality-value normalization, including the 1/1024, 1/512 and 1/256 settings.
- Preserve v0.9.98 backgrounds, maps, messages, story scripts, DSi sections and battery-save format. Supported original ROM hashes are unchanged.
- Both movies completed in isolated melonDS tests; Name Rater, party naming, Summary and IV/EV checks pass in both games. Native reward/shiny tests and exact full-ROM xdelta reconstruction pass. Kai confirmed both prepatched builds work and authorized publication. Targeted checks are not a complete new playthrough or exhaustive hardware test.

**Updating:** patch your matching clean original, keep a backup of your `.sav`, and boot normally through Continue. Older emulator states restore old code.

[Download v0.9.99](https://github.com/omgkai/Following-Black-White-2/releases/tag/v0.9.99)

## v0.9.98 — Hardware compatibility update

- Fix the nds-bootstrap Pokémon Summary freeze with self-contained handling of the native cartridge checks in both games.
- Restore Black 2’s complete ARM9i/ARM7i sections from a verified original. The required Black 2 source hash changes; White 2’s is unchanged. See [PATCHING.md](PATCHING.md).
- Preserve all v0.9.97 finished content, save format and permanent memory sizes. Public patches produce the exact same game binaries as the v0.9.98 hardware test.
- Kai confirmed Summary working on DSi hardware in DS mode and reported DSi mode working after a first launch in DS mode. Hardware coverage is not exhaustive.
- Fresh full-ROM xdelta reconstruction and paired native menu, Summary, starter-scene and compatibility regressions pass.

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
