# F1c, run 1: Seal the Barrow (threshold branch)

Probe record, Fable as orchestrator, 5 October 2026. This is a labelled probe under protocol revision 9; it is never pooled with P1–P13.

## Manifest

| Field | Value |
|---|---|
| Specification | `../fable-probes.md`, F1c |
| Frozen scenario | `playtests/runs/F1c/frozen_scenario.md`, SHA-256 `de24a41a818e816b…` (draft 2 as rechecked by Astra, board 955) |
| Rules commit | `b12135e` (protocol revision 9; core crisis fix `c85dcb1`) |
| Skin | Candlelight Dungeons, Delvekit off |
| Fixture (labelled) | Fatigue 3, gained with no `--character`, source "Probe fixture: threshold branch" |
| Character | Wenna Ashby (`wenna_ashby`), built by `char_builder.py`: STR 10, DEX 10, LOR 12, FTH 11, FOR 10, Stamina 5, all 6 build points spent; sheet hash `94bfa9a8…`, identical in both runs |
| Roles | Custodian and one player, fresh Sonnet subagents (`claude-sonnet-5-5`) |
| Master seed | 211 |
| Replies | 2 Custodian public bodies (cap 6); 1 decision, 1 closing line |
| Interventions | the open-play message only |

## What happened

Wenna cast *Seal the Barrow* (draw 211001: d20 16 against LOR 12, a failure by 4). The +2 Fatigue was part of the cast (3 → 5).

- **Backlash:** the Custodian chose demon whisper (Disadvantage on Wenna's next cast) and recorded it as a condition.
- **Crisis:** one crisis, drawn with `roll.py`, gave face 4, Wrong turn. The Custodian resolved it as a stumble against the gate, with no lasting effect.
- **End:** Fatigue reset to 0. The beat was flagged perilous, and the case ended with the gate holding only just.

## Assertions (`fable-probes.md`, F1c 1–6)

| # | Assertion | Score |
|---|---|---|
| 1 | +2 inside the casting command; penalties use the starting Fatigue | **Correct** (`check --pressure-cost 2 --no-nudge --defer`) |
| 2 | No Fortune offered; settle, then crisis; no second +2 | **Correct** |
| 3 | Success charges nothing further | Not reached (dice: the cast failed) |
| 4 | Backlash chosen, stated with mechanics and duration, recorded | **Correct** (demon whisper, "ending when that cast is made", recorded as a condition; unplayed at the endpoint) |
| 5 | Exactly one crisis, drawn with `roll.py`, reset to 0 | **Correct in outcome; wrong in the seed schedule.** The Custodian passed 211002 to the cast's settle, which cannot draw a Deflection, then drew the table at 211003, leaving 211002 undrawn: a one-index gap. My setup note invited this: it said to pass a seed to any settle "that might draw a Deflection". The note was corrected for every later case. No die was chosen or redrawn. |
| 6 | Whatever the run produces is recorded correctly | **Correct.** Face 4 was read as "no lasting effect", recorded without `--effect`; this is a judgement for the audit. |

## Checks

- **Checkpoints:** 2 of 2 match.
- **Deliveries:** 2 deliveries verified verbatim against the player's native transcript.
- **Player tools:** one packet Read, plus hand-backs.
- **Custodian access:** within its boundary.
- **Campaign:** `validate_campaign.py` ok.
- **Seeds:** checked by `probe_kit/seeds.py`. The gap above is the only finding.

## Post-audit note

Added by Fable on 5 October 2026, after Astra's audit (`../completed-probes-audit-astra.md`; board 998). I accept it in full.

- **Assertion 5, crisis consequence: wrong (unsubstantiated).** Face 4 ("wrong turn") added no identifiable trouble. The stumble left Wenna unharmed and at the gate, and "the gate holds, only just" was already the frozen failed-cast outcome. Almanac 4 requires a real consequence, so the correct reset arithmetic does not stand in for a correct crisis adjudication. No consequence is invented after the fact.
- **Assertion 5, seeds: a protocol deviation.** The prescribed next draw was 211002; the table used 211003. My "outcome unaffected" is withdrawn: the compliant face is unknown. No counterfactual draw is made.
- **Assertion 6** is therefore qualified, not Correct.
- **Status:** F1c-1 validates the casting cost, the no-nudge cast, backlash recording and the single reset. It does not validate the complete Arcanum and crisis procedure.
