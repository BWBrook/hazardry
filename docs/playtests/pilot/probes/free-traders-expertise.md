# Probe plan: Free Traders narrow specialties

**Status:** draft for Fable review. Do not freeze or run from this document until
the variant wording, fixtures and assertions below have been approved. This is a
labelled protocol-revision-9 probe, not an ordinary session or balance study.

## Question and scope

Compare the proposed ordinary narrow specialty with Free Traders' current broad
Expertise at **matched consequential tests**. The target is the modifier and
choice surface produced by the rule:

- whether table roles correctly apply each prescribed plain/Advantage modifier;
- whether another source of Advantage is unique or redundant;
- which Fate nudges and Knack choices become legally meaningful; and
- whether broad crew roles still resolve routine work without manufacturing
  tests.

The probe does not estimate success, Strain or crisis rates in normal play. P8
selected the crew and test domains, but P8 itself is not a control: its protocol,
fiction, actor selection, scene structure and advancement differ. No causal
comparison may use P8's observed seven rolls against these cases.

This probe does **not** empirically test Custodian judgment about specialty fit.
Fit and non-fit are prescribed case inputs so the probe can isolate modifier
application and the choices that follow. Boundary wording, inconsistent fit
judgments and natural free-play selection belong to a later adjudication or
ordinary-play study.

Sources to pin at freeze are `docs/playtests/pilot-protocol.md` revision 9,
`rules/core/adventurers_manual.md` section 2.6,
`skins/free_traders_of_the_drift_marches.md`, and `manifest.yaml`. The design
implements the direction recorded in `docs/playtests/pilot/review-4.md`:125-131.

## Variants

Only the free specialty differs. Both variants keep the standard six-point
creation ledger, one free prior-service Knack, one free specialty/tag, the same
attributes, gear, roles, drives and temperaments, and all other Free Traders
rules.

### B — broad Expertise comparator

Use the current skin text and P8 scopes:

- Kest Vale: **Pilot (DEX)**;
- Rook Fen: **Engineer (EDU)**;
- Mira Quill: **Liaison (SOC)**.

These remain specialties rather than blanket coverage of their attributes, but
are interpreted with the skin's present broad-Expertise rule.

### N — proposed narrow specialty

For N player packets, replace the skin's creation grant and Expertise paragraphs
in place; do not append text that leaves the broad paragraph visible. Omit the
skin's printed sample-crew section entirely, because its broad Pilot and other
Expertise snippets would contradict the variant and the players already receive
their own roster. Freeze this replacement:

> Each PC receives one prior-service Knack and one ordinary narrow tag free at
> creation. Fix the tag's scope at creation. Crew roles are broad descriptions of
> competence: routine role work needs no test. A consequential role test uses the
> plain attribute unless the narrow tag, preparation or a Knack whose printed
> activation cost is paid fits the actual method. The Knack itself remains free
> at creation. Advantage sources never stack.

Use the agreed example scopes:

- Kest Vale: **Precision docking (DEX)**;
- Rook Fen: **Jury-rigging damaged machinery (EDU)**;
- Mira Quill: **Customs law (SOC)**.

This override is confined to the probe packets and fixtures. Do not edit the
canonical skin or manifest for the probe. The character record must identify the
narrow item as a free ordinary tag. The schema accepts only `knack` and
`expertise` as free-tag grant keys, so store each narrow tag as
`grant: expertise` strictly for schema compatibility while its `name` is the
exact narrow scope above. N sheets and packets must never describe that tag as
broad Expertise. Freeze this compatibility representation and the replacement
skin paragraph for Fable's approval. Character generation therefore uses
`--free-tag "expertise=<exact narrow tag>"` for this one schema slot.

## Matched starting fixture

Create fresh characters inside every subcase with `char_builder.py --campaign`;
do not copy a played P8 sheet and do not use random generation. Recreate this
fixed, pre-advancement table at standard six-point tone:

