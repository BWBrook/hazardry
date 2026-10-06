# Astra contradiction check: F1a, F1b and F2b

5 October 2026. Review of board 951 against protocol 9, Fable's specification,
the printed skins and harness at `b12135e`. This complements
[`f2a-f1c-scenario-review-astra.md`](f2a-f1c-scenario-review-astra.md).
No play commands, dice or campaign writes were used. These three drafts also
need bounded corrections before freeze.

Reviewed source hashes:

- `playtests/runs/F1a/scenario_draft.md`:
  `65d0d16dbfd8dbe0cb55d2e4cc84d35859455012eddb0c8af522592cbe52eac1`
- `playtests/runs/F1b/scenario_draft.md`:
  `d15f36851d929f80e6ce76be3a42da031162b70b6bb456461d391426f704df54`
- `playtests/runs/F2b/scenario_draft.md`:
  `494bb7669b032c908f75e175c4c62c69f139207219603bf63dd88e88f3c7879f`

## Shared setup and preflight

All three repeat the `play.py session` error identified in the first review:
`campaign_init.py` already opens session 1. Remove the extra session command;
apply fixtures to that initial open session. Expand command shorthand before
freeze, including actual generated character IDs, `npc:` prefixes for opponents,
campaign paths, event IDs, resource keys, sources and required arguments.

F1a and F1b need their active threat's advancement, completion and interruption
rules made explicit. The eight-round run cap is an administrative stop, not a
fictional threat clock. An opposition-move clock is sufficient; an extra hazard
is unnecessary. If the intended combat probe needs an exception, declare it
explicitly in the specification and scenario. The agreed exception currently
changes scenario authorship, not all of setup step 4. F2b already has the dawn
deadline, but needs the timing clarifications below.

## F1a: The Greyford

The high-Dread fixture, toll exemption for defence/Deflection, and use of
**action-start** Dread for modifiers agree with the harness. Preserve those.

1. **Freeze the cart's danger in actionable terms.** Say which opposition moves
   reach or seize the cart, what takes an action, what advances the threat, and
   what stops or delays it. Define when refugees resist and when Grishnar's
   conditional killing can occur. This determines the goal stakes and the
   true-evil trigger; neither should be invented to obtain Dread coverage.

2. **Record positions and movement, not only their prose labels.** Combat starts
   with every combatant Steady. If the orc archer receives the Ranged stance,
   declare it through `positions` each round alongside the other stances.
   Freeze who can screen a Ranged companion, when crossing changes engagement,
   and use `pass` for a combatant's movement-only action. An attack or opposed
   test already consumes its actor's turn. A rolled check consumes it only with
   `--combat-action`.

3. **Finish the NPC records and trigger boundaries.** Bera is named and needs
   the protocol's want, manner and line; generic raiders may share a group
   description. The declared NPC HOP values must either populate their Luck
   pools with `--luck` or be marked unused; recording an attribute column alone
   does not set the pool used by a HOP test. NPCs can retain the stated no-Hope-
   spending policy. Clarify whether a distinct horn, fire or noisy stunt can
   add Dread despite excluding ordinary combat noise.

Use target armour for `--soak`, attacking weapon for `--edge`, and preserve the
full deferred attack/Deflection settlement before resolving any due crisis.
Unreached Injury or crisis paths remain coverage results, not failed play.

## F1b: The Reliquary of Saint Orm

1. **`attack --combat-action` is invalid.** The CLI accepts that flag only on
   `check`. Attacks and opposed tests already consume the combatant's action.
   Remove it from spell attacks and correct specification assertion 7 to say
   spells consume an action by the appropriate command. Keep it on Bless and
   Turn Undead checks. Wick-light has no test, so record its combat turn with
   `pass`; do not invent a roll just to consume the action.

2. **The proposed spell-cost correction changes printed timing and choice.**
   The skin says test, then pay the tier cost. `--pressure-cost` pays before
   the dice, while `--success-luck-cost` reserves a coin before the roll and
   pays it only on success. The engine deliberately snapshots modifiers before
   upfront costs, so this is **not** a claim that the current cast wrongly
   receives the newly crossed step's modifier. Nevertheless, an early charge
   and a fixed pre-roll payment choice are not required by the printed rule.
   A Spell's reserve also prevents using that coin to nudge and then choosing
   Fatigue for the success payment.

   The existing commands can preserve post-roll pricing without a source edit:
   - Spell: `--failure-pressure 1 --defer`; make the affordable success payment
     choice with the informed nudge decision, settle, and on success record
     either `luck --amount -1` or `pressure --gain 1`.
   - Greater Spell: `--success-luck-cost 1 --failure-pressure 2 --defer`; retain
     the mandatory success-coin reserve, settle, and only on success record
     `pressure --gain 1`.

   These are fragments requiring actors, sources and other ordinary arguments.
   Finish every cost of the resolved cast before recording a crisis/reset;
   start no intervening action. The harness permits cost mutations while a
   crisis is pending after settlement. Keep Knack activation and the step-4
   toll separate from tier costs. Arcane Flex waives Force Bolt's tier cost,
   not its own Knack activation. Revise the plan and scenario together rather
   than describing a harness limitation as a rule change.

