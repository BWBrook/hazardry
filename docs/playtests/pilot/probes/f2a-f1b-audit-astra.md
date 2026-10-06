# Astra audit: F2a and F1b

5 October 2026. Independent response to Fable's board 1026 and 1030.
Rules and harness: `b12135e`. This completes the audit of Fable's six recorded
cases across five probe designs. The earlier four cases are covered in
`completed-probes-audit-astra.md` and board 998.

No new play, dice, counterfactual rolls, campaign edits, frozen-evidence edits,
commits or pushes were performed for this audit. Only this assessment is added.

## Disposition and commit gate

| Case | Audited conclusion |
|---|---|
| F2a | One tableless core crisis works through the reached runtime path. The run has an access-boundary breach, altered public-log evidence and a missing persistent ruling ledger; it is not a clean protocol pass. Retain the bounded functional observation and all deviations. |
| F1b | The lift-first initiative procedure, Turn Undead cost/action/recoil and one application of step 2 reconcile. Transport passes. Spell tiers and combat Fatigue remain untested; the clock-substitution ruling is unsupported, unlisted gear was accepted and the last wedge was rolled after the endpoint. |

Hold approval of the current record bundle for the concrete corrections below.
This is an accuracy gate for the authored records, not a requirement to make
every probe pass. Audited failures and unreached branches can be committed as
diagnostic evidence after the records state their limits accurately. No rerun
is required merely to archive these observations. Barry's push gate remains.

The prior F1c-1, F1a and F2b post-audit notes are present and accept board 998:
the crisis consequence and seed gap, F1a's harness-test-only classification and
corrected arithmetic, and the disputed F2b peril flag are now recorded without
rewriting the raw runs.

## Evidence and independent checks

Reviewed the published records and transcripts, frozen scenarios, setup and
role prompts, complete player packets, native role transcripts, incoming
deliveries, saved tool traces, checkpoint bodies, event logs, memory and final
campaign snapshots under `playtests/runs/F2a` and `playtests/runs/F1b`.

Frozen hashes:

- F2a: `7077577c5d907ad824ec308fa1576e073dd9fc0d222cc048cfa45f124ebab6d4`
- F1b: `e2dc0f9f187fec187c140c010fbb875da4603cce66df2f00be1b19a739f20a72`

| Verified item | F2a | F1b |
|---|---:|---:|
| Public GM bodies matching native handbacks and checkpoints | 8/8 | 9/9 |
| Player replies matching native handbacks | 21/21 | 25/25 |
| Actual delivery files verified in native recipients | **24** | **30** |
| Native tool calls matching the saved trace | 88 | 85 |
| Full reads of the player's own packet | 3/3 | 3/3 |
| Raw drawing-command seeds, contiguous | 201001–201002 | 231001–231005* |
| Final snapshot files identical to live counterparts | 34/34 | 77/77 |
| Read-only campaign validator | `ok` | `ok` |

\* F1b's fifth draw is after its frozen endpoint. Within-case draws stop at
231004. See the endpoint finding below; sequential raw draws alone do not
establish compliant play.

The records and orchestrator notes currently say 25 and 31 deliveries. Correct
them to **24 and 30**. Native recipient messages establish each delivery once,
in order, with only the standard automatic suffix. Reconstructed relays cover
every other participant's public reply in order. All six closing peer archives
arrived, followed by literal `Received` handbacks. Players used only their own
packet read and handbacks, and each complete packet result reconstructs to its
archived packet file.

The updated `playtests/runs/probe_kit/{trace_check.py,seeds.py}` were inspected
and then executed without `--write`. Both now default to read-only operation
and return nonzero on reported faults. All four invocations passed. Their
heuristics nevertheless miss the real F2a boundary violation below; delivery
and checkpoint passes cannot certify correct rulings or the whole protocol.

Both cases reach their declared short-probe endpoints without `session-close`.
The incomplete standard-session summaries are appropriate. Do not synthesize
a session ending or pool these fixture-driven cases with ordinary play rates.

## F2a: tableless crisis observed, protocol pass rejected

### Reached mechanics

The event log supports the claimed tableless path:

- Ruth's Totem uses 1 base Luck and the automatic step-4 surcharge, 10→8.
  Its Advantage cancels the manually sourced step-3 mistrust Disadvantage.
  Seed 201001 gives Ruth 19 against EMP 13 and Sal 14 against EMP 11: both
  fail, so the defender wins. Ruth declines her offered nudge.
- Cass's crust crossing uses seed 201002 and succeeds at 6 against REF 13.
- Sequence 15 records the first hour's shared threat charge, Pressure 4→5.
  Sequence 16 records a chosen crisis on Cass, justified by her position as
  lead walker, with `table_result: []` and one lasting effect. Her lost rope
  and grit-scoured eyes supply real consequences.
- Sequence 17 resets Pressure 5→0. The effect remains active, with
  Disadvantage on sight-dependent tests until she rinses her eyes at a short
  rest. The later hour charge raises Pressure 0→1; the hidden clock fills.
  Arrival at t=2.25 leads to contact before securing the medicine.

