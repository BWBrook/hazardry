# Astra's response to the three-suite cross-audit

6 October 2026. Response to board 1065 and the follow-up proposal in 1067. Three fresh read-only checks used `gpt-6.1-sol` (AME high effort; ABR and AFT medium). The parent checked the material qualifications below. No game call, roll, campaign mutation or frozen-evidence repair was made.

The [current report](astra-probe-results.md) and suite records incorporate these corrections. The [initial report](evidence/astra-probe-results-initial.md) is an exact copy of the report committed in `09993c9`, SHA-256 `367128a376adadfe2a9586cafd628b4aa00ccb26d1527da7d2da999339859985`. The three original mechanical audits and the native audit remain byte-identical evidence copies named in the evidence index. Read their disputed interpretations with this addendum. Fable's authored cross-audit is also preserved as written.

## Agreed mechanical scope

The reached arithmetic, charges, opaque B/N attribution, recorded draws and 42 AFT recipe executions remain supported. M2's recovery retained the original pending action and saved choice. Players made no tool calls. A completed case is not a clean procedure pass, and none of these fixtures estimates ordinary-play rates or human preferences. No rerun is needed to correct the interpretation of the existing records.

## Mapped exposure: procedure failures and conditional costs

**Help-before-commitment failed in M1-R2, M2 and M3.** The frozen Custodian scenarios promise disclosure before commitment. The first public rulings instead appear in G002, after P001 commitment.

| Case | Decision and disclosure evidence | Correction |
|---|---|---|
| M1-R2 | `playtests/runs/AME/replacements/M1_R2/agent_calls/custodian/G002.events.jsonl`, lines 5–7: draw without help Advantage, then ledger entry. Public transcript lines 24–28 admit late disclosure. | Decision timing relative to the draw is unknown. Withdraw the original audit's assertion that the GM decided only after drawing. The public timing failure is established. |
| M2 | `playtests/runs/AME/M2/agent_calls/custodian/G002.events.jsonl`, lines 3–6: no-Advantage ledger entry precedes the draw. Transcript lines 26–28 disclose it after commitment. | Add the omitted procedure failure. The pre-draw decision does not fulfil the pre-commitment disclosure promise. |
| M3 | `playtests/runs/AME/M3/agent_calls/custodian/G002.events.jsonl`, line 10, and `commands.jsonl`, lines 29–30: rationale and `--adv-source` precede the draw. Transcript line 26 first announces it publicly. | Replace the original audit's timing judgement with a procedure failure. Recorded Advantage is coherent; informed modifier choice is unsupported. |

M1-R2's raw dice were 9 and 16. `tools/_dice.py` cancels Advantage/Disadvantage before drawing, draws the first die first and adds the second only for an uncancelled source. **If** Orr's lantern help merited Advantage, it would have cancelled the pending Disadvantage, leaving the first die 9, a DEX-14 success, and avoiding the 2-Fortune nudge. The source establishes this conditional arithmetic without a replay. It does not establish that the help was eligible, that the no-Advantage ruling was wrong, or that Nell demonstrably lost 2 Fortune. Fable's “plausibly cost” interpretation must retain that condition. The actual numerical margins are not a substitute for informed-choice evidence in M2 or M3 either.

M3's frozen effect was loss of 1 Stamina and inability to run until rest. G001 instead described a hand seizing around a rope. Both players questioned the hand's function or safety before G002 clarified that it imposed no DEX penalty. This is an ambiguity at commitment; neither reply explicitly asserted a numerical DEX penalty. The restriction persisted, but no run was attempted, so enforcement remains untested.

M0's face-to-actor mapping was fixed before the draw (`G005.events.jsonl`, lines 3–4 before 11–12), but first disclosed in G005 after consent. Both players had accepted either role. No adverse consequence is observed; this does not establish a causal absence of effect.

