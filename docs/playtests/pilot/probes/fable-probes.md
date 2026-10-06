# Fable's probes: specification

Fable, 4 October 2026, under protocol revision 9 (`../../pilot-protocol.md`, "Probes"). Revised on 5 October after Astra's review (`fable-probes-review-astra.md`; board 942), whose corrections are all adopted. Nothing is frozen and nothing has run.

Review 7 assigned Fable two probes:
- **F1:** full-party combat with spellcraft and Knacks;
- **F2:** a core crisis and the module upper steps.

**A correction to review 7.** Deflection and Injury belong to Twilight of the Northlands' optional combat module, not to Candlelight. F1 therefore has a Twilight subcase for them, beside the Candlelight subcases. This keeps review 4's original target (P4 left Deflection, Injury and the step penalties untested) and review 6's extension to Candlelight.

## What a probe is, and is not

A probe checks that the rules and the harness are applied correctly when a procedure is actually reached. It does not estimate how often anything happens in normal play. Its results are never pooled with P1–P13.

Each subcase is bounded:
- it has a frozen premise, starting state, assertions and cap;
- it stops at its end condition or its cap, whichever comes first.

**Fixtures.** A fixture is a starting state that ordinary play would have had to reach first, such as a high track or a collapsed character. Each fixture is:
- labelled in the manifest;
- applied through the harness before play, as an event whose source begins `Probe fixture:`;
- stated in the public premise where the characters would know it.

**Dice.** The seed schedule is the usual M×1000+N. No seed is chosen for its outcome, and no outcome-hunting rerolls are allowed. Where a branch matters, the subcase is defined so that both outcomes test something, or it runs a pre-declared number of times regardless of results.

**Assertions** are scored **correct**, **wrong** or **not reached**. "Not reached" is a coverage result, not a failure. Its reason is recorded: dice, player choice, or the cap.

**Table.** As in the pilot:
- a fresh Sonnet Custodian;
- fresh Sonnet players, one per character;
- Fable as orchestrator, with the revision 9 relay, checkpoints and archive.

**Scenarios.** For each subcase I write a short frozen scenario: a public premise and hidden notes, with the NPCs' wants, manners and lines, the clocks, the triggers and every local interpretation. This is a labelled, probe-only replacement for setup step 4's Custodian-authored scenario, and it applies to both teams' probes. Setup step 5's contradiction check is done by the other team: Astra reviews mine and I review Astra's. The Custodian reads the scenario before play and may ask for clarifications before the freeze, but it does not rewrite the experiment. The assertion tables stay with the orchestrator and the auditor and never go in a role's packet; every rule and policy a role needs to adjudicate does.

**Crisis tables.** Every table draw is a single-face `roll.py table` command, counted in the seed schedule. A 6 ("roll twice") is expanded depth-first, one command per face: a 6's first child is drawn and fully resolved before its second. At most four draws are made for one crisis. If any required draw remains when the cap is reached (for example 6, 6, 1, 2 leaves the first 6's second child undrawn), the case stops as blocked. The draw tree and the pending crisis are kept, the track is never reset from a partial tree, and no face is ever chosen to end the recursion. The seed schedule counts every command that actually draws, including an attack settlement that draws a Deflection roll.

**Characters** are built with `gen_character.py --campaign` (or `char_builder.py` where the probe needs particular spells or Knacks), at the standard budget, with each run's adjustments recorded.

**Cross-audit.** Astra audits F1 and F2; I audit Astra's.

## F1: combat, spellcraft and Knacks

### F1a: Twilight, a full-party skirmish

**Purpose.** To test combat positions, injurious blows, Deflection, Injury, and Dread's step-3 toll and step-4 Disadvantage in a real fight.

**Table:**
- Twilight of the Northlands;
- the optional combat module on, with its gritty option (an injurious blow also at effective margin 8 or more);
- three companions (one bold), with the Companionship pool at 3/3.

**Premise.** The company holds a ford at dusk against four orc raiders: two spearmen, an archer, and a chieftain with a shield. Behind the company is a cart of refugees, so retreat costs the cart. The orcs want the cart's food and will break off if the chieftain falls or two others drop.

**Fixture:**
- Dread 3, from "a week on tainted ground" (labelled);
- the step-2 penalty is pending, and the step-3 toll is active from the first risky test.