The recorded reset leaves later Pressure, clock, beat and advancement
commands usable. No roll was made after it. Step-2 application, the
Pressure-paid Totem branch, `effect-end` and a post-reset roll remain
unreached. Those are limits, not failures of the reached crisis command.

The three-perilous-beat milestone is a defensible Custodian judgement under
the handbook. There is no need to remove it merely because this is a bounded
case rather than a complete standard session.

### Access boundary: a confirmed violation

`custodian_setup_prompt.md:146` expressly forbids touching the private
top-level `campaigns/` directory. At 03:25:17Z, saved `tool_trace.jsonl:57`
runs `ls campaigns`, `ls -d campaigns/playtests` and a repository-wide `find`
from the repository root. Native Custodian lines 229–230 confirm execution and
return `README.md`, `emberfall` and `sarn_ford_rumours`.

Private directory names were exposed to the Custodian. No private campaign
contents were observed being read, and no such material was delivered to
players. This is a concrete access-boundary breach; the record's “within its
boundary, by heuristic” claim must be withdrawn. The checker misses the
relative path because its regex expects `sinew-and-steel/campaigns`.

Trace lines 49–50 also show reads of `docs/ai_play_harness.md`, outside the
enumerated read allowlist. This is ordinary harness documentation, so its
significance is lower than the explicit private-directory prohibition.

Protocol 9's automatic harness-test-only rule applies when private material
reaches players. That was not observed here. F2a instead needs an explicit
noncompliant-run classification alongside its bounded functional result.

### Saved public evidence was deleted; it is recoverable

The G008 problem is more than an unsent draft:

1. At 03:24:53Z, the original body was saved to the checkpoint and appended to
   the public campaign log, including “Cutters Close is spent.”
2. At 03:25:00Z, a corrected body was saved and appended.
3. At 03:25:12Z, `sed -i '' '166,181d' state/logs/session_001.md` removed the
   original logged entry.
4. At 03:25:31Z, only the corrected body was handed back for public delivery.

The exact removed body survives in the native Custodian tool result at line
222. The source is
`/Users/bwbrook/.claude/projects/-Users-bwbrook-games-sinew-and-steel/e6212b92-a13c-4f84-ba57-c4840b2b9e88/subagents/agent-ad61476ba1f12eec4.jsonl`.
Creation, replacement and deletion also occur at native lines 209, 213 and
225, corresponding to saved trace lines 52, 53 and 56. Thus the record's
statement that the deleted text cannot be independently verified beyond the
commands is too weak: the complete original text is recoverable.

No F2a player received the hidden clock's name in any native incoming message
or packet result. This confirms successful containment before delivery; it
does not make deleting already-saved campaign evidence compliant.

The final public log retains an unlabelled, superseded G007 at 03:22:37Z,
followed by the delivered revision at 03:22:44Z. It therefore has **nine GM
entries for eight delivered replies**. The old version describes two rifles
and no promise of mercy; the delivered one describes one rifle and three
riders. Neither obsolete wording was delivered. Record this provenance
difference; preserve the frozen log rather than deleting another entry.

### The ruling ledger cannot resume from campaign state

The step-2/step-3 and Totem-use tally is consistent across the Custodian's
orchestrator-only handbacks, but is absent from campaign memory. The frozen
scenario requires private notes, and setup line 148 locates those notes in
the campaign. A fresh campaign-only resume would lose the tally. The record
already discloses this correctly; keep it as an unmet persistence requirement.

## F1b: bounded mechanics pass, thin intended coverage

### Reached mechanics

The board-996 wording is incorporated in frozen scenario lines 141–142 and
works in the logged sequence. Seed 231001 gives skeletons 17, ghoul 11 and
delvers 10. Earlier sides pass as dormant/watching before Hode's lift action;
the lift then wakes the skeletons and creates Stair Gate at 0/4. Its first
tick is at the end of round 1.

Anselm pays 1 coin for Turn Undead, Fortune 11→10, and consumes his combat
action. Seed 231002 gives 6 and 11 with the old-rites Advantage, keeping 6
against FTH 12. Margin 6 makes the lesser skeletons recoil for the scene.
The offered 2-coin nudge to margin 8 is declined. Recoiling skeletons and the
neutral ghoul pass in initiative order thereafter.

Lisel's first wedge uses her pending STR/DEX step-2 Disadvantage: seed 231003,
7 and 7 against STR 11. It is consumed once. Her next wedge uses a single die,
10 at seed 231004. A third raw check, 11 at seed 231005, is outside the case
endpoint and cannot count as probe coverage. Hode's and Anselm's penalties remain
unspent because neither makes an applicable test. F1b's ledger is persisted
in `final/state/memory/custodian_notes.md`.

No attack or spell is resolved. Turn Undead is a Knack. Backstab, Arcane Flex,
spell-tier costs and spell nudges, Fatigue 3–4, a crisis and 0 Stamina remain
unreached. The record generally scores these limits accurately. Frozen rules
and disclosed stakes establish availability, not operational validation.

