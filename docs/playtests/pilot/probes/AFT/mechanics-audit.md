# AFT independent mechanics audit — final, 20 of 20 subcases

Status: **All twenty subcases accepted as bounded modifier-application evidence, with the untested branches and procedural exceptions below retained.** This report follows the parent's staged completion releases and final release on 2026-10-06. No case's play outputs were examined before its release. No game state, packet, runner, rule source or other auditor's file was edited, and no additional trial was run. The first sections give detailed C0–C4 findings; subsequent sections cover C5–C9 and the final assertion readout.

The complete suite contains 16 gameplay draws, seven meaningful Fate-nudge offers accepted for 19 Fate in total, two paid Scout uses, two paid Salvage uses, and four Broker offers declined. All 42 recorded gameplay commands match their frozen recipe's argument sequence and seed after accounting for the recorder's interpreter/path and seed placement; every command output equals its retained receipt. The primary mechanical signal is reached: exact narrow fits retain Advantage, adjacent broad work loses it, and prepared Watch changes from a redundant to a unique source. This is a rules-application result, not a balance or ordinary-play rate estimate.

## Evidence and fixture integrity

The accepted `docs/playtests/pilot/probes/free-traders-expertise.md` matrix and `opaque_assignment.json` determine B/N, rather than the opaque label or observed result. For C0, C1, C3 and C4, kestrel is B and lantern N; C2 reverses this assignment.

For all ten C0–C4 subcases, the retained initial and source files match `freeze.json`; execution inputs match `execution_freeze.json`; packet hashes match their frozen packet manifest. Paired `sources/common_case.md` files are byte-identical. Character differences are confined to tags, their creation metadata and corresponding notes. Attributes, STM, gear, drives, roles and starting pools match. All 30 character-builder receipts returned success with `--tone standard --strict`; each retained creation ledger uses exactly six points. Narrow tags use the agreed `grant: expertise` compatibility representation, with the narrow replacement paragraph present in all five N player-rule sources.

Primary mechanical evidence is each case's `commands.jsonl`, `collection_v2/final/state/logs/session_001.jsonl`, retained receipts, character sheets and tracker. Public choice evidence is in `transcript.md` and the verbatim player inputs; private trigger checks and endpoints are in the final memory ledgers. All 16 executed `play` command outputs in C1–C4 equal the corresponding saved receipt JSON. No gameplay command failed or was rerun; each case uses draw index 1 only, at `(81410 + case number) * 1000 + 1`. C0 uses no draw. Matched plain dice equal the first die of their Advantage partner; no seed search or outcome replacement appears in these ledgers.

## Observed mechanics

| Case | Prescribed and observed modifier | Raw dice / kept result | Meaningful Fate choice and final outcome |
|---|---|---|---|
| C0 B/N | No roll for all three routine tasks | No dice or structured mechanics events | Charting, coolant inspection and cargo filing complete without cost in both variants. |
| C1 B/N | Advantage from Pilot / Precision docking | Both `[16, 6]`, keep 6 against DEX 10 | Raw success; no defined improvement from Fate. Berth secured; no spend. |
| C2 B (lantern) | Advantage from Pilot | `[12, 11]`, keep 11 against DEX 10 | Offer 1 Fate or failure; player spends 1, final 10, success; Fate 9/10. |
| C2 N (kestrel) | Plain; docking tag does not apply | `[12]`, keep 12 against DEX 10 | Offer 2 Fate or failure; player spends 2, final 10, success; Fate 8/10. |
| C3 B/N | Advantage from Engineer / Jury-rigging damaged machinery | Both `[13, 14]`, keep 13 against EDU 10 | Both offer 3 Fate or failure; both players spend 3, final 10, success; Fate 8/11. Manifold stabilised. |
| C4 B (kestrel) | Advantage from Engineer | `[17, 2]`, keep 2 against EDU 10 | Raw success; no defined improvement from Fate. Correct reading, launch slot retained; Fate 11/11. |
| C4 N (lantern) | Plain; damaged-machinery tag does not fit intact-drive telemetry | `[17]`, keep 17 against EDU 10 | Offer 7 Fate or failure; player spends 7, final 10, success; Fate 4/11. Slot retained. |