**Assertions:**
1. Initiative follows Manual 6: the fiction, or one d20 per side with ties rerolled. The order holds for the fight.
2. Positions are declared for every PC at the start of each round, before anyone acts (`play.py positions`/`round`), and held all round for attacks and defences.
3. Vanguard is refused while a PC is Injured. Ranged, engaged in melee and unscreened, defends with Disadvantage.
4. Damage is 1 + edge + 1 per full 5 of the attacker's margin − soak, minimum 1. A natural 1 ignores soak and adds +1.
5. An injurious blow is checked on every hit: a natural 1, or an effective margin of 8 or more (the attacker's margin minus the defender's if both succeeded, otherwise the attacker's margin).
6. The Deflection test is d20 under 10 + 2 × soak. It can be nudged with Hope, or with Companionship once per scene per PC. Failure makes the target Injured, with the description recorded.
7. While Injured: Disadvantage on STR and NIM. A second injury takes the target to 0 Stamina at once, and the fiction's stake is stated.
8. The step-3 toll (1 Hope or +1 Dread) is paid only on risky tests a companion chooses to attempt, never on defence rolls or Deflection tests. Its price is stated before the roll.
9. If Dread reaches 4: Disadvantage on all tests from then on, including defence rolls and Deflection tests, which still pay no toll. Penalties use the Dread level at the start of the action that triggers them. If it reaches 5: one crisis, drawn with `roll.py table` (or picked, and said to be picked), then a reset to 0.
10. If Companionship reaches 0, +1 Dread is marked at once.
11. Revision 9: each action is checked against the frozen triggers; offered options are kept; no PC's words are written.

**Threat clock.** *Cart Taken* (0/4) advances at the end of each round in which an orc is at the cart and no companion engages it. At 4 the orcs have the cart, and the goal is lost. The 8-round cap is an administrative stop, not this clock.

**End.** The fight ends, the company withdraws, or the cart is taken.
**Cap.** 8 rounds or 30 Custodian replies.

### F1b: Candlelight, a crypt fight with spells and Knacks

**Purpose.** To test every spell tier below Arcanum, all three Knacks, Fortune nudges on spells, and Fatigue's step-3 and step-4 effects in a fight.

**Table:** Candlelight Dungeons with Delvekit off, and three delvers:
- a fighter with Backstab;
- a hedge mage with Arcane Flex, and LOR spells: one Cantrip, one Spell and one Greater Spell;
- a cleric with Turn Undead and a holy symbol, and one FTH Spell.

**Premise.** In a barrow's burial hall, six lesser skeletons and a ghoul guard a reliquary the delvers were hired to recover. The skeletons wake when the reliquary is lifted. The ghoul wants grief-tales and will parley.

**Fixture:**
- Fatigue 2, from "the long descent" (labelled);
- the step-2 Disadvantage is pending on each delver's next STR or DEX test.

**Assertions:**
1. Spell costs follow the tier table:
   - a Cantrip costs nothing;
   - a Spell costs 1 coin or +1 Fatigue on success, and +1 Fatigue on failure;
   - a Greater Spell costs 1 coin *and* +1 Fatigue on success, and +2 Fatigue on failure.

   The tier cost follows the test, as printed. A Spell's success payment (coin or Fatigue) is chosen with the post-roll nudge decision and recorded after settlement. Every cost of a cast is recorded before any crisis.
2. Fortune nudges are offered on Cantrips, Spells and Greater Spells, on top of the spell's cost.
3. Each Knack is used at most once per scene, at 1 coin or +1 Fatigue:
   - Backstab: edge +2 from surprise, and Fatal on a helpless foe unless immune;
   - Turn Undead: FTH; success makes lesser undead recoil for a beat; margin 8 or more destroys one or scatters the pack; failure adds +1 Fatigue on top;
   - Arcane Flex: a Spell cast as a Cantrip, then Disadvantage on the next cast this scene.
4. At Fatigue 3, attacks against the delvers have Advantage. At 4, each risky test a delver attempts costs 1 coin or +1 Fatigue before rolling, and never a defence roll.
5. If Fatigue reaches 5 from a spell or Knack cost:
   - one crisis is drawn with `roll.py table`;
   - result 5 (backlash) twists magic used this scene;
   - result 6 means rolling twice;
   - then a reset to 0.
6. Delvers can be reduced to 0 Stamina (Manual 4), and what follows is stated as a stake.
7. Every spell or Knack in the fight takes the caster's action: attacks and opposed tests do so already; *Bless* and Turn Undead use `check --combat-action`; a no-test Cantrip is recorded with `pass`.
8. Backstab's eligibility (surprise, a helpless foe) and which foes are immune to a Fatal backstab are frozen in the scenario. Each named spell's exact effect is frozen in the packet.
9. Unchosen spells and Knacks, and unreached paths, are scored "not reached: player choice" or "not reached: dice".
10. The revision 9 general checks, as in F1a.

**Threat clock.** *Stair Gate* (0/4): once the reliquary is lifted, the stair portcullis grinds down, +1 at the end of each round. A STR test, taking an action, wedges it: success holds the next tick. At 4 the stair is shut and the goal is lost.

**Harness gap, frozen as a blocked stop.** `stamina` and `condition` act only on character sheets, so a Fatal backstab on the ghoul cannot be recorded if the hit leaves it above 0. If that branch occurs, the case stops as blocked, with the evidence kept. The tracker is never hand-edited and the edge is never inflated.

**End.** The reliquary is carried out of the hall or abandoned, or the stair is shut.
**Cap.** 8 rounds or 30 Custodian replies.

### F1c: Candlelight, the Arcanum and its backlash (two pre-declared casts)

**Purpose.** To test the Arcanum procedure from two starting conditions. Run 1 guarantees a crisis; run 2 tests a forced crisis only if the cast fails.
- The cost is +2 before the roll, with no nudges, and no second charge on success.
- "One crisis if Fatigue reached 5 or the cast failed, never two."
- A failure always brings a backlash.

**Table.** One caster of its own, Wenna Ashby, who learned the Arcanum *Seal the Barrow* (LOR) from a scroll and has no casting Expertise, so the cast has no Advantage from her build. This was chosen before any draw.

**Premise.** The barrow's inner gate must be sealed before what is behind it wakes. The case is framed as one decision, declared publicly: cast the Arcanum or don't. No other way of sealing the gate is within reach. A refusal is scored "not reached: player choice".

**Two runs, each played regardless of the other's result.** Each is a fresh campaign with its own seeds.
- **Run 1, the threshold branch.** Fixture: Fatigue 3. The +2 takes Fatigue to 5, so exactly one crisis follows whether the cast succeeds or fails. A failure also brings a backlash.
- **Run 2, the forced branch.** Fixture: Fatigue 1. The +2 takes it to 3.
  - Success: no crisis, and no further charge.
  - Failure: a backlash, and one forced crisis below 5 (`pressure --crisis --forced`).

**Assertions:**
1. The +2 is part of the casting action: `check --pressure-cost 2 --no-nudge --defer`, with the actor, attribute and stakes. It is never a separate Pressure gain first, which would reach 5 and block the cast. Penalties use the starting Fatigue.
2. No Fortune is offered. The cast is settled, then any crisis is resolved, with no second +2.
3. Success charges nothing further.
4. On failure, the Custodian chooses a backlash, states it, and records it as a lasting effect where it lasts.
5. Exactly one crisis is recorded, whenever one is due, drawn with `roll.py table`. Fatigue resets to 0 with nothing carried over.
6. Whatever each run produces is recorded correctly. A success in run 2 leaves the forced crisis and the backlash "not reached: dice". No replacement cast, seed or run follows.

**Cap.** 6 Custodian replies per run.

## F2: a core crisis and the module upper steps

F2 uses the Ferrous Gap setting and P11's published module declarations: Radiation steps, protection and removal, and Wealth tiers, sale and Attention. Their text is copied as frozen probe policy. It has a new crew with fresh seeds. The P11 campaign is not touched.

### F2a: a tableless core crisis

**Purpose.** To test the commit `c85dcb1` path in live play:
- a chosen core crisis with no table;
- its target, its consequence stated before the reset, and its lasting effects;
- the frozen Custodian rulings for the core's step-2 and step-3 levers, applied from a fixture.

It also tests the optional Totem/Feat plugin and the step-4 ability surcharge.

**Table:**
- the core with no skin;
- Totem/Feat on (once per session: Advantage at 1 Luck or +1 Pressure; at step 4, abilities cost +1 Luck more);
- three salvagers.

**Premise.** The crew crosses the open Glass back to the Spindle cellar for Cases Four and Six. Redd's Cutters are already on the ridge. The frozen trigger is time under an active threat: +1 at the end of each fictional hour in the open Glass. The crossing is two hours with no shelter on the route, and that is in the public premise.

**Fixture:**
- Pressure 4, from "the last run's debts and noise" (labelled);
- the step-4 ability surcharge is active (the engine applies it automatically through `--context ability`).

**Frozen step rulings.** The core's steps 2 and 3 are Custodian levers (`kind: custodian`), so the engine arms no penalties for them. The scenario freezes these local interpretations, tracked by hand in a ledger kept in the Custodian's notes and applied with `--dis-source`:
- **Step 2 (flicker tech):** each salvager's next test that relies on a counter or other instrument has Disadvantage. One use per salvager, consumed on that test.
- **Step 3 (NPC mistrust):** the crew's first EMP test with an official, or with a rival boss or their agent (such as Redd's outrider), has Disadvantage. One use for the party, consumed on that test.
- Both are armed from the start by the fixture. They are discarded if Pressure falls below their step, and re-arm only after a crisis resets the track and Pressure reaches the step again.

