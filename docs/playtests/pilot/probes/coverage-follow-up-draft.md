# Coverage follow-up: draft for contradiction review

6 October 2026. **Draft; not frozen, executed or approved for launch.** Prepared in response to board 1067. This is a separate labelled tranche, never pooled with the earlier pilots or their rate summaries. It corrects scenario coverage rather than rerunning old cases until a desired result appears.

The proposed design uses prescribed transitions for branches that require particular dice or actions. It separates those checks from voluntary player uptake. Existing focused engine tests should supply coverage where they already assert the required transition; do not add mirror tests or spend role calls duplicating them. Any remaining prescribed dice inputs are declared synthetic test inputs, supplied at the dice boundary in an isolated test driver, never described as randomly drawn game results. The production rules and engine stay unchanged. A separate, small Custodian exercise checks disclosure and persistent adjudication under scripted actor declarations.

All delegated roles and audits use **`gpt-6.1-sol`**, with effort suited to the task. No Astra delegate, including a nested one. Record actual model/effort receipts. Preparation and local assertion checks do not require player-role agents.

## Eight bounded scenario families

### CF-T1: Twilight's injurious blow

**Type:** prescribed harness transition. A defender holds Steady in an exposed road skirmish. Dread starts at 3. Attacker and defender, soak, edge, Stamina and Hope are labelled fixtures. The optional Injury module is on. Use fresh state for each of four variants: a successful Deflection; failed Deflection producing the first Injury; a nudge that converts a normal failed Deflection to success; and a defender already Injured who fails again.

Choose the raw attack and defence inputs prospectively so the attacker scores a natural-1 injurious hit without ordinary damage already taking the defender to 0. Settle the primary attack before exposing and settling its distinct Deflection. Freeze the nudge amount and payer for the normal noncritical nudge variant; it is a test input, not preference evidence. The second-Injury variant must have positive Stamina immediately before Deflection and fall to 0 because of the second Injury.

**Assertions:** damage precedes Deflection; Deflection = 10 + 2×soak; the involuntary defence/Deflection pays no risky-action toll; the defender pays any Hope nudge; failed Deflection persists Injury; STR/NIM get its penalty; an attempt to declare Vanguard while Injured is rejected. A position already declared is not silently rewritten mid-round. The second Injury takes the target out. Compare the relevant assertions in `tests/test_play_runtime.py` and `tests/test_independent_combat.py` first. **End:** after the final transition and attempted stance declaration, never a recovery adventure.

### CF-T2: Candlelight's printed spell tiers

**Type:** prescribed cost matrix, with fresh Fatigue-0 state for each row. A ward must be moved before a ceiling shutter closes; each named learned effect has its stat, tier and concrete success/failure consequence frozen. Use Cantrip, Spell and Greater Spell. Arcanum already has bounded evidence in F1c and is not repeated here.

Freeze success/failure inputs for each tier; give Spell success both printed payment variants. Add one ordinary failure-to-success Fortune nudge per tier, with the needed amount fixed before execution. Keep starting Fortune sufficient for the declared choice and stop after each cast. No ambient exposure, risky step-4 toll or combat cost is present in this matrix.

**Assertions:** no tier cost before rolling; Cantrip has no tier cost on either outcome; Spell success pays 1 Fortune **or** +1 Fatigue, failure +1 Fatigue; Greater Spell success pays 1 Fortune **and** +1 Fatigue, failure +2 Fatigue. A nudge is separately charged and changes the finalized outcome used for the tier cost; it is not counted as the tier payment. Every row has one finalized cast and its stipulated fictional consequence. **End:** immediately after the cost and any resulting pending state; no second cast to repair a failure.

### CF-T3: Arcane Flex and the next cast

**Type:** prescribed three-cast sequence, repeated in fresh state for the two Knack payment forms. The caster has learned a Spell-tier barrier effect and owns Arcane Flex. A first barrier is needed to hold back debris; a second and third are separately consequential. Freeze the first as successful and the second as failed, using declared synthetic inputs. Both Knack payment variants must start below Fatigue 3 so their known costs do not mix with a step-4 toll.

**Assertions:** Arcane Flex's **Knack** still costs 1 Fortune or +1 Fatigue; its Spell-tier effect is treated as a Cantrip with no **tier** cost. The next cast has the Knack's Disadvantage, applied once and recorded persistently. That second cast pays its own ordinary failure cost. The third cast lacks the expended Flex penalty. A second Flex use in the same scene is unavailable. **End:** after the third cast and once-use check.

### CF-T4: Candlelight combat, Backstab and being taken out

**Type:** prescribed combat transitions in separate fresh fixtures. A scout strikes an active sentry from surprise; a companion stands in its attack lane. A visible bell threatens reinforcements after the fixed final action. All equipment, surprise status, foe attributes and initiative order are explicit. No persuasion declaration is used to stand in for the tested attack.

