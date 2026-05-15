# StarterNX

StarterNX is a curated Nintendo Switch CFW SD-card pack for firmware up to 22.1.0. It is built around a vanilla Atmosphere 1.11.1 / NX-Carnage-style core.

Most users should start with [NX-Carnage](https://github.com/dominatorul/Nx-Carnage) instead. It is the cleaner, lighter base for this pack and is easier to recommend for beginners or anyone who wants fewer moving parts.

StarterNX is a curated variant of that base with selected additions and independent component refreshes, so component versions can differ from the source pack.

The repo root mirrors the SD card root. Release zips are intended to be extracted directly to the root of a Switch SD card.

## Download

Download the latest release zip from:

https://github.com/lemon07r/StarterNX/releases/latest

Extract the zip to the SD card root. Back up the SD card first.

Advanced users can also clone the repo and copy the tracked payload files and folders manually.

## Base

- Atmosphere 1.11.1 core from NX-Carnage
- Horizon OC 2.3.0 with patched exosphere enabled on HOC boot entries
- Hekate-ext v6.5.2 from HATS
- sys-patch v1.6.2.0 configured for emuMMC patching only
- DNS MITM hosts for Nintendo blocking plus ad/tracker blocking

## Included Extras

- Horizon OC, hoc-clk, Horizon-OC overlay, and Horizon-OC Monitor
- Ultrahand Overlay and nx-ovlloader
- DBI English 895, JKSV, Daybreak, Sphaira, Haze, reboot_to_payload, CyberFoil, Linkalho, NxThemeInstaller, and Switch 90DNS Tester
- Alchemist 1.0.6 package for managing, converting, and installing mods
- SaltyNX, FPSLocker, emuiibo, EdiZon overlay, QuickNTP, sys-patch overlay, and ovlSysmodules
- TegraExplorer-Ext, FuseCheck, Lockpick_RCM_Pro, and Picofly toolbox payloads

## Boot Entries

| Entry | Use |
| --- | --- |
| CFW EmuMMC + HOC | Main emuMMC boot with Horizon OC and patched exosphere |
| CFW EmuMMC + HOC + Extra RAM | Test emuMMC boot with HOC plus the extra-RAM mesosphere patch |
| CFW EmuMMC Clean | Recovery emuMMC boot without Horizon OC or patched exosphere |
| CFW SysMMC Clean | SysMMC CFW boot without Horizon OC |
| Semi-Stock (SysMMC) | Minimal Atmosphere sysMMC boot |
| 100% Stock OFW | Stock firmware without CFW |

Use `CFW EmuMMC Clean` if an overclock setting prevents the main HOC entry from booting.

## Install Notes

1. Back up the SD card before replacing files.
2. Download the latest release zip and extract it to the SD root.
3. Keep `payload.bin`, `bootloader/update.bin`, `atmosphere/reboot_payload.bin`, and `bootloader/sys/*` on the same Hekate build when updating Hekate.
4. Do not run Kefir Updater, HATS-Tools, or NX-Carnage Easy Setup against this pack. Those workflows assume their own full pack layout and can overwrite StarterNX choices.

## Horizon OC

Horizon OC is installed with upstream 2.3.0 files only. No per-console tuning is included.

## Controls

Open Ultrahand with `L + DDOWN + RS`.

## Homebrew Launching

Launch Album while holding `R` to open HBMenu without the forwarder.
If the old HBMenu forwarder errors after updating, reinstall `games/Homebrew menu [03DB12780BD84000][v0].nsp` with DBI.

## Not Included

- Kefirosphere core files, Kefir updater workflows, Kefir OC, or Kefir branding
- sys-clk or sys-clk-overlay
- Tinfoil, Tinwoo, Goldleaf, or DBI RU
- MissionControl, sys-con, Status Monitor, DowngradeFixer, or Prodinfo_gen

## Credits

StarterNX is a local curated pack assembled from upstream projects and release packs. Please support the original maintainers.

- NX-Carnage: https://github.com/dominatorul/Nx-Carnage
- HATS: https://github.com/sthetix/HATS
- Horizon OC: https://github.com/Horizon-OC/Horizon-OC
- Atmosphere: https://github.com/Atmosphere-NX/Atmosphere
- Hekate: https://github.com/CTCaer/hekate
- sys-patch: https://github.com/impeeza/sys-patch
- Ultrahand Overlay: https://github.com/ppkantorski/Ultrahand-Overlay
- Alchemist: https://github.com/ppkantorski/Alchemist
