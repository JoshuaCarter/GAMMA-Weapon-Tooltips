# GAMMA Damage Stats

Per-weapon damage breakdown and optional damage stat row for **S.T.A.L.K.E.R. G.A.M.M.A.** inventory tooltips. Values are read live from merged configs — no LTX edits, no redeclared gun values.

Repository: [JoshuaCarter/GAMMA-Damage-Stats](https://github.com/JoshuaCarter/GAMMA-Damage-Stats)

## Features

### Per-ammo damage breakdown

Adds a section under the weapon's description, using the same bullet glyph and coloring as the native "STATUS" / "PROPERTIES" lines, listing every ammo type the gun accepts:

```
Damage: (49% Power)
 9x39 SP-5:  85 Dmg  AP 120
 9x39 SP-6:  54 Dmg  AP 510
 9x39 PAB-9: 57 Dmg  AP 290
```

- **header %** = gun `hit_power` × 100 (the weapon's raw damage power)
- **Dmg** = gun `hit_power` × ammo `k_hit` × 100 (× pellet count for shotguns)
- **AP &lt;n&gt;** = ammo `k_ap` × 1000 (matches the value on the ammo's own info card)

### Are these numbers "correct"?

They mirror how the ballistics overhaul (GBOOBS) actually resolves a hit. A shot's damage is `hit_power × k_hit × 1.1 × ammo_mult × [distance × bone × barrel × difficulty × …]`, so `hit_power × k_hit` is the intrinsic per-shot term — that's what `Dmg` shows (in the engine's health-fraction units, ×100 to read as a percentage). It is **not clamped to 0–100 and not divided by 1.5**: real damage isn't clamped, and the `/1.5` you might expect from the built-in Damage *bar* is purely that bar's normalization to fit a 0–100% progress meter (which is why the bar reads lower than the real value). `Dmg` therefore excludes only the situational factors a static tooltip can't know (range, hit location, barrel wear, difficulty) plus the small per-ammo `ammo_mult` and the flat `×1.1`, which scale everything roughly equally and don't change relative comparisons.

The engine's damage math is entirely floating-point — it never rounds to an integer (health is a float, and the hit is subtracted as one), so for display we simply round each value to the nearest whole number. If another on-screen figure differs by ±1, that's because it's a separate calculation/scale (or truncates instead of rounding), not a rounding bug here.

Round type for the bullet colour is read from the ammo section name when it's explicit (`…_fmj` / `…_ap` / `…_hp`); rounds without such a token (SP-5, PAB-9, SS190, …) fall back to the damage/penetration heuristic below.

`AP` is the ammo's intrinsic penetration coefficient (`k_ap`), shown at the ×1000 scale the ammo card uses. It is **not** scaled by weapon power — in combat it's only modified by hit location, barrel wear, range and difficulty (and small flat bonuses, e.g. snipers get `+0.05`), none of which apply to a static tooltip.

Rows are sorted by damage (highest first), then by AP (lowest first), so HP-style rounds lead and AP-style rounds trail. Names are trimmed of trailing "rounds" and the damage values are padded into an aligned column.

The header is white and everything after each colon is grey. Only the leading bullet dot is colored (round names stay white, numbers grey), matching the native tooltip sections. The dot color reflects the round's damage/penetration balance **relative to the other rounds that gun accepts**: high damage / low AP → **yellow** (HP-like), high AP / low damage → **red** (AP-like), balanced → **green** (FMJ-like). It's a rough visual cue, not a strict classification.

Neither `tier` nor "BR" (ballistic resistance) is shown: in GAMMA, ballistic resistance is an **armour** property (the NIJ armour class — NONE / I / IIA / IIIA…, defined by which rounds a vest can stop), not an ammo stat, so a per-ammo "BR" would be a made-up number. Only the real penetration coefficient (`k_ap`) is reported. `k_hit` isn't shown separately either, since the `dmg` number already includes it.

## MCM options (both off by default)

- **Show built-in Damage stat row** — re-injects the "Damage" stat bar that G.A.M.M.A. Accurate Defense Values comments out of `ish_item_stats.script`. Note this bar reads lower than the per-ammo numbers: it normalizes `hit_power × k_hit` against a fixed 1.5 ceiling and only samples the first ammo type (bar ≈ dmg ÷ 1.5). The main script is prefixed `zz_` so it loads *after* Accurate Defense Values, which rebuilds the whole weapon stats table on game start / difficulty change — otherwise the re-enabled row would be wiped.
- **Show old / degraded ammo** — a weapon's `ammo_class` lists every round *and* its degraded `_bad`/`_verybad` copies, so the raw list repeats each round three times. Off hides them; on lists them too, tagged `(Old)` / `(Worn)`.

## Installation

1. Place the mod folder in your MO2 mods directory
2. Enable it and load it **after** G.A.M.M.A. Accurate Defense Values
3. Launch the game

## Requirements

- S.T.A.L.K.E.R. Anomaly / G.A.M.M.A. with the standard tooltip stack (`utils_ui`, Nitpicker or GAMMA `ish_item_stats`)
- MCM (Mod Configuration Menu) is optional — used for the toggles above and on-screen debug logging; without it both toggles stay off (per-ammo breakdown still shows)