Freeze four variants: Backstab from surprise at Fatigue 3, with its Knack paid in Fortune so Fatigue stays 3 for the incoming attack; a risky PC attack at Fatigue 4 paid in Fortune; the same starting state paid in Fatigue, tipping to 5; and an ordinary resolved hit taking a PC from positive Stamina to 0. Tests use prescribed hits/failures, not favourable seed selection.

**Assertions:** surprise adds +2 edge and the Knack has its printed use cost; incoming attacks at Fatigue 3 have Advantage; Fatigue-4 toll is charged once before the PC's chosen risky attack, with the alternative stated first; action-start modifiers apply even when the cost tips to 5; resolve the attack and one crisis before reset, preserve lasting consequences; 0 Stamina is taken out rather than automatically dead. Ordinary defence rolls pay no action toll.

The helpless-target Fatal Backstab is a **separate optional binding check**, not implied by surprise. Freeze its target as an NPC with more Stamina than ordinary attack damage, declare immunity/counter status, and verify whether the current public CLI can represent the Fatal result. If it cannot, retain a blocked harness branch and the exact unsupported operation; do not hand-edit the NPC or expand this tranche into a production fix. **End:** after the declared attacks and crisis, or at that binding blocker, not after the bell's later encounter.

### CF-T5: Core Totem, crisis, lasting effect and resumed test

**Type:** prescribed transition plus a short Custodian persistence exercise. One salvager uses an instrument to identify the safe pressure-release valve; an incorrect identification vents dust across the route. Start at Pressure 4, with the F2a optional Totem/Feat declaration and labelled core step rulings. Freeze step 2 as Disadvantage on this character's next instrument test; step 3's mistrust is not applicable to this task. A dry wash station is accessible after the valve action and costs one minute. No hourly threat interval expires within this case.

The scripted actor chooses Totem's Pressure option after both prices are disclosed: **1 Luck +1 Pressure**, including the automatic step-4 ability surcharge. Apply only the base `--pressure-cost 1` with `--context ability` and `--adv-source Totem`; do not also encode the surcharge as a base Luck cost. Totem Advantage cancels the one-test instrument penalty, but consumes it. Record the actor's once-per-session use in campaign memory.

Prescribe a successful valve test to isolate the Totem-triggered crisis from the task's failure consequence. Finish the pending test and frozen Luck decision before a tableless crisis. A prospective local consequence is grit in that actor's eyes, Disadvantage on sight-dependent tests until washing. Record tipper, consequence and end condition before the atomic reset. Then prescribe washing, `effect-end`, and one consequential ordinary post-reset sight test to find the valve's small indicator. Persist the manual step ledger throughout; rebuild the resume prompt before the final test and verify it contains the current ruling state. **End:** after the resumed test and ledger inspection. It must not end merely when Pressure resets.

### CF-S1: Broker after an unnudged failure

**Type:** prescribed adjudication, two fresh port calls with identical scripted inputs except the labelled Broker payment. A merchant bargains for a fuel allotment before the seller's agreed closing time. Freeze a trade-test stat, relevant tag, Watch state, Shares and failure consequence. Supply a normal failed primary result whose success nudge would be affordable. The scripted actor declines that nudge, settles the raw failure, then invokes Broker; **withhold the trade's final failure consequence** while the reroll remains available.

Run one Fate-paid and one Strain-paid Broker. Start Strain below 3 to isolate the Knack payment from step tolls. Freeze the reroll input and nudge choice independently of the result; include a failed final result so failure Strain is applied once, after the replacement result. Declare Watch retention/clearing as a **local interpretation** if Watch is included; otherwise this case claims no Watch coverage. Natural-20 Debt needs its own declared synthetic variant or stays unreached; never search seeds for it.

**Assertions:** the Custodian offers Broker on the settled failure before the consequence; gives both prices and resulting balances; charges the selected Knack cost once; retains the new result; offers any affordable outcome-changing nudge before finalization; applies the trade consequence once; marks once-per-port use. **End:** after final trade payment/consequence. This is required-use fidelity, not evidence of voluntary Broker uptake.

### CF-S2: the keeper occupies the door

**Type:** scripted deed for doctrine timing. Osric stands **across** the vestry's sole direct doorway, holding both jambs. It cannot be reached or passed without his moving or being bodily displaced. The side passage takes ten minutes; Smoke ticks every five. Freeze a physical doorway map consistent with every packet. The Prior permits force, and the church is consecrated.