| PC | STR | DEX | EDU | SOC | FAT | STM | Knack | Crew role |
|---|---:|---:|---:|---:|---:|---:|---|---|
| Kest | 10 | 10 | 13 | 10 | 10 | 5 | Scout Surveyor | Astrogator and pilot |
| Rook | 10 | 10 | 10 | 11 | 11 | 6 | Salvage Rat | Engineer and EVA specialist |
| Mira | 10 | 10 | 10 | 13 | 10 | 5 | Merchant Broker | Broker and watch officer |

The repeated free-tag arguments are fixed exactly:

- Kest B: `--free-tag "knack=Scout Surveyor" --free-tag "expertise=Pilot (DEX)"`; Kest N replaces only the second with `--free-tag "expertise=Precision docking (DEX)"`.
- Rook B: `--free-tag "knack=Salvage Rat" --free-tag "expertise=Engineer (EDU)"`; Rook N replaces only the second with `--free-tag "expertise=Jury-rigging damaged machinery (EDU)"`.
- Mira B: `--free-tag "knack=Merchant Broker" --free-tag "expertise=Liaison (SOC)"`; Mira N replaces only the second with `--free-tag "expertise=Customs law (SOC)"`.

For each row, pass all five displayed attributes and STM explicitly with `--set`,
use `--tone standard --strict`, and pass its Knack plus the B or N specialty with
the exact `--free-tag` strings. Add the frozen role, drive, temperament and
inventory with `--note`/`update_sheet.py` from the setup manifest; do not import
sheet YAML. `playtests/runs/P8/roster_setup.json` and the P8 initial sheets are
read-only provenance for the fixed stats and loadout, not campaign-state inputs.
Do not copy P8 generation metadata, advancement, conditions, resource uses,
notes about broad Expertise, logs or outcomes. Freeze the full expanded builder
arguments and compare the recreated B/N fields before any case action.

Fate starts full, Strain and all public ship clocks start at 0, Ship Shares at 2,
and every Knack starts unused. No milestone is active or awarded; advancement,
combat, Injury, Wealth and quick ship combat are inactive. Required ordinary
tools make an action possible but do not add a second Advantage source unless a
case explicitly says preparation does so.

Crew-role labels never grant Advantage automatically. They establish routine
competence and fictional authority only. C8's Watch Advantage is the prepared
benefit of a previously successful Watch-officer test; it is not granted merely
because Mira carries the Watch-officer role label.

Replace P8's old Expertise note in N with the corresponding exact line below;
keep the role, drive, temperament, Knack and all inventory notes unchanged:

- Kest: `Free specialty: Precision docking (DEX). Advantage only when the exact narrow task fits; stored as grant: expertise for schema compatibility.`
- Rook: `Free specialty: Jury-rigging damaged machinery (EDU). Advantage only when the exact narrow task fits; stored as grant: expertise for schema compatibility.`
- Mira: `Free specialty: Customs law (SOC). Advantage only when the exact narrow task fits; stored as grant: expertise for schema compatibility.`

For every case, B and N receive byte-identical public fiction, actor, method,
attribute, stakes and starting state. Only the variant rule/tag and its
variant-specific prescribed-modifier instruction differ. The action is committed
before the roll, so actor routing and alternative methods cannot change the
comparison. Each case is independent; never carry an outcome, spent Fate,
benefit or fictional fact into another case.

### Prescribed and free elements

This is a scripted modifier-application probe. The case fixes the actor, intent,
method, attribute, stakes, starting state and whether B and N are plain or have
Advantage. The player remains free only to accept or decline an offered Knack and
to make legal post-roll Fate or Merchant Broker decisions. The Custodian applies
the one prescribed modifier for its case and remains responsible for offering
every legal choice; it does not adjudicate specialty fit.

The full matrix and assertions are auditor-only. They live in this plan and the
auditor manifest, neither of which is a packet-builder input. Each role packet is
built from a distinct, variant-specific case source containing only that role's
fiction, prescribed modifier and applicable local rulings. Freeze and hash those
sources separately; no table role receives the paired result or matrix.

