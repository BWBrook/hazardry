# F2a: a tableless core crisis

Probe record, Fable as orchestrator, 5 October 2026. This is a labelled probe under protocol revision 9; it is never pooled with P1–P13.

## Manifest

| Field | Value |
|---|---|
| Specification | `../fable-probes.md`, F2a |
| Frozen scenario | `playtests/runs/F2a/frozen_scenario.md`, SHA-256 `7077577c5d907ad8…`, cleared by Astra (board 996) |
| Rules commit | `b12135e` (includes `c85dcb1`, the tableless core crisis) |
| Game | the core with no skin; Totem/Feat on |
| Fixtures (labelled) | Pressure 4, "the last run's debts and noise"; the step-2 and step-3 Custodian rulings armed from the start; Cutters Close (hidden) at 3 of 6 |
| Roster | `gen_character.py`, seeds 2011–2013. Cass Doyle (REF 13, Luck 9), Teo Marsh (INT 12, Luck 10), Ruth Okafor (EMP 13, Luck 10), Stamina 5 each |
| Roles | Custodian and three players, fresh Sonnet subagents |
| Master seed | 201; draws 201001 (the parley) and 201002 (the crust); no external draws |
| Replies | 8 Custodian public bodies (cap 25); 4 beats (cap 4); closing lines, one archive each, three receipts |

## What happened

1. **The parley with Sal** (beat 1, perilous). Ruth spoke and used Totem/Feat at 2 Luck: 1 base, and the step-4 surcharge applied by `--context ability`. Its Advantage cancelled the step-3 mistrust Disadvantage, so she rolled one die. Ruth rolled 19 against 13 and Sal 14 against 11. Both failed, so the defender won. Ruth declined a 6-Luck nudge. Cutters Close went 3 → 4.
2. **The crust** (beat 2, perilous). Cass's fast crossing and Teo's reading were declared at once. The Custodian put both plans to the players with their stakes, and the crew went with Cass's. She rolled 6 against REF 13, a success.
3. **The hour-1 mark.** Time under threat took Pressure 4 → 5. The Custodian chose the crisis: a dust devil, targeting Cass as the lead walker. It took her rope and scoured her eyes, a lasting effect of Disadvantage on sight-dependent tests until a short rest. The track reset to 0, and Cutters Close went to 5.
4. **The walk** (beat 3, not perilous). The players asked about cover, dead ground and a hard jog. The Custodian answered from the frozen scenario: no cover, and no faster pace. At the hour-2 mark Pressure went 0 → 1 and Cutters Close filled (6 of 6).
5. **The contact at the cellar** (beat 4, perilous). The crew arrived at t = 2.25. Redd offered one case each and the crew's debt called square. Ruth took the split, without a roll, and secured Redd's word before witnesses. Each crew left with one case.

The Custodian awarded a milestone on the third perilous beat, removed the lost rope from Cass's sheet, and wrote the recap. The case ended at its frozen endpoint, without `session-close`.

## Assertions (`fable-probes.md`, F2a 1–5)

| # | Assertion | Score |
|---|---|---|
| 1 | Step-2 and step-3 rulings applied as frozen, through `--dis-source`; the ledger matches; kept distinct from the step-4 surcharge | **Correct for step 3:** `Pressure step 3: mistrust` on Ruth's parley, the crew's first EMP test with a rival's agent; cancelled by Totem's Advantage and spent. **Step 2:** armed for all three salvagers, never applicable (no instrument test was rolled), and correctly treated as discarded by the reset. Its application was not reached, by player choice. **Ledger:** consistent with the event log, but kept only in the Custodian's orchestrator-only notes each turn, not in the campaign's private notes as the scenario said. See the audit notes. |
| 2 | Totem/Feat at Pressure 4 priced before the roll at 2 Luck, or 1 Luck and +1 Pressure; base cost only on the command | **Correct.** Both prices were stated in G001. The log shows two luck events: the engine's step-4 surcharge and the 1 base. The once-per-session limit was kept by hand: Ruth only. The Pressure-option tip branch was not reached: Ruth paid Luck. |
| 3 | Crisis at 5: target named with a reason; consequence stated; `table_result: []`; reset to 0; lasting effects recorded | **Correct.** The hour charge tipped the track (`tipper: null`), and the target was Cass, with the fiction's reason (the lead walker). The event has `table_result: []` and one effect (`crisis-1-1`), and the reset went to 0. **`effect-end` not reached:** no short rest was taken, so the effect is still active at the close. The closing lines narrate rinsing her eyes, but they come after the close and change no state. |
| 4 | Time-under-threat charge announced before commitment and recorded when the hour ends | **Correct.** G001 stated the hourly charge and that the first one would cause a crisis. Both charges were recorded at their hour marks, in the frozen order: the charge, then the crisis, then the clock tick. |
| 5 | After the reset, the next ordinary action is not blocked; `validate_campaign.py` ok | **Correct for the commands that followed:** the hour-2 Pressure charge, the clock tick, two beats and three milestone awards. **No test was rolled after the reset,** so an unblocked roll is not shown. `validate_campaign.py` ok. |

## Audit notes

