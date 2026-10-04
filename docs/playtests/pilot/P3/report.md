# P3 report (orchestrator)

P3 was Mournful Shores, solo, run under protocol revision 4. It is the first pilot run in which Pressure behaved as Almanac 9 sketches. Insanity rose by 7 in the session, one Break produced the pilot's first crisis, and a time-driven threat clock advanced five times, with no roll needed for any tick.

The session finished in six beats over two acts. There were 38 Custodian replies, and every checkpoint matched. The orchestrator issued no reminders. These are the orchestrator's notes; Astra's audit decides the rules questions.

## What happened

**Act 1, three beats.**
- **The cold open.** Nell jams the cistern winch while a cult walks the survivor Ansel into rising water.
- **The cistern.** She chalks two Signs of Warding, then fights two drowned thralls with an open lantern. A failed oil throw later ignites as a natural-20 complication. Ansel is dragged back to his sister Maud.
- **The wharf and the causeway.** Constable Gant opens the gate, gives her his lantern and hands over the chart-room key.
- **The crypt.** Dean Thorne makes his offer. Nell learns the Cut Leaves' verse by ear, which tips her into a Break, then sings the Unspeakable Ebb Unspoken at the Tide-stone with Ansel. The working is unmade.

**Act 2, three beats.**
- **The Station chart room.** It is flooding on a declared tide clock. A natural 20 at the safe still yields the ledger and most of the roster.
- **The Provost.** A natural 1 holds him to an open inquiry.
- **Dawn.** A grounding confession purges 1 Insanity.

## Revision 4 against its aims

| Revision 4 change | Evidence in P3 |
|---|---|
| **Cold open** | The session opened mid-crisis with an explicit ten-minute stake; act 2 opened on the flooding Station. |
| **Threats move on their own** | The Tide Turns ticked five times: three bell verses on its timetable, and two opposition moves (the Dean reads; the sentry opens the sluice). The Station flood clock ticked four times on schedule. The player was never asked to roll for any of it. |
| **Stakes before commitment** | No roll showed stakes for the first time. Where options lacked consequences, the Custodian paused for commitment, which happened four times (G003, G012, G016, G034). Where options carried full stakes, the declaration was the commitment. |
| **NPC traits** | Maud, Thorne, Gant, Ansel and the Provost each had a declared want, manner and line, and acted by them. Thorne never used his own hands; Gant was gruff and then decent; the Provost would not lie before witnesses. |
| **Bold temperament** | Nell spent 4 Fate at once to free Ansel and paid four tolls in Fate. She chose Insanity over Fate twice, took a Break deliberately, and never abandoned the witness. |
| **Distinctive procedures** | Exercised: Rite (three times), Unspeakable, the Insanity step-2 threshold (its FRT penalty stayed pending; no qualifying test came), the step-3 toll in Fate and in Insanity, a Break with its crisis drawn by `roll.py table` and a lasting effect, the grounding purge, the lantern clock including a refuel, two combats, advancement and a milestone. Not exercised: Incantation, Fate tests, Occult Scholar, the backlash table. |

## Pressure, which is the question round 3 was set to answer

| Measure | P1 | P5 | P2 | P6 | **P3** |
|---|---|---|---|---|---|
| Pressure gained | 1 | 1 | 0 | 0 | **7** |
| Crises | 0 | 0 | 0 | 0 | **1** |
| PC rolls per beat | 1.4 | 0.3 | 2.4 | 0.2 | **4.3** |

**Where P3's Insanity came from:**
- **Five points were action costs the player chose or accepted:**
  - a Rite's success cost, paid in Insanity;
  - the Leaves, +1;
  - one step-3 toll paid in Insanity;
  - the Unspeakable rite, +2.
- **One point came from a failed rite.**
- **One point was ambient, from witnessing a horror.** This was the only charge the Custodian imposed unprompted.

**Luck spent to avoid Pressure.** This is derived from the log and messages; uncertain cases are marked.
- 4 Fate went on step-3 tolls instead of Insanity (G021, G022, G023, G024).
- The two big nudges were not about Pressure. The 4-ticket cord nudge (P009) saved Ansel; the 8-ticket offer at G005 was declined.
- So about 4 of the 10 Fate spent avoided Pressure directly.

**Reading.** The shift has two parts.
- The scenario rule and the "threats move" line made the world press on its own.
- The bold temperament and the skin's own price structure made the player buy Pressure deliberately: rite costs, tolls, the Break as a reset.

The Custodian still under-charged ambient horror. The thralls were in sight from G001, but the only witnessing charge came at G014. That narrows the earlier finding: Pressure moves when the scenario and the player's choices put it on the table. A Custodian still rarely imposes it unprompted.

## Stalls, invented content and rulings to audit

- **No stalls.**
- **Invented content, declared mid-run and logged in `keeper_notes.md`:**
  - the `station_floods` clock;
  - Provost Whitlock;
  - the requirement that Ansel hear the counter-verse unsung, which grew from the Keeper-named crisis clue;
  - Gant's lantern refuel, which the Custodian flagged as generous.