This control is what makes the tests matched. It also limits inference: the
probe cannot show how often players would choose these methods, route work to a
specialist, avoid danger, enjoy the rule, or generate Strain in free play. Those
questions require a later ordinary run after any rule adoption.

## Cases and prespecified rulings

`B` and `N` in the Prescribed modifier column state whether that variant rolls
with Advantage (`A`) or plain (`P`). Correct application of these inputs, not a
desired die outcome or an observed fit judgment, is the primary endpoint.

| ID | Frozen consequential action and stakes | Prescribed modifier | Procedure exercised |
|---|---|---|---|
| C0 | Three safe tasks: Kest plots a routine charted leg, Rook performs scheduled coolant inspection with access and time, Mira files an ordinary declared cargo form. | no roll in B or N | Negative control: crew roles retain routine competence. |
| C1 | Kest makes a precision thruster docking at a tumbling berth, DEX 10; failure loses the berth window and ticks Hull +1. | B=A, N=A | Exact narrow fit retains Advantage. |
| C2 | Kest flies a controlled evasive line through moving debris, DEX 10; failure ticks Hull +1 and leaves the patrol in pursuit. It is piloting, not docking. | B=A, N=P | Broad adjacent role work loses automatic Advantage. |
| C3 | Rook jury-rigs a cracked coolant manifold from available scrap before it ruptures, EDU 10; failure ticks Hull +1 and forces shutdown. The normal kit is required access, not a separate bonus. | B=A, N=A | Exact narrow fit retains Advantage. |
| C4 | Rook interprets an intact drive's conflicting sensor telemetry under a departure deadline, EDU 10; failure loses the launch slot and delays departure. Nothing is damaged or being jury-rigged. | B=A, N=P | Broad engineering diagnosis loses automatic Advantage. |
| C5 | Mira cites a specific customs provision to stop an unlawful cargo impound, SOC 13; failure impounds the stake for this port call. | B=A, N=A | Exact narrow fit retains Advantage. |
| C6 | Mira settles the already-completed delivery of one registered refrigerated-medicine lot to Sela Orin's clinic, SOC 13. This is one concrete, unpaid trade stake. Success consumes it and gains +1 Ship Share. Failure consumes it, gains no Share and marks +1 Strain. A natural 20 consumes it with no Share, marks +1 Strain, ticks Debt +1 and draws an audit complication. No customs question or Watch benefit applies; Merchant Broker is ready. | B=A, N=P | Broad liaison/trade coverage, Fate surface and Broker reroll. |
| C7 | Kest plots uncertain astrogation through a debris-swept jump window, EDU 13. Every completed jump ticks Fuel +1; a natural-20 misjump ticks Fuel +2 **instead**, arrives somewhere wrong and marks the role's one failure Strain. Any other failure marks that same +1 Strain once. Do not duplicate it as a generic big-blunder charge. Scout Surveyor is unused and must be offered at its printed Fate-or-Strain cost before commitment. | B=P unless Knack activated, N=P unless Knack activated | The free Knack remains available; its activation cost must be paid, and it is the only possible Advantage source. |
| C8 | Mira settles one completed, unpaid private freight job carrying certified incubators to Mercy Reach, SOC 13. This is one concrete trade stake. Success consumes it and gains +1 Ship Share. Failure consumes it, gains no Share and marks +1 Strain. A natural 20 consumes it with no Share, marks +1 Strain, ticks Debt +1 and draws an audit complication. No customs issue applies; Merchant Broker is ready. A labelled prepared fixture gives the party its previously earned Watch benefit on this encounter's first test. | B=A from Liaison + Watch, N=A from Watch only | Non-stacking and whether Watch changes the dice rather than duplicating Expertise. |
| C9 | In explicit zero-G, Rook crosses a non-rotating exterior truss to secure a loose case, DEX 10; failure costs 1 STM and loses the case. Salvage Rat is unused and must be offered at its printed Fate-or-Strain cost. Because there is no gravity, its additional +1 Strain gravity cost does not apply. Neither specialty fits. | B=P unless Knack used, N=P unless Knack used | Free Knack remains available as a costly automatic success. |

