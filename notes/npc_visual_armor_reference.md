# NPC visual outfits — raw bone armor

## Summary by armor value

**Count** = unique capture models (`models\capture\*.ltx` stems) that at least one actor visual uses in `grok_bo_models_capture.ltx`. Bone profile sections that exist only in `grok_bo_bone_profiles.ltx` and are never a `model_path` (e.g. `stalker_dolg_4_omon`) are excluded. Chip = average `hit_fraction_npc` (% of damage that still applies on a failed pen). Table name = Dorn tooltip column label when that value is shown.

**GAMMA repair** = modal `repair_type` of outfits those visuals tend to drop (`death_outfits` → Outfits Balances). Ladder is novice → light → medium → heavy → exo (Nosorog is still exo). Percents below are among mapped models at that bone value (some visuals have no death-outfit join).

**Ammo pen** = rough share of standard live firearm ammo that pens that bone armor at 20 m under **CQC** `grok_bo` math: `(k_ap × 10) × ap_scale / range_atten × 0.80` (difficulty mult = 1.0 for this table; no silencer — live CQC also ×1.07 when silenced). CQC loads above GBOOBS, so CQC owns `grok_bo` and `weapon_ammo.ltx`. Head values model `bip01_head` (no eye/eyelid AP boost). Excludes `_bad` / `_verybad`, knives, batteries, and grenades (~48 rounds). Rounded to nearest 5%.

### Torso

| Table name | Armor | Count | Avg chip | Ammo pen | GAMMA repair |
|---|---:|---:|---:|---:|---|
| Min | 0.011 | 9 | 85% | ~100% | **novice** (about 89%) — clean novice bucket |
| Lgt | 0.075 | 6 | 60% | ~80% | **medium** (about 75%), novice (about 25%) — leans medium; army/soldier minority is novice (`army_outfit`) |
| Lgt+ | 0.100 | 8 | 50% | ~70% | **medium** (about 75% of mapped), some light/novice (about 12% each) — leans medium (Sunrise-ish); a few unmapped |
| - | 0.125 | 1 | 40% | ~65% | **medium** (1/1) |
| Mid | 0.150 | 24 | 48% | ~60% | **medium** (about 87% of mapped) — best medium representative; light about 9%, novice about 4% |
| Mid+ | 0.200 | 13 | 37% | ~35% | **medium** (about 75% of mapped), heavy about 17%, exo about 8% — still medium overall, but messiest mid-tier (Berill/SEVA vs proto pull) |
| Hvy | 0.250 | 10 | 30% | ~25% | **heavy** (100% of mapped) — clean start of heavy (SKAT / assault vest / `light_*` outfits) |
| - | 0.300 | 1 | 30% | ~20% | **heavy** (exolight) |
| - | 0.350 | 2 | 22% | ~10% | **heavy** (small n) |
| Hvy+ | 0.400 | 4 | 20% | ~10% | **heavy** (100% of mapped) — mid-heavy / exolight-class, **not** exo kit |
| - | 0.430 | 1 | 15% | ~10% | **exo** (Freedom heavy / full exo drop) |
| Exo | 0.550 | 5 | 15% | ~5% | **exo** — standard full exo |
| Max | 0.650 | 2 | 15% | ~5% | **exo** — top exo / Nosorog (same exo kit) |

**Picking a “medium” column:** prefer **0.150** over **0.200** — more profiles, higher medium purity (about 87% vs about 75%), less heavy/exo bleed. **0.100** is also medium-leaning but thinner and more light/novice noise. **0.075** is the weak “Light” label — mostly medium repair, not GAMMA light kits.

**Picking a “heavy” column:** **0.250** is the cleanest heavy start; **0.400** is still heavy (exolight), not exo. True **exo** repair begins around **0.430–0.550**.

### Head

| Table name | Armor | Count | Avg chip | Ammo pen | GAMMA repair |
|---|---:|---:|---:|---:|---|
| Min | 0 | 39 | n/a (always full damage) | ~100% | mixed (body drives drop class) — not a useful repair signal |
| Lgt | 0.150 | 7 | 41% | ~55% | mostly tracks **medium** bodies |
| Mid | 0.200 | 13 | 44% | ~40% | mostly **medium** bodies |
| Hvy | 0.300 | 26 | 33% | ~20% | mixed medium/heavy/exo bodies — weak repair signal |
| Max | 0.350 | 1 | 15% | ~10% | **exo** (Nosorog) |

Head bone armor does not track repair kits cleanly; same suit family wears many helm variants.

---

Source chain (load order: higher wins):

1. NPC visual → `grok_bo_models_capture.ltx` → capture model
2. Capture `bones_protection_sect` → `grok_bo_bone_profiles.ltx` (**CQC** over GBOOBS)
3. `bone_profile` / `head_profile` → floats in Outfits Balances `damages.ltx`

