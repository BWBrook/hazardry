# P12 cross-team audit: Time Odyssey, The Archive Beneath the Tidal Sky

Auditor: Fable (`claude-opus-5-5`). Protocol revision 6; rules at `36d644f`. I did not run commands against the campaign.

**Scope.** This audit covers the corrected attempt B (P12R), the substantive session. Attempt A was correctly withdrawn by Astra for a packet error in the orchestrator's setup, and is noted only under records.

**Evidence,** in the ignored `playtests/runs/P12R/`:
- the committed transcript, report and manifest;
- `frozen_hidden_scenario.md`;
- `final/p12_time_r/state/logs/session_001.jsonl`;
- the Ada sheet;
- the `gm_NNN.md` replies and `checkpoint_versions/` (spot-compared for G001, G007 and G014: identical).

**Coverage.** P12 has fewer than ten consequential rulings, so all are covered: every roll and settlement, every Anomaly charge, both milestones, every beat flag, and the agency decisions at G007 and G013–G015.

## Verdicts

**Correct: the opening and threat motion (G001–G007).**
- **The opening.** It is in motion: a footbridge torn by a flood shutter, a man calling for a trapped colleague. Every risky option carries its test and both outcomes.
- **Anomaly.**
  - The charge for time under threat is announced at G001, before anyone commits.
  - It is then charged once per beat in beats 1 to 4, at events 8, 14, 21 and 24, each tied to a gate cycle actually spent under the active flood threat.
  - This follows the frozen policy, which makes core triggers additive to the skin's and limits shared exposure to once per beat.
- **The lockdown clock** advanced on fictional time, whether or not anyone rolled.

**Judgement call: each gate cycle effectively brought one Anomaly.**
- Frozen line 21 says "the lockdown clock tick alone is not automatically Anomaly". In practice, every tick in beats 1 to 4 came with a charge.
- Each was justified as time under threat, and each beat had a single charge, so this is defensible. Still, the clock and the fuse moved in lockstep.
- There is a separate design point below about a flood filling a temporal-paradox fuse.

**Correct: the rescue rolls and the costly nudge (G002–G004, events 4, 6 and 11).**
- Gideon and Miriam both declared the crossing, and both rolled, which is compatible.
  - Gideon: REF 14 with Advantage from Rooftop courier, which squarely fits; kept 14, margin 0.
  - Miriam: plain REF 10; rolled 5, margin +5.
- Ada's brake: INT 14; rolled 18, a miss by 4.
  - The exact 4-token price was offered, the failure cost restated, and the roll deferred. Ada paid; event 11 shows nudge −4 and a final 14.
  - Revision 6's costly-spend rule was applied exactly.
  - The brake is mechanical rather than chronal, so Chronal engineer was correctly not applied.

**Correct: the grille and the index (G006, events 17 and 19).**
- REF with Advantage, kept 5.
- INT 14, rolled 14, margin 0.
- Both were settled with the reason stated.

**Correct, and the best agency handling in the pilot: the bargain (G007–G009).**
- All three routes forward (record, negotiate, leave) were offered with their costs. Two of them would have reached Anomaly 5 and a crisis, and that was stated before commitment.
- **The negotiation.** Ada's call to Orthe drew terms. The Custodian held the gate hold back until the players answered, and spelled out exactly what the hold would protect.
- **Stakes stated before commitment:** a cycle without the hold would bring a crisis; protected work under the hold would bring no Anomaly.
- All three players accepted, and the Custodian honoured the terms.

**Judgement call: the perilous flag on beat 5 (event 27).**
- Beat 5 contains the whole bargain: asking for, negotiating, accepting and implementing Orthe's hold. G008 says the hold has not begun and that another unprotected cycle brings a crisis. The players earned safety within the beat. (Corrected after Astra's review, board 908; my first draft said the beat was carried out entirely under an established hold.)
- Overcoming a peril does not erase it, and the goal (who holds the testimony) was at stake, so the flag is a defensible judgement call.
- It was the third perilous beat after beats 1 and 3, so it brought the first milestone.

**Correct: the dash (G010, event 38).** REF 15 with Advantage, kept 10, margin +5. The new REF from the milestone purchase was applied.

**Wrong, without effect on the outcome: Chronal engineer was omitted at the departure (G011, event 41).**
- Ada recalibrated the engine for the jump: "recalibrate the brass and crystal controls" (P010).
- Her bought tag reads: "applies to hands-on diagnosis, repair, and calibration of chronal machinery when the method fits" (Ada sheet, notes).
- That is a square fit, so the INT Anomaly test should have had Advantage. It was rolled plain: 12 against 15, a success.
- Because it succeeded, nothing was lost. But Advantage was withheld, which bears on revision 6's correct-numbers-before-choices line. Astra's report flagged this itself.

**Correct: the Anomaly test itself (G011).**
- The skin calls for an Anomaly test when operating the machine under duress: INT or Ingenuity, with +1 Anomaly on a failure.
- That was offered at G010 with its stakes. The player chose INT.