The fixed actor, attribute, method and stakes appear in every consequential receipt. No player substitution, alternative method, preparation, companion bonus or gear bonus changes the test. Each Advantage check uses exactly two dice, with only its prescribed specialty source; neither extra dice nor an unrelated source is applied. C8's completed multiple-source non-stacking assessment appears under C7–C9 findings and final assertion 5 below.

Every affordable outcome-changing Fate offer in these cases was made with the raw result, cost and failure consequence visible, and the player chose before settlement. Existing raw successes had binary stakes with no improved degree specified, so no Fate choice was omitted there. No natural 1 or 20 occurred; locked natural extremes are not exercised. All eight rolled cases finish successfully, so Hull damage, shutdown, launch-delay and other final-failure consequence execution are unexercised.

## Pressure, resources and endpoints

The frozen core-trigger dispositions remain applicable: no bargain, taboo, noisy display, ritual, elapsed-time threshold or separate blunder was introduced. C2's pursuit, C3's approaching rupture and C4's deadline remain stakes rather than invented timed ticks. C1–C4 are not jump-role tests. No Engineer failure Strain was imported into C3; Salvage Rat was not offered for the manifold repair. No Knack was used in any C0–C4 subcase.

All ten C0–C4 endpoints retain Ship Shares 2, Strain 0, Fuel/Hull/Debt/Medkit clocks 0, full STM, and zero once-use expenditure. Only the reported Fate deductions change character state. No pending action, pending step effect or crisis remains; empty actor-key lists in the tracker are not pending effects. No beat, act, milestone, advancement, session-close, or extra gameplay action was inserted. Each endpoint occurs after two or three GM replies, within the four-reply cap. Each case's collector checkpoint, public-body and saved delivery-input checks passes. Open session status and zero recorded beats are intentional bounded-case state, not completed ordinary-session evidence.

## Retained exceptions and repair lineage

- **C0 collection, both labels:** the original collector failed with `Summary failed: error: no session JSONL files found`. The table itself completed without any mechanics command. V2 preserves the original error and records `not_applicable_no_structured_mechanics`, event count 0 and mechanical-command count 0. The original `final/` and `collection_v2/final/` trees are byte-identical for every original retained file. This is a read-only collection repair, not a replay or invented event log.
- **C1-kestrel collection:** the original completion is retained; its V2 recollection likewise has byte-identical retained final files and no prior collection error. Do not describe it as a repaired gameplay run.
- **C2-lantern validation:** one post-settlement `validate_campaign` command returned 1 solely for stale prompt sources. A subsequent `build_prompt` and validation both succeeded. This is the documented prompt-staleness lifecycle after state change; it did not consume a draw, alter the choice or replace the result. The failed command remains in `commands.jsonl`.

The standalone session summary classifies C1–C4 as incomplete sessions because no session-end event exists. That label must remain separate from the collector's completed **case** disposition. C0 has no applicable session metrics at all.

## Inference boundary and remaining coverage

This tranche supports correct application of prescribed exact-fit and adjacent-non-fit modifiers and the resulting Fate choice surface. It does not test independent specialty-fit judgment, ordinary-play role routing, player preference, balance or crisis/Strain rates. The observed 1-versus-2 and 0-versus-7 Fate differences are matched-seed observations following player choices; they are not population estimates or evidence that the players would make the same decisions elsewhere. P8 is not a control.

The complete suite verdict is given in the final assertion readout below. Unreached branches were left unexecuted as the protocol requires.

## C5–C6 addendum

The four newly released subcases pass the same frozen initial/source/execution-input/packet hash checks and strict six-point builder checks. Their paired common inputs are byte-identical; paired sheet differences remain confined to tags, their creation metadata and notes. Every recorded `play` output equals its saved receipt. All four complete without failed recorded gameplay commands, use only draw index 1, and pass the collector's checkpoint/public-body/delivery-input checks.

