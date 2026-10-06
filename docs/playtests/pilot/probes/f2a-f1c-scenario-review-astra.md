# Astra contradiction check: F2a and F1c

5 October 2026. Review of board 949–950 and the two scenario drafts against
protocol 9, the current specification, printed rules and harness at `b12135e`.
No play commands, dice or campaign writes were used. Neither scenario is cleared
for freeze yet; the issues below are bounded corrections to the drafts.

Reviewed source hashes:

- `playtests/runs/F2a/scenario_draft.md`:
  `fa6e5a543c0cde75cb8035a545d9e161882629ab0ae17bd33a9afc7770a767b6`
- `playtests/runs/F1c/scenario_draft.md`:
  `75608831984b5c22a283935e743e22d9573a05cd76cc4342ac6a9386674a9701`

## Common setup correction

Both setup sections call `play.py session` after `campaign_init.py`. A fresh
campaign already has **session 1 open** (`campaign_init.py`, scaffold tracker).
`play.py session` rejects it: “close the current session before beginning
another.” Remove that call and apply the fixtures to the initial open session;
do not add a dummy close or an invented completed session.

Command fragments are acceptable draft shorthand, but the freeze must contain
expanded commands with the campaign, actual actor IDs, stable event IDs,
required arguments and draw seeds. Do not discover missing arguments with a
diagnostic play roll.

## F2a: Cutters on the Ridge

The tableless-crisis path, actor-free shared fixture and Totem surcharge are
sound. These timing and outcome details need resolution before freeze:

1. **One time origin.** The opening says the crew left an hour before dawn and
   the route takes two hours, yet the elapsed count starts at 0 and the first
   hour's midpoint crust field is still ahead. State exactly where `t=0` is,
   how much walking remains, and whether the already elapsed travel was before
   this threat became active. A clean option is two hours *remaining* from the
   opening, but the choice belongs in both public premise and private schedule.

2. **Pressure after an early crisis.** Section 6 gives hour 2 as 0→1 for both
   expected paths. If a Totem tips the track before hour 1, the reset is 0,
   hour 1 then gives 1, and hour 2 gives **2**. If the hour-1 charge itself
   triggers the crisis, hour 2 gives **1**. These are conditional on continuous
   exposure and no other gains. Gunshots, flares, bargains and blunders can
   create other valid paths; withdrawal or genuinely breaking sight can leave
   the crisis unexercised. Do not mark them wrong for missing the two examples.

3. **Tick displacement and ties.** Moving only the first hourly Cutters tick
   from hour 1 to hour 2 puts it on top of the second tick. State whether both
   happen then or the subsequent schedule moves. Under a fixed 1/2/3-hour
   schedule, delaying the first tick alone does not delay arrival at hour 3.
   Also freeze ordering when work completion, Cutters ticks, threat Pressure,
   arrival and a crisis share a time boundary. Never continue a new action
   past a pending crisis merely to maintain the schedule.

4. **Missing durations and stakes.** Give Sal's parley a duration. Give the
   instrument-reading option both its duration and concrete success/failure
   consequences; it presently names a test and modifier but not the failure.
   These determine whether step 2/3 survive until their test or have already
   been discarded by a crisis. Tell the player before commitment that a failed
   parley gives Sal actionable information, if that is automatic. Show its
   implications without disclosing the hidden counter/timetable.

5. **Align two local policies with the specification.** The scenario's step 3
   covers a rival boss's **agent**; the specification covers an official or
   rival **boss**. Explicitly include Sal's role in both. Likewise choose the
   endpoint: the specification stops at reaching the cellar, whereas the
   scenario waits until the cases are secured or contact concludes. Keep one
   definition and corresponding cap/coverage criteria.

The Totem flags can also be added to the **opposed** parley; they do not turn
it into an unopposed `check`. Freeze the final roster, names/IDs, loadouts,
drives/temperaments and NPC records before generating role packets.

## F1c: Seal the Barrow

Wenna's off-casting Expertise is a legitimate pre-draw fixture choice. LOR 12
costs 4 points and FTH 11 costs 2; the printed free Knack and Expertise leave
the standard six-point budget intact. The two cases still test starting
conditions, not guaranteed success/failure outcomes. Keep the same caster in
both and retain every predetermined run regardless of the first result.

1. **Actor ID is wrong in the action and crisis recipes.** Building `Wenna
   Ashby` without an explicit alternative filename creates **`wenna_ashby`**.
   `_runtime.actor_key` accepts an exact stem or full name, not the first name
   `wenna`; a crisis target must be the stored ID. Use `wenna_ashby` consistently
   for `--character` and `--target`, or explicitly create the intended ID.

2. **Face 5 applies on a successful threshold cast too.** It is currently
   nested under “Backlash, on failure only.” Move it into the common crisis
   procedure. A successful run-1 Arcanum still used magic, still causes a
   crisis, and face 5 still twists it. A failed cast additionally gets its
   chosen backlash, separate from any table twist. All rolled face effects
   must be stated/recorded before the atomic crisis reset. A robust order is:
   settle cast; if failed, record the chosen backlash; expand the crisis draw
   tree if due; adjudicate its faces; record target/effects and reset once.
   A blocked table expansion must not erase an already due failure backlash.

3. **Alternative approaches versus automatic gate opening.** The public text
   permits another approach, but the private truth says any non-cast makes the
   gate open. Distinguish refusal without an effective alternative from a
   genuinely effective alternate method. Either make this a declared one-cast
   or refusal fixture, or honour adjudicated alternatives and score the Arcanum
   not reached. Do not advertise an alternative whose result is privately
   prohibited regardless of method.

4. **Freeze the one-minute and core-trigger dispositions.** State the cast's
   fictional duration, what delays wake the sleeper, and how information/Luck
   discussion is separated from fictional time. The expected run-2 success at
   Fatigue 3 assumes no additional core charge. State whether risky ritual,
   big-blunder and time-under-threat labels describe this same priced act or
   genuinely separate events, and how they are treated under the frozen policy.
   If extra charges are possible, make the matrix conditional and announce
   independent foreseeable costs. This need not add a new rule; it must remove
   a silent assumption about which events occur.

5. **Persist exact consequences at the endpoint.** Face 1 loses the next
   eligible action, even if that occurs in another scene; an effect that merely
   expires at the next scene boundary would not implement it. Record drop and
   duration precisely. A generic `condition` records a backlash flag but does
   not automatically apply its next-cast Disadvantage, extinguish lights or
   suppress recovery: state the selected mechanical effect and expiry, with
   actual state changes where needed. Deferred consequences can remain unplayed
   at this short case's endpoint; do not claim their later application tested.

The atomic `--pressure-cost 2 --no-nudge --defer` cast, post-settlement crisis
and below-threshold `--forced` distinction are otherwise consistent. Run 2
success stays at 3 without reset under its stated isolated-cast conditions.

## Specification and our final tidy-ups

Fable's recursion correction is present: depth-first expansion and a blocked
stop whenever any required descendant remains at four draws. Heat's dawn
advance at Wealth 3+ is also explicit. These close the previous review points.

Board 949's remaining points in our three plans are now settled: M0 uses one
exclusive outcome label, records the post-jam loss of the dry alternative,
has its own catch text and explicit generator `--seed`; Briar prices a forced
door as separate noisy heroics and defines open versus concealed or permitted
writ inquiry; Free Traders marks recipes as shorthand, fixes Knack/Watch
wording, excludes broad sample-crew text from narrow packets and uses one
explicit fresh-build route for the P8-derived fixture.

No source change is requested. Return the corrected scenario drafts for a
focused check of these items before freeze; full packet/state validation still
belongs to preflight.