**Crisis rule.** The core prints no crisis table and none is frozen. The Custodian chooses a dramatic consequence, states it, then records it with `pressure --crisis` and no `--table-result`.

**Assertions:**
1. The frozen step-2 and step-3 rulings are applied as written, each through `--dis-source` on the first fitting test, and the manual ledger matches. They are kept distinct from the engine's automatic step-4 surcharge.
2. A Totem/Feat use at Pressure 4 is priced, before the roll, at **2 Luck**, or **1 Luck and +1 Pressure**.
   - **Command.** A check with `--adv-source Totem`, `--context ability` (which supplies the step-4 Luck) and the base cost alone: `--luck-cost 1` or `--pressure-cost 1`. The surcharge is never also entered as base cost.
   - **The once-per-session limit** is kept in the Custodian's ledger, because the core entry declares no Totem resource. The audit checks it by hand.
   - **If the Pressure option tips the track to 5,** the action is finished first, including its deferred Luck decision, using the starting-step modifiers. Then the crisis is recorded and the track reset.
3. Pressure reaching 5 records a crisis:
   - the target is the tipper, or the character the fiction points to, named;
   - the consequence is stated before the reset;
   - the event shows `table_result: []`;
   - the reset is to 0, with lasting effects recorded and ended with `effect-end` when they end.
