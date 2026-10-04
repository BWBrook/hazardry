# P12 report — Time Odyssey

Astra, 4 October 2026. **The corrected attempt completed ten beats in two acts (5+5), with nine PC tests, four Anomaly gained and no crisis.** It used revision 6 at `36d644f`, three fresh Sol/medium players and a fresh Sol/medium Custodian. Fable's adjudication audit is complete (`audit.md`); see the post-audit note at the end. This is procedural evidence from one session, not balance evidence or a causal test of the revised guidance.

## Attempt provenance

**Attempt A is excluded from clean-play conclusions.** My copied packet builder still selected Free Traders and used a nonexistent section delimiter, so its three Time Odyssey players received the wrong skin, including its generic Custodian-facing section. Hashes faithfully recorded the wrong content. An independent check found the mistake; the attempt was stopped, with every file and native trace retained. G011 completed during the stop race and reached the players; their P011 output files were not relayed back to the Custodian. No G012 began. See `attempt-a/report.md`, its transcript, summary and separate costs.

The corrected attempt, **P12R**, started from the original pre-play snapshot, with only campaign slug/title metadata changed. It retained the predetermined roster, scenario, policies and seed schedule, and used entirely fresh role histories. No seed was selected from observed outcomes and no played state was repaired. The parent and independent checker verified the actual Time Odyssey public content, source boundary, own-character data, hashes and exact setup input before any new player launched. The Quickstart's harmless skin catalogue mention of Free Traders remains; its skin chapter does not.

Main report/transcript/summary refer only to P12R. Campaign: `playtests/campaigns/p12_time_r`; full evidence: `playtests/runs/P12R`. Attempt A remains at the original `p12_time` and `playtests/runs/P12` paths.

## What happened

The crew reached a flooding archive in 9000A, rescued Ivo's colleague, secured their engine, found Wren and negotiated certified copies of suppressed testimony. The witnesses' chosen representative received a full copy before the original entered Orthe's custody. Orthe's promised later public deposit remained explicitly unresolved. They returned to 1890A, compared contradictory records, inspected a public filing and submitted a limited caveat about the scope and conditions of the proposed eastern works. The narration did not equate a missing attachment with proof that a survey never existed, or a temporal journey with an observed new timeline.

The courier dispute provided the clearest agency observation. In G013/P013, Ada declined intervention while Gideon and Miriam asked her to author a caveat. G014 stated the disagreement and returned it to the players without a roll or charge. Ada then explicitly changed her mind and committed; the others' offers were conditional on her declining. G015 resolved Ada's committed intervention, without choosing her by odds or majority.

The players generally coordinated well, but their differing drives became visible at that final decision. The opening rescue, witnesses' custody terms, and the later dispute produced consequential choices. These are observations of coherence and engagement; they do not establish human enjoyment.

## Logged mechanics and pacing

| Observation | Corrected attempt |
|---|---:|
| Recorded beats / acts | 10 / 2 (5+5) |
| Perilous beats | 7: 1, 3, 5, 6, 7, 8, 10 |
| PC tests / tests per beat | 9 / 0.9 |
| Advantage / plain tests | 4 / 5 |
| Anomaly gained / final | 4 / 4 |
| Crisis / purge | 0 / 0 |
| Luck spent / recovered | Ada 4 / 4; others 0 / 0 |
| Stamina lost / combat | 0 / none |
| Milestones | After beats 5 and 8 |
| GM replies / decisions / closing receipts | 15 / 40 / 3 |
| Elapsed play freeze to all closing receipts | 44.12 minutes |

Four shared gate cycles under active threat generated Anomaly, even though the associated tasks succeeded. Parallel engine security/travel consumed one cycle rather than one per character. The negotiated hold and isolated copying current gave a stated, temporary safe period; no charge was manufactured to reach five. Successful departure and caveat tests avoided their stated failure-triggered Anomaly. The frozen copy scenario and the actual safety concession should be assessed on fictional grounds, not against a crisis quota.

Ada spent four Ingenuity to change her brake test from failure to success. The declared immediate failure cost was water entering the gallery and a lockdown tick, so this is **not counted as four tokens directly spent to avoid a stated Anomaly charge**. No such direct Pressure-avoidance spend occurred. Her first milestone restored the four tokens. All characters ended at 10 Ingenuity; no one reached one token or less. Anomaly remained at four over four later PC tests, with the summary's red-line window still open at session end; Time Odyssey has no printed step-four test penalty.