Do not add preparatory actions, helpful companions or gear bonuses to C1-C9.
Those would change the estimand. The player may accept or decline an explicitly
listed Knack and may make legal post-roll Fate choices; record the choice rather
than steering it.

C1-C5 are isolated shipboard actions, not jump-leg role tests. The jump role
table therefore does not supply their consequences: in particular, C3's failure
is only its frozen Hull +1 and shutdown, not the Engineer row's Strain +1 plus
Hull +1. Salvage Rat is not offered in C3 because repairing a manifold is not a
manoeuvre. These dispositions are part of the prescribed fixture.

The exact-match positives C1, C3 and C5 and explicit non-fits C2, C4 and C6 do
not exercise a specialty's ambiguous scope boundary. C6's classification of
Liaison as fitting trade settlement in B is prescribed locally despite being the
most contestable classification; it is not evidence that another Custodian would
make the same fit judgment.

### Frozen local rulings and Pressure map

The following are labelled fixture rulings for C6 and C8 rather than claims about
unambiguous printed rules:

- the named port-call trade is an encounter and its trade check is that
  encounter's first test;
- ordinary trade failure takes the skin's Strain option, not Debt;
- failure consumes the named one-use stake as well as success; and
- Watch applies to the whole first trade test, including Merchant Broker's
  printed reroll; that reroll is the same test, retains the original modifier
  sources and does not become a new encounter test.

Fable accepted the final ruling as the natural local reading. Freeze all four in
both relevant Custodian packets and report the Watch/encounter/reroll ambiguity
as a Stage 3 rules-text gap; a successful probe does not silently adopt this
wording as a general rule.

C8's Watch benefit is a prepared setup change, not the result of an invented
prior roll. Before either C8 role launches, use `play.py condition` with
`--character mira_quill` to set
`watch_early_warning_party_first_test_next_encounter`; do not write the sheet
directly. The command form is `play.py --character mira_quill condition ...`.
Identify it as a labelled prepared fixture and freeze its
receipt plus the before/after snapshot hashes. Pass the benefit explicitly as
`--adv-source "Watch officer early warning (prepared C8 fixture)"`; the condition
does not add a die automatically. Once the primary result and any Broker reroll
are complete, clear it through `play.py --character mira_quill condition --clear`.
The final sheet keeps the condition key with value `false`, so that expected
difference from the baseline must remain in the retained snapshot. No other case
starts with a Watch benefit.

Core Pressure remains additive outside these frozen case dispositions. Each
subcase opens immediately before its one action and ends after settlement:

| Almanac 4 trigger | Frozen disposition for C0-C9 |
|---|---|
| Desperate bargains | Absent. No action buys fictional permission or advantage through a bargain. |
| Taboo acts | Absent. None of the prescribed methods violates a stated taboo. |
| Noisy heroics | Absent. C2 is a controlled piloting line; none of the other methods creates a separate noisy display. |
| Risky rituals | Absent. No case contains a ritual. |
| Big blunders | A natural 20 is not automatically an extra core gain in this probe. The frozen case consequences are exhaustive; C6-C8 use their stated skin/fixture consequences. This is a labelled fixture ruling, including C7's single failure Strain rather than a duplicate big-blunder gain. |
| Time passing under threat | Absent. No subcase action consumes a stated time threshold. C2's pursuit, C3's impending rupture and C4's departure deadline define stakes, not elapsed intervals. |

C6 and C8 therefore have one final-result failure Strain consequence, and C7
has one jump-failure Strain consequence. C1-C5 and C9 have none. A
player-chosen +1 Strain Knack or Broker payment remains a separate additive
cost. If a role identifies a fact that contradicts this frozen map, stop before
the draw and preserve the discrepancy. That stop is a probe-local override of
ordinary play's charge-or-explain procedure, used only to keep the matched input
intact; do not generalise it to play.

## Dice matching and execution

Run each ID as two fresh bounded subcases, one B and one N, using fresh Custodian
and relevant player sessions with the same model and settings. No role session
may inherit P8, another case or the other variant's history. Use
scenario-identical case packets: public fiction, committed action and starting
resources are the same, while each role can see its actual B or N rule and
character tag. Use the same case master seed in both variants:

