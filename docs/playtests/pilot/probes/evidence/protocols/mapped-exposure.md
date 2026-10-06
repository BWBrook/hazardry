# Probe specification: mapped Fatigue exposure

**Status:** draft for Fable's cross-review; no case has run or been frozen.
Revised 5 October 2026 following board 945 and `astra-probes-review-fable.md`.
**Owner:** Astra. **Protocol:** revision 9. **Source baseline:** `b12135e`
(including the crisis fix `c85dcb1`). This is a labelled experimental probe,
not an ordinary pilot or evidence of a normal Pressure rate.

## Question and scope

Can a Custodian apply a thematic mapping when a warranted exposure actually
occurs, carry its step effects into subsequent choices, and resolve its crisis
without treating the reset as relief from the crisis's consequences?

Use Candlelight Dungeons, with Delvekit **off**. This isolates the mapped
exposure left unexercised in P13. Spellcraft, Knacks, combat, Injury and the
Arcanum/backlash interaction belong to Fable's separate probe; they are not
required here. Keep the printed rules for them if a player invokes them, and
report such departures. Step 3's enemy Advantage remains in force but this
probe does not claim to test it without an actual attack.

Sources: `manifest.yaml`, `skins/candlelight_dungeons.md`, Adventurer's Manual,
Almanac 4 and 9, `docs/playtests/pilot-protocol.md`, and review 5/7. P13 is design
background for the orchestrator and auditor only, not a role handout.

## Frozen experimental mapping

Replace the core's additive generic triggers for this probe only. The shared
track, printed steps, crisis table, spell/Knack costs and native Fatigue
triggers remain unchanged. Generic triggers add **one shared Fatigue** only in
these forms:

| Core trigger | Qualifying exposure | Explicit exclusion |
|---|---|---|
| Desperate bargain | Accepted bodily exhaustion/exposure as its price | Debt, promises or lost property alone |
| Taboo act / risky ritual | Grave chill, fumes or bodily magical surge | Moral offence or ritual difficulty alone |
| Noisy heroics / big blunder | A sustained chase, frantic scramble or hazardous collapse physically endured | Noise or failed dice alone |
| Time under threat | A full interval of forced effort, cold water, bad air or forced march | Safe waiting, talk, darkness, ordinary movement, or a clock tick alone |

One physical event is one shared charge, even if both PCs suffer or two trigger
labels describe it. A distinct printed cost remains separate; name both causes
if both occur. Never charge for real-world deliberation. This mapping is public
in every packet, including exclusions. Native forced marches, grave wounds,
missed rest and printed spell/Knack costs are not silently switched off.
Two distinct physical exposures in one beat charge twice; this event-based
frequency is a frozen local interpretation. Both manifest and audit record the
override of Almanac 4's additive default, and packets label it **experimental,
not adopted rules**. Step effects and tolls are consequences of the current
track, not new mapped exposures; record those categories separately.

## Common setup

Use two fresh PCs in each case: **Nell**, a rope worker, and **Orr**, a keeper of
records. In each case generate with `tools/gen_character.py --campaign PATH`
using `--tone heroic`,
`--seed 1410041` and `--seed 1410042`, `--steps 3`, and primaries DEX and LOR
respectively. Both use `--free-tag 'knack=Beast Tongue'`; Nell also uses
`--free-tag 'expertise=rope work (DEX)'`, Orr
`--free-tag 'expertise=manuscript study (LOR)'`. Compare generated sheet hashes
between cases before fixture gains, with the same descriptive metadata and
loadouts; do not copy a played sheet into another campaign. Freeze generated attributes, maxima, tags and all
descriptive adjustments before launch; do not regenerate for better scores.
Nell's free Expertise is rope work (DEX), Orr's manuscript study (LOR); each
has the free Beast Tongue Knack. These are setup choices, not earned tags.
There are no natural creatures in the frozen sluice, so this Knack has no
eligible target in the prescribed cases. If the fiction legitimately changes
that, retain the legal choice and report the departure rather than suppressing it.
Neither has a spell. Each starts at full Stamina and Fortune; both carry leather
(soak 1), a dagger (edge 0), cloak, food and water. Nell has a rope; Orr a hooded
lantern and one oil flask. No gear grants automatic Advantage on the latch
tests below. The proposed DEX tests involve unfamiliar mechanisms, not rope
work. If preflight finds a conflicting generated tag, replace it explicitly
before freezing, never during play.

