# GAMMA Tooltip Weapon Damage

Adds weapon damage information to weapon tooltips (and description box) in **S.T.A.L.K.E.R. G.A.M.M.A.**

## What it does

When you hover a weapon, you get a **DAMAGE** table under the description:

- One row per ammo type
- **AP** — same number as on the ammo card
- **vs Torso / vs Head** — estimated damage at 20 meters against different armor tiers (which are user-friendly mappings to NPC armor values)
- Color highlights so you can see at a glance how effective a weapon is against higher armor tiers.

Optional: bring back the original **Damage** stat in the normal weapon stats block, or show **Hit Power** (weapon base power as %, good for comparing guns). The per-ammo **Damage (ammo)** slash stat uses the same legacy Dmg formula for each round.

<img width="523" height="371" alt="Details" src="https://github.com/user-attachments/assets/58f594ac-0683-4d68-9f17-ee3e2b5ff8f2" />
<img width="722" height="1081" alt="Tooltip" src="https://github.com/user-attachments/assets/afb6609d-7232-44ce-b395-f2bd05997856" />

## MCM

All under **Dorn's Weapon Tooltip** in MCM. Info tab explains the columns if you're curious.

- **Show damage table** — On / Off
- **Weapon damage stat row** — Hit Power / Damage (Dmg) / Damage (ammo) / Off
- **Damage column headers** — BRC tier labels / raw NPC armor %

## Installation

1. Download the latest release from https://github.com/JoshuaCarter/GAMMA-Tooltip-Weapon-Damage/releases
2. Install via MO2 like normal
3. Load **after** G.A.M.M.A. Accurate Defense Values (or anything that messes with weapon tooltips)

## Notes

- Consider this a work-in-progress as I can't be 100% sure I've gotten the calculations correct, or that all weapons/ammo are working correctly yet.