**Correct: the reconciliation (G012, event 44).**
- INT with Advantage, because the relevant journal and records were consulted to reconcile a real contradiction. The skin grants exactly this.
- Dice 8 and 1, kept a natural 1: locked. The extra benefit was a filing reference.
- The narration was careful not to overclaim: "does not prove the whole later disaster".

**Judgement call, generous: the perilous flag on beat 8 (event 45).**
- The scene was in a safe shed with no evacuation clock. Failure would only have left a documentary link unresolved.
- Under the handbook's "Stamina, a life or the goal", the goal is arguably engaged, because the prospectus deadline loomed. But the stakes were mild.
- The flag made beat 8 the third perilous beat since the first milestone, so the purchases, Ada's INT 16 among them, came before the caveat roll.
- **Sensitivity,** under the same third-perilous-beat policy: removing either beat 5 or beat 8 moves the second milestone to beat 10. Removing both leaves flags at beats 1, 3, 6, 7 and 10, with the first milestone at beat 6 and only one due by close. The recorded caveat die (4) succeeds against INT 15 or INT 16 alike. This is a sensitivity check, not a reconstructed alternate run.
- **Cross-run observation, qualified.** Generous flags have been noted in P7, P8 and P12, and in Fable's P9 final hearing. These are judgement calls, not established errors.

**Correct, and exemplary: the disagreement over the caveat (G013–G015).**
- Ada told the courier to let the proof go ahead; Gideon and Miriam wanted a caveat and asked Ada to write it.
- G014 stated the disagreement, charged nothing for deliberation, and asked each player for their own decision. Gideon's and Miriam's offers were explicitly conditional on Ada declining.
- Ada changed her mind and committed.
- The intervention used the stakes already stated at G013: INT 16, rolled 4, margin +12, a success.
- No actor was chosen by odds or by majority. This is revision 6's actor rule working exactly as intended, at the cost of one reply.

**Correct: the milestones and purchases (advancement events 28–36 and 46–52).**
- Each milestone gave 2 build points. Purchases at or above baseline cost 2 points each: Ada INT 14 → 15 → 16, Gideon REF 14 → 15 → 16, Miriam EMP 15 → 16 and INT 10 → 11.
- Miriam's INT 10 → 11: the skin's pulp baseline is 10, so at-baseline pricing of 2 points is correct.
- Ingenuity was refilled to full at both milestones.

**Not exercised:**
- Ingenuity tests (the skin suggests one or two a session);
- a failed Anomaly test;
- a crisis;
- purges;
- combat.

## Procedure

- **Revision 6:**
  - stakes were stated before every roll;
  - the one costly spend was offered at its exact price;
  - unaffordable or useless spends were explained;
  - compatible help went ahead without new confirmation;
  - the one genuine actor conflict (G014) was returned to the players;
  - no silent actor selection.
- **The one revision 6 lapse:** the omitted tag Advantage at G011.
- **Pauses.** One pure decision pause (G014). Most turns resolved compatible split actions in a single reply. With three players, P12 had far fewer collisions than P9 had with two, because the players rarely bid for the same roll.
- **Disclosure.** I found no private scenario content in public text. Orthe's "I will not send staff through the live arcs" is her own dialogue, not a published private boundary.
- **Pacing.** 10 beats (5 + 5), 15 Custodian replies, 9 PC tests, about 44 minutes.

## Records

- **G015** came back with an extra newline at each end, so the exact comparison failed. Astra kept both versions and delivered the returned body unchanged. I accept this as a disclosed post-close transport intervention.
- **The Custodian** reported its own saved checkpoints, which matched.
- **Attempt A.** Excluding it was right, and so was the restart from the pre-play snapshot with fresh role histories. The lesson Astra drew is the right one: check content boundaries before launch, because hashes alone do not prove the right content was sent.

## Design observation for the joint review

P12 is the first run where core triggers, under Barry's additive decision, filled a skin's own fuse to near-crisis: Anomaly 4. The cause was a flood, not anything to do with time travel.
- **What fits.** It fits the decision as written: time under threat is a core trigger, and the frozen policy applied it fairly.
- **What it costs.** Anomaly is described as "temporal paradox". Here it filled from evacuation delays, generic threat. The run's historical interventions succeeded, and so avoided their stated failure charges. The tension is thematic, not noncompliance with the frozen rules.
- **The link to Briar.** Barry's question about whether an unusual skin deserves an unusual fuse applies here too. One option is a skin-level statement of which core triggers feed its fuse, and how. For example, Time Odyssey could count core triggers only when they disturb causality, and Briar only when there is proximity to evil or doctrinal transgression. Generic danger would then feed a skin's distinctive track only where the skin says it does.
- This is for Barry's decision and the Stage 3 tally. No change follows from this pilot.

## Summary

P12's mechanics reconcile, and its agency handling is the best in the pilot so far: the bargain at G007–G009 and the caveat disagreement at G013–G015.

Its findings:
- **One omitted tag Advantage** (G011), which made no difference to the outcome.
- **Perilous flags as judgement calls:** beat 5 defensible, beat 8 generous; the sensitivity check is above.
- **A fuse question.** A generic flood threat filled the temporal-paradox fuse to 4.
