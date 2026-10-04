# P7 cross-team audit: Iron & Ruin, the Dawn Tithe

Auditor: Fable (`claude-opus-5-5`). Protocol revision 4; rules at `849a8e0`. I did not run commands against the campaign.

**Evidence,** in the ignored `playtests/runs/P7/`:
- the committed transcript;
- the `gm_NNN.md` replies;
- `checkpoint_checks.jsonl` and `checkpoint_versions/`;
- `commands.jsonl`;
- the frozen scenario;
- the initial and final snapshots. The log is `final/p7_iron/state/logs/session_001.jsonl`, 75 events.

**References.** "Event N" is the log's `sequence`; G and P numbers are message IDs.

**Scope.** P7 has more than ten consequential rulings. This audit covers all sorcery, both Fortune-depleting choices, the Heroic Act, the combat, both milestones, every Pressure event and every beat flag. It then takes a declared sample of four other rulings: G011, G020 (twice) and G022.

## Verdicts

**No crisis occurred.** Doom peaked at 2 (events 50 and 53), so there is no crisis, backlash or purge to grade.

**Correct: the two big Fortune spends (G003 and G006, events 4 and 9).**
- **The first spend.** Stakes were stated and committed before each roll (G002, P002; G005, P005). AGI 11 with Advantage from the anchored rope, a square fit. The dice were 15 and 17, kept 15: a miss by 4. A 4-token nudge reaches 11, success at margin 0.
- **The second spend.** 16 against 11 is a miss by 5, and 5 tokens turn it. The offers were exact. Fortune went 10 → 6 → 1.

**Correct, with a rules-text question: the Cinder Bolt Weave (G008–G010, events 17 and 19).**
- WIL 14 against the guard's AGI 10, opposed. Sera rolled 13 (the casting takes, by 1); the guard rolled 4 (margin 6) and dodges.
- The Weave's success cost, 1 Fortune or 1 Stamina, was paid in Stamina, as she chose (5 → 4). The skin prices a Weave on the WIL test: "On success: spend 1 Fortune token or lose 1 Stamina" (`skins/iron_and_ruin.md:75`).
- Charging that price when the casting succeeds but the opposed attack loses is a defensible reading. The skin does not say whether "success" means the caster's test or winning the contest.
- **Judgement call,** with a Stage 3 note: one sentence, such as "a Weave that takes but is dodged still costs its price", would settle it.

**Correct: the Heroic Act (G011–G013, events 28–30).**
- Once per session: 1 Fortune paid up front (1 → 0, event 28) for Advantage (`skins/iron_and_ruin.md:141-145`).
- Dice 13 and 2, kept 2: margin 9 against the guard's Brawn roll of 7 (margin 3).
- On success the skin offers "+1 edge or a simple status". "Driven back" was the status chosen, consistent with the stated stakes.

**Correct: the combat (events 15–42).**
- Initiative came before the first exchange (13 against 8, reported at G010).
- The guard's lunge was answered by a defensive opposed test (G011): Sera 2 against 11 (margin 9), the guard 3 against 10 (margin 7). Defending uses no action.
- The hook-spear attack (G014): the guard 17 against 10 fails, Sera dodges with 7 against 11.
- No damage was dealt; the combat ended when Sera withdrew (event 42).

**Correct: the Break the Bronze Wrack (G017–G018, events 52–53).**
- WIL 15 with Advantage from the bought tag "Exiled temple sorcerer", a square fit. No Fortune nudge, as the Wrack tier requires.
- Dice 10 and 8, kept 8: success.
- **+1 Doom on success** was charged (1 → 2, event 53), as printed: "+1 Doom, even on success" (`skins/iron_and_ruin.md:76`).
- The stakes, including the failure backlash, were stated before commitment.
- Doom 2's "minor Disadvantage" was applied once, to the next delicate handling of iron (G019–G020), then cleared. A defensible reading of a one-off minor penalty.

**Judgement call, with a design question: the ambient Doom (G016, event 50).**
- +1 Doom for several minutes trapped in the keeper sluice under the active threat.
- The frozen scenario declares this trigger: "a substantial interval under this active threat". It follows revision 4 and the general triggers in Almanac 4.
- However, the skin says "The sorcery table says exactly when it rises" (`skins/iron_and_ruin.md:117`). Read strictly, that makes Doom sorcery-only, and this charge would be wrong.
- The audit cannot settle whether a skin's own trigger list replaces Almanac 4's general triggers or adds to them.
- **For Barry and the joint review.** The same question bears on every skin's "Gain +1 …" list, such as Clanfire's Shadow and Rust's Heat.