| Case | Prescribed and observed modifier | Raw dice / kept result | Choice and endpoint |
|---|---|---|---|
| C5 B (kestrel) / N (lantern) | Advantage from Liaison / Customs law | Both `[3, 19]`, keep 3 against SOC 13 | Customs citation succeeds, margin +10; no meaningful Fate improvement and no applicable Broker trade test. No spend, impound stopped. Two GM replies each. |
| C6 B (lantern) | Advantage from Liaison | `[15, 14]`, keep 14 against SOC 13 | Offer 1 Fate; player spends it. Primary settles at 13, success. Broker then offered at 1 Fate or +1 Strain; player declines. Fate 9/10, Shares 3. |
| C6 N (kestrel) | Plain; Customs law excluded | `[15]`, keep 15 against SOC 13 | Offer 2 Fate; player spends it. Primary settles at 13, success. Broker then offered at 1 Fate or +1 Strain; player declines. Fate 8/10, Shares 3. |

C6 fixes the actor, SOC attribute, settlement method and named refrigerated-medicine delivery to Sela Orin's clinic. There is no Watch or customs benefit. Both primary commands defer with failure Pressure 0. Their primary settlement events contain only the Fate deduction and finalised roll; no Share, Strain or Debt consequence is applied before the Broker decision. G003 then explicitly offers both printed Broker payment alternatives, warns that the new result replaces the success, and identifies the same modifier. Each player declines in P003. Only afterwards does the sole `final-success` resource event increase Shares 2→3; G004 and the retained fiction consume the one delivered claim once. Both end at G004, within the six-reply cap. No Broker use, cost, second draw, duplicate payment or failure consequence occurs.

The two Broker offers and voluntary declines satisfy the offer/choice assertion, including an offer after success. They **do not exercise** Broker activation, replacement-result settlement, a reroll Fate choice or any reroll-specific consequence. Neither final-failure trade Strain nor natural-20 Debt/audit is exercised. The natural extremes remain absent. C5 retains Shares 2; C6 finishes at Shares 3; all four retain Strain/clocks 0, full STM, unused Knacks and no unresolved action or effect. No beat, advancement or session-close is introduced.

Three direct read-only help calls outside `record_cli.py` are retained as procedural exceptions. C5-lantern directly invokes `uv run python tools/build_prompt.py --help`; its private ledger discloses this. C9-kestrel invokes the same help command successfully. C7-kestrel instead invokes `python3 tools/build_prompt.py --help`, which exits 1 at import with `ModuleNotFoundError: No module named 'yaml'`; later recorded setup succeeds using the project environment. The native traces preserve all three. None is a gameplay command or state mutation, so none invalidates the mechanics evidence; they remain recorder-discipline debt, with a recovered environment error in C7. There is no direct unrecorded gameplay invocation among the inspected native tool calls.

## C7–C9 findings

All six subcases pass the retained initial/source/execution-input/packet hash checks, strict six-point builder checks, recorded `play` output-to-receipt comparison, and collector checkpoint/public-body/delivery-input checks. No recorded gameplay command failed. C7, C8 and C9 common input files are byte-identical within each pair. Paired sheet differences remain confined to the permitted tag, creation and note fields.

**C7 paid Scout Surveyor:** Both packets offer a plain EDU 13 roll if declined, or Scout Advantage for 1 Fate **or** +1 Strain. N/kestrel chooses Fate; B/lantern chooses Strain. Each activation marks Scout used once and records its chosen payment before the raw-roll event. N ends with Fate 9/10 and Strain 0; B ends with Fate 10/10 and Strain 1. Both checks use only `Scout Surveyor` as the Advantage source, draw `[2, 17]` at seed 81417001, keep 2, and succeed with margin +11. No meaningful post-roll Fate improvement exists. Settlement precedes one Fuel tick, 0→1, in each case. No jump-failure Strain is charged on success. These different payment choices do not establish a B/N causal effect. The declined-Scout plain-roll, jump-failure and natural-20 misjump branches remain unexercised.

