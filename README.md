# Dragonborn Forge

A character planner for the **Simonrim (Crusader)** Skyrim SE modlist.

**[Open the planner](https://g7138580.github.io/dragonborn-forge/)**

Pick a name, race, class, trait, standing stone and devotion, spend perk points
across the 18 skill trees, and see the resulting attributes and effects.

## What it does

- **18 perk trees**, 213 learnable perks, laid out the way the game draws them.
- **70 perk points** by level 100 (+1 Imperial, +1 Faithless, so 72 at most).
- **Live effects**: race powers, class effects, traits, standing stones and
  Pilgrim devotions are parsed from the mods' own description text, so bonuses
  and penalties both feed the derived stats.
- **Survival Mode** toggle for the carry weight penalty.
- **Share a build** with the link button. The whole build lives in the URL.
- **Print or export** a character sheet as PDF or plain text.

Nothing is stored or sent anywhere. The page is static, works offline once
loaded, and keeps your build in the address bar.

## Notes

- Skill levels derive from the perks you buy, floored by your class.
- A devotion only takes effect with rank 2 of the Pilgrim perk.
- Lowering your level does not refund anything. The build is flagged as over
  budget and left alone for you to fix.
- Shrine blessings are temporary, so they are listed but kept out of the totals.

## Data

Every number comes from the modlist's own plugin files. Nothing is
hand-transcribed. The extractors that generate `data/*.js` parse the `.esp` /
`.esm` / `.esl` binaries directly.

Built for the Simonrim suite: Adamant (perks), Aetherius (races), Apprentice
(classes and traits), Mundus (stones), Mysticism, Thaumaturgy, Pilgrim
(religion), Starfrost (survival), Blade and Blunt, Apothecary, Gourmet.

## Running it locally

Download `index.html` and the `data/` folder, keep them together, and open
`index.html` in a browser. No server, no build step, no dependencies.
