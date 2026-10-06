# ABR Briar mechanics audit — final independent report

**Status:** Final for the four frozen ABR cases collected on 2026-10-06.

## Scientific target and scope of inference

The bounded target is implementation fidelity for the accepted Briar doctrinal-Sin probe, not a population estimate of Sin frequency, player preference, scenario quality, or ordinary-play balance. The case-level estimands are:

- **ABR-A:** conditionally on the live player choices, whether nonviolent rescue adds no violence Sin; and, only if reached, whether door noise, a violent deed, a second Smoke tick under threat, and a later clergy test receive their distinct pre/post-deed timing and step effects.
- **ABR-B:** whether the exact scripted oath question receives an honest direct answer; whether the exact scripted lie then produces one fused doctrinal/taboo Sin charge after the deed; whether the Abbot's permission is correctly treated as non-absolving; and, conditionally on a voluntary open inquiry, whether the step-3 toll and all test stakes are applied before the roll.
- **ABR-C1:** whether entry into direct sight of the defiled remains produces exactly one ambient Sin charge at 4, reaches the crisis threshold, draws the frozen table deterministically, records target and consequences before reset, and preserves lasting effects; or, if Cadoc avoids sight, whether no exposure crisis occurs.
- **ABR-C2:** whether the exact scripted ordinary examination remains a true nontrigger, with no test, draw, Sin gain, or premature Supplies tick, while every frozen trigger is checked privately.

All cases are engineered single realizations in fresh campaign workspaces. A's turns, B's later writ choice and C1's entry are model-agent choices under fully disclosed player packets and cannot support a behavioural generalization. B's oath turns and C2's examination are scripted interventions that measure Custodian rule application and harness provenance; they do not measure spontaneous player uptake. C2 is a negative control for one exact act, not an estimate of the workflow's false-positive rate across ordinary play.

## Decisive verdict

The four-case suite is **supported for every assertion that its realized branches actually reach**. I found no contradictory charge, missed charge, duplicate charge, fabricated roll, wrong draw, incorrect reset, state mismatch, or provenance leak. The result is bounded mechanistic evidence. It is not a Sin-rate estimate, player-behaviour study, or validation of unchosen branches.

| Case | Realized branch | Mechanics result | Correctly supported claim | Material untested branches |
|---|---|---|---|---|
| A | Live, nonviolent persuasion and keyed rescue | Sin 1→1; Smoke 0/3; one seeded MCY success; two beats | Nonviolent rescue adds no violence Sin; informed alternatives remained live | Violence/fusion timing, forced-door noise, second Smoke tick, Smoke-3 aid, clergy Disadvantage |
| B | Scripted question and lie; live open LOR inquiry | Fused Sin 2→3 after lie; Verdict 0→1; Providence 8→7 toll, then 7→6 Insight; one seeded LOR success | Honest direct answer, non-absolution, one post-deed fused charge, voluntary step-3 toll | Lie refusal, Sin-payment toll, failed inquiry, MCY, concealment, lifted prohibition, decline |
| C1 | Live open entry and direct witnessing | Ambient Sin 4→5; face 2; Cadoc targeted; atomic reset 5→0; future-scene effect active; one beat | Direct exposure charges once; face-2 consequence survives reset and remains unplayed | Avoidance, PRV step 4, faces 1/3/4/5/6, recursion, clue loss, table cap, bell tick |
| C2 | Scripted ordinary examination | Sin 0→0; Supplies 0/2; no draw or test; one beat | Exact consented ordinary act is a true nontrigger | Any changed act, stochastic branch, broader false-positive rate |

**ABR-A: supported for the reached nonviolent branch only.** The autonomous players chose persuasion, a keyed entry and a no-test account. The rescue finished at fictional minute four, before the first Smoke tick, with Sin unchanged at 1. The reportable result is `undisclosed-price timing not reached: player choice`; the case supplies no live evidence about the violence charge, door-noise charge, second-tick charge, Smoke-3 aid, or step-2 clergy Disadvantage.

