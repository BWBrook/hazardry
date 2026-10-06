# F1b: The Reliquary of Saint Orm

Probe record, Fable as orchestrator, 5 October 2026. This is a labelled probe under protocol revision 9; it is never pooled with P1–P13.

## Manifest

| Field | Value |
|---|---|
| Specification | `../fable-probes.md`, F1b |
| Frozen scenario | `playtests/runs/F1b/frozen_scenario.md`, draft 4, SHA-256 `e2dc0f9f187fec18…`. Astra cleared it conditionally (board 996), and her lift-first wording is incorporated verbatim. |
| Rules commit | `b12135e` |
| Game | Candlelight Dungeons, Delvekit off |
| Fixtures (labelled) | Fatigue 2, "the long descent": the step-2 Disadvantage was pending for each delver. Six lesser skeletons and the ghoul were entered as NPCs. |
| Roster | `gen_character.py`, seeds 2311–2313, standard budget (6), with free Knack and Expertise tags: Hode Brannock (STR 12, Fortune 11, Stamina 5, Backstab, fighter); Lisel Marrow (LOR 13, STR 11, Fortune 9, Stamina 4, Arcane Flex, hedge magic; *Wick-light*, *Force Bolt*, *Bone-Shatter*); Brother Anselm (FTH 12, Fortune 11, Stamina 5, Turn Undead, the old rites; *Bless*, holy symbol). |
| Packets | `packet_hode.md` `52fa871e…`, `packet_lisel.md` `81949b43…`, `packet_anselm.md` `fb6f9ff7…`. Each carries its owner's spell and Knack effects, without the private details: *Bone-Shatter*'s skeleton-kill arithmetic, "as frozen above", and the harness reason why destroy-one is not available. |
| Roles | Custodian and three players, fresh Sonnet subagents |
| Master seed | 231; draws 231001–231005; no `roll.py` draws |
| Replies | 9 Custodian public bodies (cap 30); 4 combat rounds (cap 8); 1 beat; closing lines, one archive each, three receipts |

**Pre-open clarification.** I gave this before play opened, as the author's reading; the frozen text is unchanged, as with F1a. It is logged in `orchestrator_notes.md`.
- **Stair Gate.** The portcullis is at the stair's foot, so the carrier's third move passes it within that round, before the round's tick.
- **Skeleton reach.** A skeleton more than a few paces from a delver spends its action closing one niche-length. One within a few paces attacks without moving.
- **Time-passing Fatigue.** I declined to rule on it: applying Almanac 4 was left to the Custodian.

## What happened

1. **The ghoul.** Hode declared a creep and Backstab. Lisel and Anselm each declared a tale of grief. The Custodian put the conflict to the players and offered a tie-break die only if all agreed. They chose the tale first and Lisel as teller. Her tale in her own words was ruled moving, with no roll and no cost. The ghoul stood aside for the scene. Lisel asked it to help, then withdrew the request before the lift, at Anselm's urging.
2. **The lift** (round 1). Hode and Lisel both claimed the lift. Lisel yielded and Hode lifted.
   - **Start of combat.** Combat started at the declaration of the lift: `combat-start`, seed 231001, with skeletons 17, ghoul 11, delvers 10. The skeletons passed as dormant and the ghoul as watching before the delvers' turn. Then Hode's lift was recorded with `pass`, the skeletons woke, and Stair Gate was created at 0/4.
   - **Turn Undead.** Anselm's Turn Undead (seed 231002, FTH 12 with Expertise Advantage, 1 coin) rolled 6 and 11 and kept 6: margin 6, a success. He declined the 2-coin nudge to margin 8, which would have scattered the pack.
   - **The tick.** Lisel held her action, and the tick went to 1/4.
3. **The carry** (rounds 2–4). Hode carried the reliquary three moves while Anselm walked backward with the symbol raised. The skeletons passed as recoiling every round. Lisel wedged the gate three times:
   - 231003: two dice with the Weary Disadvantage, 7 and 7, kept 7;
   - 231004: one die, 10;
   - 231005: one die, 11.

   All three succeeded, so each tick was held and Stair Gate ended at 1/4. Hode passed the portcullis in round 4, which met the end condition.

No attack was made by or against anyone. Fatigue stayed at 2, and no Stamina was lost. One beat was recorded, flagged perilous because the goal was at stake.

