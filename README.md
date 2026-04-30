# StarterNX

Custom Nintendo Switch CFW pack built from Kefirosphere 818, HATS 2026-04-21, and Horizon OC.

**Firmware support:** Up to 22.1.0

## Design Principles

- **Kefirosphere** as CFW base (signature patches, thermal tweaks, telemetry blocking)
- **Hekate-ext** as bootloader (v6.5.2 from HATS)
- **Horizon OC** as the sole overclocking system (no sys-clk, no Kefir OC)
- **Ultrahand** as overlay menu (required by HOC, replaces Uberhand)
- **DNS MITM + application-level telemetry blocking** (merged from both packs)

## Boot Entries

| Entry | Description |
|-------|-------------|
| CFW EmuMMC + HOC | EmuMMC with Horizon OC active |
| CFW EmuMMC Clean | EmuMMC without OC KIP (recovery/debugging) |
| CFW SysMMC Clean | SysMMC without OC KIP |
| Semi-Stock (SysMMC) | Atmosphere with stock sysmodules |
| 100% Stock OFW | Original firmware, no CFW |

## Installed Components

### Core
| Component | Version | Source |
|-----------|---------|--------|
| Kefirosphere | 818 | Kefir |
| Hekate-ext | v6.5.2 | HATS |
| Horizon OC (hoc.kip) | latest | HOC |
| hoc-clk | latest | HOC |

### Sysmodules
| Module | TID | Source |
|--------|-----|--------|
| hoc-clk | 00FF0000636C6BFF | HOC |
| nx-ovlloader | 420000000007E51A | HATS v2.0.0 |
| nx-ovlreloader | 420000000007E51B | HATS / Ultrahand |
| MissionControl | 010000000000bd00 | HATS v0.15.1 |
| sys-patch | 420000000000000B | HATS v1.6.1 |
| SaltyNX | 0000000000534C56 | HATS v1.7.5 |
| emuiibo | 0100000000000352 | HATS |

### Overlays (switch/.overlays)
| Overlay | Source |
|---------|--------|
| Ultrahand (ovlmenu.ovl) | HATS v2.4.1 |
| Horizon OC Overlay | HOC |
| Horizon OC Monitor | HOC |
| ovlSysmodules | HATS v1.5.0 |
| ovlEdiZon | HATS v1.0.14 |
| FPSLocker | HATS v3.3.2 |
| emuiibo | HATS v1.1.3 |
| QuickNTP | HATS v1.6.0 |
| sys-patch overlay | HATS v1.6.1 |

### Homebrew Apps (switch/)
| App | Source |
|-----|--------|
| DBI English | HATS v874 |
| JKSV | HATS |
| Daybreak | HATS |
| Sphaira | HATS |
| CyberFoil | HATS v1.4.4 |
| Linkalho | HATS v2.0.2 |
| NxThemeInstaller | HATS v4.8.3 |
| Switch 90DNS Tester | HATS v1.0.4 |
| Ultrahand-Reload | HATS |

### Payloads (bootloader/payloads)
| Payload | Purpose |
|---------|---------|
| TegraExplorer-Ext | Recovery file manager |
| FuseCheck | Fuse state diagnostic |
| Lockpick_RCM_Pro | Console key dumping |
| hwfly_toolbox | HWFly modchip tools |
| Instinct-NX_toolbox | Instinct-NX modchip tools |
| picofly_toolbox | PicoFly modchip tools |

### Extra Data
| Item | Purpose |
|------|---------|
| SaltySD | Runtime plugin framework for game mods |
| emuiibo/overlay/lang | Localization for emuiibo overlay |
| themes/ | Theme patches for NxThemeInstaller |
| scripts/ | TegraExplorer recovery scripts |

## Horizon OC Status

Horizon OC is installed with the upstream `hoc.kip`, `hoc-clk`, overlays, and template config only.
No prior per-console OC tuning has been carried into this pack. Apply tuned `hoc.kip` / `config.ini`
later after validating the base pack boots cleanly.

## Intentionally Excluded

| Item | Reason |
|------|--------|
| sys-clk / sys-clk-overlay | Replaced by Horizon OC (hoc-clk) |
| Uberhand | Replaced by Ultrahand (required for HOC) |
| Kefir OC configs | Replaced by Horizon OC |
| Kefir Updater | Would overwrite custom pack choices |
| HATS-Tools | Would overwrite custom pack choices |
| Tinfoil | Unnecessary with DBI |
| Tinwoo Installer | Redundant with DBI |
| Goldleaf | Redundant with DBI + Sphaira |
| DBI RU | Redundant (English version kept) |
| Status Monitor Overlay | HOC Monitor covers this role |
| sys-con | Not needed (user preference) |
| DowngradeFixer payload | Niche recovery tool, not needed for daily use |
| Prodinfo_gen payload | Niche recovery tool, not needed for daily use |

## Config Highlights

- **system_settings.ini**: Merged from Kefir (comprehensive telemetry/background task blocking) + DNS MITM enabled (from HATS approach)
- **DNS hosts**: `atmosphere/hosts/default.txt` contains the HATS Nintendo blocklist plus Kefir ad/tracker entries
- **HATS system settings**: external Bluetooth DB and OLSC communication block are enabled
- **exosphere.ini**: PRODINFO blanked on both SysMMC and EmuMMC
- **exefs_patches**: Merged from both packs (bluetooth, btm, hid, disable_remap_dialog, logo_sloth, SaltyNX_Fixes)
- **Ultrahand key combo**: L+DDOWN+RS

## Updating Components

Individual components can be updated by downloading new releases and replacing the relevant files:
- **Atmosphere/Kefirosphere**: Replace `atmosphere/package3`, `atmosphere/stratosphere.romfs`
- **Hekate**: Replace `bootloader/sys/*`, `bootloader/update.bin`, `payload.bin`, `atmosphere/reboot_payload.bin`, `boot.dat`
- **Horizon OC**: Replace `atmosphere/kips/hoc.kip`, `atmosphere/contents/00FF0000636C6BFF/exefs.nsp`, overlays, and `config/horizon-oc/`
- **Ultrahand/nx-ovlloader**: Replace `atmosphere/contents/420000000007E51A/`, `atmosphere/contents/420000000007E51B/`, and `switch/.overlays/ovlmenu.ovl`
- **Individual overlays/apps**: Replace the .ovl or .nro file

Do NOT use Kefir Updater or HATS-Tools to update -- they will overwrite your custom configuration.
