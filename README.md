# Dragonborn Forge

A character planner for the **Morning Star / Winds of the North** Skyrim SE
modlist.

**[Open the planner](https://g7138580.github.io/dragonborn-forge/)**

> Built specifically for Morning Star / Winds of the North. It may work for
> other lists built on the same Simonrim suite, but the numbers are read from
> *this* modlist's plugins, so anything that differs will be wrong. The **Mod
> versions** button shows exactly what the data was built from.

Pick a name, race, class, trait, standing stone, devotion and beast form, spend
perk points across the 18 skill trees, equip gear, and see the resulting
attributes and effects.

## What it does

### Character

- **18 perk trees**, 213 learnable perks, laid out the way the game draws them.
- **70 perk points** by level 100 (+1 Imperial, +1 Faithless, so 72 at most).
- **Three power trees** on top of that, each with its own currency and cap, so
  they never compete with your level-up points:
  - **Shouts** 10 perks, 16 points, earned with dragon souls
  - **Vampire** 15 perks, 22 points, earned by feeding
  - **Werewolf** 14 perks, 22 points, earned by feeding
- **Vampirism and lycanthropy are mutually exclusive**, the way they are in
  game. Shouts are always available alongside either.
- **Vampire stages 1-4.** Both the resistances and the drawbacks scale with the
  stage, so it is a real choice rather than a status readout.
- **Transformed-form toggle** for Vampire Lord and beast form, including the
  level-scaled bonuses each one gains at its breakpoints.
- **Vampiric bloodlines** each of the ten races reacts differently to
  vampirism, applied automatically once you are a vampire of that race.
- **Class starting spells** for the classes that begin with any.
- **Survival Mode** and **Oghma Infinium** toggles.

### Gear

- **Eight slots**: head, body, hands, feet, amulet, ring and both hands.
- **Armor type per slot** from the modlist's own material keywords, each
  already knowing whether it is heavy, light or clothing.
- **Enchantments** from Thaumaturgy's pool, with what is legal on a slot
  derived from which enchanted items actually exist there.
- **323 artifacts** from Artificer, each with its fixed enchantment.
- **11 set bonuses.** Wear the whole set and the bonus applies; wear all but
  one and the planner says which piece is missing.
- **Twin Secrets** puts a second enchantment on an item once you take the perk.
- **The Aetherial Crown** grants a second standing stone while it is worn.
- **Hands work like the game.** A shield goes in the left hand only, a
  two-handed weapon or bow occupies both, and empty hands are a real choice
  because Hand to Hand has seven perks that need them.

### The rest

- **Only the body slot changes the numbers.** Simonrim's 20 "while wearing
  heavy/light armor" perks are gated on the cuirass, so a perk that does not
  apply is shown greyed out with the reason rather than quietly counted.
- **Live effects**: race powers, class effects, traits, standing stones,
  devotions, bloodlines, beast abilities, gear enchantments and set bonuses
  all feed the derived stats, with bonuses and penalties both counted.
- **Factions**: a checklist of the eleven joinable guilds. Dawnguard/Volkihar
  and Legion/Stormcloaks are mutually exclusive; nothing else about them
  affects the build.
- **Notes**: free text for a character concept or playthrough log, stored in
  the build link itself.
- **Select all** on any tree, enabled only when you can afford the whole thing.
- **Mod versions** button in the header, showing which versions the data came
  from.
- **Share a build** with the link button. The whole build lives in the URL.
- **Print or export** a character sheet as PDF or plain text, including gear,
  enchantments, set bonuses, factions and notes.

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
- **Armor ratings are deliberately absent.** They are a formula over skill,
  perks and tempering, so any number shown here would be wrong for most
  characters. Enchantment strength is left out for the same reason: the tier
  depends on your Enchanting skill and soul gem, not on the build.
- Taking off the Aetherial Crown, or untaking Twin Secrets, leaves the pick it
  allowed stored but inactive rather than throwing it away.
- The longer your notes, the longer the build link. Very long links can be cut
  short by chat apps and email.

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

Two facts are not on any record and are reproduced from where they really live:
the armor perks' chest keywords are handed out at runtime by Adamant's Keyword
Item Distributor rules, and the Aetherial Crown's second stone is left to
Dawnguard's own quest script.

The one thing the planner does not read from the mods is the faction list.
Guild names live in Bethesda's string tables rather than in the records, and
nothing in the suite keys off membership, so those toggles are a hand-written
checklist that deliberately claims no mechanical effect.

Built against these versions:

| Mod | Version | Provides |
|---|---|---|
| Adamant | 6.0.4 | perks |
| Hand to Hand | 2.0.1 | perks |
| Thaumaturgy | 1.5 | perks, enchantments |
| Aetherius | 2.15.1 | races |
| Apprentice | 1.1 | classes, traits |
| Mundus | 1.15.1 | standing stones |
| Mysticism | 2.5 | magic |
| Pilgrim | 1.3.1 | religion |
| Starfrost | 2.0 | survival |
| Scion | 2.2.2 | vampirism |
| Manbeast | 2.1.1 | lycanthropy |
| Stormcrown | 1.1.17 | shouts |
| Artificer | 1.0.11 | artifacts, set bonuses |
| AEGIS | 1.1.2 | armor types |
| Blade and Blunt | 4.0.2 | armor keywords |

The **Mod versions** button on the page shows this list live, read from the
installed mods rather than from this table.

## Running it locally

Download `index.html` and the `data/` folder, keep them together, and open
`index.html` in a browser. No server, no build step, no dependencies.

`index.html` here is minified. The readable source, with the comments
explaining the awkward parts of the data, lives in the parent project as
`index.src.html` and is compiled by `minify.js`. The data files beside it are
generated by the extractors in that same project.
