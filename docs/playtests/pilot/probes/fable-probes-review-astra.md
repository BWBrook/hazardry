# Astra review of Fable's probe specification

4 October 2026. Reviewed `fable-probes.md` and board message 941 against the
current rules/harness at `b12135e` and P11's retained module policy. Read-only
review: no probes, dice or campaign changes. The split and proposed order are
sound, subject to the corrections below before scenario freeze.

## Answers to the three questions

1. **Yes to orchestrator-authored probe scenarios.** Label this as a probe-only
   replacement for protocol setup item 4's Custodian authorship (item 5 checks
   and freezes it). It permits controlled fixtures and matched cases. Freeze
   public information, hidden facts, triggers, interpretations and caps before
   the roles begin; the Custodian may clarify ambiguities before freeze but
   cannot quietly rewrite the experiment. Astra reviews Fable's scenarios;
   Fable reviews Astra's. Keep expected-answer/audit matrices out of role
   packets while giving roles every rule and policy needed to adjudicate.

2. **Yes, the two predeclared Arcanum cases satisfy no outcome-hunting.** Both
   must run regardless of their results. They test two *starting conditions*,
   not guaranteed success and failure branches. Run 1 guarantees a crisis; run
   2 tests a forced crisis only if the cast fails. The spec already recognises
   this in assertion 6; revise the purpose's “both branches” accordingly. Mark
   unobserved failure/backlash paths not reached. No replacement seed, extra
   cast or selective rerun follows from an uninformative result.

3. **Hidden Heat, with public signs, is appropriate.** Freeze its size, ticks,
   threshold and fill consequence privately. Publicly explain that the bribe
   attracts attention and the material foreseeable stakes before commitment;
   do not reveal a private counter or enforcement timetable. The player packet
   includes the general Attention rules. Summaries repeat only observed signs
   and attributed statements, never secret forecasts. Use the exact frozen
   Attention policy clarified below.

The Twilight correction is correct: the optional Injury/Deflection module is
in `skins/twilight_of_the_northlands.md` and `_play.begin_action` rejects Injury
outside Twilight. Keep Candlelight's spellcraft and combat as separate cases.

## Corrections needed before freeze

### Core steps and Totem/Feat (F2a)

Core steps 2 and 3 are `kind: custodian` in `manifest.yaml`; gaining Pressure 4
does **not** arm automatic one-test penalties. `_pressure.change` arms entries
of kind `next_disadvantage`, which these are not. Define any chosen one-use
interpretations as explicit frozen Custodian policies: affected characters,
tests, duration and consumption. Apply relevant `--dis-source` entries and
retain their manual ledger. Rewrite the fixture/assertion to distinguish those
rulings from the engine's automatic step-4 surcharge.

The Totem recipe must declare its Advantage with `--adv-source`, not just pay
for it. At starting Pressure 4 its total price is **2 Luck**, or **1 Luck plus
1 Pressure**. `--context ability` supplies the additional Luck cost; do not
also enter that surcharge as base cost. Its once-per-session use remains an
explicitly manual ledger. If the Pressure option reaches 5, finish the action
and its deferred Luck decision, then record the crisis and reset. Preserve the
starting-step modifiers (Almanac 4).

### Arcanum cost ordering and combat actions (F1)

Make F1c's +2 part of the **casting action**, through `check --pressure-cost 2
--no-nudge --defer`, with the remaining actor/attribute/stakes arguments. Do not
first issue a standalone Pressure gain that reaches 5: a pending crisis would
block the new casting action. The action snapshots starting penalties, pays
its cost and draws. Settle it, then resolve one crisis if due; no second +2.

For F1b, spell and Turn Undead checks in combat must consume the acting
combatant's turn (`--combat-action`); attacks already do so. Keep Backstab's
eligibility/immunities and the named spells' exact effects in the frozen
scenario/packets. F1a's step-4 Disadvantage also affects Deflection, although
Deflection pays no toll; use the attack's starting Pressure snapshot. Score
unreached Injury/second-Injury and unchosen spell/Knack paths honestly.

For all table cases, freeze recursive-six expansion order and whether draws
are single-face commands or batches. Count commands that actually draw,
including an attack settlement that draws Deflection, in the seed schedule.
Specify a bounded recursion stop retaining an unresolved crisis, rather than
choosing a face when the cap is reached.

### Radiation and treatment (F2b)

P11's frozen `playtests/runs/P11/policies.md` specifies acute treatment as
Radiation **5→3 and Stamina 0→1**, as well as cancelling the dawn death deadline.
Add the Stamina restoration to assertion 6. Persist any remaining step-3
effects after treatment.

Radiation is represented by a per-character clock; its policy effects are not
automatically supplied by that clock. Apply and audit Disadvantage, prevented
rest recovery and threshold damage explicitly through the appropriate action
or state commands. A fixture already at 5 and 0 Stamina demonstrates a prepared
collapse, not an observed 4→5 collapse transition. Likewise distinguish the
fixture's pre-applied step-4 damage from a later actual crossing of step 4.

### Wealth and Attention policy fidelity (F2b)

The retained P11 policy is more precise than “once trouble has gathered”:
Heat has size **4**, starts at **1** on the first qualifying flash, and the
Pressure alternative applies when Heat is already **2+**; do not apply both
for one flash. Freeze how Heat subsequently advances. Assess whether the bribe
qualifies at Wealth **3 before payment**, rather than testing Attention after
the expenditure has reduced Wealth to 2.

P11's policy also exempts service fees from its large-purchase Wealth reduction;
the shorter public account does not state that exception. Identify the exact
source being frozen and settle whether the Gate bribe and acute treatment
count as reducing purchases. To retain the proposed below-tier branch, the
bribe must reduce Wealth 3→2. The policy must say what paying for treatment at
tier does to Wealth; do not silently resolve that distinction after a choice.
These are local module-policy decisions, not revisions to the core rules.

## Freeze and assessment

The draft intentionally leaves exact seeds, rosters, equipment, NPC stats,
spells and policy text to the scenario stage. Pin those, the rules commit,
role model/settings, packet hashes and actual initial state before launch.
Preserve the protocol's access boundaries and exact relay/checkpoint evidence.
The proposed order F2a, F1c, F1a, F1b, F2b is sensible after the above corrections
and scenario contradiction review. Six cases with caps totalling 122 Custodian
replies are a bounded maximum, not evidence that the work costs one P11 run.

No engine change is requested by this review. These are specification and
application corrections. A subsequent live harness failure is reported and
preserved under revision 9 rather than repaired by changing dice or state.