**ABR-B: supported for every reached primary assertion.** The direct answer, post-deed fused charge, clock, optional open-defiance toll, seeded test, final state, checkpoint copies, and open-session endpoint agree. The unchosen MCY, concealed, lifted-prohibition, refusal, and failed-test branches remain untested.

**ABR-C1: supported for the reached direct-witnessing branch.** Open entry at t=1 produces the one specified ambient charge, one deterministic face-2 draw, the correct sole target, an ordered crisis/reset pair, and an active future-scene consequence. Avoidance and every other table face remain untested.

**ABR-C2: supported for the exact scripted nontrigger.** The act was injected by the orchestrator, resolved without a roll, recorded with the complete private nontrigger ledger, and left Sin and Supplies unchanged. This is a valid case-specific negative control.

No mechanics defect invalidates any completed case.

## Evidence and diagnostics

### ABR-A — live nonviolent rescue

1. **Frozen continuity and readiness clarification.** Every hash in `A/execution_freeze.json` still matches its source, and all 13 archived initial-campaign files match the frozen hashes. The Custodian resumed in the same thread recorded before play. `PREOPEN_READY001` asked only for an exact administrative token, explicitly preserved all frozen inputs, and produced `Ready`; `A/interventions.jsonl` labels it as a pre-open readiness clarification rather than a game turn. The prior response, original role session and clarified response remain preserved.

2. **Live choice rather than a scripted branch.** `A/interventions.jsonl` contains no play intervention. Both role agents independently asked Osric for the keys. When both initially nominated themselves, G002 preserved both intents and required them to agree on one speaker; both then selected Aveline without a tie-break draw. No fictional time was charged for the real-world coordination.

3. **Informed alternatives and trigger separation.** G001 discloses the exact persuasion, keyed-entry, forced-door, side-passage and retreat timing and consequences. It preannounces the second-tick time-under-threat charge and the separate noisy-door charge, and states that neither persuasion nor forcing the door requires striking Osric. This keeps door noise distinct from violence against the keeper and leaves talk, force, delay and retreat live.

4. **One deterministic appeal test.** Event `abr-a-avelines-appeal` uses draw index 1 and frozen seed 141021001. The declared MCY 13 test rolls 11, succeeds at margin +2, and carries no Advantage, Disadvantage or Pressure cost at starting Sin 1. `abr-a-avelines-appeal-settle` records no nudge or second draw. The fictional clock advances only by the stipulated two minutes.

5. **Correct nonviolent resolution.** Aveline declines Insight, turns the keyed latch quietly at t=3, and carries conscious Elian out with Cadoc by t=4. The frozen first Smoke tick is at t=5, so Smoke correctly remains 0/3. There is no forced-door noise, contact with Osric, vow breach, second tick, aid test, or other printed trigger. Sin therefore remains at the fixture value 1. The first scene closes as one perilous rescue beat.

6. **Clergy interaction and endpoint.** Both PCs choose the no-test truthful account rather than seeking Anselm's public acknowledgement. They continue guiding Elian into clear air before t=5. The second scene closes as a nonperilous beat with `--act-end`; no MCY test is manufactured. Final state is Sin 1, Smoke 0/3, Cadoc Providence 8/8 and Stamina 4/4, Aveline Providence 9/9 and Stamina 3/3, beat 2, no pending action or crisis, and `session_closed: false`.

7. **Receipts and closeout.** The event log is continuous through sequence 9, with one raw/finalized roll pair and no other draw. All G001–G005 bodies match received copies, checkpoints and single public-log occurrences; all saved delivery inputs match. One terminal Cadoc reply after G005 contains a brief in-character intention rather than the requested administrative receipt. It receives no Custodian reply, command, fictional-time advance or state mutation. The separate `CLOSING_ARCHIVE` exchange obtains accepted `Received.` tokens from both players. The mechanical endpoint remains G005, but the extra terminal line is a minor closeout-protocol deviation and must not be treated as executed play.

8. **Conditional assertion accounting.** The required report is `undisclosed-price timing not reached: player choice`. A confirms that the nonviolent rescue incurs zero violence Sin. It does not test the post-deed fused violence charge, the preannounced noisy-door charge, the independent second-Smoke-tick charge, the collapsed-child aid branch, or clergy Disadvantage at Sin 2+.