| Case | Master seed | First gameplay seed | Broker reroll seed |
|---|---:|---:|---:|
| C0 | 81410 | 81410001 reserved; zero draws expected | — |
| C1 | 81411 | 81411001 | — |
| C2 | 81412 | 81412001 | — |
| C3 | 81413 | 81413001 | — |
| C4 | 81414 | 81414001 | — |
| C5 | 81415 | 81415001 | — |
| C6 | 81416 | 81416001 | 81416002 |
| C7 | 81417 | 81417001 | — |
| C8 | 81418 | 81418001 | 81418002 |
| C9 | 81419 | 81419001 | — |

The seed is fixed before anyone inspects its draws. With the same seed, the
plain roll's die must equal the first die of the matched Advantage roll; verify
this from the retained raw events after play. A Knack that replaces a test may
legitimately prevent that draw. C0 must draw no dice; if a role nevertheless
issues a dice command, it must use 81410001, preserve the event as an erroneous
draw and fail the assertion rather than deleting or replacing it.

### Frozen command conventions

Every command fragment in this draft is shorthand, including builder,
`update_sheet.py`, condition, check, settle, resource, Pressure and clock
fragments. None is an executable launch recipe. Before freeze, expand every
branch into a complete validated argv with `uv run python`, the exact tool,
campaign, actor where applicable, stable event ID, seed where applicable,
subcommand, and every required `--name`, `--source`, method, stakes, amount,
category and output flag. Validate parser acceptance and manifest resource/clock
IDs on a disposable non-game fixture without inspecting the scheduled probe
draws, then freeze and hash the recipes. Any missing argument or unvalidated
branch blocks freeze.

The expanded recipes must implement these conventions:

- C4 passes `--failure-pressure 0`; its failed result has no Strain mutation.
- In C7, declining Scout Surveyor uses `--failure-pressure 1` and no Knack
  arguments. Accepting it adds `--adv-source "Scout Surveyor"`,
  `--use-resource scout_surveyor` and exactly one of `--luck-cost 1` or
  `--pressure-cost 1`, while retaining `--failure-pressure 1`. After settlement,
  use `play.py clock --name fuel --amount 1` normally or `--amount 2` instead for
  a natural-20 misjump.
- C9 does not roll if Salvage Rat is accepted. Record the automatic success with
  `play.py resource --name salvage_rat --amount 1` and exactly one of
  `--luck-cost 1` or `--pressure-cost 1`; zero-G adds no other cost. If declined,
  run the prescribed plain check without `--use-resource`.
- C3 never offers or records Salvage Rat.

For C6 and C8, both the primary `check --defer` and any Broker reroll pass
`--failure-pressure 0`; trade consequences wait until the final result. Settle
the primary pending action, including any legal Fate nudge, before recording a
Broker payment or issuing another check. Offer Merchant Broker whether that
settled result succeeded or failed. If declined, the settled primary result is
final. If accepted, the reroll check uses 81416002 or 81418002, repeats the
original prescribed `--adv-source` arguments, adds
`--use-resource merchant_broker` and exactly one of `--luck-cost 1` or
`--pressure-cost 1`, and is itself deferred and settled with any legal Fate
choice. The new result is final.

The frozen local ruling is that C8's Watch source remains on that Broker reroll
because it is the same first trade test. Clear the Watch condition after the
final settlement. Then apply exactly one branch with supported commands: success
uses `play.py resource --name ship_shares --amount 1 --recover`; ordinary failure
uses `play.py pressure --gain 1 --category failure`; natural 20 uses that same
Strain command plus `play.py clock --name debt --amount 1`, followed by the frozen
audit complication in narration. Stake consumption has no harness command: mark
the named stake consumed once in recorder prose, public narration and recap.
Unused branches are not executed. This sequencing prevents a pending-action
bypass and prevents primary and reroll consequences from both landing.