Nell wants everyone out and takes bodily risks for a companion, but will not
leave one trapped to save property. Orr wants the
register saved but gives up property before gambling another person's life.
Only each PC's own drive and temperament enter its packet. Fresh Custodian and
separate player histories for each case; no reused pilot roles or historical
memory. Instructions enforce access boundaries unless the runtime can enforce
them technically; record which. Use protocol 9's full player packet and verify
the actual delivered hashes, including the printed Fatigue/crisis sections.

**M1–M3 starting fiction:** both delvers have already spent the last interval
bracing an inspection platform in a cold flooded sluice; the scene opens as
the platform reaches a dry refuge. Completing this interval is the declared
scripted exposure. It does not retrospectively impose a cost on a
player decision. All later exposure is avoidable by remaining in the refuge;
there is no recurring automatic charge. Show the cold, shivering and strained
hands publicly, then record +1 shared Fatigue once. The setup explicitly
announces this opening event and charge before any player response.
The Custodian issues that gain with `--category ambient`, a source beginning
`Scripted exposure:`, and no `--character`; the orchestrator logs the scripted
premise as an intervention. M0 instead begins dry, with no opening gain.

**Goal:** bring both delvers and the parish register to the dry exit. A water
clock starts at 0/2 and ticks at each full fictional minute, whether the party
works or waits on the dry landing or elsewhere. Each listed work attempt takes
one minute; its result is resolved before that minute's tick. At two ticks it sweeps away any register
still below. It neither floods the refuge nor kills people already there.
Talking and making a post-roll Luck decision do not by themselves consume a
minute; an explicitly declared wait does. Safe shelter stops bodily exposure,
not the water. There is no listed delay or interruption of the water schedule;
an inventive one must have its effect on the whole schedule declared before
commitment and be recorded as a departure. Retrieving or
losing the register ends that threat. A dry retrieval attempt does not expose
the party to another Fatigue charge. No hidden NPCs or secret motives are
needed. Players may abandon the register; record the changed goal when declared.

The high starting tracks below are **prepared fixtures**, not prior observed
play. Build them through `play.py pressure --gain` with a fixture source before
the opening exposure; retain those receipts and the initial snapshot. Do not
edit tracker values. Where the fixture passes step 2, both PCs start with its
one-test penalty unspent. Freeze no pending action, no crisis, cycle 0 and no
lasting effects. Use `--category ambient` and a `Probe fixture:` source for
prepared gains. Separate those gains, scripted opening exposures and live
player-chosen exposures in reports.

## Bounded cases and assertions

### M0 — a live mapped exposure or an honest avoidance

Start dry in the refuge, Fatigue **0**, no opening exposure, master seed
**141010**. The register is still in the cradle. There are two routes:

- From the landing, operate two unfamiliar linked catches in order. Each
  requires one DEX test and one minute: success releases that catch; failure
  jams it until proper tools arrive. The first must release before the second
  can be operated, so attempts cannot overlap. Two successes secure the
  register before the second minute's water tick. There is no step-2 penalty
  at this case's starting Fatigue 0 and the dry route adds no Fatigue. Give M0
  its own packet text rather than importing M1's fixture/penalty paragraphs.
- Wade to a reachable manual release and brace it for one full minute against
  the cold current. This bypasses both catches and secures the register before
  the minute's water tick. It needs effort, not uncertain execution: no test.
  There is no unannounced drowning, damage or equipment-loss risk on this route.

The public scene describes the icy waist-deep water, current, accessible lever
and full minute of bracing. The Custodian has the mapping and must recognise,
price and explain **+1 shared Fatigue** before commitment to that route. The
expected-answer matrix remains outside role packets. A declared method that
really avoids the cold/effort must be honoured, with its reason recorded; mere
rewording does not remove an exposure that still happens.

Assertions: a completed wet route charges 0→1 once even if both PCs help; dry
work or waiting on the landing charges zero despite advancing the water clock.
Withdrawing before entering/doing the work charges none of that action's cost.
Score this live opportunity once: **applied** when completed and correctly
priced/charged; **avoided opportunity** when offered and refused or genuinely
circumvented; **missed trigger/timing error** when it occurs uncharged or is
first priced after commitment; or **not reached** when the wet route was never
offered before the case ended (give the reason). Do not also label an avoided
opportunity “not reached: player choice.” Preserve actual state after an error;
the scripted M1–M3 gains cannot substitute for live application.

A failed first catch jams the dry route. Taking the wet route afterwards can
still test **application**, but no longer tests a choice between two viable
retrieval routes; flag that loss of the dry alternative. Abandonment remains
available. Record which options were viable when the decision was made.

End when the register is retrieved, lost or abandoned. Cap: two work attempts,
two scenes or 18 Custodian replies. No outcome-driven extra opportunity is added.

