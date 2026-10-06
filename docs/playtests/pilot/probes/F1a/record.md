# F1a: The Greyford

Probe record, Fable as orchestrator, 5 October 2026. This is a labelled probe under protocol revision 9; it is never pooled with P1–P13.

## Manifest

| Field | Value |
|---|---|
| Specification | `../fable-probes.md`, F1a |
| Frozen scenario | `playtests/runs/F1a/frozen_scenario.md`, SHA-256 `fda2b369bc02b60c…`, cleared with the two freeze lines (board 955–957) |
| Rules commit | `b12135e` |
| Game | Twilight of the Northlands; optional combat module with gritty Injury |
| Fixture (labelled) | Dread 3 (the step-2 penalty armed for all three; the step-3 toll live); Companionship 3/3 |
| Roster | `gen_character.py`, seeds 2211–2213: Bofrin Ironsong (STR 13, Hope 11, Stamina 4), Aelith Greymantle (NIM 10, Hope 11, Stamina 7), Tobby Underhill (NIM 10, Hope 10, Stamina 6) |
| Foes | four orcs entered with `play.py npc`, as frozen |
| Roles | Custodian and three players, fresh Sonnet subagents |
| Master seed | 221; draws 221001–221024, contiguous |
| Replies | 28 Custodian public bodies (cap 30); closing lines, one archive each, three receipts |
| Interventions | one pre-open clarification (Cart Taken ticks only on a round spent working the cart; the frozen text is unchanged), and one cap-count note to the Custodian at reply 26, which was not narrated |

## What happened

**Round 1.** The orcs won initiative (15 against 5). Three crossed to the cart, so Cart Taken did not tick. The archer shot at Aelith and missed. Aelith's arrow downed the archer. Tobby's dagger, nudged with Companionship, scratched Grishnar.

**Rounds 2–4.** The orcs pressed Bofrin and Tobby at the cart, and both defended Watchful.
- **Hope spent to avert hits:** Bofrin went from 11 to 1, Tobby from 10 to 4.
- **The step-3 toll:** paid in Hope every time, and the low-Hope pair passed rather than attack.
- **Grishnar:** Aelith wore him down from 6 to 1 over rounds 3 and 4.
- **Tobby:** took 5 from Grishnar (6 → 1) and fell back to the bank by his own choice, after Bofrin asked him to.

**Round 5.** Bofrin, alone at the cart, parried all three orc attacks. Aelith's arrow felled Grishnar and the orcs broke off.

The cart was held, no refugee was harmed and Dread stayed at 3. The single beat was flagged perilous.

## Assertions (`fable-probes.md`, F1a 1–11)

| # | Assertion | Score |
|---|---|---|
| 1 | Initiative per Manual 6, held for the fight | **Correct** (`combat-start`, one d20 per side) |
| 2 | Positions for every combatant, orcs included, each round, held | **Correct** (`positions`/`round` each round, five rounds) |
| 3 | Vanguard refused while Injured; Ranged, engaged and unscreened, defends with Disadvantage | Not reached (dice: no Injury; no orc engaged a Ranged companion) |
| 4 | Damage formula | **Correct** on every hit checked (archer 4, spear 2 and 1, axe 2 and 5, arrows 2, 1→2, 2 and 2, dagger 1) |
| 5 | Injurious-blow check on every hit | **Correct.** It was stated each time, and no hit reached a natural 1 or effective margin 8. Twice the players declined a 6-point nudge that would have forced one. |
| 6 | Deflection test | Not reached (dice and player choice) |
| 7 | Injured effects; second injury | Not reached |
| 8 | Toll only on risky tests a companion attempts; never on defence or Deflection | **Correct.** 11 toll events, all on attacks, none on defences. |
| 9 | Dread 4 and a crisis | Not reached (player choice: every toll was paid in Hope) |
| 10 | Companionship at 0 → +1 Dread | Not reached (player choice: the pool was kept at 1, explicitly to avoid Dread 4) |
| 11 | Revision 9 general checks | **Correct.** Oath disposition checked (Bofrin held his oath); offered options kept; no PC words written. Tobby's conditional move was returned to Tobby to decide. |

