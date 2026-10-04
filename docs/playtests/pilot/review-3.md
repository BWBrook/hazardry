# Pilot review 3: P3 and P7

Fable, 4 October 2026. Round 3 was the first under protocol revision 4: cold opens, threats that move on their own, stakes before commitment, NPC wants and lines, and bold temperaments.

Its two runs were both solo:
- **P3,** Mournful Shores, audited by Astra (`P3/audit.md`);
- **P7,** Iron & Ruin, audited by Fable (`P7/audit.md`).

This review proposes changes before round 4 (P4 and P8). As before, they need Astra's view and Barry's approval, and no rule changes follow from the pilot alone.

**Caveat.** Each round changed the skin, the party, the scenario and the agents as well as the guidance. The comparison shows what revision 4 *can* produce. It cannot isolate what the guidance itself caused.

## The six completed runs

| | P1 | P5 | P2 | P6 | **P3** | **P7** |
|---|---|---|---|---|---|---|
| Protocol | rev 2 | rev 2 | rev 3 | rev 3 | rev 4 | rev 4 |
| Skin, party | Clanfire, 2 | Rust, 2 | Clanfire, 2 | Candlelight, 4 | Mournful, 1 | Iron & Ruin, 1 |
| Beats (acts) | 10 (5+5)* | 7 (4+3) | 10 (6+4) | 6 (4+2)* | 6 (3+3) | 8 (4+4) |
| PC rolls per logged beat | 1.4 | 0.3 | 2.4 | 0.2 | 4.3 | 1.25 |
| Pressure gained | 1 | 1 | 0 | 0 | **7** | **2** |
| Crises | 0 | 0 | 0 | 0 | **1** | 0 |
| Threat-clock ticks without a roll | 0 | 0 | 0 | 0 | **9** | **5** |
| Luck spent | 8 | 0 | 13 | 1 | 10 | 10 |
| Milestones | 1, late | 1 | 1 | 0 | 1 | 2 |
| Custodian replies | 16 | 15 | 23 | 15 | 38 | 25 |
| Replies with a separate commitment request | 0 | 0 | 0 | 0 | 4 | **8** |
| Status | complete | complete | complete | complete | **harness test only** | complete |

\* Audit adjustments are in the earlier reviews; the logs are unchanged.

## Observed under revision 4

- **Threats now move without being prompted.** P3's tide clock ticked five times and its flood clock four. P7's Dawn Tithe advanced five times on Varkos's orders and the passage of time. In rounds 1 and 2, no clock moved without a roll.
- **Cold opens worked in both runs:** the cistern, and the tipping wagon.
- **Bold players spent their resources.** Under the bold temperament, both players spent Fortune or Fate down to nothing, paid sorcery and rite costs in Stamina or Pressure, and took real risks. P3's player deliberately took a Break.
- **NPCs had distinct, motivated voices** in both runs: Maud, Thorne, Gant and the Provost; Varkos, Ossian and Nima.
- **The skins' distinctive procedures got used:**
  - P3: Rite, Unspeakable, the step-2 threshold (its FRT penalty left pending, persuasion correctly excluded), the step-3 toll, Break and crisis, purge;
  - P7: Weave, Wrack and the Heroic Act.

## What still fell short, and a new cost

1. **Pressure still depends on what the skin lets in.**
   - P3 gained 7, mostly prices the player chose: rite costs, tolls, reading forbidden pages.
   - P7 gained 2: one Wrack cost and one ambient charge. Iron & Ruin says "the sorcery table says exactly when [Doom] rises", which leaves little room for ambient Doom, and P7's single ambient charge is questionable under that wording.
   - P3's Custodian under-charged *ambient* Pressure: the thralls were in sight from G001, but the first witnessing charge came at G014. P7 had one ambient charge under an explicitly additive frozen policy; without identified missed triggers, that alone does not show under-charging.
2. **The stakes rule is now the main cost in replies.** Twelve replies across the two runs (4 in P3, 8 in P7) asked separately for commitment, because the options had named a test without its consequences. P7's eight did nothing else; P3's four also resolved earlier actions or advanced the fiction. In P7 a roll often took three replies.
3. **A protocol leak.** P3 printed the full crisis table publicly to make a Break an informed choice. Under the Leaks rule, P3 counts as a harness test only.
4. **Small recurring slips:**
   - chronology (P3 twice);
   - a hidden solution offered as an option (P3);
   - no public session log (P3);
   - inventory continuity, such as the rope never recovered (P7);
   - recap threads that cannot be closed (P6 and P7).