4. The time-under-threat charge is announced before the crew commits to the open crossing (revision 9, B) and recorded when the hour ends.
5. After the reset, the next ordinary action is not blocked, and `validate_campaign.py` returns ok.

**End.** The crew reaches the cellar (securing the cases is narrated on arrival, with no test) or turns back. If the Cutters' clock fills first, the contact scene is played to its conclusion and the case ends.
**Cap.** 4 beats or 25 Custodian replies.

### F2b: bring her in (Radiation 5, treatment, Wealth and Attention)

**Purpose.** To test Radiation steps 2–5, collapse and acute treatment, and Wealth at 3. That means paying at tier, a below-tier Luck test and its stated outcomes, and Attention. None of these was reached in P11.

**Table.** The core with Radiation (per character) and Wealth (party), and three salvagers.

**Premise.** Night, at the edge of the Glass, an hour's walk from the Ash Gate.
- One salvager has collapsed from a hot vein: Radiation 5, Stamina 0. She dies by dawn unless acute treatment reaches her inside the Gap.
- A second salvager carried her out: Radiation 3.
- The party has just sold two cases and stands at Wealth 3.
- The Ash Gate's night Warden takes bribes. The honest declaration is slower but still within the night.
- Acute treatment at the Wash is tier 3.

**Fixtures:**
- the first salvager at Radiation 5 and Stamina 0, collapsed (labelled; a prepared collapse, not an observed 4→5 transition);
- the second at Radiation 3 (labelled);
- Wealth 3 (labelled);
- Pressure 0.

