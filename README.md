# Valhalla for Diablo II 1.13c

A port of the Valhalla mod from Diablo II 1.10 to 1.13c.

## How it works

Valhalla's data tables have almost the same structure as stock 1.13c, so the port merges the two instead of overwriting one with the other:

- **Missing content added:** Rows from the 1.11–1.13c Pandemonium Event (monsters, levels, items, drop classes, cube recipes) are copied into Valhalla's tables. Stock row positions are kept where the engine may depend on them.
- **Strings rebuilt:** Valhalla's custom item, unique, set and runeword names were missing from the `.tbl` files. A new `patchstring.tbl` is generated from the tables, so names show correctly.
- **BH compatibility:** A small patch to `BH.dll` turns off the stat-range display, which crashed on items with cube-added bonuses. Everything else in BH works.

## Removed files

Some of Valhalla's original files had to be removed or replaced with the stock 1.13c versions, because they crashed the game (Act 5 in particular):

- **Level tables:** `LvlMaze.txt`, `LvlPrest.txt`, `LvlSub.txt`, `LvlTypes.txt` and `LvlWarp.txt` use the stock 1.13c versions.
- **Custom tiles:** Some custom tiles in `global\TILES` were removed.

The level tables and tiles must all come from the same game version. Mixing 1.10 and 1.13c versions breaks level generation. As a result, Valhalla's level changes (for example to the Cow Level and some Act 1 and 2 areas) are not included.

## Usage

1. Start from a clean 1.13c install.
2. Copy the tables to `data\global\excel\` and `patchstring.tbl` to `data\local\LNG\ENG\`.
3. Delete all `.bin` files and launch with `-direct -txt`.

## Status

Not fully tested in game. 1.10 → 1.13c balance changes to rows both versions share are not ported.

*Valhalla belongs to its original author. This project is not affiliated with him.*