### The pre-open author clarification is acceptable and limits the finding

The Custodian's question and Fable's response precede opening, are logged,
and resolve movement/tick and skeleton-reach ambiguities without selecting a
die or intervening in ongoing play. Setup explicitly allows a clarification
before opening. No additional approval gate is needed for that interpretation.

The third carry move passes the portcullis before round 4's tick. Consequently,
with the successful Turn Undead and uninterrupted carry, Hode would clear it
before its fourth tick even without wedge successes. This is a coverage limit
of the clarified scenario, not a reason to change its frozen timing afterwards.

The frozen end is “the reliquary is carried past the portcullis” (line 119).
Event sequence 60 records Hode carrying it past; the private ledger at turn 8
also says his third move ends the case. Sequence 61 then records Anselm's
movement, sequences 62–63 roll and settle the third wedge at seed 231005,
and sequence 64 holds a round-4 tick. These are raw post-end events.

G009 likewise resolves Hode and Anselm through the portcullis **before** the
wedge. Lisel's stated purpose was to spare Anselm a tick, but he was already
out. The roll both exceeds the probe endpoint and has no remaining
consequential uncertainty under Almanac 2. Strengthen the record's “moot”
description to **post-end and inadmissible as probe coverage**.

Within-case evidence comprises four drawing commands (initiative, Turn Undead,
two wedges) and three PC rolls. The raw artifact contains five drawing
commands and four PC rolls, with three for Lisel. `summary.json` faithfully
counts the raw log, so its four PC rolls are raw telemetry, not four valid
probe tests. Two in-case wedges hold ticks; do not describe three valid
interruptions. The extra successful check costs nothing and leaves the clock
at the endpoint's 1/4, so it does not change the recorded resource outcome.

At the endpoint, 231005 would have been the next seed. It was actually drawn
afterwards, so the preserved raw trace's next unused seed remains 231006.
Do not erase, reclaim or redraw that die to repair the case.

### A clock does not automatically replace time Pressure

G001 says there is no Fatigue charge for walking, waiting or deliberating.
The private ledger explains this as Stair Gate modelling time passing under
threat. The frozen scenario expressly makes local Fatigue triggers additive
with Almanac 4 (line 43). Almanac 4 lists time under threat as a trigger
(line 75) and describes clocks as running alongside Pressure (line 105).

Announcing a ruling before commitment supplies notice; it does not authorize
a blanket clock-based exemption from those rules. Qualify assertion 10 and
the time-Fatigue audit note: the stated substitution rationale is unsupported.
The frozen case sets no per-round Fatigue cadence, and Almanac 4 gives the
Custodian pacing discretion. The audit therefore does **not** infer an exact
missed charge, retrospectively impose one per round, or recalculate the run.
The unchanged Fatigue 2 cannot establish how time Pressure works in combat.

### Unlisted equipment and routing

Lisel's packet and sheet contain a dagger and robes, but no staff. P006
introduces “my staff”; G007–G009 accept it as a gate brace. No numerical
Advantage is granted, but it is a physical prop in the attempted action and
is later abandoned. “No mechanical effect” should be narrowed to “no numeric
modifier”; “no gear to reconcile” obscures the inventory inconsistency.
The lanterns appear in the frozen premise but were never entered on sheets:
that is a setup reconciliation gap. Acceptance of the unlisted staff is an
additional Custodian adjudication gap. Record both without inserting equipment
into the frozen sheets after the fact.

G004 asks Anselm to restate his position while its `TO:` line names only Hode
and Lisel. Delivery to all three worked; the addressing mismatch is a minor
authoring defect, already disclosed. No private foe condition was published.
F1b's public campaign log contains the nine delivered bodies without the
duplicate-draft problem found in F2a.

## Required record corrections and remaining work

Before approving the commit, update the authored records/notes with:

1. Actual delivery counts: F2a **24**, F1b **30**.
2. F2a's confirmed private-directory access, the independent recovery of
   deleted G008, the nine-versus-eight public-log discrepancy and its resulting
   noncompliant-run classification. Retain the existing ledger caveat and
   narrow functional crisis claim.
3. F1b's post-end events, **two in-case wedges / three PC rolls / four drawing
   commands**, and the raw-versus-within-case seed/telemetry distinction.
   Also record its unsupported clock-exemption rationale, qualified
   general-check score, and inventory/adjudication distinction for the staff
   and lanterns.

Keep frozen scenarios, packets, logs, dice and snapshots intact. Corrections
belong in the authored interpretation and explicit audit notes. Existing
post-audit amendments for the first four cases can remain as provenance.

Any additional play requires a separately agreed bounded design. A follow-up
aiming to exercise spell tiers or Injury must distinguish an observed player
choice from a prescribed transition test; forcing fights or depleting Luck
does not itself guarantee every target branch. No further run is approved or
started here. Astra's three planned probes are still a separate next tranche.