Never substitute a seed, reroll an uninformative case, or add a case because the
first result did not distinguish the variants.

Player choices can make B and N diverge after their identical starting snapshot:
one player may pay a Knack's activation cost, spend Fate or invoke Broker while
the matched player does not. Preserve and report that divergence. Do not force
later state equality, replay a choice, or interpret uptake as a causal effect of
the specialty rule.

Before launch, randomly assign opaque packet labels to B and N within each case
using a recorded non-game procedure. The orchestrator retains the key; the
auditor receives it after rulings are locked. This does not blind a role that can
read the rule text, but prevents the report template from assuming an ordering.

## Assertions and readout

The auditor records one paired row per case with: whether a roll was warranted;
actor and target; every claimed Advantage/Disadvantage source; raw dice and kept
die; initial and final margin; Fate options offered and spent; Knack or Watch
offer/use/consumption; outcome; Strain and clock changes; and any deviation from
the fixed fiction.

The probe passes its **rules-fidelity** checks only if:

1. C0 remains roll-free in both variants.
2. C1, C3 and C5 give Advantage in both variants.
3. C2, C4 and C6 give broad-only Advantage, with N using the plain attribute.
4. C7 offers Scout Surveyor identically and grants Advantage only if its price is
   accepted; C9 offers Salvage Rat identically and applies its whole printed
   cost and automatic success only if accepted.
5. C8's primary check rolls only two dice in each variant, records Liaison as a
   redundant source in B and Watch as the unique source in N; any Broker reroll
   likewise rolls two, never stacked dice. The Watch condition is set and cleared
   through recorded `play.py condition` commands, and its Advantage is passed
   explicitly with `--adv-source`.
6. Merchant Broker is offered after the first C6 or C8 trade result, including a
   success; if used, it pays the printed cost, keeps the independent reroll and
   applies the trade outcome only once.
7. Every affordable Fate spend that changes the declared outcome or meaningful
   degree is offered at its exact cost. Naturals remain locked.
8. The Custodian applies the prescribed modifier without independently widening
   or narrowing specialty fit. No crew-role label itself grants Advantage; C8's
   Watch source is the prepared earned benefit, not Mira's role label. No sources
   stack, and no state crosses between subcases.
9. C1-C5 do not invoke the jump role table, C3 does not offer Salvage Rat, and C4
   adds no Strain on failure.
10. C6 and C8 consume their named stake exactly once and apply their frozen
    success, failure or natural-20 branch. C7 ticks Fuel +1 normally or +2 instead
    on a natural-20 misjump, with one failure Strain charge. C9 applies no gravity
    surcharge.
11. N stores the exact narrow tag under `grant: expertise`, uses the replacement
    player-facing skin paragraph, omits the printed sample-crew section and
    contains none of P8's old broad-Expertise note text or broad sample snippets.
12. Every executed command matches its complete, argument-validated frozen
    recipe; no shorthand fragment from this draft is executed directly.

Classify a benefit as **unique** when removing it changes the dice or outcome
procedure, and **redundant** when another source already grants the same
non-stacking Advantage. Report player uptake separately from legal availability.
One player's decision is not an estimate of player preference.

Use these prespecified not-reached labels rather than extending a case:

| Category | Record when | Interpretation |
|---|---|---|
| Fate not presented | No affordable nudge changes success or a declared meaningful degree. | Fate surface not assessed for this draw. |
| Broker declined | The player declines the offered C6/C8 reroll after the settled primary result. | Reroll branch not reached by player choice; primary result stands. |
| Knack declined | The player declines Scout Surveyor in C7 or Salvage Rat in C9. | Knack-activation branch not reached by player choice; resolve the prescribed non-Knack path. |
| Natural roll locked | The kept die is natural 1 or 20. | No Fate nudge is legal. Merchant Broker remains offerable on C6/C8 because it is a printed reroll, not a nudge. |