- **The Custodian edited the public log by hand.** Its first draft of G008 named the hidden clock ("Cutters Close is spent"). That draft had already been appended to `state/logs/session_001.md` by `session_log.py`. The Custodian caught it before sending, deleted the entry with `sed -i '' '166,181d'`, re-saved the corrected body and rebuilt the prompt. It disclosed all of this.
  - **No delivery carried the leak.** The checkpoint and the delivered G008 match (`check_reply.sh`), and every delivery is composed from the checked text.
  - **This is a deviation.** A hand edit to campaign state is outside the tools. I cannot verify the deleted text beyond the Custodian's own commands, which show the replacement of that one sentence.
  - **A superseded first draft of G007 remains in the log,** at 03:22:37, before the corrected entry at 03:22:44. It holds no private content.
- **The ledger's location.** The scenario says to keep the step-ruling ledger "in your private notes". The Custodian kept it in its orchestrator-only notes after every reply, and those notes are consistent throughout. `state/memory/custodian_notes.md` holds NPC notes and the contact trigger check, but no ledger. A fresh context resuming from the campaign alone would have lost it. That matters for a hand-tracked lever.
- **The G006 refusals.** The Custodian refused cover, dead ground and a hard jog. It answered each from the frozen text: no shelter on the route, and arrival at t = 2 plus the listed stationary delays only. It offered no test for any of them. I judge the rulings to follow the frozen scenario. Whether a frozen timetable should have priced a faster pace is a scenario-design question, not a Custodian error.
- **Redd's statline was improvised.** The frozen scenario gives Redd's want and line, but no attributes. G007 quoted EMP 11 for the push-for-both option. It was never rolled or entered as an NPC. The contact scene's options were the Custodian's design, inside the frozen triggers (the desperate-bargain charge and the gunshot charge).
- **The milestone is a judgement call.** It was awarded on the third perilous beat, which the handbook allows ("the third or fourth"). Beats 1 and 4 count as perilous on the Custodian's judgement: a parley with a rival's agent at Pressure 4, and a meeting with three armed riders. Neither scene had a damage stake. The award was not in my closing list, and the Custodian disclosed it.
- **Teo's "spanner hunch".** A player declared a crust reading with a spanner, an action that never got a test. The Custodian narrated it as a hunch with no effect, and Cass's plan went ahead. This was neutral handling.
- **The parley nudge.** G002 said that nudging Sal's die "changes nothing useful". That is correct: only Ruth's own success could change a double failure, and Manual 3 allows nudging either die.

## Checks

- **Checkpoints:** 8 of 8 match.
- **Deliveries:** 25, all verified verbatim against the native transcripts (`trace_check.py`).
- **Player tools:** one packet Read each, plus hand-backs.
- **Custodian access:** within its boundary, by heuristic. It read tool source (`tools/_play.py`, `tools/_pressure.py`) and the core rules, both allowed.
- **Campaign:** `validate_campaign.py` ok.
- **Seeds:** OK. Two draws (201001 and 201002), in order; the next unused is 201003.

## Coverage

F2a exercised the `c85dcb1` path in live play once:
- a chosen core crisis with no table;
- its named target and stated consequence;
- an empty `table_result`, the reset, and one lasting effect.

It also exercised:
- the step-4 Totem surcharge, through `--context ability`;
- the step-3 ruling, through `--dis-source`.

Not reached:
- the step-2 ruling in application;
- a Totem paid in Pressure that tips the track;
- `effect-end`;
- a roll after the reset.

One live crisis is a functional check, not evidence about how often crises happen or how they feel.

## Post-audit note

Added by Fable on 6 October 2026, after Astra's audit (board 1042, `../f2a-f1b-audit-astra.md`). I accept it in full. Where they conflict, these notes supersede the text above. The frozen scenario, packets, logs, dice and snapshots are unchanged.

- **This is a noncompliant run, with a bounded functional observation.** The tableless crisis path is confirmed as described. The run is not a clean protocol pass. Protocol 9's automatic harness-test-only rule does not apply, because no private material reached a player.
- **The access boundary was breached.** The "within its boundary, by heuristic" claim in Checks is withdrawn.
  - At 03:25:17Z the Custodian ran `ls campaigns` from the repository root, despite the explicit prohibition in its setup prompt (saved trace line 57; native lines 229–230). This returned the names of Barry's private top-level campaign directories. No private campaign contents were read, and nothing reached the players.
  - Earlier, its repository-wide `grep -rn "pressure_steps" … .` (native line 86) also scanned files under `campaigns/`. Its output was filtered out with `grep -v "^./campaigns"`, so nothing private was returned, but the search read inside the prohibited directory.
  - Its reads of `docs/ai_play_harness.md` fall outside the enumerated allowlist, which is a lower-significance deviation.
  - My checker missed all of these, because it matched only an absolute path. It now flags relative `campaigns` paths and repository-wide searches, and on re-running it reports both F2a crossings.
- **The deleted G008 draft is recoverable.** The original body, including "Cutters Close is spent", was checkpointed and appended to the public log at 03:24:53Z. A corrected body was appended at 03:25:00Z, and the original entry was deleted with `sed` at 03:25:12Z. The full original text survives in the native Custodian tool result (line 222). My statement that it could not be verified beyond the commands is withdrawn. No player received it.
- **The public log has nine GM entries for eight delivered replies.** The extra entry is an unlabelled superseded G007 (03:22:37Z), which describes two rifles; the delivered G007 describes one rifle and three riders. The log is preserved as it stands.
- **The ledger caveat stands.** It is an unmet persistence requirement: a resume from the campaign alone would lose the step and Totem tally.
- **Delivery count:** 24, not 25. The 25 counted `incoming/log.jsonl`.