**C8 prepared Watch and non-stacking:** Both `before_watch` snapshots match their frozen hashes; Mira has no Watch condition there. Each successful setup receipt uses `play.py condition` to add the explicitly labelled prepared Watch fixture, whose active condition appears in the frozen initial sheet. No prior Watch roll was invented. B/kestrel's recorded sources are `Liaison (SOC)` plus `Watch officer early warning (prepared C8 fixture)`; N/lantern has only the latter. Both use exactly two dice `[9, 15]` at seed 81418001, keep 9 against SOC 13, and succeed with margin +4. Thus Watch is redundant with broad Liaison and is the unique Advantage source under the narrow tag; it does not stack extra dice in B.

Both C8 primary results settle without a nudge before Broker is offered. G002 offers keeping the success or paying 1 Fate/+1 Strain for a replacement reroll, explicitly preserving the same Advantage sources. Both P002 replies decline. The following `watch-clear` command changes the condition to false, and the final-success resource command grants Shares 2→3 once. Each final sheet retains the condition key with value `false`, as prescribed; the certified-incubator freight claim is consumed once. Fate remains 10, Strain and Debt 0, Broker unused. The test, choice and endpoint take three GM replies. Watch is not cleared before the Broker decision.

Across **all four C6/C8 trade subcases**, Broker is offered after the settled primary success with both printed payment alternatives, and every player declines. The four offers are verified; **zero Broker activations or rerolls occur**. Retaining Watch through a hypothetical same-test Broker reroll follows the accepted local fixture, but its actual reroll application is not exercised. The Watch/encounter/reroll interpretation remains a **Stage 3 rules-text gap**, not a silently adopted general rule.

**C9 paid Salvage Rat:** In both N/kestrel and B/lantern, Rook is offered either printed cost, automatic success without a die, or a plain DEX 10 roll on decline with 1 STM/case-loss failure stakes. Both players choose 1 Fate. Each command marks Salvage Rat used once and Fate 11→10; the case is secured without a gameplay draw. STM remains 6, Strain 0, Shares 2 and every clock 0. No gravity surcharge applies to the explicit zero-G fixture. Each endpoint takes two GM replies. The Strain-payment alternative, declined-Knack roll and failure branches are unexercised.

All six cases finish with no unresolved action, step effect or crisis, and without added beats, advancement or session-close. C7's sole Strain gain is its freely selected activation payment; C8 and C9 add no unexpected core-trigger charge.

## Final paired readout

`A` means two dice, keep the lower; `P` means one die. No case has a Disadvantage source. Each arrow gives initial→final margin; the first value is before any nudge. Tags and other sources are identified in the detailed rows above. All actions preserve their frozen fiction, actor and target.

| Pair | Actor / target; B versus N procedure | Kept result and margin B / N | Fate and ability use; final changes |
|---|---|---|---|
| C0 | Three routine crew tasks; no roll / no roll | N/A / N/A | No Fate presented, no Knack; no change. |
| C1 | Kest DEX 10; A / A | 6, +4→+4 / 6, +4→+4 | Fate not presented; berth secured, no change. |
| C2 | Kest DEX 10; A / P | 11→10, −1→0 / 12→10, −2→0 | Fate 1 / 2; debris cleared, no Hull or Strain. |
| C3 | Rook EDU 10; A / A | 13→10, −3→0 / 13→10, −3→0 | Fate 3 / 3; manifold stable, no shutdown, Hull or Strain. |
| C4 | Rook EDU 10; A / P | 2, +8→+8 / 17→10, −7→0 | Fate not presented / 7; correct telemetry and slot retained. |
| C5 | Mira SOC 13; A / A | 3, +10→+10 / 3, +10→+10 | Fate not presented; customs impound stopped. |
| C6 | Mira SOC 13; A / P | 14→13, −1→0 / 15→13, −2→0 | Fate 1 / 2; Broker declined both; each named claim consumed once, Shares +1. |
| C7 | Kest EDU 13; Scout A / Scout A | 2, +11→+11 / 2, +11→+11 | B pays +1 Strain, N pays 1 Fate; Scout used once each; Fuel +1 each. Fate nudge not presented. |
| C8 | Mira SOC 13; Liaison+Watch A / Watch A | 9, +4→+4 / 9, +4→+4 | Fate not presented; Broker declined both; Watch cleared, each claim consumed once, Shares +1. |
| C9 | Rook DEX 10 alternative; Salvage automatic / automatic | No die / no die | Each pays 1 Fate and consumes one Salvage use; case secured, no STM loss or gravity surcharge. |