The scripted declaration is: “I strike Osric to drive him from the doorway, then enter to reach Elian.” This is an assault on a person; forcing an unobstructed door is not a substitute. Freeze a resolved successful nonfatal assault before the first Smoke tick. The Custodian states injury, elapsed-time and rescue stakes beforehand, without spontaneously supplying the numerical doctrinal price; the scripted actor asks no direct Sin question. The full public doctrine remains in the actor packet: this tests GM disclosure timing, not ignorance of the printed rule. Any direct question must receive an honest answer and changes the price-timing coverage label.

**Assertions:** the achieved strike gives one fused violence/vow-breach/taboo Sin charge **after** the deed, with an explanation despite the Prior's permission. Door noise, if independently qualifying, is a distinct prospective event, not a duplicate label on the assault. Prescribe a subsequent MCY interaction with clergy to apply step 2. Freeze that interaction's intent and stakes; do not improvise a guaranteed route solely to get a roll. **End:** after rescue/settled rescue failure and that one interaction. The record must call the assault an intervention, never spontaneous player choice. A later voluntary rescue-choice study would be a different design with conditional coverage.

### CF-S3: three remaining mapped exposures

**Type:** scripted, paired positive/exclusion checks, with fresh Fatigue-0 state for each cell. Reuse the experimental mapping printed in `mapped-exposure.md`, labelled as replacing generic triggers locally; preserve all native Fatigue and spell/Knack costs. One physical event produces one shared charge, even if both delvers participate or several labels describe it.

| Pair | Prescribed qualifying act | Matched exclusion |
|---|---|---|
| Bargain | Delvers accept a lock-keeper's immediate price: haul a weighted chain through icy water for the frozen full interval. | Accept a debt/promise for the same access without bodily exposure. |
| Taboo/ritual | Lift a forbidden seal that releases the frozen grave chill/fumes; both endure the same one exposure event. | Lift its otherwise identical inert duplicate: moral offence or ritual difficulty alone, with no chill/fumes/surge. |
| Heroics | Remain under falling masonry for the frozen interval to brace a collapsing accessway; physical effort/exposure occurs. | Make the equally noisy signal from a safe landing; no sustained scramble, chase or hazardous collapse is endured. |

The experimental charge and exclusions are stated before the scripted actor confirms the act. Freeze duration, body exposure, props and ordinary success/failure stakes for each cell; declare that no native forced march, grave wound, spell cost, missed-rest trigger or separate physical event is present. No clock tick alone adds Fatigue. Use definite exposure facts so a die is unnecessary to decide whether the trigger occurred. If a consequential task check is included, declare it separately and rule on all help before commitment.

**Assertions:** each qualifying event adds exactly 1 shared Fatigue; each exclusion adds 0; private notes give an individual reason for every trigger checked. Required positive and negative actions are interventions, not voluntary uptake. **End:** after the act, charge/noncharge and one exact saved GM response. These cells validate only the specified mapping examples.

## Binding and freeze requirements

Fable's first check should challenge fictional necessity, trigger separation, price timing, artificial outcomes, endpoints and whether a claimed automatic rule is actually manually prescribed. Resolve disagreements in the draft before producing run inputs.

Before freeze, bind every selected cell to exact actor IDs, generated attributes/maxima, initial state, loadout, tags, command argv, event IDs, fixture ledger, public/GM packet bytes, synthetic input or untouched seed schedule, and expected assertions. State which existing tests already supply each transition and omit duplicates. Inventory changes and trigger exclusions must be prospective. A cost, attack, crisis and settlement may not be silently collapsed into one draw.

No synthetic receipt is introduced into a live campaign or passed off as an engine-generated random draw. Its separate fixture driver, output namespace and raw/final distinction must be reviewable before execution. If live seeded role play is selected instead, fix attempt counts before launch, accept unreached dice branches and stop at the same caps; no seed search, result replacement or extension follows.

Any Custodian exercise is capped at **6 public replies per selected cell**; CF-T5 is capped at 8 to allow crisis, washing and resumed test. Synthetic local checks need no role calls. Log every scripted declaration and opening before delivery. Disclose help, source, cost and method rulings before commitment, then ask for confirmation if the ruling changes the stated action. Fix tie-break mappings before consent. Use exact public bodies for checkpoint, log and relay, with final collections after the endpoint and no later drawing command counted as case coverage.

Restrict reads to explicit rule/tool files and the assigned case. Ban top-level relative `campaigns/` and repository-wide searches, including output-filtered searches. The revised native access checker, or an equivalent for the Codex histories, must report attempted and executed access separately; it is a detection heuristic, not enforcement. All later immutable inputs, script interventions, receipts and source bytes must be retained.

**Current status:** scenario design only. Setup scripts, fixtures, synthetic driver, packets, exact cell count, model-effort receipts and freeze hashes do not yet exist. Fable's contradiction review precedes those bindings and the freeze. No campaign, seed query, role call or production-code change was made to prepare this draft.
