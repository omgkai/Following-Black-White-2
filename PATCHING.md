# Patching & updating

Download the patch for your game from the [latest release](https://github.com/omgkai/Following-Black-White-2/releases/latest). The original ROM must match one of the supported source images below. Both are English DSi Enhanced images.

| Game | Required original SHA-256 |
| :--- | :--- |
| Black 2 | `603cc1e8c5c999abe5ea17e6c624dac80c3352bd063bb5db9bb171e326a2e825` |
| White 2 | `3e50aec3db401332175a5d2b5fe2a68ac1a05ec63995dba9d1506b1b51837446` |

Other regions, revisions, trimmed files and modified source ROMs have not been validated. A filename containing “DSi Enhanced” alone does not establish that the file is the supported source; the hash identifies it.

## Apply the patch

1. Open an xdelta3-compatible patcher.
2. Choose `Following-Black-2-v0.9.97.xdelta` or `Following-White-2-v0.9.97.xdelta` for the corresponding game.
3. Choose your matching original ROM as the source.
4. Choose a new `.nds` output filename and apply the patch. The resulting ROM is 512 MiB.

For the [official xdelta3 command-line tool](https://github.com/jmacd/xdelta):

```sh
xdelta3 -d -s "Original Black 2.nds" "Following-Black-2-v0.9.97.xdelta" "Following Black 2.nds"
xdelta3 -d -s "Original White 2.nds" "Following-White-2-v0.9.97.xdelta" "Following White 2.nds"
```

## Keep your progress when updating

Apply the new patch to the original ROM again, rather than to a previous Following build. Keep a backup of your existing battery `.sav`, then match its base filename to the new ROM. Start normally and select Continue. A new game is not required to upgrade.

Older `.mln` states contain loaded code and memory from the version that created them. Loading one can restore an old bug even while the new ROM is selected. Use a normal boot through Continue or New Game when validating an update.

## Verify v0.9.97

Both patches were applied to their supported originals, and the full resulting ROMs matched these SHA-256 hashes:

| Game | Patched v0.9.97 SHA-256 |
| :--- | :--- |
| Black 2 | `e485889bfe11fbeda4560968220e91da3f9cd5070a83c94153da5ea2c77d1300` |
| White 2 | `fad197f7b196aebfed2d00506c5064b62ee758594c115ea338320870e9653dcf` |

Each release includes patch checksums and a release manifest. On macOS, `shasum -a 256 "your-file.nds"` prints a file's SHA-256. In Windows PowerShell, use `Get-FileHash "your-file.nds" -Algorithm SHA256`.

The patches preserve the DSi Enhanced source format. Actual DSi hardware/enhanced-mode compatibility is not established by that format check.
