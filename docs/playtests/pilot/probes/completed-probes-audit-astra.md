# Astra audit: F1c-1, F1c-2, F2b and F1a

5 October 2026. Independent response to Fable's board 979, with the pending
scenario confirmation from board 957 recorded separately in board 996.
Rules and harness: `b12135e`. No probe was rerun, no counterfactual dice were
drawn, and no campaign or frozen evidence was changed during this audit.

## Disposition

| Case | Audited conclusion |
|---|---|
| F1c-1 | Casting arithmetic and backlash recording observed correctly; seed schedule breached and consequential crisis resolution not demonstrated. Do not score the complete procedure as passed. |
| F1c-2 | Reached success branch passes. Forced crisis remains not reached by dice. |
| F2b | Reached honest-payment/treatment branch passes; beat-1 peril flag disputed. Declined branches remain untested. |
| F1a | Reached combat mechanics reconcile, but G027 discloses private state: **harness-test-only under protocol 9**. Correct the accounting and narrow behavioural claims. |

F2a is cleared for freeze/preflight. F1b is cleared conditional on the precise
lift-first ordering clarification sent in board 996, plus ordinary preflight.
Those pending cases are separate from the completed-run findings below.

## Evidence and scope

Reviewed the published records/transcripts in this directory and the ignored
raw evidence under `playtests/runs/F1c/{run1,run2}`, `F2b` and `F1a`: frozen
scenarios, setup, role prompts and packets, native agent transcripts, incoming
delivery logs, tool traces, checkpoint versions, telemetry and final state.

The frozen scenario hashes match their records:

- F1c: `de24a41a818e816b114bbf17234ecc8505adccee8e1402ef53a8c53935fbbf35`
- F2b: `84f7ef7f948499f3af92a9e0d64b0fcd17c05a9f19a05de973a34c880541f4e4`
- F1a: `fda2b369bc02b60c6bf0b4657a258999b0d8da557b08c41d95a338496f82ea35`

The read-only campaign validator returns `ok` for all four live campaigns.
Every file in their final snapshots still matches its live counterpart:
17 files for F1c-1, 15 for F1c-2, 27 for F2b and 80 for F1a. This verifies the
state inspected; a validator pass does not establish correct fictional rulings.

The summaries leave these short cases under incomplete standard sessions
(`missing session_end`). That is compatible with reaching their bounded probe
endpoints. Do not describe them as completed two-act sessions or pool their
fixture-driven observations with ordinary-play rates. Preserve their logs;
do not add a retrospective session closure to make a metric appear complete.

## F1c-1: correct arithmetic, failed crisis validation

The observed casting procedure is supported by the receipts and telemetry:

- `f1c-cast`, sequences 3–4: Fatigue 3→5, then LOR 12 against die 16 at
  seed 211001; action-start modifiers use Fatigue 3; nudging disabled.
- `f1c-settle`, sequence 5: the failed cast settles without another draw.
- Sequence 6: demon-whisper backlash records Disadvantage on Wenna's next
  cast. Its future application remains unplayed.
- External table draw: seed 211003 gives face 4.
- `f1c-crisis`, sequences 7–8: one recorded crisis on Wenna, reset 5→0,
  with no lasting crisis effects.

Two material corrections are needed in the record's interpretation.

**The crisis has no identifiable new consequence.** Candlelight face 4 requires
blundering into trouble or splitting the party. The frozen solo scenario asks
the Custodian to choose the trouble. G002 supplies a stumble, cold bronze and a
frost-handprint, then explicitly states no Stamina loss or lasting effect.
Wenna remains at the gate. The gate barely holding with the wight awake is
already the scenario's failed-cast outcome. No additional trouble, cost,
changed position or obligation is evidenced.

A crisis need not inflict numerical harm or a lasting condition, but Almanac 4
requires a real consequence and forbids using it as a free reset. This record
does not demonstrate such a consequence. Assertion 6 cannot remain an
unqualified **Correct**, and assertion 5's successful reset must not stand in
for successful crisis adjudication. Retain the observed arithmetic and label
crisis consequence application **wrong/unsubstantiated**. Do not invent a
consequence after the run to repair its evidence.

**The skipped seed prevents an “outcome unaffected” claim.** The non-drawing
settlement was given 211002, then the table used 211003. The prescribed next
draw was 211002. The actual recorded path is reproducible, and no selected or
repeated outcome is evidenced, but the compliant sequence's crisis face is
unknown. No counterfactual draw is needed or justified for this audit. Report
the gap as a protocol deviation; do not say it had no effect on the outcome.

This case remains useful evidence of the casting, backlash-recording and reset
operations, and of the two failures above. It does not validate the complete
Arcanum/crisis procedure.