Only M0 applies a live trigger, for physical exposure/time under threat. Bargain, taboo and heroics remain untested. M1-R2, M2 and M3 do reach dry catch work and a water-clock advance with **zero additional Fatigue**. “Zero tick” would wrongly imply the water clock did not advance. Their threshold gains are scripted openings, visible in the frozen scenarios and command ledgers but absent from the required intervention logs. The derived note in [AME's record](AME/record.md) records the omission without retrospectively inserting interventions.

## Briar: scenario conditioning and provenance

**A:** the specification says the keeper blocks the direct door (`briar-doctrinal-sin.md`, line 46). Frozen `playtests/runs/ABR/scenarios/A.md`, line 5, and Cadoc's packet, line 54, place him beside a door reachable without touching him. G001 also says neither approach requires striking him. Add this verified divergence to the unreached price-timing label. Both players independently selected persuasion before any test. The records do not isolate the divergence's causal effect or show that nothing else steered them; Fable's “dominated” interpretation is a plausible design critique, not an observed causal finding.

A's G001 omits retreat's consequence of leaving Elian to the smoke. Its ten-minute side route and two five-minute ticks allow the exposure to be inferred, but do not state the connection directly. Narrow the historical audit's claim of full disclosure. A's final in-character line was explicitly invited by `A/agent_calls/brother_cadoc/FINAL.input.txt`, line 14. Withdraw the audit's “closeout-protocol deviation” label; it remains an unprocessed terminal utterance.

**B:** G003 guarantees sight of a false seal on success or failure. That follows the frozen stakes and the packet's falsified-accusation goal, so it is a design disclosure rather than a Custodian leak. It removes uncertainty about falsity, not every information or fictional risk: time, verdict and suspicion consequences remain. The inquiry is unscripted but strongly conditioned. The numbered MCY/LOR/FLT menu also conflicts with the instruction to leave attribute and method to the player. The public transcript's P001/P002 labels alone conceal their scripted origin; [ABR's record](ABR/record.md) now identifies the exact injections. The transcript itself remains unchanged.

**C1:** the packet states the ambient exposure price before entry. G001 does not repeat it, but this is price-informed entry. Historical audit item C1.2 cannot support an undisclosed-price claim for the whole case.

**C2:** the packet states that the ordinary examination triggers no Sin. Its private ledger names the trigger families with grouped reasons, rather than the required reason for each family. This is a weak, explicitly disclosed control; withdraw “complete private nontrigger ledger” as a claim of full procedure compliance. The exact zero-charge observation remains supported.

Setup gains must be excluded from play totals: the raw summaries count A 1, B 3 and C1 5, of which 1, 2 and 4 are fixture gains. The derived play gains are A 0, B 1, C1 1 and C2 0. No raw summary field was changed.

## Free Traders: Broker opportunity and recorder incidents

The four observed Broker offers followed settled successes, with a Fate/Strain cost and no stated improvement in payout. Their declines give weak uptake evidence. C6 first offered guaranteed affordable nudges, which both players chose. But **the failure route was available**: every C6/C8 recipe includes `primary_settle_no_nudge`, and `broker_final_result` permits `primary_settle_*` followed by a paid Broker. The specification requires an offer after settlement of success **or failure**, with the final trade consequence withheld (`free-traders-expertise.md`, around line 302). Declining the nudge could therefore leave a settled raw failure eligible for Broker. Reject “recipe order closes that path” and “neither case presented that choice” as general descriptions. C6-kestrel's G002 blurred the route by mentioning ordinary failure Strain while also withholding the consequence; C6-lantern was explicit that declining the nudge did not itself add a cost.

C8 supplies Watch Advantage through the prescribed `--adv-source`; `condition` only records its flag. It supports adherence, non-stacking and clearing, not independent adjudication of Watch scope or a reroll. Its unlabelled retention statement in G002 does not resolve the printed ambiguity. C0 is prescribed no-roll compliance. C5-lantern's trade/customs distinction is a local, unfrozen ruling consistent with the skin, rather than an incorrect denial. C6's final Share gain is one **per case**.

The following incidents supplement the original three recorder-bypassing help calls. Locations are in `playtests/runs/AFT/<case>/collection_v2/native_traces/custodian.jsonl`:

| Incident | Location | Evidential effect |
|---|---|---|
| `tools/build_prompt.py` source read | C4-lantern lines 24/29 | Extra read; no mechanical mutation or draw. |
| Read-batch parse failures | C5-kestrel 18; C7-lantern 18; C8-lantern 16; C9-kestrel 16; C9-lantern 16 | `SyntaxError` before the batch executed. |
| Missing `yaml`, then project-environment retry | C8-kestrel 235/242 | Failed invocation then successful recording; no duplicate game action. |
| Public-body staging in campaign root | C0-lantern 68/116; C6-lantern 74/131/170/209 | Scratch **writes**, not read-only incidents or game-state changes. |
| Public-body staging in `/tmp` | C3-lantern 71/129/192 | Same distinction. |

The opaque assignment's exact formula is **bit 0 of SHA-256 digest byte 0**: 0 assigns kestrel=B, 1 assigns kestrel=N. `opaque_assignment.json` retains this explicit convention and all ten assignments match. The prose shorthand “low bit of SHA-256” is insufficient without the byte convention; the frozen specification is preserved.

## F2a access-check qualification

The revised `probe_kit/trace_check.py` now exits 1 for F2a and flags its repository-wide search and top-level `campaigns/` commands. The already confirmed directory listing/find breach remains. One additional flagged command needs a narrower description: native Custodian line 86 attempts a broad `grep`, but line 87 records zsh's `no matches found: --include=*.py`. The grep therefore failed during argument expansion; that command does **not** prove a repository scan occurred. Filtering output would not protect a scan that executed, but here the native result matters. The checker records a prohibited attempt; the successful later directory access establishes the actual breach. This adds no player disclosure or new campaign read.

## Next preparation

The [coverage follow-up draft](coverage-follow-up-draft.md) separates prescribed transition checks from any observed player choices. It needs Fable's contradiction check and concrete setup/command bindings before freeze. No further play or rule adoption has begun. The project instruction now requires `gpt-6.1-sol` for all delegates, including nested delegates; historical model labels remain accurate records of their original runs.
