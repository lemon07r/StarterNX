# StarterNX

StarterNX is a curated Nintendo Switch CFW SD-card pack for firmware up to 22.5.0. It uses the vanilla Atmosphere 1.11.2 core, selected HATS components, and Horizon OC as its only overclocking system. It is not Kefirosphere-based.

Most users should start with [NX-Carnage](https://github.com/dominatorul/Nx-Carnage) instead. StarterNX is a more opinionated variant with independent component refreshes and a recovery-focused boot layout.

## Download

Download the latest release ZIP from:

https://github.com/lemon07r/StarterNX/releases/latest

Back up the SD card, then extract the ZIP directly to the SD-card root. Users can also clone the repository and copy the tracked files and folders manually.

## Current Stack

- Atmosphere 1.11.2 with Haze and Daybreak, supporting HOS 22.5.0
- Hekatos 6.5.3 from HATS 2026-07-25 (`3e7a04f`)
- Horizon OC 2.5.1 with its patched exosphere, hoc-clk, overlay, and ppkantorski Status Monitor 1.4.1+r4
- sys-patch 1.6.2.3, configured for emuMMC patching only
- Ultrahand Overlay 2.5.3 with nx-ovlloader 2.0.2
- DBI English 898, FuseCheck 1.0.4, Lockpick_RCM_Pro 2.1.0, and ovlSysmodules 1.5.3
- sys-dock 1.0.2 and NX-FanControl, with the NX-FanControl 1.0.3+r4 overlay
- Alchemist 1.0.6, SaltyNX, FPSLocker, emuiibo, EdiZon, QuickNTP, JKSV, Sphaira, CyberFoil, Linkalho, NxThemeInstaller, and Switch 90DNS Tester
- DNS MITM hosts for Nintendo blocking plus ad/tracker blocking

HATS calls its Hekate fork “Hekatos.” All Hekatos payload, update, boot, and `bootloader/sys` files in this pack come from the same 6.5.3/4 GB build.

## Boot Entries

| Entry | Use |
| --- | --- |
| CFW EmuMMC + HOC | Main emuMMC boot with Horizon OC and patched exosphere |
| CFW EmuMMC + HOC + Extra RAM | Test emuMMC boot with HOC plus the retained extra-RAM mesosphere |
| CFW EmuMMC Clean | Recovery emuMMC boot without Horizon OC or patched exosphere |
| CFW SysMMC Clean | SysMMC CFW without Horizon OC |
| Semi-Stock (SysMMC) | Minimal Atmosphere sysMMC boot |
| 100% Stock OFW | Stock firmware without CFW |

Use `CFW EmuMMC Clean` if an overclock setting or HOC migration prevents the main entry from booting.

## Install and Migration Notes

1. Back up the SD card before replacing files.
2. Extract the release ZIP to the SD-card root.
3. If upgrading from HOC 2.4.1, preserve `config/horizon-oc/config.ini`, then reboot through a HOC entry twice. HOC 2.5.1 uses the first boots to migrate the saved configuration into the new KIP.
4. Verify the migrated settings before stress testing. The clean EmuMMC entry remains available throughout recovery.
5. Daybreak is at `switch/daybreak.nro`. DBI and its language/config files are consolidated under `switch/DBI/`.
6. Keep `payload.bin`, `boot.dat`, `bootloader/update.bin`, `atmosphere/reboot_payload.bin`, and `bootloader/sys/*` together when refreshing the boot stack.
7. Do not run Kefir Updater, HATS-Tools, or NX-Carnage Easy Setup against this pack. Those full-pack workflows can overwrite StarterNX choices.

No per-console Horizon OC tuning is shipped in this repository.

## Controls and Homebrew

Open Ultrahand with `L + DDOWN + RS`.

The root `hbmenu.nro` intentionally launches Sphaira. Launch Album while holding `R` to open HBMenu without the forwarder. For HOS 22.5.0, reinstall the refreshed `games/Homebrew menu [03DB12780BD84000][v0].nsp` with DBI if an older installed forwarder errors.

StarterNX retains selected, unchanged Kefir-derived behavior: hbloader 2.4.4, the accessible-URL list, `boot.ini`, Mariko warmboots, the Sphaira root launcher, and curated configuration choices. It does not include the Kefir core, payload, updater, scripts, branding, or OC system.

## Not Included

- Kefirosphere core files, Kefir updater workflows, Kefir OC, or Kefir branding
- sys-clk or sys-clk-overlay
- MissionControl, sys-con, Tinfoil, Tinwoo, Goldleaf, DBI RU, KitNX, HATS-Tools, or ProdinForge
- DowngradeFixer, Prodinfo_gen, or other destructive/redundant tools

## Credits

StarterNX is assembled from upstream open-source projects and release packs. Please support the original maintainers.

- [Atmosphere](https://github.com/Atmosphere-NX/Atmosphere)
- [HATS](https://github.com/sthetix/HATS)
- [Horizon OC](https://github.com/Horizon-OC/Horizon-OC)
- [Hekate](https://github.com/CTCaer/hekate)
- [NX-Carnage](https://github.com/dominatorul/Nx-Carnage)
- [sys-patch](https://github.com/impeeza/sys-patch)
- [Ultrahand Overlay](https://github.com/ppkantorski/Ultrahand-Overlay)
- [Alchemist](https://github.com/ppkantorski/Alchemist)
