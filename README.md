# StarterNX

Custom Nintendo Switch CFW pack for firmware up to 22.1.0.

## Source Stack

- Atmosphere 1.11.1 core from the local NX-Carnage release
- Selected HATS components from 2026-05-11 (7fba776)
- Horizon OC 2.3.0

## What's Included

- Atmosphere 1.11.1 core with HOC patched exosphere
- Hekate-ext v6.5.2
- Horizon OC 2.3.0
- Ultrahand Overlay
- nx-ovlloader v2.0.1
- DBI English 895
- JKSV, Daybreak, Sphaira, Haze, reboot_to_payload, CyberFoil, Linkalho, NxThemeInstaller, and Switch 90DNS Tester
- sys-patch v1.6.2.0
- SaltyNX, FPSLocker, emuiibo, EdiZon overlay, QuickNTP, and ovlSysmodules
- TegraExplorer-Ext, FuseCheck, Lockpick_RCM_Pro, and Picofly toolbox payload
- DNS MITM hosts for Nintendo blocking plus ad/tracker blocking

## Boot Entries

| Entry | Use |
|-------|-----|
| CFW EmuMMC + HOC | Main EmuMMC boot with Horizon OC and patched exosphere enabled |
| CFW EmuMMC + HOC + Extra RAM | Test boot with Horizon OC plus the extra-RAM mesosphere patch |
| CFW EmuMMC Clean | EmuMMC recovery boot without Horizon OC |
| CFW SysMMC Clean | SysMMC CFW boot without Horizon OC |
| Semi-Stock (SysMMC) | Minimal Atmosphere boot |
| 100% Stock OFW | Stock firmware without CFW |

Use the clean EmuMMC entry if an overclock setting prevents the main HOC entry from booting.

## Horizon OC

Horizon OC is installed with upstream 2.3.0 files only. No per-console tuning is included.
Apply your tuned HOC config later after confirming the base pack boots cleanly.

## Not Included

- Kefirosphere core files or Kefir splash/logo branding
- sys-clk or sys-clk-overlay
- Kefir OC configs
- Uberhand
- Kefir Updater or HATS-Tools
- Tinfoil, Tinwoo, Goldleaf, or DBI RU
- MissionControl or sys-con
- Status Monitor Overlay
- DowngradeFixer or Prodinfo_gen

Do not use Kefir Updater or HATS-Tools with this pack. They are designed for their own full packs and can overwrite StarterNX choices.

## Controls

Open Ultrahand with `L + DDOWN + RS`.

## Homebrew Launching

Launch Album while holding `R` to open HBMenu without the forwarder.
If the old HBMenu forwarder errors after updating, reinstall `games/Homebrew menu [03DB12780BD84000][v0].nsp` with DBI.