### M1 — shared exposure and personal step-2 penalties

Start at Fatigue **1**. Master dice seed **141011**. Scripted opening exposure makes
Fatigue **2**, once for the party. Each PC now owes Disadvantage on their own
next STR/DEX test, independently.

The dry refuge has two reachable unfamiliar catches on the register cradle.
M0's wet bypass is absent in M1–M3: their release lever was broken before setup.
The catches are mechanically linked: the first must release before the second
can be operated, so their one-minute attempts cannot run simultaneously.
Either PC may attempt one DEX test per catch; success releases that catch,
failure jams it until proper tools arrive and costs one clock tick. A success
also takes one tick. Both catches must release to retrieve the register before
the clock expires; on the second successful attempt the register is secured
before that attempt's tick. No retry of a jammed catch. Passing the task to a
companion is allowed; no silent choice of roller by the Custodian.

The numerical assertions below assume no intervening legitimate purge, Knack
cost or other separately warranted change. If play introduces one, record it
and assess the resulting state honestly; do not call the prescribed branch
covered or undo the player's action to recover it.

Must observe for full coverage: scripted exposure 1→2; both independently tracked
penalties; at least one chosen DEX test actually consumes its actor's penalty.
If the other PC does not test, its penalty must remain unspent. If one actor
operates both catches, only its first applicable test uses the step-2 penalty.
Stakes, automatic modifiers and meaningful Luck choices precede settlement.
No failure surcharge is invented. On the dry landing, calling loudly for help
and waiting one minute are offered as safe alternatives: either, if chosen,
must add **zero** Fatigue. A clock tick alone also adds zero.

End when the register is saved, lost or abandoned and both delvers are safe.
Cap: two latch tests, two scenes or 18 Custodian replies, whichever comes first.
Avoidance is a legitimate ending, with unexercised assertions marked so.

### M2 — exposure to step 4, followed by an informed toll choice

Independent fixture at Fatigue **3**, both step-2 penalties unspent. Master
seed **141012**. The opening exposure makes Fatigue **4**; it is not a risky
test and pays no toll. Use the same refuge, clock and catches.

Before a chosen latch test, explain the DEX test, Disadvantage if still pending,
failure consequence, and the choice of **one personal Fortune coin or +1
Fatigue** for the step-4 toll. Explain the crisis risk of the latter before
commitment. It is the acting PC's cost, not both PCs' or the party's Luck.

Assertions are conditional on the actual choice:

- Pay Fortune: exactly one coin before rolling; Fatigue stays at 4 unless a
  separately warranted cost occurs. Any post-roll nudges are extra, recorded
  separately. Do not charge the toll twice when settling.
- Pay Fatigue: 4→5 once; keep the action's starting-step modifiers, finish the
  deferred action and Luck decision, then resolve exactly one crisis. A test
  demanded by the crisis itself pays no step toll. Use M3's table interpretations
  with the acting PC as the personal target instead of Nell, and retain its
  recursive-draw cap. Apply them to the actual post-latch state; a dropped item
  is whatever that actor actually holds.
- Decline the action: neither toll is charged; retain the opening exposure.

Must reach for full coverage: 3→4 and one legally settled risky test with the
chosen toll. The unchosen toll branch is **not tested**; do not clone the live
decision afterwards to claim both. M3 guarantees separate crisis exposure.
Stop after that test and any resulting crisis, or after a refusal/withdrawal
ends the case. Cap: one latch test, two scenes or 18 Custodian replies.
This is a procedure endpoint, not a completed retrieval: record the remaining
catch and water clock as unresolved at the saved checkpoint **unless a crisis
has already ended that threat**, such as face 5 destroying the cradle. A lone
successful latch test cannot save the register. Do not invent a second attempt or tick
time after the stop merely to finish the story.

### M3 — unavoidable shared exposure, crisis and surviving consequences

Independent fixture at Fatigue **4**, step-2 penalties unspent. Master seed
**141013**. Opening exposure makes Fatigue **5**, triggering one crisis with
no player test required. Nell bore the forward brace and is the fixed target
where a personal target is needed; explain this fictional attribution. This
does not make the shared exposure two personal charges.
Pass Nell's sheet ID explicitly as `--target` at crisis settlement; the shared
opening gain has no actor/tipper.

Draw the printed d6 table through `roll.py table`, **one face per command**.
Result 6 creates two child draws; expand depth-first, completing the first
child's subtree before the second. Expand further sixes honestly, retaining
the complete draw tree. Freeze the
following **probe-local consequence interpretations/overrides**, applying all
terminal results in recorded order. These specialise the printed faces for
this sluice; their exact damage, darkness and split are not new general rules:

| Face | Consequence in this scene |
|---|---|
| 1 | Nell drops her held rope and loses her next action; record both and their duration. |
| 2 | The next scene, the dry exit passage, begins in darkness; retain this until that scene or honest relighting resolves it. |
| 3 | Nell loses 1 Stamina and cannot run until she rests; record the ongoing restriction separately. |
| 4 | A sliding partition separates Nell into the adjacent dry inspection bay; opening its ordinary bolt reunites them but takes an action. |
| 5 | No magic was used: a late spring trap strikes Nell's exposed hand for 1 Stamina and destroys the register cradle, dropping any register still in it into the current and losing it. An already secured register remains safe. This is a frozen hazard consequence, not a fabricated attack roll. |

M3's opening is before player action, so face 5 can lose the register without a
live retrieval attempt; label that a scripted-consequence branch. In M2, if a
legitimate departure introduced magic (including Beast Tongue, counted as magic
for this local policy), face 5 instead twists it: any currently persisting
benefit of that magic ends and the target gains Disadvantage on their next
attempt to use the same magic. Record the effect until used; do not also spring
the trap. The Custodian receives this consequence policy, but not the assertion
matrix. Players receive the printed crisis table and foreseeable stakes; they
do not receive the private sluice-specific consequence table in advance.

Repeated faces apply each Stamina loss and lost action; record the total owed.
Repeated darkness or cramp shares the same ending condition, not an invented
extra duration. Repeated wrong turns put an additional ordinary bolt between
the separated delver and the party, each taking an action to open. Preserve all
faces in the crisis record even when their continuing restrictions coincide.

Record the actual target, rolled faces, consequences and lasting effects with
the crisis, then its atomic reset to **0** and one cycle increment. Stamina
losses use `play.py`; dropped/consumed gear is reconciled descriptively. Step
penalties clear at reset, but cramp, lost action, darkness and separation last
for their stated durations. Resolve one subsequent decision in the dry refuge
or exit so any applicable continuing effect is actually respected. A first
action forfeited to collapse is not quietly replaced by another immediate
action. Do not invent a toll on a crisis-mandated test.

Must reach: scripted exposure, a real table draw, target/consequence recorded,
one reset and the correct continuation (or a genuine incapacitation ending).
Not every table face is coverage: report only the faces drawn. Stop after this
continuation. Cap: two scenes, 18 Custodian replies or 20 table-draw commands.
If recursive sixes exhaust the draw cap, retain the unresolved tree and pending
crisis and mark the case incomplete; never substitute a result.

## Execution and evidence contract

Before running, resolve Fable's review; freeze the exact rules commit, scenario,
roster/loadouts, public mapping, these case conditions, model IDs/settings,
module exclusions and policy interpretations. Use unique campaign slugs under
`playtests/campaigns/` and raw evidence under `playtests/runs/`; no role reads
other cases. The Nth dice-drawing command uses `M*1000+N`, starting at 1 in
each case, including crisis expansions. No seed search or diagnostic rolls;
retries preserve seed and event ID. Setup generation has its separate declared
seeds. Non-drawing `pressure` and noncombat `settle` calls here take no draw
index; do not generalise that to combat settlements that draw Deflection.
Keep command receipts and snapshots sufficient to verify the prepared
one-test penalties as well as the track number.

Protocol 9 governs exact checkpoints, relays and sole orchestrator transcript
authorship, public-only summaries, per-declaration trigger checks and no
improvised error compensation. Preserve invalid draws and stop blocked cases
without manual repair. Any private leak makes that case harness-only. Record
any rules error for the audit rather than coaching the Custodian mid-case.

These bounded probes may end before two acts. Record real scenes as beats;
never create filler scenes to obtain a milestone or session close. Save the
checkpoint and snapshot at the probe endpoint; do not pretend a partial session
completed. Apply protocol 9's exact closing-message/peer-archive delivery even
when the case is merely paused at its cap.

Publish a case manifest, exact public transcript, summary, report and Fable's
audit under `docs/playtests/pilot/probes/mapped-exposure/`. Keep initial/final snapshots,
frozen files/hashes, exact packets and delivered messages, command ledger, draw
indices, checkpoint comparisons, native traces and role costs in raw evidence.
Reports distinguish prepared fixture points, scripted opening exposures,
live mapped gains, toll/cost gains, avoided opportunities,
missed triggers and procedures never reached. Give each assertion a result:
passed, wrong, judgement call, not reached or blocked. A valid crisis demonstration
supports the procedure under this fixture; it says nothing about ordinary
session crisis frequency or whether this mapping should become a published rule.