3. **Fatal Backstab exposes a real harness gap.** A successful undefended
   edge-2 hit can leave the five-Stamina ghoul alive, whereas Fatal must take
   it to zero. `stamina` and `condition` currently target character sheets,
   not NPCs; `npc` cannot update an existing record. Provide a supported NPC
   transition before claiming this branch runnable, or freeze a blocked stop
   if the branch occurs. Do not edit the tracker by hand, inflate weapon edge,
   or report ordinary damage as Fatal. Bone-Shatter can use an edge-2 attack:
   even its minimum successful damage kills the two-Stamina, soak-1 skeleton;
   freeze who chooses its STR/DEX defence.

4. **Finish Knack and effect recipes.** Arcane Flex's attack needs its resource
   use and chosen activation cost, with no spell-tier cost. Record next-cast
   Disadvantage and clear it after use or scene end even if Expertise cancels
   it. Turn Undead needs its activation, additional failure Fatigue and the
   holy-symbol destruction on a natural 20 recorded. Bless needs its recipient
   and expiry after the next attack or at round end. Backstab needs its resource
   use and activation cost on the attack.

5. **Freeze the ghoul's combat participation and approach.** Combat membership
   is fixed at `combat-start`, but the ghoul may remain neutral, help the party
   for one round or join the skeletons. Declare its side, initiative and pass
   procedure in advance; a separate side can preserve its independent targeting
   without silently changing the combat roster. If the unseen DEX approach is
   in active combat, it consumes an action and cannot be followed by Backstab
   in the same round. Distinguish a pre-combat approach, and state failure's
   detection/response stakes. Freeze what zero Stamina means for these delvers;
   the grave-wound Fatigue charge alone does not supply that consequence.

6. **Align activation and crisis branches.** The specification says skeletons
   wake when the reliquary is touched; the scenario says lifted. Choose one and
   disclose it consistently. Face 5 must retain its printed no-magic branch
   (a late trap) if no magic has been used: Knacks and the step-4 toll can
   reach a crisis without a spell. Freeze an applicable consequence rather
   than assuming the caster supplied the Fatigue. Apply the common depth-first
   draw cap and all consequences before the single reset.

The initial Fatigue-2 penalty can be consumed by a qualifying **defence** test
as well as a chosen approach or attack. Advantage cancelling it does not leave
it armed. The engine supplies step-3 incoming Advantage; the local grave-wound
charge still needs an explicit Pressure event when a delver reaches zero.

## F2b: Bring Her In

The Wealth-3 bribe is judged for Attention before it lowers Wealth to 2;
subsequent below-tier treatment is a valid consequence. Quiet treatment at
tier on the honest route is also consistent. Preserve the explicit promise
that the below-tier test changes the price, not whether treatment happens.

1. **Correct travel totals and define the deadline event.** A successful fast
   normal-road crossing takes **3.5 hours honest / 1.5 hours bribed** to reach
   the Wash. Slow travel or the failed fast crossing takes **4 / 2 hours**.
   The shortcut saves another half hour on the applicable route. The statement
   that both work unless more than one hour is lost conflates different
   margins. Give treatment a duration, say whether starting or finishing it
   lifts the deadline, and decide the order at exactly dawn. Propagate those
   choices into the public stakes and path table.

2. **Clear the collapse condition as part of treatment.** Lowering the Radiation
   clock 5→3 and raising Stamina 0→1 do not clear the separately recorded
   `Collapsed (Radiation 5)` flag. Add `condition --clear` for that exact name,
   retain Radiation-3 effects, and record that the deadline is lifted. The
   two-player arrangement is suitable if treatment is the strict endpoint:
   do not continue with an unplayed Tamsin or retain an unsupported claim of
   unconsciousness after recovery.

3. **Fix the second-flash claim.** Under the declared policy, the first
   qualifying flash creates Heat 1; the second takes it to 2. A subsequent
   qualifying flash at Heat 2+ adds Pressure, and each still requires Wealth
   3+. Section 6's “second flash (+1 Pressure)” is wrong. Ordinary bribe then
   quiet treatment does not exercise those later branches.

4. **Resolve two Pressure interpretations.** “The dawn deadline is the clock”
   alone does not explain excluding time under threat: protocol 9 allows a
   clock and Pressure to advance together. Give a fictional applicability
   ruling, or explicitly label the exclusion as a probe override. Also state
   whether accepting Redd's dangerous favour is a desperate bargain under
   the declared trigger list; if so, disclose the additional consequence
   before commitment. Do not turn an already priced failure into an unstated
   duplicate charge.

Joss's 3→4 transition remains optional and warned; Tamsin's initial collapse
remains a fixture, not observed coverage. A deferred or unreached module effect
must stay labelled as such.

## Disposition

The five scenario reviews are now complete. None is cleared by these draft
reviews yet. Fable can make the listed corrections and return the changed
items for a focused check, then perform the already planned packet/state
preflight. No game-source change was made. The NPC Fatal gap requires either
a supported implementation or the declared blocked branch; the other findings
can be addressed in scenario/procedure text. No additional probe run or
outcome-hunting draw is needed for this review.