## F1c-2: reached success branch passes

The second independent cast uses seed 212001 and rolls 12 against LOR 12.
Fatigue rises 1→3, with no second charge, backlash, crisis or reset. The newly
armed STR/DEX penalty is recorded and remains unplayed. The no-nudge rule is
respected. These reached assertions pass.

The below-threshold forced crisis was not reached because the cast succeeded.
That was an accepted outcome of the predeclared design. It is neither a failed
run nor a reason to replace its seed or repeat casting until failure.

## F2b: honest payment and treatment pass

The actual choice sequence is supported by the public transcript and telemetry:
slow Sheet crossing at t=1.5, honest admission after the two-hour wait, then
arrival and treatment beginning at t=4.0. The payment changes Wealth 3→2;
treatment changes Tamsin's Radiation 5→3, Stamina 0→1 and clears the stored
collapse condition. The deadline is lifted at the frozen strict endpoint.
No dice were drawn, no Heat clock was created and Pressure stays at 0.

The record correctly separates disclosure from application: the Radiation
penalties and Attention terms were explained, but no qualifying Joss roll,
Heat advance, below-tier purchase or Radiation-4 crossing occurred. Treatment
leaves the Radiation-3 state in place; its later penalties were not exercised.

**Beat 1's non-perilous flag is inconsistent with the strongest reading of
protocol 9.** The road scene presented a real crossing whose fast failure
cost Stamina; the players selected the slow safeguard within that same scene.
The protocol classifies peril at the consequential choice and says safety
earned within the scene does not erase it. Record this as an audit disagreement
with the logged flag, without rewriting the frozen log. Beats 2 and 3 are
judgement calls: the gate wait and at-tier treatment were guaranteed, but the
scene retained Tamsin's life/deadline stakes. Their flags should not be treated
as independent validation of the peril classification rule.

The safe choices show how these players handled this fixture. They do not
test the declined Wealth/Attention branches or establish typical behaviour.

## F1a: exercised mechanics pass; accounting and claims need correction

The 114-event log supports one initiative result (orcs 15, company 5), five
rounds of declared positions, 23 attacks and 46 finalized opposed-side rolls.
All attacks enable Injury and the gritty option. The reached action economy,
stance modifiers, damage, toll scope and nudges reconcile with the rules and
final state. Nudging the opponent's die is permitted by Manual 3; it is not an
error.

Correct three numerical/reporting points before treating `record.md` as the
audited account:

| Item | Audited result |
|---|---|
| Hope-paid attack tolls | **10**, not 11: Aelith 5, Bofrin 3, Tobby 2 |
| Bofrin's total Hope loss | 11→1: **3 tolls + 7 nudge points**, not all defensive spending |
| Tobby's total Hope loss | 10→4: **2 tolls + 4 nudge points** |
| Aelith's total Hope loss | 11→5: **5 tolls + 1 nudge point** |
| Personal Hope spent | **22**: 10 tolls + 12 nudge points |
| Companionship spent | **2**, in separate resource events; pool ends at 1 |
| Actual damage events | **7**: 4, 1, 2, 1, 5, 2, 2, in event order |

The record's damage list mixes offered pre-nudge outcomes with actual damage.
Actual hits were Aelith→archer 4, Tobby→Grishnar 1, Aelith→Grishnar 2,
spearman→Bofrin 1, Grishnar→Tobby 5, then Aelith→Grishnar 2 and 2. Keep the
correct hypothetical calculations separate from realized damage.

**Injury coverage was not reached.** The seven winning hits have effective
margins 7, 0, 3, 0, 6, 2 and 5, with no winning natural 1. Their injurious
criteria were evaluated correctly; this does not test Deflection settlement,
Injury, second Injury or Injured/Vanguard refusal. Ranged defence while engaged
and unscreened was also unreached. Dread stayed at 3 because every toll was paid
in Hope, and Companionship was retained above zero.

Twice Aelith declined six-point nudges that could have made an injurious hit.
Even those would only have triggered Deflection, not guaranteed its failure.
The party also accepted ordinary harm: Bofrin lost 1 Stamina and Tobby fell
from 6 to 1. Replace the general claim about careful players avoiding Injury
with a claim about this observed encounter:

> In this seeded encounter, the party kept Dread flat by paying tolls in Hope
> and used defensive nudges to avert several ordinary hits. Injury remained
> unobserved because no settled hit met its trigger.

Cart Taken correctly remained at 0: round 1 was crossing, and later orcs at
the cart were engaged and attacking rather than working it. The pre-open
clarification of the work requirement is disclosed. The harmless rejected
`combat-end` command was corrected without changing dice. “Dead archer” is
stronger than the mechanical observation of zero Stamina; distinguish that
fictional ruling in the record.

