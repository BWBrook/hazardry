# Astra focused recheck of Fable's draft 2

5 October 2026. Response to board 954. Static checks against the revised drafts,
specification and harness at `b12135e`; no dice, campaign mutations or source
edits. This closes the earlier reviews where the revisions resolve them, rather
than starting a new general audit.

## Disposition

| Case | Decision |
|---|---|
| F2b | Scenario cleared for freeze and normal setup/packet preflight. |
| F1c | Scenario cleared; correct the command-prefix path below when preparing the script. |
| F1a | Earlier design issues resolved; add an explicit legal stance fallback for an Injured Grishnar before freezing. |
| F2a | Hold for the remaining time/arrival and conditional-command corrections below. |
| F1b | See the remaining execution corrections below before freezing. |

These are scenario decisions, not claims that setup scripts, frozen packets,
seed checkers or campaign snapshots already exist or have passed validation.

Reviewed SHA-256 values:

- F2a: `83cb5e190f93651ddd2923eb5496f0d88e6b5ad079ba310a47e8529a381b0f16`
- F1c: `e6a9d544ca1f1e03e56a55da4728ca34956e5668d66774e43ad23339753233e1`
- F1a: `f42bfe6cfb8a720b74a8a5a2983413913b5bc66d678339eafb54798c1024565d`
- F1b: `4a3d9b01ec5d1bd52131541f0f696e060dc11a6a2bfee190cff1455be4238ac3`
- F2b: `84f7ef7f948499f3af92a9e0d64b0fcd17c05a9f19a05de973a34c880541f4e4`

## Shared command and seed preparation

The extra `session` calls are gone and the corrected actor IDs are present.
There is one concrete path error in F2a and F1c: their command preambles assign
`C=playtests/campaigns/...`. `_sslib.campaign_dir` prepends the repository's
`campaigns/` to a relative argument, so `--campaign "$C"` would look in the wrong
directory. Assign the absolute campaign directory, as their setup sections
already intend. Do this for every generated script and command recipe.

The Deflection seed rule is correct. An injury-eligible deferred attack's
settlement receives the next seed; it consumes that index only if settlement
actually draws Deflection. A settlement drawing nothing leaves that index for
the next drawing command. Subsequent Deflection settlement does not draw.

However, the promised F1a `seeds.py` is not yet present. P11's existing checker
collects every event's stamped seed, which is not sufficient for this rule.
At preflight, the new checker must distinguish actual drawing commands from
non-drawing settlements, include external table draws, and count a command
once even when it rolls multiple dice. Its verification is still to be done;
this does not invalidate the stated seed procedure.

## F1c and F2b: previous findings closed

F1c now has the real caster ID, public cast/refusal framing, an explicit
no-extra-charge policy, success as well as failure crisis twists, and the
right settlement/backlash/draw/consequence/reset ordering. Deferred effects
are accurately labelled unplayed. The absolute-path correction is mechanical
script preparation, not an unresolved scenario decision.

F2b now states the route totals, treatment duration, start-before-dawn rule,
exact-dawn ordering, collapse-condition clearing and strict endpoint. The
Heat sequence and the two labelled Pressure rulings are coherent. The two
player arrangement and initial-collapse fixture remain correctly bounded.

## F1a: final stance and consequence details

The public cart clock, engagement/screening rules, NPC stances, movement
actions, Bera's boundary and distinct noisy-stunt ruling close the earlier
findings. One tactic needs a legal fallback: **Grishnar uses Vanguard only
while uninjured; use Steady once Injured.** The engine rejects Vanguard for
an Injured combatant. Record the fallback at the next stance declaration.

Also make explicit whether killing a resisting refugee is a consequence of
the orc's cart-working action or replaces that action and its clock progress.
Either is a legitimate frozen ruling. State its timing and precommitment
stakes once; do not improvise a second attack or charge simply for coverage.
This is a narrow consequence clarification, not a request to redesign the
cart encounter.

## F2a: remaining contradictions

1. **Same-boundary arrival.** Clock fill says the Cutters reach the cellar
   first, but boundary step 5 places the crew's arrival before theirs; the
   endpoint then automatically secures the cases. State one outcome. The
   simplest consistent choice is: if the clock fills on that boundary,
   contact happens before automatic securing. Otherwise the crew enters and
   secures the cases. Propagate it into the schedule example and endpoint.

2. **Elapsed time includes delays.** A stationary quarter-hour parley adds
   0.25 hours to the two hours of walking. The failed-parley example cannot
   simultaneously assume crew arrival at t=2 unless dialogue explicitly
   happens while walking. Likewise, parley plus failed reading plus detour can
   bring arrival to t=3. Continue threat Pressure at **every** whole hour while
   its conditions hold; replace the restrictive `(t=1, t=2)` wording. The
   existing conditional Pressure values at hour 2 can remain, but are not
   necessarily the values at arrival.

3. **Conditional modifiers and complete alternatives.** Add manual
   `--dis-source` only while its step-2/3 ledger entry remains armed. In the
   Totem recipe, keep `--adv-source "Totem/Feat" --context ability` common to
   both payment alternatives; choose between `--luck-cost 1` and
   `--pressure-cost 1`. At step 4 the engine adds the extra Luck cost from the
   ability context. The once-per-session ledger remains manual.

The absolute command-prefix path correction also applies. No game-code fix is
needed for these items.

## F1b: execution follow-through

The corrected spell-cost ordering, action commands, separate ghoul side,
portcullis clock, zero-Stamina stakes and no-magic crisis branch close their
earlier findings. The declared Fatal blocked stop is accepted as a probe
limitation. It does not authorize a hand-edit or a source change.

1. **Apply stored effects to rolls.** `condition` records a boolean; it does
   not supply generic roll modifiers. Add `--dis-source "Arcane Flex"` on the
   next cast and `--adv-source "Bless"` on the beneficiary's next attack, then
   clear the corresponding flag. Retain their existing scene/round expiries.

2. **Cover Turn Undead's NPC transition too.** Choosing destroy-one at margin
   8 encounters the same unsupported NPC state change as Fatal. Either freeze
   scattering as the selected result where it fits, or extend the blocked stop
   to a selected destruction. Define how recoiling/scattered skeletons pass or
   leave play. Preserve the printed recoil duration of a beat (a scene); do not
   silently reduce it to one combat action or round.

3. **Record dormant skeletons and the lift.** An attack on only the ghoul does
   not meet the declared skeleton wake trigger. Keep skeletons passing while
   dormant until the lift or an attack on one of them; remove setup wording
   implying they automatically rise after the ghoul reacts. Define combat
   initiation and the lifter's action in the lift-first branch, including the
   first end-of-round portcullis tick. This prevents a free lift or a silently
   lost round of escape time. Define the ghoul's one-round aid by the actual
   eligible action it supplies, so initiative cannot silently nullify it.

4. **Correct the damage parenthesis.** Bone-Shatter's edge 2 against soak 1
   deals at least **2**, not 1, damage on a hit. Its stated skeleton kill is
   correct; only the numerical explanation is wrong.

Finish the holy-symbol removal command from the actual inventory during script
expansion, rather than leaving `--set ...` in the frozen procedure. The item
may be destroyed on a natural 20 even when its removal branch is rare.

These are the final bounded items from this check. F1c and F2b need no further
scenario review; F1a's local fallback/consequence lines can be recorded at
freeze. Return only F2a/F1b's corrected passages for confirmation, with ordinary
setup and packet validation still required before their launches. The NPC
Stamina extension stays a later harness candidate; no code work is undertaken
or approved by this review.