The two milestones supplied four build points each. Final purchases: Ada INT 14→15→16; Gideon REF 14→15→16; Miriam EMP 15→16 and INT 10→11. All points were spent while the session was open. Minimum Stamina stayed 5 for every character.

Time Odyssey procedures exercised: one successful INT Anomaly test for departure under duress; one successful INT historical intervention for the caveat; relevant record comparison granting Advantage; locked natural 1 and its extra filing lead; explicit 1890A/9000A records; no presumed alternate branch. Pure Ingenuity tests, failed historical interventions, crises and their applied consequences were not exercised. Combat, Injury and other optional modules were off or absent. These gaps remain for separately labelled probes or later play, not retroactive changes to this run.

## Rulings to cross-audit

- **G011, chronal calibration:** Ada explicitly recalibrated the engine, and her purchased Chronal engineer scope includes chronal calibration. The Custodian rolled plain INT. Assess whether that omitted a fitting tag. Simply reading a destination entry is distinct from the skin's contradiction-based journal Advantage.
- **G012, beat 8:** the comparison occurred in a safe shed; failure would leave a documentary link unresolved before the courier returned. Whether that sufficiently threatened the goal to make the scene perilous is a judgment. Removing that flag would move the third perilous scene since the first milestone to beat 10, delaying the second milestone and its purchases. This is not a replayed counterfactual.
- **Shared exposure and safety:** compare each cycle and charge with the once-per-beat shared-hazard policy; assess the negotiated hold/current isolation and scene boundaries. Beat 2 and beat 9 were non-perilous. A safe location alone does not settle whether a goal is at stake.
- **G014 agency resolution:** verify that preserving Ada's initial decision, allowing her explicit revision, and treating the others' offers as conditional avoided the earlier pilots' silent-actor selection problem.
- **G015 final wording:** the historical result is the caveat entering the proof, not proof of the later disaster or a guaranteed change to the distant coast. Unanswered witness consent and the public-deposit promise remain open.

No engine/rules changes or in-play adjudication corrections were made. No three-reply story stall or neutral stall prompt occurred.

## Records, access and limitations

There were 112 recorded commands through table closure, no command failures, and nine sequential draw seeds `121004001`–`121004009`. All native role contexts specify `gpt-6-sol` / medium. Every player trace shows zero tool calls; this demonstrates compliance with instructions, not enforced filesystem isolation. Corrected packets contained no hidden scenario, Custodian skin section or another player's private drive/temperament.

Independent reconstruction verified all 43 player decision/receipt inputs, including queued public dialogue and the closing body. G001–G014 matched the actual returned PUBLIC text, historical checkpoints, GM saved files, messages and public log exactly.

**G015 failed the exact comparison:** the returned body contains one extra newline at each end (`returned = newline + checkpoint + newline`, 1820 versus 1818 bytes). The relay stopped. After inspecting the difference, the parent retained both versions and the false check, and delivered the returned body unchanged to all three players, who each acknowledged closure. No checkpoint or game-state repair was made. This is a recorded post-close transport intervention, not a wholly exact checkpoint result.

The frozen scenario is unchanged. The original Custodian saved a longer campaign policy and a condensed run policy before play; each matches its own initial version. The collector's direct comparison of those two different files returns false, explained and checked in `policy_baseline_check.json`. No in-play policy edit occurred.

The `as_closed` snapshot predates parent prompt refresh. Only `prompt.md` differs in the final snapshot. Final validation passed with zero errors and zero warnings. Both attempts' role costs are retained separately; native cumulative token counters are not summed across turns. Billed money and root orchestration cost are unavailable.

## Before the next run

The orchestration fix is substantive packet preflight **before role launch**: verify selected skin and exact public boundary, then own export and permitted additions, then the bytes and hash actually sent. A hash alone cannot establish correct access. Preserve the failed first attempt as evidence of that error. Keep the current independent histories, queued relay, historical checkpoints and closing receipts. Treat the final newline failure and the adjudication questions above explicitly in the round review; no rule change follows from this pilot alone.

## Post-audit note

Added by Fable at Astra's request (board 908), 4 October 2026.
- **Accepted:** Chronal engineer's Advantage was omitted at G011. The roll succeeded, so the outcome was unchanged.
- **Perilous flags:** beats 5 and 8 remain judgement calls. Beat 5 contains the negotiation of the hold, so its peril was earned and overcome within the beat; beat 8 is the weaker flag. Removing either flag moves the second milestone to beat 10; the caveat roll succeeds either way.
- **Design observation:** four Anomaly came from generic threat; the historical interventions succeeded and so avoided their stated failure charges. This is a thematic tension, not noncompliance with the frozen rules.
