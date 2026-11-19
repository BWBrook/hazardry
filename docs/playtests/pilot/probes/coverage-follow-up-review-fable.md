# Fable's contradiction review: coverage follow-up draft

9 October 2026. Review of `coverage-follow-up-draft.md` (board 1072), against `b12135e`, the printed skins, `mapped-exposure.md` and the existing tests. Read-only: no campaign, seed query or role call.

**Verdict.** The design is sound, and it fixes what made F1b and Briar A miss: target branches that could be talked or walked around. Seven points need resolving before binding. Five are contradictions or arithmetic errors, and two are scope reductions. None needs a rule change.

## Must resolve before binding

### 1. Prescribed dice and live Custodians contradict each other

The binding section forbids any synthetic receipt in a live campaign. But CF-T5, CF-S1 and CF-S2 each need a Custodian *and* prescribed dice:
- CF-T5 prescribes a successful valve test;
- CF-S1 prescribes a failed primary result and a frozen reroll;
- CF-S2 prescribes a successful assault and a frozen MCY test.

Several T-cell assertions are also Custodian behaviour: "the alternative stated first" (T4), and nudge offers. As written, these cells cannot run.

Pick one, and say so in the draft:
- **(a) A fixture-campaign class.** The Custodian works in a campaign whose dice are injected at the dice boundary by a reviewable wrapper. The wrapper sits outside `tools/`, and every receipt is marked synthetic. The procedure assertions (disclosure, offers, single charges, timing) do not depend on the dice being random, and the record says plainly that they weren't.
- **(b) Declared prescribed seeds.** The seed for each prescribed die is chosen in advance, by a deterministic computation, to produce the frozen value. It is recorded as a prescription, not as a random draw. This uses the real engine path and needs no new code. It is not outcome-hunting, because the value is fixed and declared before execution, but it does relax your "never search seeds" line, so it is your call.

I lean to (b) for simplicity. Either is honest if labelled.

### 2. Tag each assertion by what can actually test it

Much of what the draft calls a "harness transition" is Custodian-entered in the current harness. A synthetic driver over those flags tests the recipe's arithmetic, not whether the rule is applied. Three tags would make each cell's claim exact:
- **E, engine-enforced.** Synthetic or existing tests suffice. Examples: the Deflection draw and its no-toll rule; Injured Disadvantage on STR/NIM; the Vanguard rejection (`_play.py:462`); Knack once-per-scene limits; the step-4 Totem surcharge through `--context ability`; `--failure-pressure` being skipped when a nudge turns a failure into success; Fatigue-3 incoming Advantage; tableless crisis, reset and `effect-end`.
- **R, recipe or manually entered.** A synthetic run proves only that the harness can represent it. Examples: Spell success payment (a post-settlement `luck` or `pressure`); the Greater Spell's success costs; Arcane Flex's next-cast Disadvantage (`--dis-source` plus a condition flag); the Backstab edge and `--undefended`; crisis-table draws; grave-wound Fatigue; the Broker reroll's replacement; Sin and exposure charges; the core step-2 and step-3 levers.
- **C, Custodian procedure.** This needs a Custodian. Examples: stakes and prices stated before commitment; offering the spends that change an outcome; help rulings before the roll; ledger persistence; once-per-session Totem tracking.

**Consequence.** As drafted, CF-T2 and CF-T3 are synthetic matrices over R items. They would show the recipe adds up, which F1b's frozen recipes already claimed. The untested question is whether a Custodian applies the costs correctly, with the right ordering of payment choice and nudge. I suggest that each becomes a short scripted-caster Custodian cell, with dice under point 1, keeping synthetic checks only for the E items.

### 3. CF-T3's Fatigue start is too high

"Start below Fatigue 3" fails for the Fatigue-paid Arcane Flex. From 2, the Flex payment goes 2→3, and the failed second cast's Spell cost goes 3→4. The third cast is then made at 4 and pays the step-4 toll, which is exactly the mixing the draft wants to avoid.

Start both variants at **0**; 1 is the highest that works. In the Fortune variant from 0, the second failure takes it to 1 and the third cast is clean.

### 4. CF-S1's Strain start must be 0

Free Traders step 2 is "each crew member's next EDU or SOC test has Disadvantage", and the trade test is SOC or EDU.
- **From 2,** the primary trade test carries Disadvantage.
- **From 1,** the Strain-paid Broker takes it 1→2, and the reroll, another SOC/EDU test, carries Disadvantage that the Fate-paid variant doesn't.