### ABR-B — false oath and voluntary open inquiry

1. **Frozen inputs and starting state.** Every hash in `B/execution_freeze.json` still matches its source. All 12 archived initial-campaign files match the frozen hashes. The session begins with shared Sin 2, Verdict 0/2, Cadoc at Providence 8/8 and Stamina 4/4, and no pending action.

2. **Script provenance and timing.** `B/interventions.jsonl` contains exactly the two frozen turns, labelled `B-question` and `B-lie`, with exact text and `Noted.` receipts. In `B/messages.jsonl` they are the scripted messages `P001_brother_cadoc` and `P002_brother_cadoc`. The corresponding player-role outputs contain only `Noted.`; the Custodian did not fabricate either turn.

3. **Direct doctrinal answer.** G002 begins `Yes`, states that the knowing oath lie will mark `+1 Sin`, and says that neither Godric's order nor Cadoc's compassionate aim absolves it. It repeats the worldly alternatives before the lie and does not turn the answer into an action menu. No charge occurs before P002.

4. **One fused post-deed charge.** After P002, event `abr-b-oath-sin` records one pressure gain with source `Knowing false witness under oath; same-deed vow breach and core taboo fused`, changing Sin 2→3. There is no second taboo or doctrinal gain. G003 explains the breach after the deed. Event `abr-b-witness-clock` separately advances Verdict 0→1 for the completed first witness.

5. **Genuine later choice and informed stakes.** G003 publicly prohibits inquiry, offers permission-seeking, open MCY, open LOR, concealed FLT, another method, and decline, and states the common success/failure consequences. It correctly marks MCY against clergy as Disadvantaged at Sin 3. The unscripted P003 chooses an open LOR examination and explicitly chooses the Providence toll.

6. **Step-3 toll and deterministic draw.** `abr-b-open-seal-check` consumes Providence 8→7 before recording the raw roll. The action starts at Sin 3 with context `open_defiance`; the engine identifies the step-3 toll once. Draw index 1 uses the frozen seed 141022001 and yields 6 against LOR 14, a success at margin +8 with no Advantage or Disadvantage. Settlement adds no nudge. Verdict therefore remains 1/2 and the false seal is exposed before another witness.

7. **Immediate Insight use.** The success makes the printed once-per-scene Insight available. P004 voluntarily asks whether the lower impression matches Godric's seal; `abr-b-insight-seal` consumes Providence 7→6. The private ledger gives the defensible case-specific ruling that this protective evidentiary question is not petty sacred use, so Sin stays 3. G005 limits the answer to identification of the seal die and does not claim who pressed it. The second beat then closes and resets the scene-limited Insight use normally.

8. **Endpoint and state.** The event log is continuous through sequence 14: one session start, the frozen fixtures, one post-deed Sin gain, one Verdict tick, two beats, one raw/finalized roll pair, two Providence costs, and one Insight-use record. Final state is Sin 3, Verdict 1/2, Providence 6/8, Stamina 4/4, beat 2, no pending action, no crisis, and `session_closed: false`. Only one drawing command occurred. All G001–G005 bodies match their received copies, checkpoints, and single public-log occurrences; all delivery inputs match saved inputs.

### ABR-C1 — direct witnessing and face-2 crisis

1. **Frozen continuity and readiness clarification.** Every hash in `C1/execution_freeze.json` still matches its source, and all 11 archived initial-campaign files match the frozen hashes. `PREOPEN_READY001` resumes the same Custodian thread, asks only for an exact administrative token, explicitly preserves the frozen inputs, and receives `Ready`. The prior setup response and clarification are preserved separately.

2. **Correct exposure boundary.** G001 locates Cadoc outside the sightline and does not charge for the heard blow or dust. It discloses that open entry takes one minute and reveals the tomb; quiet entry takes one minute with a FLT test and stated failure harm; waiting reaches the t=2 bell without sight; leaving takes one minute and avoids exposure. It does not announce the experimental ambient price as an option menu and calls no fear test.