## Assertions (`fable-probes.md`, F1b 1–10)

| # | Assertion | Score |
|---|---|---|
| 1 | Spell costs follow the tier table | **Not reached: player choice.** No spell was cast: Lisel held her spells "until something reaches us", and nothing did. *Wick-light* was narrated as lantern light, not cast. |
| 2 | Fortune nudges offered on spells, on top of cost | **Not reached: player choice** (no casts). A nudge offer was correctly made on the Turn Undead check (2 coins to reach margin 8). On the binary wedges, the Custodian correctly said no spend could change the outcome. |
| 3 | Knacks once per scene at 1 coin or +1 Fatigue | **Correct for Turn Undead:** the `turn_undead` resource was used once, and 1 coin was paid (Fortune 11 → 10). It was FTH with Expertise Advantage, made lesser undead recoil for the scene, and offered margin 8 or more to scatter the pack. It made no Fatigue charge on success. **Backstab and Arcane Flex: not reached, player choice** (the creep was dropped in favour of the tale, and no spell was cast). |
| 4 | Fatigue 3 Advantage; Fatigue 4 toll, never on a defence roll | **Not reached: player choice.** Fatigue stayed at 2. Anselm paid his Knack in coin, and he said why: to avoid step 3. G004 stated the step-3 effect as a stake for a failed Turn Undead. |
| 5 | Crisis at 5 from a spell or Knack cost | **Not reached.** |
| 6 | Delvers reduced to 0 Stamina; what follows stated as a stake | **Not reached:** no attack was made. The skeletons' reach and damage were stated publicly (G003, G004) before the lift. |
| 7 | Every spell or Knack takes the caster's action; `check --combat-action` for Turn Undead and *Bless*; `pass` for a no-test Cantrip | **Correct for Turn Undead** (`check --combat-action`). Other entries were not reached. Moves and the lift were recorded with `pass`, and wedges with `check --combat-action`. |
| 8 | Backstab eligibility, Fatal immunity and each spell's effect frozen | **Correct as frozen.** The scenario and packets carry them, and G001 restated Backstab's terms before the choice. Not exercised in play. |
| 9 | Unchosen and unreached paths scored with their reason | This table. |
| 10 | Revision 9 general checks | **Mostly correct; see the audit notes.** Stakes were stated before commitment, with their triggers (B, E). Offered options were kept (F). Player collisions were put back to the players, with an opt-in die never drawn. Actions in one round were taken by the earlier side first (skeletons and ghoul, then delvers). The step-2 penalty was consumed exactly once, on Lisel's first STR test. The gear reconciliation is noted below (G). |

**The step-2 fixture** worked in play. The engine applied `pressure:party:step2` as Disadvantage on Lisel's first STR test, the wedge in round 2, and consumed it there. It was not applied to Anselm's FTH Turn Undead. Hode's and Anselm's step-2 penalties were never consumed, since neither made a STR or DEX test.

## Audit notes

- **No time-passing Fatigue.** The Custodian ruled that Stair Gate stands in for "time passing under threat", so no Fatigue charge was made for the four rounds. It said so publicly in G001 ("I charge no Fatigue for walking, waiting or deliberating"), before any commitment. I gave no ruling on this before play. It is the Custodian's application of Almanac 4, and Astra should audit it.
- **Lisel's staff.** P006 Lisel braced "my staff" under the gate, and her gear lists only a dagger and robes. G007–G009 accepted the staff in narration, and G009 lists it as left in the hall. It had no mechanical effect: the wedge is a plain STR test, and no Advantage was given. The lanterns were also never on any sheet. So there was no gear to reconcile, which is a gap in my setup rather than the Custodian's.
- **A routing mismatch in G004.** The body asks "Anselm, say again where you stand", but its `TO:` line names only Hode and Lisel. I relayed it as written, and Anselm received it with no answer due.
- **The round-4 wedge was moot.** Hode and Anselm were recorded through the portcullis before Lisel's third wedge was rolled, so her declared purpose (a spare tick for Anselm) no longer applied. The Custodian disclosed its reading of the order. It changed no outcome: the case ended that round.
- **The tale ruling.** The Custodian required the tale in the player's own words before ruling, and judged it moving enough to need no roll, which the frozen text allows. The ghoul's no-attack-on-a-teller line stayed private.
- **The ledger was kept in the campaign.** Unlike F2a, the Custodian kept a turn-by-turn ledger in `state/memory/custodian_notes.md`: seeds, pending penalties, rulings and my clarification.
- **No foe's condition was published.** No foe took damage. The skeletons' weapon edge (+1) and the damage formula were stated publicly in G004, but not their Stamina. Stating the edge is public weapon-table information, not private state.

