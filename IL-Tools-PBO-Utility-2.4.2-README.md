# IL Tools PBO Utility 2.4.2

One program to pack and unpack Operation Flashpoint / Arma: Cold War Assault Remastered `.pbo` files.

**File:** `IL-Tools-PBO-Utility-2.4.2.exe`  
**Version:** 2.4.2  
**Date:** 24 Sep 2026  
**Project:** https://github.com/Ironlion1970/IL-Tools-PBO-Utility

This replaces IL Tools MakePBO2 and IL Tools UnPBO2. There is no separate unpacker.

---

## Pack

1. Run `IL-Tools-PBO-Utility-2.4.2.exe`
2. Drop a folder on the window, or click **Browse...**
3. Leave **Prefix** empty
4. Leave **Compress text with OFP Cprs** unchecked
5. Check **Output .pbo** ends with `.pbo`
6. Click **Pack PBO**

| Kind | Folder must contain | Put the .pbo in |
|---|---|---|
| Addon | `config.cpp` or `config.bin` | `Addons` or `@Mod\Addons` |
| Mission | `mission.sqm` | `Missions` or `MPMissions` |

Pick the folder that directly contains that file — not Desktop, not the parent `@mod` / `Missions` folder.

Missions do not use a prefix. The utility clears prefix when it sees `mission.sqm` and no `config.cpp`.

### Header written

```
Vers
product = OFP: Resistance
files stored uncompressed
timestamps = 0
```

Leave prefix blank unless you need an Arma-style namespace.

---

## Unpack

1. Drop a `.pbo` on the window
2. Output defaults to `YourFile.pbo` → `YourFile\`
3. Click **Unpack PBO**

Cprs files are decoded to raw. Product / prefix / version are written as `$PBOPRODUCT$`, `$PBOPREFIX$`, `$PBOVERSION$` so you can pack the folder again.

---

## Where packed files go

Addon:

```
...\Arma Cold War Assault Remastered\Addons\YourAddon.pbo
...\@YourMod\Addons\YourAddon.pbo
```

Launch with `-mod=@YourMod` if you use a modfolder.

Mission:

```
...\Arma Cold War Assault Remastered\Missions\YourMission.pbo
...\Arma Cold War Assault Remastered\MPMissions\YourMission.pbo
```

Remastered and classic CWA are separate installs.

---

## Drag and drop

- Folder with `config.cpp` or `mission.sqm` → ready to pack
- `.pbo` file → ready to unpack
- Drop the EXE onto a folder in Explorer to pack `foldername.pbo` beside it
- Drop the EXE onto a `.pbo` to unpack it beside the archive

---

## Command line

```
IL-Tools-PBO-Utility-2.4.2.exe
IL-Tools-PBO-Utility-2.4.2.exe pack C:\Work\natofix -o natofix.pbo --product "OFP: Resistance" --no-compress
IL-Tools-PBO-Utility-2.4.2.exe pack C:\Work\MyMission -o MyMission.pbo --no-compress
IL-Tools-PBO-Utility-2.4.2.exe unpack MyMission.pbo
IL-Tools-PBO-Utility-2.4.2.exe unpack MyMission.pbo -o C:\Work\MyMission
IL-Tools-PBO-Utility-2.4.2.exe inspect MyMission.pbo
```

---

## Notes

- Windows SmartScreen may warn on an unsigned EXE: **More info → Run anyway**.
- Output must be a `.pbo` file, not a folder such as Desktop.
- Leave Cprs off for Remastered.
- Source: https://github.com/Ironlion1970/IL-Tools-PBO-Utility
