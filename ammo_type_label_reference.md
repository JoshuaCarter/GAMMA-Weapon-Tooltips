# Ammo Type label reference (Dorn's Weapon Tooltip)

Complete list of every ammo section in this doc (sorted by section).
Full display name = translated `inv_name`. Source for clean = translated `inv_name_short` (else `inv_name`).
Tooltip label = `AMMO_TYPE_SHORT` in `zz_dorn_weapon_tooltip_main.script` (≤6 chars; unmapped → `????`).
`used` = referenced by at least one weapon `ammo_class` under `c:/GAMMA/mods` (`no` = ammo section exists with ballistic props but no weapon lists it).


| section                | used | full display name (`inv_name`) | source text used for clean | Tooltip label | Color  |
| ---------------------- | ---- | ------------------------------ | -------------------------- | ------------- | ------ |
| `ammo_11.43x23_fmj`    | yes  | .45 ACP FMJ rounds             | .45 FMJ                    | `FMJ`         | yellow |
| `ammo_11.43x23_hydro`  | yes  | .45 ACP Hydra-shock HP rounds  | .45 HP                     | `HP`          | teal   |
| `ammo_12.7x55_ap`      | yes  | 12.7x55 mm STs-130 VPS rounds  | 12.7x55 AP                 | `AP`          | orange |
| `ammo_12.7x55_fmj`     | yes  | 12.7x55mm STs-130 rounds       | 12.7x55 FMJ                | `FMJ`         | yellow |
| `ammo_12x70_buck`      | yes  | 12x70 buckshot shells          | 12x70 buck                 | `BUCK`        | teal   |
| `ammo_12x76_bull`      | yes  | 12x76 Bull shells              | 12x76 Bull                 | `BULL`        | yellow |
| `ammo_12x76_dart`      | yes  | 12x76 AP slugs                 | 12x76 AP slugs             | `SLAP`        | orange |
| `ammo_12x76_zhekan`    | yes  | 12x76 slug shells              | 12x76 slug                 | `SLUG`        | yellow |
| `ammo_20x70_buck`      | yes  | 20x70 buckshot round           | 20x70 buckshot round       | `BUCK`        | teal   |
| `ammo_23_eco`          | yes  | Ecolog-23 cartridge            | Ecolog-23                  | `ECO`         | grey   |
| `ammo_23x75_barrikada` | yes  | "Barrikada" 23x75mm            | "Barrikada" 23x75mm        | `BARR`        | orange |
| `ammo_23x75_shrapnel`  | yes  | "Shrapnel-25" 23x75mm          | "Shrapnel-25" 23x75mm      | `SHRAP`       | teal   |
| `ammo_338_federal`     | yes  | .338 Federal                   | .338 Federal               | `FED`         | teal   |
| `ammo_357_hp_mag`      | yes  | .357 HP rounds                 | .357 HP                    | `HP`          | teal   |
| `ammo_4.6x30_fmj`      | no   | 4.6x30 mm FMJ rounds           | 4.6x30 FMJ                 | `FMJ`         | yellow |
| `ammo_5.45x39_ap`      | yes  | 5.45x39 mm AP rounds           | 5.45x39 AP                 | `AP`          | orange |
| `ammo_5.45x39_ep`      | yes  | 5.45x39 mm HP rounds           | 5.45x39 HP                 | `HP`          | teal   |
| `ammo_5.45x39_fmj`     | yes  | 5.45x39 mm FMJ rounds          | 5.45x39 FMJ                | `FMJ`         | yellow |
| `ammo_5.56x45_ap`      | yes  | 5.56x45 mm AP rounds           | 5.56x45 AP                 | `AP`          | orange |
| `ammo_5.56x45_fmj`     | yes  | 5.56x45 mm FMJ rounds          | 5.56x45 FMJ                | `FMJ`         | yellow |
| `ammo_5.56x45_ss190`   | yes  | 5.56x45 mm HP rounds           | 5.56x45 HP                 | `HP`          | teal   |
| `ammo_5.7x28_ss190`    | yes  | 5.7x28 SS190 rounds            | 5.7x28 AP                  | `AP`          | orange |
| `ammo_5.7x28_ss195`    | yes  | 5.7x28 mm SS195 rounds         | 5.7x28 FMJ                 | `FMJ`         | yellow |
| `ammo_50_bmg`          | no   | .50 BMG rounds                 | .50 BMG                    | `BMG`         | orange |
| `ammo_7.62x25_p`       | yes  | 7.62x25 mm LRNPC rounds        | 7.62x25 LRNPC              | `LRNPC`       | yellow |
| `ammo_7.62x25_ps`      | yes  | 7.62x25 mm Pst rounds          | 7.62x25 Pst                | `PST`         | orange |
| `ammo_7.62x39_ap`      | yes  | 7.62x39 mm M43 rounds          | 7.62x39 AP                 | `AP`          | orange |
| `ammo_7.62x39_fmj`     | yes  | 7.62x39 mm FMJ rounds          | 7.62x39 FMJ                | `FMJ`         | yellow |
| `ammo_7.62x51_ap`      | yes  | 7.62x51 mm NATO AP rounds      | 7.62x51 mm NATO AP rounds  | `AP`          | orange |
| `ammo_7.62x51_fmj`     | yes  | 7.62x51 mm NATO ball rounds    | 7.62x51 FMJ                | `FMJ`         | yellow |
| `ammo_7.62x54_7h1`     | yes  | 7.62x54 mm 7N1 rounds          | 7.62x54 7N1                | `7N1`         | yellow |
| `ammo_7.62x54_7h14`    | yes  | 7.62x54 mm 7N14 rounds         | 7.62x54 7N14               | `7N14`        | orange |
| `ammo_7.62x54_ap`      | yes  | 7.62x54 mm AP rounds           | 7.62x54 AP                 | `AP`          | orange |
| `ammo_7.92x33_ap`      | yes  | 7.92x57 mm AP rounds           | 7.92x57 AP                 | `AP`          | orange |
| `ammo_7.92x33_fmj`     | yes  | 7.92x57 mm FMJ rounds          | 7.92x57 FMJ                | `FMJ`         | yellow |
| `ammo_9x18_ap`         | yes  | 9x18 mm AP rounds              | 9x18 AP                    | `AP`          | orange |
| `ammo_9x18_fmj`        | yes  | 9x18 mm FMJ rounds             | 9x18 FMJ                   | `FMJ`         | yellow |
| `ammo_9x18_pmm`        | yes  | 9x18 mm HP rounds              | 9x18 HP                    | `HP`          | teal   |
| `ammo_9x19_ap`         | yes  | 9x19 mm AP rounds              | 9x19 AP                    | `AP`          | orange |
| `ammo_9x19_fmj`        | yes  | 9x19 mm FMJ rounds             | 9x19 FMJ                   | `FMJ`         | yellow |
| `ammo_9x19_pbp`        | yes  | 9x19 mm HP rounds              | 9x19 HP                    | `HP`          | teal   |
| `ammo_9x21_sp10`       | yes  | 9x21 mm SP10                   | 9x21 mm SP10               | `SP10`        | yellow |
| `ammo_9x39_ap`         | yes  | 9x39 mm SP-6 rounds            | 9x39 SP-6                  | `SP-6`        | orange |
| `ammo_9x39_pab9`       | yes  | 9x39 mm SP-5 rounds            | 9x39 SP-5                  | `SP-5`        | yellow |
| `ammo_gauss`           | yes  | Batteries                      | Batteries                  | `BATT`        | grey   |
| `ammo_m209`            | yes  | M203 grenade                   | M203                       | `M203`        | grey   |
| `ammo_magnum_300`      | yes  | .338 Lapua Magnum rounds       | .338 Lapua Magnum          | `MAG`         | orange |
| `ammo_og-7b`           | yes  | OG-7V warhead                  | OG-7V                      | `OG-7V`       | grey   |
| `ammo_pkm_100`         | yes  | 7.62x54 mm PP rounds           | 7.62x54 PP                 | `PP`          | yellow |
| `ammo_vog-25`          | yes  | VOG-25 grenade                 | VOG-25                     | `VOG-25`      | grey   |
| `ammo_vog-30`          | no   | VOG-30 Grenade                 | VOG-30                     | `VOG-30`      | grey   |