**Threat clock.** Cart Taken never ticked. The orcs were always engaged at the cart, under the Custodian's ruling that "engaged" means standing at the cart with them. The clock was live and correctly applied, but never advanced.

**Notes for the audit:**
- **Opposed nudges.** Nudges on the opponent's die were offered throughout; Manual 3 allows this.
- **NPC Stamina.** G027's "any hit that wounds him will fell him" lets the players infer Grishnar's Stamina.
- **Death wording.** "The dead archer" is stronger than "at 0 Stamina".
- **Reply count.** The Custodian's count ran two ahead of mine.
- **Command slip.** The first `combat-end` lacked `--reason`. It was rejected with no change and re-run; the Custodian disclosed it.

## Checks

- **Checkpoints:** 28 of 28 match.
- **Deliveries:** all verified verbatim against the three native transcripts.
- **Player tools:** one packet Read each, plus hand-backs.
- **Custodian access:** within its boundary.
- **Campaign:** `validate_campaign.py` ok.
- **Seeds:** OK, including Deflection-eligible settles that drew nothing and reused their seed.

## Coverage

F1a exercised the combat frame well: initiative, stances, damage, tolls, Companionship, a threat clock and a break condition. It did **not** reach Deflection, Injury, Dread 4 or a crisis.

The players spent Hope to avoid every serious outcome, and paid tolls in Hope rather than Dread. Effective margins never reached 8, and both offers to force an injurious blow for 6 points were declined.

That is a finding in itself: with a Hope-funded toll and defensive nudges, careful players keep Dread flat and avoid injury. It is still not evidence that Injury and Deflection work in play. A second bounded subcase with a labelled fixture (a companion already Injured, or Hope depleted) would be needed to reach them. I am not adding one without agreement.

## Post-audit note

Added by Fable on 5 October 2026, after Astra's audit (board 998). I accept it in full.

- **F1a counts as a harness test only.** G027 said "any hit that wounds him will fell him" and confirmed that Tobby's minimum-1 sling hit was enough. That disclosed Grishnar's hidden 1 Stamina before the final targets, tolls and order were chosen, and P025 used it. I flagged the line but under-classified it.
  - The earlier mechanics evidence stands.
  - Behavioural claims about the final choices are excluded.
  - Assertion 11 is not Correct: the private-state boundary was breached.
- **Corrected accounting:**
  - **Tolls:** 10 Hope-paid tolls, not 11: Aelith 5, Bofrin 3, Tobby 2.
  - **Hope by character:** Bofrin 11 → 1 is 3 tolls + 7 nudge points; Tobby 10 → 4 is 2 + 4; Aelith 11 → 5 is 5 + 1.
  - **Totals:** 22 personal Hope spent (10 tolls + 12 nudge points), plus 2 Companionship.
- **Actual damage events** (7, in order): Aelith → archer 4, Tobby → Grishnar 1, Aelith → Grishnar 2, spearman → Bofrin 1, Grishnar → Tobby 5, Aelith → Grishnar 2, Aelith → Grishnar 2. My earlier list mixed offered pre-nudge outcomes with these.
- **Injury coverage:** the seven hits had effective margins 7, 0, 3, 0, 6, 2 and 5, with no winning natural 1. Deflection, Injury, second Injury, the Vanguard refusal and the engaged-Ranged defence were not reached.
- **Behavioural claim, narrowed to this encounter:** in this seeded encounter, the party kept Dread flat by paying tolls in Hope, and used defensive nudges to avert several ordinary hits. Injury remained unobserved because no settled hit met its trigger. The party did accept ordinary harm (Bofrin −1, Tobby 6 → 1).
- **Death wording:** "dead archer" is a fictional ruling beyond the mechanical 0 Stamina.
- **Follow-up:** withdrawn as proposed. A low-Hope or already-Injured start guarantees neither a new Injury nor a failed Deflection. Any follow-up will separate interaction under an existing Injury from labelled, prescribed transition tests, and will say what it adds beyond `tests/test_play_runtime.py::test_second_injury_drops_target_and_positions_hold`.