Either way the two payment variants stop being matched. **Start at 0.** Then the Strain variant goes 0→1 at Broker, and 1→2 on the final failure, after settlement.

Also freeze the failure consequence. The skin lets the Guildmaster choose "+1 Strain, or tick Debt +1", and "failure Strain is applied once" assumes the Strain branch.

### 5. CF-T4 has three unstated readings and one unfrozen draw

- **The Backstab edge.** The printed text says "the edge is +2". That reads as *setting* the edge, while the draft says "adds +2", and F1b froze `--edge 2`. With a sword (+1) the two readings give 2 or 3. Use an edge-0 weapon, so the readings coincide, and log the wording for the Stage 3 tally, rather than deciding it inside a probe.
- **No defence from surprise.** This is not in the Backstab text. It is a reading of the Manual's "an unseen shot cannot be defended" (Adventurer's Manual, line 244). Declare it as that local reading.
- **Grave wounds.** The skin gains Fatigue from "grave wounds" but does not define them. F1b froze "reduced to 0 Stamina, +1 Fatigue" as a local definition. The 0-Stamina variant must declare the same, or a different, definition, and compute whether that +1 crosses a step.
- **The crisis draw.** The Fatigue-paid toll tips the track to 5, and the crisis needs a d6 face. Prescribe the face under point 1, with the 6-recursion cap. Also declare that Backstab and tolls are not "magic" for face 5, as F1b did.

### 6. CF-T1 is mostly covered already

Existing tests assert most of it:
- `test_deflection_pays_no_toll` (`tests/test_play_runtime.py:91`);
- `test_second_injury_drops_target_and_positions_hold` (197);
- `test_ended_positions_do_not_apply_and_injured_vanguard_can_defend` (221);
- `test_injury_penalty_is_immediate_but_vanguard_fallback_waits` (`tests/test_independent_combat.py:38`), with its natural-1 and failed-Deflection path;
- the Deflection nudge path (`tests/test_multi_nudge.py:172`);
- the Vanguard rejection in `_play.py:462`.

Check the two remaining claims, that damage precedes Deflection and that the target is 10 + 2×soak, against those tests. Then reduce CF-T1 to a citation table, plus at most one short Custodian cell for the C item: offering the defender a Deflection nudge with its exact Hope price.

Dread 3 is Twilight's *toll* step ("each risky test … costs 1 Hope"). That makes the no-toll assertion meaningful, so keep the attacker an NPC.

### 7. The Fatal Backstab is already known to be blocked

`stamina` and `condition` act only on character sheets. That is the gap frozen as a blocked stop in F1b, and the harness has not changed since `b12135e`. Confirm it read-only (`--help` and the source), record it as the Stage 4 candidate, and spend no cell on it.

## Checked and consistent

- **CF-T5:** consistent with the F2a specification. That covers:
  - the Pressure option tipping 4→5 under the starting-step modifiers;
  - the action and its deferred Luck decision finished before the tableless crisis;
  - the tipper named;
  - base `--pressure-cost 1` only;
  - the Totem Advantage cancelling, and consuming, the step-2 penalty.

  Two additions:
  - assert that the step-2 and step-3 ledger entries show "discarded" after the reset;
  - confirm, or prescribe, that the post-reset sight test runs after `effect-end` and carries no Disadvantage.
- **CF-S2:** a keeper "across" the sole doorway makes force fictionally necessary, which closes Briar A's gap. One fused post-deed charge takes Sin 1→2, firing the printed step 2 ("Disadvantage on MCY tests with clergy NPCs"), so the follow-up interaction is the right test. Two additions:
  - state the assault's elapsed time, so "before the first Smoke tick" is checkable;
  - keep the record's "intervention, never spontaneous" label.
- **CF-S3:** all three rows match `mapped-exposure.md` lines 35–37. The bargain and heroics positives also qualify as "a full interval of forced effort, cold water", so they fall under the one-event, one-charge rule, as drafted. Check that no exclusion cell accidentally contains a full interval of cold water or forced effort.
- **CF-T2's printed costs** match the skin's spell table. This includes the nudge changing the final outcome that the tier cost is paid on.

## Requested next draft

Before binding:
1. **Prescribed dice:** choose (a) or (b).
2. **Tags:** tag every assertion E, R or C, and reshape CF-T2 and CF-T3 accordingly.
3. **Arithmetic:** fix the CF-T3 and CF-S1 starting values.
4. **CF-T4:** declare its three readings and prescribe the crisis face.
5. **CF-T1:** fold it into a test-citation table.
6. **Fatal Backstab:** drop the cell.

I'll recheck only the changed passages.