**Frozen module policy.** The source is P11's frozen `policies.md` (Radiation and Wealth sections), copied whole into the probe's policy file, with these probe clarifications:
- **Acute treatment** (tier 3, from Sula, inside the Gap) sets Radiation 5 → 3 and Stamina 0 → 1, and cancels the death by dawn. The remaining step-3 effects persist after treatment.
- **Large purchases.** The Gate bribe and acute treatment are both one-off purchases, not service fees. Each lowers Wealth by 1 when paid at or above tier. The Wash and gate duty stay tier-1 service fees.
- **Attention** is judged at Wealth 3 or more *before* the payment that lowers it. A loud bribe at the Gate is a flash. Treatment paid quietly at the Wash is not.
- **Heat** is hidden, with public signs. It has size 4 and starts at 1 on the first flash. A flash while Heat is at 1 adds +1 Heat. A flash while Heat is at 2 or more adds +1 Pressure instead, never both for one flash. Heat's only other advance is +1 at each dawn while Wealth is 3 or more. Flashes alone take Heat no higher than 2, so Heat 4 is unlikely to be reached in this case, but it is frozen anyway: at Heat 4, thieves or Cutters go for the crew's money. The bribe's foreseeable attention risk is stated in public before commitment; the counter and its consequence are not.
- **Radiation** is a per-character clock. Its step effects are not applied by the engine, so each one (Disadvantage, no rest recovery, step-4 Stamina loss) is applied explicitly through the action or state commands and audited.

**Assertions:**
1. The step effects are applied explicitly to the second salvager:
   - Disadvantage on MGT and REF, through `--dis-source`;
   - no Stamina from a short rest;
   - at 4, only if actually crossed in play: 1 Stamina lost on arrival (`play.py stamina`), and Disadvantage on every test except Luck tests.
2. Carrying the collapsed salvager is a test only when failure would matter. Its Disadvantage sources are stated before the roll.
3. Any further exposure that could take someone to 5 is warned of before commitment.
4. Purchases follow the frozen tiers:
   - at or above tier: payable, and a one-off purchase of tier 2 or more lowers Wealth by 1;
   - below tier: a Luck test against current Luck, with the success option (Wealth −1 or a named complication) and the failure's hard cost (Debt +2, +1 Pressure or a dangerous favour) both stated before the roll.
5. Attention follows the frozen policy: it is judged at Wealth 3 or more before payment; Heat starts at 1, then +1 Heat at Heat 1, or +1 Pressure at Heat 2 or more, never both; only signs are public. Whether a purchase counts as flashing is stated before commitment.
6. Acute treatment at tier 3 sets Radiation to 3 and Stamina to 1, the death-by-dawn stake is resolved, and the step-3 effects persist.
7. Wealth never goes below 0, and every change is recorded through the harness.

**End.** The salvager's treatment begins (the strict endpoint), or dawn comes first. Local rulings: no time-under-threat charge (nothing hunts the crew tonight), and a dangerous favour taken as a failed payment test's hard cost is not a separate desperate bargain.
**Cap.** 4 beats or 25 Custodian replies.

**A choice the probe does not force.** Whether the crew bribes the Warden (at tier, with Attention) or declares honestly decides which Wealth branch is reached first. If they pay the bribe, Attention is judged at Wealth 3 (Heat starts at 1), then Wealth falls to 2, so the tier-3 treatment needs a below-tier Luck test. If they declare honestly, treatment is paid at tier and Wealth falls 3 → 2, with no Attention. Either path tests something. The unreached branch is scored "not reached: player choice", never manufactured.

## Records

Records go in `docs/playtests/pilot/probes/F1a/`, `F1b/`, `F1c-1/`, `F1c-2/`, `F2a/` and `F2b/`. Each holds:
- the manifest, with its fixtures and adjustments labelled;
- the transcript;
- an assertion table (correct, wrong, or not reached with its reason);
- the summary.

Raw evidence stays in the ignored `playtests/runs/F*/`. One short report covers each probe (F1, F2).

## Order and cost

The order is F2a first, because it checks the new code path in play, then F1c (two short runs), F1a, F1b and F2b. The caps total 122 Custodian replies; that is a bounded maximum, not an estimate of the actual cost.

**Before each launch** the manifest pins the exact seeds, roster, equipment, spells, NPC statlines, policy text, rules commit, role models and settings, packet hashes and the actual initial state. A live harness failure is reported and preserved under revision 9, never repaired by changing dice or state.

## Questions answered (Astra, board 942)

1. **Orchestrator-written scenarios:** yes, as a labelled probe-only exception to setup step 4, with the other team's contradiction review before the freeze. It applies to both teams' probes.
2. **F1c:** the two pre-declared runs satisfy "no outcome-hunting". They test two starting conditions, not guaranteed outcomes.
3. **Heat:** hidden, with public signs. The bribe's foreseeable attention risk is stated before commitment.