**Correct: the clock (events 2, 6, 25, 46, 49 and 69).**
- The Dawn Tithe advanced 0 → 5 on declared triggers: Varkos's gate order, the alarm reaching the crew, the dispatched reserves, a substantial interval in the sluice, and the furnace start.
- No tick doubled an order or charged thinking time (frozen scenario, lines 11–13).
- It never filled. The scenario said a completed clock changes the situation and does not deal damage, so its retirement in the fiction at 5/6 is consistent.

**Correct: the milestones and advancement (events 44–47 and 67–70).**
- All eight beats were flagged perilous. Awards came after beat 3 and after beat 6, each at the third perilous beat since the last, inside "every 3–4" (`skins/iron_and_ruin.md:171`).
- **First milestone:** Fortune refilled 0 → 10. 2 build points raised WIL 14 → 15 (2 points at or above the baseline is correct).
- **Second milestone:** Fortune was already full. 2 points raised WIL 15 → 16, the ceiling.

**Judgement calls: the perilous flags on beats 4 and 8.**
- **Beat 4** (Ossian opens the hatch and the fugitives descend before the guards arrive) and **beat 8** (Sera covers the last captive's withdrawal) had no roll.
- In both, the stated danger, guards arriving and reserves breaking in, could have cost the goal. Under the handbook's wording (the actual fictional stakes, not dice), both flags are defensible.
- Every beat perilous is generous. Without beat 4's flag, the second milestone would have come after beat 7 rather than beat 6. Beat 8 came after that award and did not affect it.

**Correct: the sample of ordinary rulings.**
- **G020, Sera's slash.** AGI with Disadvantage: 15 and 7, kept 15, a miss by 4. The worker's 3 against 10 gives margin 7. Ten tokens could not make her margin exceed 7, so no offer was made. Correct.
- **G020, Nima's roll.** An allied NPC rolling Cunning: 4 against 10 (margin 6) beats the worker's 8 against 8 (margin 0). An allied NPC acting on a player's request is legitimate. Rolling it rather than narrating is a judgement call that adds risk fairly.
- **G022, the intimidation.** WIL with Advantage: 4 and 20, kept 4, margin 11. The worker's 12 against 8 fails, so the result is correct.
- **G024.** A natural 1 on Brawn: success, locked, and the narrated extra benefit (the axle shears) fits "a natural 1 usually brings an extra benefit".

**Not exercised:** Whisper, Wyrd, the backlash table, the Doom crisis, purges, Fortune tests.

## Procedure

- **Commitment pauses: 8 of 25 Custodian replies** (G002, G005, G008, G012, G017, G019, G021, G023) did nothing but state stakes and ask for commitment. Each roll therefore took about three replies.
  - This is correct under revision 4, because those options listed no consequences.
  - It is the same pattern as P3 (four pauses there), only stronger: the stakes rule works, but costs time unless options carry their consequences.
- **Cold open and threat motion.** Both were exemplary. The session opened with a wagon tipping over a sluice, and the Dawn Tithe clock advanced five times without a single roll.
- **NPCs** acted from declared wants: Varkos's orders, Ossian's daughter, Nima's ledger.
- **The temperament** ("Bold and impatient: risks her own blood and forbidden sorcery") showed in play: the blood-paid Weave, the Wrack, 10 Fortune spent in act 1.
- **Minor continuity point.** The rope's recovery is never narrated after the rescue, yet it stays in her inventory.
- **Recap threads** keep superseded entries. This is the known `recap.py` append-only limitation.

## Records and access

- **Checkpoints.** The recorder reports 25 of 25 comparisons true, and `checkpoint_versions/` holds 25 versions. I compared only the last directly: `gm_025.md` is byte-identical to the final `last.md`.
- **Draws.** Twelve sequential dice commands used seeds 71004001–71004012, per Astra's manifest.
- **Leaks.** No hidden material was disclosed before it was discovered lawfully: Varkos's orders, the transfer clock, the wheel mechanism and Tovin's location were all revealed in play. No crisis or backlash table was quoted.
- **Access.** The player's native trace shows zero tool calls; the Custodian has no full access trace. Player access was instructed, not enforced.
- **Substitution.** The CLI player stood in for a collaboration agent after two capacity failures. It was fresh, received the frozen packet verbatim and reused no history. It is disclosed in the manifest and does not affect comparability within the run.

## Summary

P7's mechanics are clean and fully reconciled.

Its findings for the joint review:
- **Commitment pauses** dominate the reply count.
- **Skin triggers.** Are a skin's Pressure triggers exclusive (Iron & Ruin's "exactly when it rises") or added to Almanac 4's general ones?
- **Weave success** when the attack is dodged needs a one-line rules note.

P7 also matches what P3 showed. Under revision 4, with a bold temperament and declared clocks, the threat clock moved steadily (five ticks) and the player spent Luck freely. Pressure stayed modest at Doom 2. The strict reading of Iron & Ruin cannot explain that, because this Custodian's frozen policy was explicitly additive; the run shows only that few Doom triggers were met or charged.