**G027 is a private-state leak under the frozen protocol.** Describing Grishnar
as visibly bloodied or near collapse would follow the public fiction. Instead,
G027 guarantees that any damaging hit will fell him, then explicitly confirms
that Tobby's minimum-one sling hit is enough. That reveals the hidden
one-Stamina threshold. Public damage totals do not establish it because the
players were not given his initial Stamina.

The guarantee accompanies a request for targets, tolls and attack order; P025
then coordinates Aelith first with conditional follow-ups. Under protocol 9's
private-state boundary and Leaks clause, classify the run **harness-test-only**.
The disclosure is late, at the last company turn, and does not invalidate
earlier arithmetic. Preserve its useful initiative, stance, damage, cost and
clock evidence, while excluding clean behavioural claims about the final
choices. Assertion 11's unqualified **Correct** is not sustainable. This is
content leakage, not unauthorized tool access.

## Delivery, packet and tool evidence

The independent native-transcript checks support:

- **36** Custodian public bodies matching all saved checkpoint versions,
  byte-for-byte: 2 + 2 + 4 + 28.
- **69** saved deliveries matching actual received messages in order, each
  once. Native transport adds only its automatic task-addressing suffix,
  without extra game or private content.
- **64** archived player replies matching native outputs.
- **7** player instances, each with exactly one read of its own packet and
  only hand-backs thereafter. The actual Read results reconstruct to the
  full packet files, not merely a declared path.
- All F2b and F1a peer closing lines are delivered through their one-time
  archives, with literal receipts. Joss's extra receipt-turn tool activity
  does not contain another file read or other access.
- **260** native tool calls reproduced exactly in the saved tool traces; no
  observed Custodian tool access outside its assigned boundary.

These observations support instruction compliance in the observed traces;
they do not prove enforced isolation on the shared filesystem. Tool-access
compliance also does not by itself rule out a disclosure in public narration.

The seed checker reports F1c-1 indices **[1,3]**, F1c-2 **[1]**, F2b **[]**,
and F1a **[1…24]**. The F1a non-drawing settlements correctly leave their seed
available to the next drawing command.

The reusable checkers have narrower coverage than these independent checks:

- `trace_check.py` checks delivery substring presence, not by itself full
  transcript coverage, chronological uniqueness, native reply/checkpoint
  fidelity or final acknowledgements. It counts packet reads without checking
  the exact path or returned bytes. The independent comparisons above cover
  those points for these runs.
- Its Custodian access check uses path substrings/regular expressions, so it
  is not an enforced access boundary and can miss indirect/relative paths.
  Native calls were inspected here; no such access violation was found.
- `trace_check.py` rewrites derived evidence files. It was inspected, not
  executed during this audit. `seeds.py` is read-only and was run on all four
  cases. It reads live logs; the final/live equality checks above establish
  their identity for this audit.
- `seeds.py` ignores seedless drawing events, trusts the external-draw ledger,
  and does not establish interleaving against native commands. It also prints
  a misleading next seed after a gap (211003 for run 1, already used). Native
  commands corroborate the actual draws here. Both tools print findings
  without failing their process exit status.

Retain these limitations in the tooling description. Before relying on the
checkers as automatic gates, make missing seeds and failed checks fail
explicitly and verify external-draw order against the command trace. Do not
rewrite the frozen run evidence while improving those checks.

## Proposed follow-up

A further labelled coverage probe is reasonable to design, but low Hope and
an existing Injury do not guarantee the missing transitions. Low Hope changes
payment and nudge options; it does not guarantee a qualifying hit or a failed
Deflection. Starting Injured can exercise baseline penalties and stance
refusal, but does not establish a new Injury or second-Injury transition.

Separate the objectives before proposing another run:

- **Interaction under an existing Injury:** a frozen starting condition and
  bounded seeded play can test penalty application and player decisions;
  new injurious hits still have a legitimate “not reached” outcome.
- **Guaranteed transition coverage:** use a clearly labelled prescribed or
  synthetic mechanics test, with supplied qualifying-hit/Deflection outcomes,
  kept distinct from free-choice seeded play. Do not hunt a campaign seed or
  repeat until a desired outcome appears.

The repository already contains a deterministic runtime test for second
Injury and the Vanguard prohibition (`tests/test_play_runtime.py`,
`test_second_injury_drops_target_and_positions_hold`). This audit inspected
that test but did not rerun it. A new live case should state what interaction
evidence it adds. No additional run is authorized or launched by this audit.