3. **Live branch and absence of aliasing.** Cadoc autonomously enters openly with staff lowered. At t=1 he directly sees scattered consecrated remains. Event `abr-c1-g002-ambient-sin` records one ambient gain from direct witnessing, Sin 4→5, with Cadoc as actor/tipper and crisis pending. The ledger separately excludes PC grave disturbance, violence, vow breach, noisy heroics, taboo, timed threat and big blunder. No second doctrinal or core charge aliases the exposure.

4. **Exact table draw and recursion rule.** The only drawing command is `roll table --sides 6` at draw index 1, frozen seed 141023001. It returns the single face `[2]`. Face 2 has no child draws, so stopping after one draw is correct; depth-first face-6 recursion and the 20-draw cap are not exercised.

5. **Target, consequence and reset ordering.** Event sequence 6 is the crisis record: target and tipper `brother_cadoc`, table result `[2]`, and active effect `crisis-1-1`, Custodian control of Cadoc for one future scene. Event sequence 7 is the associated pressure reset, Sin 5→0. The final tracker retains the active effect after reset, advances the cycle to 1, and has no crisis pending. This satisfies the requirement to record target and consequence before the atomic reset while preserving the lasting effect.

6. **Clock, endpoint and cap.** Open entry finishes at t=1, before the next struck bell at t=2, so Antagonist Desecration correctly remains 1/2. No PRV test, MCY fear test, Stamina loss, clue removal or additional chamber scene is invented. The face-2 control remains pending and unplayed. One perilous beat is recorded; play pauses after G002, within the two-beat and 12-reply caps, with no pending action and `session_closed: false`.

7. **Transport and endpoint verification.** G001 and G002 match their received copies, checkpoints and single public-log occurrences. Both delivery inputs match their saved copies, the terminal player response is the pure receipt `Received.`, and `closing_archive.json` correctly requires no repair. The final public text distinguishes ambient exposure from self-disturbance and states the pending future effect without executing it.

8. **Conditional assertion accounting.** C1 supports the witnessing path. Leaving or waiting outside sight, step-4 Providence Disadvantage, bell advancement, Stamina loss on failed stealth, faces 1/3/4/5/6, recursive resolution, keyed clue loss and the 20-draw cap remain untested.

### ABR-C2 — ordinary infirmary negative control

1. **Frozen inputs and starting state.** Every hash in `C2/execution_freeze.json` still matches its source. All 10 archived initial-campaign files match the frozen hashes. The case begins at Sin 0, Supplies 0/2, Providence 8/8 and Stamina 4/4.

2. **Script provenance.** `C2/interventions.jsonl` contains exactly `C2-exam` with the frozen declaration and a `Noted.` receipt. It appears as scripted `P001_brother_cadoc`; the player-role output is only `Noted.`. There is no evidence that the Custodian authored the player turn.

3. **Correct narrative resolution.** G002 resolves the trained examination in 15 fictional minutes without a test, identifies fever and untreated lung infection, records truthful notes, and introduces no oath, taboo, ritual, supernatural event, or additional deed.

4. **Complete private nontrigger assessment.** `final/state/memory/abr_c2_ledger.md` explicitly checks church-ground violence/vow-break, oath lie, sanctified-grave disturbance, petty sacred Insight, failed clue test, failed poultice, Grim Portent fear, direct desecration witnessing, desperate bargain, risky ritual, noisy heroics, time under threat, taboo, and big blunder. It ties the absence findings to consent, an unconsecrated room, an ordinary patient, truthful notes, and the absence of any roll.

5. **State and endpoint.** The only play event after setup is the nonperilous beat `abr-c2-beat-ordinary-infirmary`. There is no drawing command, raw roll, finalized roll, pressure event, resource use, gear change, or clock advance. Final state is Sin 0, Supplies 0/2, Providence 8/8, Stamina 4/4, beat 1, no pending action or crisis, and `session_closed: false`. G001–G002 match their received copies, checkpoints, and single public-log occurrences; delivery inputs match saved inputs.

## Assumptions, alternatives, and residual risks