**Torso armor** = `bip01_spine` bone armor (compared to combat AP in live CQC damage).
**Head armor** = `bip01_head` (no eye/eyelid AP boost in these columns).

Count: **86** unique capture models used by actor visuals (105 bone profile sections exist; 19 are never a `model_path`). Torso range: **0.011–0.650**. Head range: **0–0.350**.

**Naming:** Labels are **death-outfit inventory display names** inferred from visuals that share each bone profile (`models_capture` → `outfit_by_visual`). One profile can drop several faction kits; the name is the canonical / most-common player outfit for that look (e.g. SSP → SSP-99, not the internal `stalker_ssp` id). Combat armor still comes from the bone profile — loot can differ. Unmapped profiles end with `[?]`. Detail rows below still list bone profiles (including unused ones) for reference; **Count** columns use unique used models only.

### Profiles by torso armor

| Typical loot outfit | Torso | Head | Chip (hit_frac) | AP scale | Related loot names |
|---|---:|---:|---:|---:|---|
| Black Leather Jacket | 0.011 | 0.000 | 0.90 | 0.90 | Black Leather Jacket |
| Heavy Brown Overcoat | 0.011 | 0.000 | 0.85 | 0.90 | Heavy Brown Overcoat |
| Leather Jacket (neutral 1) | 0.011 | 0.000 | 0.90 | 0.90 | Leather Jacket |
| Leather Jacket (novice 1) | 0.011 | 0.000 | 0.90 | 0.90 | Leather Jacket |
| Leather Jacket (novice) | 0.011 | 0.000 | 0.90 | 0.90 | Leather Jacket |
| Overcoat (trenchcoat 1) | 0.011 | 0.000 | 0.70 | 0.85 | Overcoat |
| Overcoat (trenchcoat) | 0.011 | 0.000 | 0.70 | 0.85 | Overcoat |
| Leather Jacket (novice 2) | 0.011 | 0.200 | 0.90 | 0.90 | Leather Jacket |
| Leather Jacket (novice 3) | 0.011 | 0.300 | 0.90 | 0.90 | Leather Jacket |
| Military Service Outfit (army uniform 1) | 0.075 | 0.000 | 0.60 | 0.85 | Military Service Outfit |
| Military Service Outfit (army uniform) | 0.075 | 0.000 | 0.60 | 0.85 | Military Service Outfit |
| Military Service Outfit (soldier 1) | 0.075 | 0.000 | 0.70 | 0.85 | Military Service Outfit |
| Monolith X-18 Suit (sts) | 0.075 | 0.000 | 0.40 | 0.85 | Monolith X-18 Suit |
| Overcoat (bandit 4) | 0.075 | 0.000 | 0.70 | 0.85 | Heavy Brown Overcoat, Overcoat, bandit 6a |
| SSP-99 Bodysuit | 0.075 | 0.150 | 0.80 | 0.90 | SSP-99 Bodysuit |
| Military Service Outfit (army uniform 2) | 0.075 | 0.200 | 0.60 | 0.85 | Military Service Outfit |
| Military Service Outfit (army uniform 3) | 0.075 | 0.300 | 0.60 | 0.85 | Military Service Outfit |
| "Sunrise" Stalker Suit (neutral 2 antigas) | 0.100 | 0.000 | 0.50 | 0.80 | "Sunrise" Stalker Suit |
| "Sunrise" Stalker Suit (neutral 2) | 0.100 | 0.000 | 0.50 | 0.80 | neutral2v, "Sunrise" Stalker Suit, Berill-5M Armored Suit |
| "Sunrise" Stalker Suit (sunrise 1) | 0.100 | 0.000 | 0.50 | 0.80 | "Sunrise" Stalker Suit |
| "Sunrise" Stalker Suit (sunrise) | 0.100 | 0.000 | 0.50 | 0.80 | "Sunrise" Stalker Suit |
| Oon 1 [?] | 0.100 | 0.000 | 0.50 | 0.80 | oon 1 |
| Oon 2 [?] | 0.100 | 0.000 | 0.50 | 0.80 | oon 2 |
| Wind of Freedom (freedom 1) | 0.100 | 0.000 | 0.50 | 0.80 | Wind of Freedom |
| "Sunrise" Stalker Suit (neutral 2 helmet) | 0.100 | 0.200 | 0.50 | 0.80 | neutral2h |
| "Sunrise" Stalker Suit (sunrise 2) | 0.100 | 0.200 | 0.50 | 0.80 | "Sunrise" Stalker Suit |
| CS-1 Body Armor | 0.100 | 0.200 | 0.50 | 0.75 | CS-1 Body Armor |
| "Sunrise" Stalker Suit (sunrise 3) | 0.100 | 0.300 | 0.50 | 0.80 | "Sunrise" Stalker Suit |
| "Sunrise" Stalker Suit (sunrise 4) | 0.100 | 0.300 | 0.50 | 0.80 | "Sunrise" Stalker Suit |
| CS-2a Body Armor | 0.125 | 0.200 | 0.40 | 0.80 | CS-2a Body Armor |
| Fenced LC Suit | 0.150 | 0.000 | 0.40 | 0.80 | Fenced LC Suit |
| ISRIT Guard Jumpsuit | 0.150 | 0.000 | 0.40 | 0.85 | ISRIT Guard Jumpsuit |
| Mercenary LC Suit (lcs 1) | 0.150 | 0.000 | 0.50 | 0.80 | Mercenary LC Suit |
| Mercenary LC Suit (lcs) | 0.150 | 0.000 | 0.50 | 0.80 | Mercenary LC Suit |
| Mercenary LC Suit (merc 1) | 0.150 | 0.000 | 0.50 | 0.80 | Mercenary LC Suit |
| Mercenary LC Suit (merc 2) | 0.150 | 0.000 | 0.50 | 0.80 | Mercenary LC Suit |
| Monolith X-18 Suit (monolith 2) | 0.150 | 0.000 | 0.45 | 0.80 | Monolith X-18 Suit |
| Neutral 7 [?] | 0.150 | 0.000 | 0.45 | 0.80 | neutral 7 |
| Overcoat (trenchcoat armor 1) | 0.150 | 0.000 | 0.45 | 0.80 | Overcoat |
| Overcoat (trenchcoat armor) | 0.150 | 0.000 | 0.45 | 0.80 | Overcoat |
| PS5-M Universal Protection Suit (dolg 2) | 0.150 | 0.000 | 0.45 | 0.80 | PS5-M Universal Protection Suit |
| PS5-M Universal Protection Suit (ps5 1) | 0.150 | 0.000 | 0.45 | 0.80 | PS5-M Universal Protection Suit |
| PS5-M Universal Protection Suit (ps5) | 0.150 | 0.000 | 0.45 | 0.80 | PS5-M Universal Protection Suit |
| SEVA Bodysuit (neutral nauchniy no helmet) | 0.150 | 0.000 | 0.40 | 0.80 | dol1nh, nauchnh |
| Sentinel of Freedom (freedom 2) | 0.150 | 0.000 | 0.45 | 0.80 | Sentinel of Freedom |
| Tactical Stalker Suit | 0.150 | 0.000 | 0.70 | 0.85 | Tactical Stalker Suit |
| Zombied 1 [?] | 0.150 | 0.000 | 0.85 | 0.90 | zombied 1 |
| Monolith Scientific Suit | 0.150 | 0.150 | 0.40 | 0.80 | Mercenary SEVA Suit, monolith1, Monolith Scientific Suit |
| PS5-9Md Universal Scientific Suit | 0.150 | 0.150 | 0.40 | 0.80 | PS5-9Md Universal Scientific Suit |
| SEVA Bodysuit (neutral nauchniy) | 0.150 | 0.150 | 0.40 | 0.80 | PS5-9Md Universal Scientific Suit, ecolog 1, ecolog green 1, SEVA Bodysuit |
| Mercenary LC Suit (lcs 2) | 0.150 | 0.200 | 0.50 | 0.80 | Mercenary LC Suit |
| PS5-M Universal Protection Suit (dolg 2 helmet) | 0.150 | 0.200 | 0.45 | 0.80 | dolg2h |
| PS5-M Universal Protection Suit (ps5 2) | 0.150 | 0.200 | 0.45 | 0.80 | PS5-M Universal Protection Suit |
| Sentinel of Freedom (freedom 2 helmet) | 0.150 | 0.200 | 0.45 | 0.80 | freedom2h |
| Wind of Freedom (sts 2) | 0.150 | 0.200 | 0.40 | 0.85 | Wind of Freedom |
| Mercenary LC Suit (lcs 3) | 0.150 | 0.300 | 0.50 | 0.80 | Mercenary LC Suit |
| Mercenary LC Suit (lcs 4) | 0.150 | 0.300 | 0.50 | 0.80 | Mercenary LC Suit |
| Monolith X-18 Suit (sts 3) | 0.150 | 0.300 | 0.40 | 0.85 | Monolith X-18 Suit |
| PS5-M Universal Protection Suit (ps5 3) | 0.150 | 0.300 | 0.45 | 0.80 | PS5-M Universal Protection Suit |
| PS5-M Universal Protection Suit (ps5 4) | 0.150 | 0.300 | 0.45 | 0.80 | PS5-M Universal Protection Suit |
| Wind of Freedom (sts 4) | 0.150 | 0.300 | 0.70 | 0.85 | Wind of Freedom |
| "Sunrise" Exoskeleton (proto 1) | 0.200 | 0.000 | 0.45 | 0.70 | "Sunrise" Exoskeleton |
| "Sunrise" Exoskeleton (proto) | 0.200 | 0.000 | 0.45 | 0.70 | "Sunrise" Exoskeleton |
| Berill-5M Armored Suit (berill 1) | 0.200 | 0.000 | 0.30 | 0.75 | Berill-5M Armored Suit |
| Berill-5M Armored Suit (berill) | 0.200 | 0.000 | 0.30 | 0.75 | Berill-5M Armored Suit |
| Berill-5M Armored Suit (soldier 3 no helmet) | 0.200 | 0.000 | 0.30 | 0.75 | soldie3nh |
| Zombied 2 [?] | 0.200 | 0.000 | 0.60 | 0.85 | zombie 2, zombied 2 |
| SEVA Bodysuit (seva) | 0.200 | 0.150 | 0.45 | 0.70 | SEVA Bodysuit |
| "Sunrise" Exoskeleton (proto 2) | 0.200 | 0.200 | 0.45 | 0.70 | "Sunrise" Exoskeleton |
| Berill-5M Armored Suit (berill 2) | 0.200 | 0.200 | 0.30 | 0.75 | Berill-5M Armored Suit |
| Berill-5M Armored Suit (soldier 2 helmet) | 0.200 | 0.200 | 0.30 | 0.75 | soldier2h |
| Berill-5M Armored Suit (soldier 2) | 0.200 | 0.200 | 0.30 | 0.75 | Berill-5M Armored Suit |
| CS-3a Body Armor | 0.200 | 0.200 | 0.30 | 0.75 | CS-3a Body Armor |
| Guardian of Freedom | 0.200 | 0.200 | 0.30 | 0.75 | Guardian of Freedom |
| "Sunrise" Exoskeleton (proto 3) | 0.200 | 0.300 | 0.45 | 0.70 | "Sunrise" Exoskeleton |
| Berill-5M Armored Suit (berill 3) | 0.200 | 0.300 | 0.30 | 0.75 | Berill-5M Armored Suit |
| Berill-5M Armored Suit (berill 4) | 0.200 | 0.300 | 0.30 | 0.75 | Berill-5M Armored Suit |
| Berill-5M Armored Suit (soldier 3) | 0.200 | 0.300 | 0.30 | 0.75 | Deserter's B-5M Armored Suit, Berill-5M Armored Suit |
| Interceptor Body Armor (assault vest 1) | 0.250 | 0.000 | 0.30 | 0.75 | Interceptor Body Armor |
| Interceptor Body Armor (assault vest) | 0.250 | 0.000 | 0.30 | 0.75 | Interceptor Body Armor |
| Skat-9 Armored Suit (skat 1) | 0.250 | 0.000 | 0.30 | 0.75 | Skat-9 Armored Suit |
| Skat-9 Armored Suit (skat) | 0.250 | 0.000 | 0.30 | 0.75 | Skat-9 Armored Suit |
| Zombied 3 [?] | 0.250 | 0.000 | 0.40 | 0.80 | zombied 3 |
| Hero 1 [?] | 0.250 | 0.150 | 0.25 | 0.60 | hero 1, hero stc strelok, trader 1, ucheniy 1 |
| Skat-9 Armored Suit (skat 2) | 0.250 | 0.200 | 0.30 | 0.75 | Skat-9 Armored Suit |
| Interceptor Body Armor (assault vest 3) | 0.250 | 0.300 | 0.30 | 0.75 | Interceptor Body Armor |
| Skat-9 Armored Suit (skat 3) | 0.250 | 0.300 | 0.30 | 0.75 | Skat-9 Armored Suit |
| Skat-9 Armored Suit (skat 4) | 0.250 | 0.300 | 0.30 | 0.75 | Skat-9 Armored Suit |
| Exosuit (exolight) | 0.300 | 0.300 | 0.30 | 0.70 | Exosuit |
| Zombied 4 [?] | 0.350 | 0.000 | 0.25 | 0.75 | zombied 4 |
| Skat-9 Armored Suit (soldier 4) | 0.350 | 0.300 | 0.20 | 0.75 | Skat-9 Armored Suit |
| PSZ-7p Shell Armor (dolg 3 no helmet) | 0.400 | 0.000 | 0.20 | 0.75 | Hybrid Armored Suit |
| Exosuit (neutral 3) | 0.400 | 0.300 | 0.20 | 0.75 | Exosuit |
| Mercenary Exosuit | 0.400 | 0.300 | 0.20 | 0.75 | Mercenary Exosuit |
| Monolith Exosuit | 0.400 | 0.300 | 0.20 | 0.75 | Monolith Exosuit |
| PSZ-7p Shell Armor (dolg 3) | 0.400 | 0.300 | 0.20 | 0.75 | PSZ-7p Shell Armor, heavy, heavy low |
| Paragon of Freedom | 0.430 | 0.300 | 0.15 | 0.70 | Paragon of Freedom |
| Exoskeleton (exo s) | 0.550 | 0.150 | 0.15 | 0.70 | Exoskeleton |
| Exoskeleton (exo) | 0.550 | 0.300 | 0.15 | 0.70 | Exoskeleton |
| Exoskeleton (neutral 4) | 0.550 | 0.300 | 0.15 | 0.70 | Exoskeleton |
| Mercenary Exoskeleton | 0.550 | 0.300 | 0.15 | 0.70 | gilet mask damage low, Mercenary Exoskeleton |
| Monolith Exoskeleton | 0.550 | 0.300 | 0.15 | 0.70 | Monolith Exoskeleton |
| PSZ-10d Exoskeleton (dolg 4) | 0.650 | 0.300 | 0.15 | 0.70 | PSZ-10d Exoskeleton |
| Military Stalker Nosorog | 0.650 | 0.350 | 0.15 | 0.70 | Military Stalker Nosorog |
| PSZ-10d Exoskeleton (dolg 4 omon) [unused model] | 0.650 | 0.350 | 0.15 | 0.70 | PSZ-10d Exoskeleton |

