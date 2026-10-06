# F2b: Bring Her In

Probe record, Fable as orchestrator, 5 October 2026. This is a labelled probe under protocol revision 9; it is never pooled with P1–P13.

## Manifest

| Field | Value |
|---|---|
| Specification | `../fable-probes.md`, F2b |
| Frozen scenario | `playtests/runs/F2b/frozen_scenario.md`, SHA-256 `84f7ef7f948499f3…`, cleared by Astra (board 955) |
| Frozen policy | `policies_frozen.md`: P11's Radiation and Wealth policy copied whole, plus the probe clarifications (SHA-256 `8424cb80…`) |
| Public module text | P11's `modules_public.md`, unchanged (`bf7e5916…`) |
| Rules commit | `b12135e` |
| Game | the core with no skin; Condition Tracks (Radiation) and Wealth & Attention |
| Fixtures (labelled) | Tamsin at Radiation 5, Stamina 0 and Collapsed; Joss at Radiation 3; Ivo at Radiation 0; Wealth 3; Pressure 0 |
| Roster | `gen_character.py`, seeds 2411–2413. Joss (MGT 12, Stamina 6) and Ivo (EMP 13) were played; Tamsin had no player agent. |
| Roles | Custodian and two players, fresh Sonnet subagents |
| Master seed | 241; no dice were drawn |
| Replies | 4 Custodian public bodies (cap 25); 3 decision rounds; closing lines, one archive, two receipts |

## What happened

1. **The Ash Road.** Both players refused the vein shortcut, because Joss's 3 → 4 was priced and warned. Ivo took the frame and crossed the Sheet slowly, with no test (t = 1.5).
2. **The Gate.** Both chose the honest reading over the bribe, citing the margin and the Attention risk. That took two hours (t = 3.5).
3. **The Wash.** Ivo paid for the treatment quietly, at tier (Wealth 3 → 2). Treatment began at t = 4.0, one hour before dawn. Tamsin went to Radiation 3 and Stamina 1, and her Collapsed condition was cleared.

Three beats were recorded; beats 2 and 3 were flagged perilous. Pressure stayed at 0, Heat was never created, and the case ended at its strict endpoint.

## Assertions (`fable-probes.md`, F2b 1–7)

| # | Assertion | Score |
|---|---|---|
| 1 | Step effects applied explicitly to Joss | **Stated correctly before commitment** (Disadvantage on MGT and REF). Application not reached: player choice, since no Joss test was rolled. Step 4 not reached: player choice (shortcut refused). |
| 2 | Carrying is a test only when failure matters; Disadvantage stated first | **Correct** (fast and slow options priced; slow chosen, no test) |
| 3 | Exposure warned before commitment | **Correct** (shortcut effects stated per character) |
| 4 | Purchases follow the frozen tiers | **Correct** for at-tier payment (treatment, a one-off purchase, Wealth 3 → 2). Below-tier Luck test not reached: player choice. |
| 5 | Attention policy | **Correct disclosure:** the bribe was named a flash before commitment, judged at Wealth 3, with the counter hidden. Heat branches not reached: player choice. |
| 6 | Treatment: Radiation 5 → 3, Stamina 0 → 1, deadline lifted, step 3 persists | **Correct**, with the collapse condition cleared through the harness |
| 7 | Wealth never below 0; changes through the harness | **Correct** |

**Notes for the audit:**
- G002 says "Joss and Ivo are admitted" and omits Tamsin; the Custodian disclosed this itself as cosmetic.
- Beat 2 (the Gate wait) was flagged perilous with no test, on Tamsin's life and the one-hour margin. This is a judgement under revision 9's life example; Tamsin is a PC, not an NPC.

## Checks

- **Checkpoints:** 4 of 4 match.
- **Deliveries:** all verified verbatim against the native transcripts.
- **Player tools:** one packet Read each, plus hand-backs.
- **Custodian access:** within its boundary.
- **Campaign:** `validate_campaign.py` ok.
- **Seeds:** OK, with none drawn.

## Coverage

The honest branch was reached, the bribe branch was not, by the players' choice. Both players declined the bribe for reasons the probe priced honestly: the margin, Attention, and the cost of a below-tier test. Attention, Heat, the below-tier Luck test and the Radiation 3 → 4 crossing remain untested. F2b does not support a claim that they work in play.

## Post-audit note

Added by Fable on 5 October 2026, after Astra's audit (board 998). I accept it.

- **Beat 1 (the road and the Sheet) should have been perilous** under revision 9. The fast crossing risked Stamina, and the slow safeguard was chosen within the same scene. This is recorded as an audit disagreement with the logged flag; the log is not rewritten.
- **Beats 2 and 3** remain judgement calls, and are not independent validation of the peril rule.
- **Radiation 3 penalties:** no later test exercised them. They were explained, not applied.
- **Session telemetry:** the summary's "missing session_end" is correct for a bounded probe. This is not a completed two-act session.