- **Primary causal contrast:** A, B, C1 and C2 differ in many fixed narrative features as well as trigger status. They demonstrate correct adjudication of pre-specified cases, not isolated causal effects of violence, oath lying, direct witnessing or ordinary examination. A closer negative control would hold actor, setting, timing and wording constant while changing only the doctrinally relevant fact, but that is outside this accepted probe.
- **A branch selection:** A's successful persuasion prevents observation of every positive-charge branch. It is evidence for the nonviolent rule and live player avoidance, not evidence that undisclosed post-deed pricing or the Smoke clock works when a threshold is crossed.
- **A terminal utterance:** Cadoc's non-token FINAL response is preserved after the explicit G005 pause. Treating it as executed fiction would be wrong because the harness neither routed it to the Custodian nor changed state. Its only defensible status is an unprocessed terminal utterance followed by a separate accepted archive receipt.
- **Scripted versus spontaneous behaviour:** B-question, B-lie, and C2-exam are interventions. They establish rule response under exact inputs. They must never be cited as evidence that an autonomous or human player naturally asks the question, accepts the lie, or chooses examination.
- **C1 table coverage:** The face-2 result validates targeting, pending-effect persistence and reset ordering for that face. It gives no evidence about recursive draws, Stamina loss, suspect-test penalties, clue deletion, perilous-beat penalties or cap recovery. A synthetic table-recovery suite would discriminate those implementations directly.
- **Branch coverage:** B's successful open-LOR branch does not test failure consequences, the Sin-payment alternative, MCY Disadvantage execution, concealed inquiry, permission-first inquiry, or decline. C2 contains no stochastic or adversarial branch. Evidence that would discriminate implementation quality on those paths is a separately frozen counterfactual or synthetic recovery test, not reinterpretation of this run.
- **Choice conditioning:** B's packet and G003 disclose the mechanics and viable attributes. The unscripted LOR choice is valid play under the protocol, but it is highly conditioned and cannot estimate unaided method selection.
- **Optional Insight at the boundary:** The immediate Insight question follows directly from the successful writ test and stays within beat 2 and the public-reply cap. It introduces no contradictory trigger and is fully logged. For the narrowest endpoint interpretation, analysts may report the primary B result at G004 and treat P004/G005 as an immediate ancillary resolution; either treatment leaves the primary estimands unchanged.
- **No replication or calibration claim:** A, B and C1 each contain one deterministic draw, while C2 contains none. They provide no information about outcome calibration, variance, crisis rate, or reproducibility across models/seeds. Replayability from the fixed seeds is distinct from generality, and all role sessions use the same model family/settings.
- **Provenance and transport:** All current frozen input files match their recorded hashes. The preserved `initial/A`, `initial/B`, `initial/C1` and `initial/C2` trees contain all 46 files named in the four starting hash maps, and every byte hash matches. A and C1 have versioned, same-thread pre-open receipt clarifications; B and C2 completed under the original runner. This supports continuity, though the records remain writable local artefacts without an external immutable anchor.
- **Open-session summaries:** All four summaries correctly classify these as incomplete sessions because the protocol forbids a false `session-close`. They must remain outside completed-session rate estimates.

## Recommendation

Retain all four ABR cases as valid, case-specific mechanistic evidence. Report A as a successful nonviolent rescue with the doctrinal-price branch not reached by player choice; report B's scripted doctrinal result separately from its single unscripted open-inquiry choice; report C1 as one reached direct-witnessing/face-2 crisis path with avoidance and other faces untested; and report C2 only as the exact negative control. Do not pool them into ordinary-run Sin rates, crisis rates or player-behaviour claims.

The least disruptive next validation is a synthetic recovery matrix for the unobserved crisis faces and B failure/toll alternatives, plus a separate live A run only if post-deed violence timing itself must be demonstrated. Do not rerun these frozen cases merely to manufacture coverage.

**Sol Max audit:** not justified. The central mechanics, state, provenance and public records are concordant, and the residual risks are explicit scope and branch-coverage limits rather than unresolved contradictions that threaten the supported claims. A maximum-effort audit would be warranted only before a stronger claim that generalizes to untested crisis faces, counterfactual branches, ordinary-play rates or human player behaviour.