### Profiles by head armor

Same 105 profiles, sorted by **head** then torso.

| Typical loot outfit | Head | Torso | Chip (hit_frac) | AP scale | Related loot names |
|---|---:|---:|---:|---:|---|
| Black Leather Jacket | 0.000 | 0.011 | 0.90 | 0.90 | Black Leather Jacket |
| Heavy Brown Overcoat | 0.000 | 0.011 | 0.85 | 0.90 | Heavy Brown Overcoat |
| Leather Jacket (neutral 1) | 0.000 | 0.011 | 0.90 | 0.90 | Leather Jacket |
| Leather Jacket (novice 1) | 0.000 | 0.011 | 0.90 | 0.90 | Leather Jacket |
| Leather Jacket (novice) | 0.000 | 0.011 | 0.90 | 0.90 | Leather Jacket |
| Overcoat (trenchcoat 1) | 0.000 | 0.011 | 0.70 | 0.85 | Overcoat |
| Overcoat (trenchcoat) | 0.000 | 0.011 | 0.70 | 0.85 | Overcoat |
| Military Service Outfit (army uniform 1) | 0.000 | 0.075 | 0.60 | 0.85 | Military Service Outfit |
| Military Service Outfit (army uniform) | 0.000 | 0.075 | 0.60 | 0.85 | Military Service Outfit |
| Military Service Outfit (soldier 1) | 0.000 | 0.075 | 0.70 | 0.85 | Military Service Outfit |
| Monolith X-18 Suit (sts) | 0.000 | 0.075 | 0.40 | 0.85 | Monolith X-18 Suit |
| Overcoat (bandit 4) | 0.000 | 0.075 | 0.70 | 0.85 | Heavy Brown Overcoat, Overcoat, bandit 6a |
| "Sunrise" Stalker Suit (neutral 2 antigas) | 0.000 | 0.100 | 0.50 | 0.80 | "Sunrise" Stalker Suit |
| "Sunrise" Stalker Suit (neutral 2) | 0.000 | 0.100 | 0.50 | 0.80 | neutral2v, "Sunrise" Stalker Suit, Berill-5M Armored Suit |
| "Sunrise" Stalker Suit (sunrise 1) | 0.000 | 0.100 | 0.50 | 0.80 | "Sunrise" Stalker Suit |
| "Sunrise" Stalker Suit (sunrise) | 0.000 | 0.100 | 0.50 | 0.80 | "Sunrise" Stalker Suit |
| Oon 1 [?] | 0.000 | 0.100 | 0.50 | 0.80 | oon 1 |
| Oon 2 [?] | 0.000 | 0.100 | 0.50 | 0.80 | oon 2 |
| Wind of Freedom (freedom 1) | 0.000 | 0.100 | 0.50 | 0.80 | Wind of Freedom |
| Fenced LC Suit | 0.000 | 0.150 | 0.40 | 0.80 | Fenced LC Suit |
| ISRIT Guard Jumpsuit | 0.000 | 0.150 | 0.40 | 0.85 | ISRIT Guard Jumpsuit |
| Mercenary LC Suit (lcs 1) | 0.000 | 0.150 | 0.50 | 0.80 | Mercenary LC Suit |
| Mercenary LC Suit (lcs) | 0.000 | 0.150 | 0.50 | 0.80 | Mercenary LC Suit |
| Mercenary LC Suit (merc 1) | 0.000 | 0.150 | 0.50 | 0.80 | Mercenary LC Suit |
| Mercenary LC Suit (merc 2) | 0.000 | 0.150 | 0.50 | 0.80 | Mercenary LC Suit |
| Monolith X-18 Suit (monolith 2) | 0.000 | 0.150 | 0.45 | 0.80 | Monolith X-18 Suit |
| Neutral 7 [?] | 0.000 | 0.150 | 0.45 | 0.80 | neutral 7 |
| Overcoat (trenchcoat armor 1) | 0.000 | 0.150 | 0.45 | 0.80 | Overcoat |
| Overcoat (trenchcoat armor) | 0.000 | 0.150 | 0.45 | 0.80 | Overcoat |
| PS5-M Universal Protection Suit (dolg 2) | 0.000 | 0.150 | 0.45 | 0.80 | PS5-M Universal Protection Suit |
| PS5-M Universal Protection Suit (ps5 1) | 0.000 | 0.150 | 0.45 | 0.80 | PS5-M Universal Protection Suit |
| PS5-M Universal Protection Suit (ps5) | 0.000 | 0.150 | 0.45 | 0.80 | PS5-M Universal Protection Suit |
| SEVA Bodysuit (neutral nauchniy no helmet) | 0.000 | 0.150 | 0.40 | 0.80 | dol1nh, nauchnh |
| Sentinel of Freedom (freedom 2) | 0.000 | 0.150 | 0.45 | 0.80 | Sentinel of Freedom |
| Tactical Stalker Suit | 0.000 | 0.150 | 0.70 | 0.85 | Tactical Stalker Suit |
| Zombied 1 [?] | 0.000 | 0.150 | 0.85 | 0.90 | zombied 1 |
| "Sunrise" Exoskeleton (proto 1) | 0.000 | 0.200 | 0.45 | 0.70 | "Sunrise" Exoskeleton |
| "Sunrise" Exoskeleton (proto) | 0.000 | 0.200 | 0.45 | 0.70 | "Sunrise" Exoskeleton |
| Berill-5M Armored Suit (berill 1) | 0.000 | 0.200 | 0.30 | 0.75 | Berill-5M Armored Suit |
| Berill-5M Armored Suit (berill) | 0.000 | 0.200 | 0.30 | 0.75 | Berill-5M Armored Suit |
| Berill-5M Armored Suit (soldier 3 no helmet) | 0.000 | 0.200 | 0.30 | 0.75 | soldie3nh |
| Zombied 2 [?] | 0.000 | 0.200 | 0.60 | 0.85 | zombie 2, zombied 2 |
| Interceptor Body Armor (assault vest 1) | 0.000 | 0.250 | 0.30 | 0.75 | Interceptor Body Armor |
| Interceptor Body Armor (assault vest) | 0.000 | 0.250 | 0.30 | 0.75 | Interceptor Body Armor |
| Skat-9 Armored Suit (skat 1) | 0.000 | 0.250 | 0.30 | 0.75 | Skat-9 Armored Suit |
| Skat-9 Armored Suit (skat) | 0.000 | 0.250 | 0.30 | 0.75 | Skat-9 Armored Suit |
| Zombied 3 [?] | 0.000 | 0.250 | 0.40 | 0.80 | zombied 3 |
| Zombied 4 [?] | 0.000 | 0.350 | 0.25 | 0.75 | zombied 4 |
| PSZ-7p Shell Armor (dolg 3 no helmet) | 0.000 | 0.400 | 0.20 | 0.75 | Hybrid Armored Suit |
| SSP-99 Bodysuit | 0.150 | 0.075 | 0.80 | 0.90 | SSP-99 Bodysuit |
| Monolith Scientific Suit | 0.150 | 0.150 | 0.40 | 0.80 | Mercenary SEVA Suit, monolith1, Monolith Scientific Suit |
| PS5-9Md Universal Scientific Suit | 0.150 | 0.150 | 0.40 | 0.80 | PS5-9Md Universal Scientific Suit |
| SEVA Bodysuit (neutral nauchniy) | 0.150 | 0.150 | 0.40 | 0.80 | PS5-9Md Universal Scientific Suit, ecolog 1, ecolog green 1, SEVA Bodysuit |
| SEVA Bodysuit (seva) | 0.150 | 0.200 | 0.45 | 0.70 | SEVA Bodysuit |
| Hero 1 [?] | 0.150 | 0.250 | 0.25 | 0.60 | hero 1, hero stc strelok, trader 1, ucheniy 1 |
| Exoskeleton (exo s) | 0.150 | 0.550 | 0.15 | 0.70 | Exoskeleton |
| Leather Jacket (novice 2) | 0.200 | 0.011 | 0.90 | 0.90 | Leather Jacket |
| Military Service Outfit (army uniform 2) | 0.200 | 0.075 | 0.60 | 0.85 | Military Service Outfit |
| "Sunrise" Stalker Suit (neutral 2 helmet) | 0.200 | 0.100 | 0.50 | 0.80 | neutral2h |
| "Sunrise" Stalker Suit (sunrise 2) | 0.200 | 0.100 | 0.50 | 0.80 | "Sunrise" Stalker Suit |
| CS-1 Body Armor | 0.200 | 0.100 | 0.50 | 0.75 | CS-1 Body Armor |
| CS-2a Body Armor | 0.200 | 0.125 | 0.40 | 0.80 | CS-2a Body Armor |
| Mercenary LC Suit (lcs 2) | 0.200 | 0.150 | 0.50 | 0.80 | Mercenary LC Suit |
| PS5-M Universal Protection Suit (dolg 2 helmet) | 0.200 | 0.150 | 0.45 | 0.80 | dolg2h |
| PS5-M Universal Protection Suit (ps5 2) | 0.200 | 0.150 | 0.45 | 0.80 | PS5-M Universal Protection Suit |
| Sentinel of Freedom (freedom 2 helmet) | 0.200 | 0.150 | 0.45 | 0.80 | freedom2h |
| Wind of Freedom (sts 2) | 0.200 | 0.150 | 0.40 | 0.85 | Wind of Freedom |
| "Sunrise" Exoskeleton (proto 2) | 0.200 | 0.200 | 0.45 | 0.70 | "Sunrise" Exoskeleton |
| Berill-5M Armored Suit (berill 2) | 0.200 | 0.200 | 0.30 | 0.75 | Berill-5M Armored Suit |
| Berill-5M Armored Suit (soldier 2 helmet) | 0.200 | 0.200 | 0.30 | 0.75 | soldier2h |
| Berill-5M Armored Suit (soldier 2) | 0.200 | 0.200 | 0.30 | 0.75 | Berill-5M Armored Suit |
| CS-3a Body Armor | 0.200 | 0.200 | 0.30 | 0.75 | CS-3a Body Armor |
| Guardian of Freedom | 0.200 | 0.200 | 0.30 | 0.75 | Guardian of Freedom |
| Skat-9 Armored Suit (skat 2) | 0.200 | 0.250 | 0.30 | 0.75 | Skat-9 Armored Suit |
| Leather Jacket (novice 3) | 0.300 | 0.011 | 0.90 | 0.90 | Leather Jacket |
| Military Service Outfit (army uniform 3) | 0.300 | 0.075 | 0.60 | 0.85 | Military Service Outfit |
| "Sunrise" Stalker Suit (sunrise 3) | 0.300 | 0.100 | 0.50 | 0.80 | "Sunrise" Stalker Suit |
| "Sunrise" Stalker Suit (sunrise 4) | 0.300 | 0.100 | 0.50 | 0.80 | "Sunrise" Stalker Suit |
| Mercenary LC Suit (lcs 3) | 0.300 | 0.150 | 0.50 | 0.80 | Mercenary LC Suit |
| Mercenary LC Suit (lcs 4) | 0.300 | 0.150 | 0.50 | 0.80 | Mercenary LC Suit |
| Monolith X-18 Suit (sts 3) | 0.300 | 0.150 | 0.40 | 0.85 | Monolith X-18 Suit |
| PS5-M Universal Protection Suit (ps5 3) | 0.300 | 0.150 | 0.45 | 0.80 | PS5-M Universal Protection Suit |
| PS5-M Universal Protection Suit (ps5 4) | 0.300 | 0.150 | 0.45 | 0.80 | PS5-M Universal Protection Suit |
| Wind of Freedom (sts 4) | 0.300 | 0.150 | 0.70 | 0.85 | Wind of Freedom |
| "Sunrise" Exoskeleton (proto 3) | 0.300 | 0.200 | 0.45 | 0.70 | "Sunrise" Exoskeleton |
| Berill-5M Armored Suit (berill 3) | 0.300 | 0.200 | 0.30 | 0.75 | Berill-5M Armored Suit |
| Berill-5M Armored Suit (berill 4) | 0.300 | 0.200 | 0.30 | 0.75 | Berill-5M Armored Suit |
| Berill-5M Armored Suit (soldier 3) | 0.300 | 0.200 | 0.30 | 0.75 | Deserter's B-5M Armored Suit, Berill-5M Armored Suit |
| Interceptor Body Armor (assault vest 3) | 0.300 | 0.250 | 0.30 | 0.75 | Interceptor Body Armor |
| Skat-9 Armored Suit (skat 3) | 0.300 | 0.250 | 0.30 | 0.75 | Skat-9 Armored Suit |
| Skat-9 Armored Suit (skat 4) | 0.300 | 0.250 | 0.30 | 0.75 | Skat-9 Armored Suit |
| Exosuit (exolight) | 0.300 | 0.300 | 0.30 | 0.70 | Exosuit |
| Skat-9 Armored Suit (soldier 4) | 0.300 | 0.350 | 0.20 | 0.75 | Skat-9 Armored Suit |
| Exosuit (neutral 3) | 0.300 | 0.400 | 0.20 | 0.75 | Exosuit |
| Mercenary Exosuit | 0.300 | 0.400 | 0.20 | 0.75 | Mercenary Exosuit |
| Monolith Exosuit | 0.300 | 0.400 | 0.20 | 0.75 | Monolith Exosuit |
| PSZ-7p Shell Armor (dolg 3) | 0.300 | 0.400 | 0.20 | 0.75 | PSZ-7p Shell Armor, heavy, heavy low |
| Paragon of Freedom | 0.300 | 0.430 | 0.15 | 0.70 | Paragon of Freedom |
| Exoskeleton (exo) | 0.300 | 0.550 | 0.15 | 0.70 | Exoskeleton |
| Exoskeleton (neutral 4) | 0.300 | 0.550 | 0.15 | 0.70 | Exoskeleton |
| Mercenary Exoskeleton | 0.300 | 0.550 | 0.15 | 0.70 | gilet mask damage low, Mercenary Exoskeleton |
| Monolith Exoskeleton | 0.300 | 0.550 | 0.15 | 0.70 | Monolith Exoskeleton |
| PSZ-10d Exoskeleton (dolg 4) | 0.300 | 0.650 | 0.15 | 0.70 | PSZ-10d Exoskeleton |
| Military Stalker Nosorog | 0.350 | 0.650 | 0.15 | 0.70 | Military Stalker Nosorog |
| PSZ-10d Exoskeleton (dolg 4 omon) [unused model] | 0.350 | 0.650 | 0.15 | 0.70 | PSZ-10d Exoskeleton |

