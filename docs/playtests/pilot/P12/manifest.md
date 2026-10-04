# P12 manifest — Time Odyssey

Status: corrected-packet attempt B complete and frozen. Attempt A is stopped and excluded from clean-play evidence; see attempt-a/report.md. Protocol revision 6; rules commit `36d644f3fe11dd14e208667eafe200da0d6b96f7`. Scenario: **The Archive Beneath the Tidal Sky**.

Campaign: `playtests/campaigns/p12_time_r`. Evidence: `playtests/runs/P12R`, including frozen scenario, policies, initial state, source snapshots, exact packets, inputs, native traces at close, historical checkpoints and command receipts. Setup freeze: 2026-10-04T04:49:28.838336+00:00. Master seed **121004**, in-play draw N uses 121004000+N; creation seeds 1210041–1210043 fixed before generation.

Custodian and all three players: separate fresh Codex CLI sessions, `gpt-6-sol`, medium reasoning. GM: `01a1053c-81ae-7c10-a11e-cdf722718eb1`. Root orchestrator gives no rulings. Player isolation is instructed, not enforced; packets delivered verbatim in setup prompts and zero tool use confirmed in all three native player traces.

Pulp12 creation; each paid2BP for one tag. No free tags, score edits or rerolls. Injury, gritty, Condition Tracks, Wealth & Attention off. Shared engine has no numerical bonus.

- **Ada Mercer** — chronal engineer; seed 1210041; player `01a1053d-6673-7fc2-ab4f-a6d4af6a05ac`. Drive: Bring back proof that the vanished surveyor survived without sacrificing the people now living in the future. Temperament: Methodical and compassionate; risks her own safety for a testable rescue, but will not knowingly erase a living community. Equipment: leather riding jacket, portable tool roll, bound epoch journal, graphite pencils, calibration key, pocket watch.
- **Gideon Vale** — courier and expedition scout; seed 1210042; player `01a1053d-667c-7dc3-9308-d794a0f8e8d7`. Drive: Find the missing surveyor, who once rescued Gideon's sister, and bring them home alive if possible. Temperament: Bold and fast; takes the exposed route first when someone is in danger, but refuses to abandon a companion. Equipment: leather riding jacket, walking cane, coil of climbing rope, folding knife, signal whistle, chalk, folded city map.
- **Miriam Ash** — oral historian and field interviewer; seed 1210043; player `01a1053d-667a-70d1-b150-f5073aaa2ac1`. Drive: Preserve the testimony of people history has overlooked, even when it complicates the expedition's official account. Temperament: Patient and sceptical; accepts social and reputational risks for a witness, but will not coerce testimony. Equipment: tweed coat, field satchel, interview notebook, charcoal rubbings, glass photo plate, pocket compass.

Exact attributes and purchased tag scope are retained in initial sheets and reviewed public packets.

Policies: INT or current Ingenuity for a historical intervention as method warrants; one test per intervention; genuine new leverage needed for another. Skin and core Pressure triggers additive, without double-counting one causal event. Shared exposure charged once per beat when triggered. Purges require demonstrated fictional achievement/sacrifice/safety. Epochs and contradictory records tracked; relevant journal use can grant printed Advantage. No Pressure quota.

Source caveat: Fable updated P8 audit and handbook withdrawal caveat during setup; working diff and committed/live handbook copies retained. Protocol already contains that caveat; no mechanical changes.

Packets SHA-256:

- ada_mercer: `72b93c10f7f0fb1c49255b85c739536d268de1d507b79214ae50ecdc746e2bc2`
- gideon_vale: `1b40a33b9792025919850aafedf370c370b6f5f3af5f394b3f0d5cf7f6298cb3`
- miriam_ash: `c22bc4f6b619b245b395ede02097c06fa5dceef28189729d99347829348386a5`

Interventions: none during play. After closure, the exact-text relay stopped on G015 outer blank lines; parent preserved the mismatch and delivered the returned body unchanged to all players. No rule, dice, checkpoint or mechanical state repair. Monetary and root-orchestrator costs unavailable.

Restart provenance: pre-play initial snapshot cloned into distinct campaign, only slug/title metadata changed; scenario, roster, policies and seeds preserved. No played state or role history carried over. Independent content preflight passed BEFORE fresh player launch. Attempt A record and all costs retained separately.

## Completion and cost

Play freeze/start: 2026-10-04T04:49:28.838336+00:00. Final GM completion: 2026-10-04T05:31:42.592117+00:00. All closing receipts: 2026-10-04T05:33:36.174871+00:00. Elapsed through receipts: 44.12 minutes (includes the closing-format inspection).

Native cumulative token totals below include setup. Cached input is a subset of input; reasoning is a subset of output. Wall time sums role calls, so player work overlaps. No monetary estimate is inferred.

| Role | Calls | Input (cached subset) | Output (reasoning subset) | Call wall seconds |
|---|---:|---:|---:|---:|
| gm | 16 | 21607563 (21393408) | 72616 (34984) | 2429.27 |
| ada_mercer | 16 | 1032580 (956928) | 2212 (953) | 205.55 |
| gideon_vale | 15 | 895439 (806528) | 1755 (572) | 185.85 |
| miriam_ash | 15 | 906758 (838400) | 3209 (2097) | 223.89 |

The native trace has 17 GM turn-context records for 16 CLI calls, including a continuation within G015; all specify gpt-6-sol / medium. Player contexts likewise confirm that model and effort, with zero tool calls. Access was instructed, not technically isolated.

Final evidence: 15 GM bodies, 40 decision replies and three closing receipts; 112 recorded commands before parent closeout, zero failures; nine draw indices/seeds in order. All returned bodies retained. G001–G014 byte-match historical checkpoints, GM save files and public log; G015 returned/delivered body equals newline + saved body + newline. The false check and both originals remain. Independent replay confirmed all43 decision/receipt inputs including queued dialogue. No hidden scenario exposure found in corrected packets.

The campaign scenario is unchanged. The longer campaign policy and shorter run policy were different at setup and each remains unchanged against its own frozen baseline (policy_baseline_check.json). The collector's cross-file policies_unchanged=false compares those different versions, not an in-play edit. The as_closed snapshot predates parent prompt refresh; only prompt.md differs in final. Campaign validation after refresh: zero errors, zero warnings.