5. **Long replies.** P3 averaged about 450 words, against the 300-word guide in Fable's Custodian brief; the protocol itself set no length. P7's were shorter.

## Proposals before round 4

**A. Custodian brief, protocol revision 5:**
- **Risky options name their consequences.** Every risky option in a menu states its test and its consequences on success and failure, so that choosing it is the commitment. A bare "(AGI, risky)" is not allowed.
- **Telegraph or charge Pressure at its trigger.** When a declared trigger first occurs, such as a horror in view or time passing under threat, either charge it or say plainly that it will be charged if the character stays, looks or waits.
- **Never offer a hidden solution as an option.** An option may point to a lead the characters have discovered, never to an answer known only from private notes.
- **Records.** Write the public session log with `session_log.py` each turn, alongside the checkpoint.

**B. Packets.** Add each skin's crisis and backlash tables to the player packet. They are printed in the book's player-readable skins, and P3 showed that an informed Break is good play. Where a printed rule lets the Custodian choose a result, that choice stays allowed and is recorded as chosen; what stays private is any preselection before it applies. Disclosing the consequence actually applied is separate.

**C. Reply guide.** Put a length guide of about 400 words in the protocol's brief, so both teams use the same one. Cut description before stakes or options.

**D. For Barry: are skin Pressure triggers exclusive or additive?** P7 exposed a real ambiguity.
- Iron & Ruin says Doom rises "exactly" when the sorcery table says.
- Almanac 4 lists general triggers for every skin: time under threat, noisy heroics, desperate bargains, taboo acts.
- Clanfire, Rust and Mournful Shores all print "Gain +1 …" lists without saying whether those replace or add to Almanac 4.

This is a rules-text decision. Under the additive reading, the AI Custodian's guidance ("apply the core or skin's trigger") is right. Under the exclusive reading, ambient Pressure is mostly closed off in Iron & Ruin.

My recommendation is **additive**, with Iron & Ruin's line reworded to "The sorcery table says exactly what each casting costs". This needs Barry's decision and would be a Stage 3 tally item.

## Decision

Barry, 4 October 2026: "Decision: I recommend additive, agreed. Sorcery in Iron & Ruin is meant to be especially "warping", much like it is done in Dungeon Crawl Classics." He approved implementing revision 5 and committing the round 3 bundle, with Astra's cross-check to follow before P4 and P8.

**Adopted as protocol revision 5,** with matching handbook lines:
- **A.** Risky options carry their test and consequences. Triggers are charged or telegraphed when they first arise. No option depends on private-only knowledge. The public session log is written every turn.
- **B.** Crisis and backlash tables are in the player packet.
- **C.** The brief carries a 400-word reply guide.
- **D.** A skin's Pressure triggers add to Almanac 4's; they do not replace them. This is stated in the brief and the handbook now. The skin and Almanac wording waits for Stage 3: reword Iron & Ruin's "exactly when it rises" line so that it keeps sorcery's own Doom prices, which are meant to be especially warping, without excluding the core triggers.

## Backlog

**Stage 3 rules-text tally:**
- the skin triggers wording (D, decided: additive);
- the Mournful Shores backlash table, which is missing;
- the scope of Mournful's step-2 effect, needing one example;
- whether an Iron & Ruin Weave that takes but is dodged still costs its price, needing one line;
- how a Clanfire Beast Bond is gained (from review 2).

**Stage 4 harness backlog:**
- NPC Stamina changes outside `attack`;
- closing or replacing recap threads;
- an NPC defeat or removal command;
- adding a combatant mid-fight;
- accepting `update_sheet` values containing ": ";
- relative `--campaign` paths resolving under `campaigns/`;
- the act counter shown after the close;
- weapon edge on sheets.

## Round 4

Two multi-character runs will test revision 5 at larger tables, with differing temperaments and at least one bold character:
- **P4** (Fable): Twilight of the Northlands, three characters, with combat positions and Injury, plus the gritty option;
- **P8** (Astra): Free Traders, three characters, with assigned crew roles.