## Final assertion and coverage verdict

| Protocol assertion | Verdict on reached evidence | Coverage limit |
|---|---|---|
| 1. C0 no-roll | Pass: six routine rulings, zero dice. | No manufactured test to create mechanics metrics. |
| 2. C1/C3/C5 exact fits | Pass: all six use prescribed Advantage. | Fit is scripted, not independently adjudicated. |
| 3. C2/C4/C6 adjacent work | Pass: B Advantage and N plain in all three pairs. | Matched outcomes and player spending are descriptive. |
| 4. Paid Scout/Salvage | Pass: identical legal menus; four accepted activations charge the selected cost and mark use. Both Scout payment types reached; both Salvage users pay Fate. | No Knack declined; Salvage Strain payment not reached. |
| 5. Watch/non-stacking | Pass: each primary has two dice; B records two redundant sources, N one unique Watch source; tool-set fixture and tool-clear verified. | No Broker reroll tests source retention in execution. |
| 6. Broker | Pass for all four mandatory post-settlement offers and voluntary declines. | **Broker declined ×4**; activation cost, independent reroll, replacement settlement and reroll Fate branches not reached. |
| 7. Fate | Pass: all seven affordable outcome-changing nudge offers made at exact cost and settled after choice. | **Fate not presented ×9 rolled subcases** where raw success had no improved degree. No kept natural 1/20; **Natural roll locked** not reached. C0/C9 have no Fate-nudge surface because no roll occurs. |
| 8. Prescribed modifiers and isolation | Pass: exact sources, no automatic role bonus, no stacked dice; independent matched starts and matching primary seeds. | Free-play routing and scope judgment not tested. |
| 9. Isolated actions | Pass: no jump-role consequences imported into C1–C5, no Salvage offer in C3, no C4 Strain charged. | All settle successfully; C4 failure mutation branch not reached. |
| 10. Final consequences | Pass: four trade claims consumed once with one +1 Share each; two jumps tick Fuel +1; two zero-G Salvage uses avoid gravity surcharge. | No final failure or natural 20 anywhere: failure Strain/Hull/STM, shutdown/impound/delay, misjump Fuel +2 and Debt/audit execution not reached. |
| 11. Narrow representation | Pass: exact free narrow tags under compatibility grant; all ten N rule-source pairs omit broad Pilot/Engineer/Liaison sample snippets and printed sample crew, with the replacement paragraph and narrow sheet notes. | Generic core discussion of possible skin Expertise remains, without granting it to these PCs. |
| 12. Frozen recipe discipline | All 42 recorded gameplay commands match frozen mechanical recipes; two prepared Watch setup commands are separately receipted and labelled. | Three direct help invocations (C5-lantern, C7-kestrel and C9-kestrel), including C7's recovered missing-PyYAML error, are disclosed read-only procedural exceptions; do not claim perfect recorder compliance. |

The suite is complete for its prescribed run design, with no mechanics blocker found in the reached branches. It does not certify the unexecuted conditional branches. The C0 collector repair, C2 stale-prompt recovery and three direct-help exceptions remain part of the evidence, not erased clean-run claims. No further case or reroll is warranted merely to improve coverage or distinguish the variants. Stage 3 must retain the Watch/encounter/reroll text gap and the separation between this scripted probe and a future ordinary-play study.