- **For the audit:**
  - **The crisis table disclosed (G030).** The Custodian printed the full Insanity crisis table publicly, to make the Break an informed choice. The protocol excludes crisis tables from player material. Under its Leaks rule, **the whole of P3 counts as a harness test only** (as Astra's audit confirms). It remains procedure and pacing evidence, but not uncontaminated programme evidence. The table is printed in the book, so this was a pilot packet-boundary breach, not a game secret.
  - **No public session log.** The Custodian never ran `session_log.py`, which AGENTS.md requires. The relay transcript preserves the fiction.
  - **Witnessing charged late and unavoidably (G014).** The Custodian flagged this itself.
  - **A puzzle hint in an option (G029).** "Say Maud's name to her as he did when he was small" pointed at the private solution; the Custodian flagged this itself.
  - **Two continuity slips.** Gant says "thirty years" (G025) and the ledger holds "eleven years" of payments (G036), but the drownings were in 1921 and the session is set in 1924.
  - **NPC Stamina tracked outside the engine.** Silas's lantern damage was kept in notes only (see harness gaps).
  - **The perilous flags:** beats 1, 3 and 4 perilous; beats 2, 5 and 6 not.
  - **The milestone** came at the third perilous beat (beat 4), with Fate refilled. The crisis's "next rest restores no Fate" effect was correctly kept, because a milestone is not a rest.
  - **The Unspeakable procedure (G032):** +2 up front, no nudges, Advantage from Ansel singing, success. Check `--pressure-cost 2 --no-nudge` against the skin's procedure.

## Harness gaps

- **NPC damage outside `attack`.** No command lowers an NPC's Stamina outside `attack`, so damage from won opposed tests has nowhere to go in the engine. This is new.
- **Carried over from P2, and seen again here:**
  - there is no NPC defeat or removal command;
  - relative campaign paths need to be given as absolute paths.
- **No new defects.** The step-3 toll (`--toll luck` and `--toll pressure`), the `--pressure-cost` and `--no-nudge` flags on rites, `roll.py table`, a forced crisis with its target and lasting effect, and the purge all worked as documented.

## Rules-text gaps

- **Backlash.** Mournful Shores names "a backlash" for failed Incantations and Unspeakable rites but prints no backlash table or procedure. The Custodian declared its own before play.
- **Step-2 Disadvantage scope.** The step-2 effect is "Disadvantage on your next FRT test to resist fear or coercion". Both the player and the Custodian read persuasion as outside it, so the effect was never consumed. That reading is correct, but a one-line example in the skin would help.

## Pacing against Almanac 9

This is a description, not a target.

- **Six beats in two acts of three.** That is shorter than the sketch, but the session reached its own ending.
- **Beat 1 ran 24 Custodian replies.** It held two combats and a parley in one place, so it was one scene. Replies averaged 400–500 words against a 300-word guide; the longest was about 660.
- **26 PC rolls**, 23 of them in act 1.
- **One milestone, on time.** One Break; Fate went 10 → 0 → milestone refill → 11.
- **Speed.** About 61 minutes of play. With beats this dense, the session would reach 16 beats only well past the 150-reply cap.

## Coherence and fun

The strongest run so far.
- **A coherent weird-horror arc.** The drive got its answer: the Dean's confession and the Provost's inquiry.
- **NPCs with distinct voices,** each acting on a declared want.
- **Real losses:** Ansel slipped away twice, three roster names were lost, and Maud lost her voice.
- **A climax** that used the skin's Unspeakable tier as written.
- **A bold player who stayed honest.** The temperament line produced both the risk and the restraint: she chose Insanity over Fate only when Fate was gone, and stopped her ears to avoid the choir.

## What to change for round 4

1. **Every risky option carries its consequences.** P3 lost four round trips to commitment pauses.
2. **Custodians charge witnessing as it happens.** Charge horror at first exposure, or say the charge is coming before the player looks.
3. **Packet boundary.** Either add each skin's crisis table to the player packet, as the book already publishes it, or forbid quoting it before a Break. I recommend adding it: informed choice about a Break proved valuable.
4. **Reply length.** Raise the guide to 400 words, or ask that settlement, beat close and new scene be split across replies.
5. **Stage 3 tally:** the Mournful Shores backlash table, and the scope of the step-2 effect.
6. **Stage 4 backlog:** NPC Stamina changes outside `attack`.

## Post-audit note

Astra's audit (`audit.md`) is accepted. It corrects this report in three ways:
- P3 counts as a harness test only, under the protocol's Leaks rule. It is not merely excluded from secrecy evidence.
- The public session log is missing.
- P3 changed the skin, the party, the scenario and the player as well as the guidance. It shows that revision 4 *can* produce Pressure and threat motion. It does not show that the guidance alone caused them.
