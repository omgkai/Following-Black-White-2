# Patching & updating

Download the patch for your game from the [latest release](https://github.com/omgkai/Following-Black-White-2/releases/latest). The original ROM must match one of the supported source images below. Both are English DSi Enhanced images.

| Game | Required original SHA-256 |
| :--- | :--- |
| Black 2 | `2e6b2415354aa41471bc7617068dce059a59931bf5c4348a264f8043f297683a` |
| White 2 | `3e50aec3db401332175a5d2b5fe2a68ac1a05ec63995dba9d1506b1b51837446` |

**Black 2’s supported original has changed in v0.9.98.** Earlier patches used a source with blank DSi code sections despite its enhanced-format header. Use the complete original identified above. White 2’s supported original is unchanged.

Other regions, revisions, trimmed files and modified source ROMs have not been validated. A filename containing “DSi Enhanced” alone does not establish that the file is the supported source; the hash identifies it.

## Apply the patch

1. Open an xdelta3-compatible patcher.
2. Choose `Following-Black-2-v0.9.99.xdelta` or `Following-White-2-v0.9.99.xdelta` for the corresponding game.
3. Choose your matching original ROM as the source.
4. Choose a new `.nds` output filename and apply the patch. The resulting ROM is 512 MiB.

For the [official xdelta3 command-line tool](https://github.com/jmacd/xdelta):

```sh
xdelta3 -d -s "Original Black 2.nds" "Following-Black-2-v0.9.99.xdelta" "Following Black 2.nds"
xdelta3 -d -s "Original White 2.nds" "Following-White-2-v0.9.99.xdelta" "Following White 2.nds"
```

## Keep your progress when updating

Apply the new patch to the original ROM again, rather than to a previous Following build. Keep a backup of your existing battery `.sav`, then match its base filename to the new ROM. Start normally and select Continue. A new game is not required to upgrade.

Older `.mln` states contain loaded code and memory from the version that created them. Loading one can restore an old bug even while the new ROM is selected. Use a normal boot through Continue or New Game when validating an update.

## Verify v0.9.99

Both patches were applied to their supported originals, and the full resulting ROMs matched these SHA-256 hashes:

| Game | Patched v0.9.99 SHA-256 |
| :--- | :--- |
| Black 2 | `d29ff125588a343edd2f452c9728fb8b4ade3c23e8ff3d53b031fa806bc62a13` |
| White 2 | `cf7d3167ab9b4dc1540621dee548c95985da4659616894b17988a1082e8db430` |

Each release includes patch checksums and a release manifest. On macOS, `shasum -a 256 "your-file.nds"` prints a file's SHA-256. In Windows PowerShell, use `Get-FileHash "your-file.nds" -Algorithm SHA256`.

Both patches contain the complete DSi code sections from their verified originals. Kai confirmed that the Summary issue is fixed on DSi hardware running through nds-bootstrap in DS mode, and subsequently reported DSi mode working after first booting in DS mode. This is a hardware test report, not a claim of exhaustive compatibility. If you see a white screen on an initial DSi-mode launch, try one normal launch in DS mode, then switch back to DSi mode.

v0.9.99 uses the same supported originals as v0.9.98. Kai confirmed both v0.9.99 prepatched builds work before publication. Targeted paired melonDS and native checks cover the Pokéstar and Name Rater fixes, party naming, Summary and IV/EV viewing. This does not represent a new complete playthrough or exhaustive hardware test.
