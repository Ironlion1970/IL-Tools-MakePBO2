# IL Tools MakePBO2

OFP / Arma: Cold War Assault Remastered PBO packer.

**Version:** 2.2.0  
**Date:** 23 Sep 2026  
**Project:** https://github.com/Ironlion1970/IL-Tools

## What it does

Packs an addon folder into a Resistance-style `.pbo` that Remastered will load.

## Game-safe pack settings

These settings were confirmed in-game:

- Profile / product: `OFP: Resistance`
- **Prefix: leave blank**
- **Compress text: unchecked**
- `config.cpp` must be in the folder you pack (archive root)

Header written:

```
Vers
product = OFP: Resistance
files stored uncompressed
timestamps = 0
```

Do not add a prefix unless you need an Arma-style namespace. A prefix is why earlier packs were ignored by the game.

## How to use

1. Run `IL-Tools-MakePBO2.exe`
2. Drop the addon folder on the window, or click **Browse...**
3. Check **Output .pbo** ends with `.pbo`
4. Click **Pack PBO**
5. Copy the file into the game:

```
...\Arma Cold War Assault Remastered\Addons\YourAddon.pbo
```

or a modfolder:

```
...\@YourMod\Addons\YourAddon.pbo
```

Launch with `-mod=@YourMod` if you use a modfolder.

## Drag and drop

Drop the folder that **contains** `config.cpp`, not Desktop and not the parent `@mod` folder.

Dropping the EXE onto a folder from Explorer also packs `foldername.pbo` beside it.

## Command line

```
IL-Tools-MakePBO2.exe
IL-Tools-MakePBO2.exe pack C:\Mods\natofix -o natofix.pbo --product "OFP: Resistance" --no-compress
IL-Tools-MakePBO2.exe inspect natofix.pbo
```

## Install notes

- Remastered and classic CWA are separate installs. Put the PBO in the tree you actually launch.
- Windows SmartScreen may warn on an unsigned EXE: More info → Run anyway.
- Leave **Compress text with OFP Cprs** off for Remastered.

## Source

https://github.com/Ironlion1970/IL-Tools
