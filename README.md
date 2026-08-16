# Dragonborn Forge

A character planner for the **Simonrim (Crusader)** Skyrim SE modlist.

**[Open the planner](https://g7138580.github.io/dragonborn-forge/)**

Pick a name, race, class, trait, standing stone, devotion and beast form, spend
perk points across the 18 skill trees, and see the resulting attributes and
effects.

## What it does

- **18 perk trees**, 213 learnable perks, laid out the way the game draws them.
- **70 perk points** by level 100 (+1 Imperial, +1 Faithless, so 72 at most).
- **Three power trees** on top of that, each with its own currency and cap, so
  they never compete with your level-up points:
  - **Shouts** 10 perks, 16 points, earned with dragon souls
  - **Vampire** 15 perks, 22 points, earned by feeding
  - **Werewolf** 14 perks, 22 points, earned by feeding
- **Vampirism and lycanthropy are mutually exclusive**, the way they are in
  game. Shouts are always available alongside either.
- **Vampire stages 1–4.** Both the resistances and the drawbacks scale with the
  stage, so it is a real choice rather than a status readout.
- **Transformed-form toggle** for Vampire Lord and beast form, including the
  level-scaled bonuses each one gains at its breakpoints.
- **Vampiric bloodlines** each of the ten races reacts differently to
  vampirism, applied automatically once you are a vampire of that race.
- **Class starting spells** for the nine classes that begin with any.
- **Live effects**: race powers, class effects, traits, standing stones,
  devotions, bloodlines and beast abilities all feed the derived stats, with
  bonuses and penalties both counted.
- **Select all** on any tree, enabled only when you can afford the whole thing.
- **Survival Mode** and **Oghma Infinium** toggles.
- **Mod versions** button in the header, showing which versions the data came
  from.
- **Share a build** with the link button. The whole build lives in the URL.
- **Print or export** a character sheet as PDF or plain text.

Nothing is stored or sent anywhere. The page is static, works offline once
loaded, and keeps your build in the address bar.

## Notes

- Skill levels derive from the perks you buy, floored by your class.
- A devotion takes effect at rank 2 of its gating perk: Pilgrim for the Aedra,
  Cultist for the Daedra. Rank 1 doubles that type's shrine blessings, and a
  doubled blessing is labelled as such in Active Effects.
- The transformed-form toggle is a **view**, not part of the build. It defaults
  off, so the numbers you see are your everyday mortal ones.
- Effects that only apply in a specific form are marked, and conditional ones
  ("while exposed to sunlight") are listed as text without moving the totals.
- Lowering your level does not refund anything. The build is flagged as over
  budget and left alone for you to fix.

## Data

Every number comes from the modlist's own plugin files. Nothing is
hand-transcribed. The extractors that generate `data/*.js` parse the `.esp` /
`.esm` / `.esl` binaries directly, and read compiled Papyrus out of the mods'
BSAs where a fact exists only in a script class skills and starting spells,
for instance, live nowhere else.

Where a mod's own description text disagrees with its records, **the records
win**. Beast and vampire perks are the worst offenders: `MAG_Lycanthrope` reads
"As a Werewolf…" and applies in mortal form regardless, so which form an effect
belongs to is read from its `GetIsRace` condition rather than its prose.

Built against these versions:

| Mod | Version | Provides |
|---|---|---|
| Adamant | 6.0.2 | perks |
| Hand to Hand | 2.0.1 | perks |
| Thaumaturgy | 1.5 | perks |
| Aetherius | 2.15.1 | races |
| Apprentice | 1.1 | classes, traits |
| Mundus | 1.14.2 | standing stones |
| Mysticism | 2.5 | magic |
| Pilgrim | 1.3.1 | religion |
| Starfrost | 2.0 | survival |
| Scion | 2.2.2 | vampirism |
| Manbeast | 2.1.1 | lycanthropy |
| Stormcrown | 1.1.17 | shouts |

The **Mod versions** button on the page shows this list live, read from the
installed mods rather than from this table.

## Running it locally

Download `index.html` and the `data/` folder, keep them together, and open
`index.html` in a browser. No server, no build step, no dependencies.

`index.html` is minified. The readable source, with the comments explaining the
awkward parts of the data, lives in the parent project as `index.src.html`.