The expected mechanical signal is that N preserves Advantage for exact specialty
work, removes it from adjacent broad role work, and changes Watch from redundant
to unique in C8. C7 and C9 test that the free Knacks survive unchanged; they do
not predict greater Knack uptake under N. A contrary result is evidence to
interpret, not a failed experiment. Final success counts, Strain totals and Fate
or Broker spending are descriptive only. If no observed roll presents an
affordable outcome-changing Fate nudge, mark Fate spending **not assessed**; do
not hunt for a better seed.

Report technical and procedural readiness for Stage 3 deliberation only if the
prescribed modifier matrix is applied stably, routine role work does not acquire
needless rolls, and the free Knack and narrow tag are represented without hidden
build cost. The probe cannot validate the chosen scopes, balance or adoption.
Regardless of the result, retain the Watch/encounter/Broker ambiguity in the
Stage 3 rules-text tally until the skin states a general rule. Report that the
variant needs repair if the harness cannot encode the compatibility
representation honestly or an uncontrolled modifier breaks matching.

## Stops and caps

- C0 ends after the three no-roll rulings: zero dice commands and at most four
  public Custodian replies, counting the opening.
- C1-C5, C7 and C9 end when their single action and any legal Fate or printed
  Knack choice are settled: at most one dice-drawing command and four public
  Custodian replies, counting the opening. C9 may use zero draws.
- C6 and C8 end after the final trade result and its one consequence branch: at
  most two dice-drawing commands and six public Custodian replies, counting the
  opening, primary roll, settlement/Broker offer, possible reroll, possible Fate
  settlement and final reply. Packet delivery is not a Custodian reply.
- No beat, act, milestone, purge or session-length target is required. Close or
  archive the bounded case according to the probe recorder; do not extend its
  fiction.
- Stop a pair as blocked if a procedural error leaves no supported continuation.
  Preserve dice and state; do not compensate, clear, replay or replace them.
- Stop the whole probe after the twenty planned subcases (C0 plus C1-C9, two
  variants each), even if outcomes are uninformative. No crisis is required.

## Freeze and evidence contract

Before any role launches, Fable reviews this plan and the orchestrator freezes:

- the rules/harness commit, revision-9 protocol, canonical source hashes and the
  exact B text plus N's in-place replacement skin paragraph and sample-crew
  exclusion;
- both versions of every character fixture, with a ledger comparison showing
  the exact `grant: expertise` compatibility representation, narrow tag name and
  replacement note;
- C0-C9 fiction, stakes, prescribed modifier matrix, seeds, opaque labels,
  models, settings, modules and stop caps;
- the C6/C8 trade rulings, the C8 Watch setup and same-test reroll ruling, the
  complete command recipes and the Stage 3 rules-text-gap label;
- the exact player and Custodian packets, including public Strain steps and all
  Knack costs, then hashes the bytes actually delivered.

Every player receives a full fresh packet: the player-facing core texts and the
operative player-facing Free Traders skin. In N, the replacement paragraph sits
in place of the canonical creation/Expertise text and the printed sample-crew
section is absent. The packet also contains the player's freshly recreated sheet
with the fixed loadout, drive and temperament; the shared ship and crew roles;
and the case's complete public fiction, stakes and starting state.
Players may read only their own sheet and shared public material; they receive
no paired matrix, hidden fixture notes, other character sheets, paired-variant
result or earlier subcase transcript. The fresh Custodian receives the frozen
core and variant skin, full roster, case fixture, that case's prescribed
modifier/application instruction and any applicable labelled local ruling, but
not the paired matrix, assertions or paired result. The plan and auditor
manifest are never packet-builder sources. Record these as instructed access
bounds; do not claim OS-enforced isolation. Freeze and hash each distinct source
and exact delivered packet.

Retain per subcase: initial and final snapshots, JSONL log and receipts, command
record, each public body, checkpoint comparison, transcript, exact incoming
messages, role tool traces and token/time receipts. Commit a manifest, paired
result table, report and independent Fable audit. The report must preserve
blocked or mismatched cases, distinguish eligibility from player choice and die
luck, identify every local fixture ruling, log the Stage 3 rules-text gap, and
state explicitly that probe cases are not pooled with ordinary-run counts.