## Checks

- **Checkpoints:** 9 of 9 match.
- **Deliveries:** 31, all verified verbatim against the native transcripts (`trace_check.py`).
- **Player tools:** one packet Read each, plus hand-backs.
- **Custodian access:** within its boundary, by heuristic.
- **Campaign:** `validate_campaign.py` ok.
- **Seeds:** OK. Five draws, 231001–231005, in order; the next unused is 231006.

## Coverage

F1b's purpose was spell tiers, all three Knacks, Fortune on spells, and Fatigue's step 3 and step 4 in a fight. Almost none of it was reached. Every unreached path was **the players' choice:**
- they talked the ghoul down rather than backstabbing it;
- Anselm turned the skeletons on the first action;
- nobody attacked anything after that;
- Lisel's wedges kept the clock at 1/4.

**Exercised:**
- Turn Undead, with its Knack cost and nudge offer;
- the step-2 fixture, applied and consumed;
- the lift-first initiative wording (Astra's board 996): `combat-start` at the declaration, dormant and watching passes, the lift recorded with `pass`, then the clock created;
- the Stair Gate clock and its wedge interrupt, three times;
- the no-roll parley path;
- collision handling.

F1b does not support any claim about spell costs, Fortune on spells, Backstab, Arcane Flex, Fatigue 3 or 4, or crisis handling in Candlelight combat.

**For any rerun:** a probe that must reach the spell tiers needs a scenario in which fighting is not easily avoided. That is a design note for a later probe, not a reason to rerun here. Probe framing (revision 9, H) forbids outcome-hunting, so any rerun needs a bounded design agreed with Astra first.

## Post-audit note

Added by Fable on 6 October 2026, after Astra's audit (board 1042, `../f2a-f1b-audit-astra.md`). I accept it in full. Where they conflict, these notes supersede the text above. The frozen scenario, packets, logs, dice and snapshots are unchanged.

- **The case contains post-end events.** The frozen end is the reliquary carried past the portcullis (scenario line 119). Event sequence 60 records Hode doing that. Sequences 61–64 come after the endpoint and are inadmissible as probe coverage: Anselm's move, Lisel's third wedge (seed 231005) and its settlement, and the held round-4 tick.
  - **Within-case evidence** is two wedges, three PC rolls and four drawing commands, ending at seed 231004.
  - **The raw log** has three wedges, four PC rolls and five draws, and `summary.json` counts it as raw telemetry, not valid probe tests.
  - **Seeds:** the 231005 die is preserved. The raw trace's next unused seed is 231006, and 231005 is not to be reclaimed or redrawn.
  - "The round-4 wedge was moot" and "three times" in What happened and Coverage are corrected accordingly.
- **The clock-substitution rationale is unsupported.** The frozen scenario makes its Fatigue triggers additive with Almanac 4. Almanac 4 lists time under threat as a trigger and has clocks running alongside Pressure, so announcing the exemption gave notice but did not justify it. No per-round cadence was frozen, so no specific missed charge is inferred and nothing is recalculated. Assertion 10 is qualified accordingly, and time-Fatigue handling in combat is unvalidated.
- **Gear: two separate gaps.**
  - The lanterns appear in the frozen premise but were never entered on sheets. This is my setup gap.
  - The Custodian accepted Lisel's unlisted staff as a prop in the wedge and later as abandoned gear. This is a separate adjudication gap.

  "No mechanical effect" narrows to "no numeric modifier". "No gear to reconcile" is withdrawn: inventory reconciliation is not established. No equipment is added to the frozen sheets.
- **The clarification limits coverage.** With Turn Undead succeeding and the carry uninterrupted, Hode clears the gate before the fourth tick even without a successful wedge. This is a coverage limit of the clarified scenario, not a reason to change its frozen timing.
- **Delivery count:** 30, not 31. The 31 counted `incoming/log.jsonl`.