## By torso armor value

Curated examples for each bone armor bucket (at least 3 when the bucket has ≥3 models and ≥3 distinct DB names; otherwise all available; max 10). Names are exact [GAMMA 0.9.5 outfit DB](https://stalker-gamma-db.com/db/gamma-0.9.5/outfits?lang=en&sort=ui_inv_ap_res&dir=desc) display names. Prefer outfits whose name (and name-family, e.g. all Leather Jackets) sits mostly or entirely in this bucket — cross-tier names are used only to meet the minimum of 3.

| Torso armor | Models | Representative outfits |
|---:|---:|---|
| 0.011 | 9 | Leather Jacket, Black Leather Jacket, Heavy Brown Overcoat, Overcoat |
| 0.075 | 6 | Military Service Outfit, SSP-99 Bodysuit, Monolith X-18 Suit |
| 0.100 | 8 | "Sunrise" Stalker Suit, CS-1 Body Armor, Wind of Freedom |
| 0.125 | 1 | CS-2a Body Armor |
| 0.150 | 24 | Mercenary LC Suit, PS5-M Universal Protection Suit, Sentinel of Freedom, Fenced LC Suit, ISRIT Guard Jumpsuit, Monolith Scientific Suit, PS5-9Md Universal Scientific Suit, Tactical Stalker Suit, SEVA Bodysuit |
| 0.200 | 13 | Berill-5M Armored Suit, CS-3a Body Armor, Guardian of Freedom, "Sunrise" Exoskeleton |
| 0.250 | 10 | Interceptor Body Armor, Skat-9 Armored Suit |
| 0.300 | 1 | Exosuit |
| 0.350 | 2 | Skat-9 Armored Suit |
| 0.400 | 4 | PSZ-7p Shell Armor, Mercenary Exosuit, Monolith Exosuit |
| 0.430 | 1 | Paragon of Freedom |
| 0.550 | 5 | Exoskeleton, Mercenary Exoskeleton, Monolith Exoskeleton |
| 0.650 | 2 | Military Stalker Nosorog, PSZ-10d Exoskeleton |

## By head armor value

Same selection rules as torso (exact DB name; prefer names that do not span several head armor values; fill to ≥3 when possible). Head 0.000 is “no head bone armor” — many open-face / no-helm looks.

| Head armor | Models | Representative outfits |
|---:|---:|---|
| 0.000 | 39 | Overcoat, Heavy Brown Overcoat, Fenced LC Suit, ISRIT Guard Jumpsuit, Tactical Stalker Suit, Black Leather Jacket, Leather Jacket, Monolith X-18 Suit, "Sunrise" Exoskeleton |
| 0.150 | 7 | Monolith Scientific Suit, SSP-99 Bodysuit, PS5-9Md Universal Scientific Suit, SEVA Bodysuit |
| 0.200 | 13 | CS-1 Body Armor, CS-2a Body Armor, CS-3a Body Armor, Guardian of Freedom, Sentinel of Freedom, Mercenary LC Suit, Wind of Freedom, Berill-5M Armored Suit, "Sunrise" Stalker Suit, PS5-M Universal Protection Suit |
| 0.300 | 26 | Exosuit, Mercenary Exosuit, Monolith Exosuit, Paragon of Freedom, Mercenary Exoskeleton, Monolith Exoskeleton, Exoskeleton, PSZ-7p Shell Armor, Skat-9 Armored Suit, Interceptor Body Armor |
| 0.350 | 1 | Military Stalker Nosorog |
