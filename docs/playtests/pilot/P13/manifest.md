# P13 manifest — The Bell Beneath Ashwater

Status: completed; Fable's independent cross-audit and Astra's response in report.md are complete. This is a procedural pilot, not balance evidence.

- Protocol: revision 7, 4 October 2026.
- Rules and protocol commit: `110106d6c1435bf16de8d767e30bc57b70920d62`; working tree clean at setup freeze.
- Skin: Candlelight Dungeons, with the Candlelight Delvekit sidecar on. Medium expedition difficulty, standard creation budget 6. All other optional modules off.
- Master seed: `131004`. New in-play dice command N receives `131004000 + N`; character creation uses the separately fixed seeds below. The recorder checks sequential indices before execution and retains all rejected/failed attempts. Identical successful indexed retries replay saved output. Conditional initiative/Deflection draws still require the caller to supply an index and will be checked against native evidence after play.
- Access: instructed, not enforced. Fresh CLI histories for one Custodian and three players. Players receive their public packets verbatim in their initial input and are instructed to use no tools. Shared filesystem access remains technically available.
- Exact model/settings: all four roles `gpt-6-sol`, `model_reasoning_effort="medium"`, through `codex exec` and `codex exec resume`; native context records will be retained.
- Setup freeze: `2026-10-04T07:01:34.266762+00:00`. No in-play dice or player actions before freeze. Preflight: 174 tests passed; campaign validation had no errors (expected warning: no public session log yet).

## Roster fixed before generation

All characters were generated once, in the declared order, with no attribute adjustments. Primary is a generator bias, not a guaranteed highest score. Each received one free Knack and one free broad Expertise; no paid tags. Exact original sheets and notes are retained in the initial snapshot.

| Character | Seed / primary | Initial STR/DEX/LOR/FTH/FOR | STM | Tags |
|---|---|---|---|---|
| Mara Venn, discharged gate warden | 1310041 / STR | 10/11/8/13/10 | 5 | Second Wind; gate warden (STR) |
| Ivo Pell, itinerant lamp scholar | 1310042 / LOR | 10/10/13/10/10 | 5 | Arcane Flex; lamp scholar (LOR) |
| Sera Quill, lay keeper of the chapel dead | 1310043 / FTH | 9/10/9/10/12 | 7 | Turn Undead; chapel keeper (FTH) |

Mara seeks the parish record concerning her brother; she is bold at a threshold and will risk a blow for an ally, but will not abandon a trapped companion. Ivo seeks the bell's underside inscription; he will spend time and light on a clue, but will not cast blindly into an allied position. Sera seeks burial evidence for the waiting families; she accepts danger for the living and refuses to desecrate remains for a shortcut. Only each player's own drive and temperament were in that player's packet.

Mara carries a sword (+1 edge), chain shirt (soak 2), a descriptive shield without a numerical bonus, rope, two torches, tinder, spikes, water and rations. Ivo has a dagger (edge 0), robes (soak 0), spellbook without an automatic bonus, hooded lantern, two oil flasks, chalk, mirror, water and rations. Sera has a spear (+1 edge), leather (soak 1), holy symbol, two candles, bandages, salt, water and rations. Ivo knows Wickglow (Cantrip, LOR) and Hush the Bell (Spell, LOR); Sera knows Candle Benediction (Cantrip, FTH) and Mercy of the Threshold (Spell, FTH). Exact scopes and printed costs are in their frozen packets.

## Frozen setup and public delivery

Ignored evidence root: `playtests/runs/P13/`; live campaign: `playtests/campaigns/p13_delve/`.

- `roster_plan.json` predates character generation; `roster_setup.json` is the packet input.
- `frozen_hidden_scenario.md` contains the full keyed map, NPC motives/boundaries, autonomous threat timetable, alternatives and experimental mapping. `initial/` preserves the campaign before play; `freeze.json` and `initial_snapshot_hashes.json` preserve hashes.
- `public_fuse_mapping.md` is the exact labelled experimental mapping embedded in the scenario. It overrides the core additive default for this pilot only: generic triggers feed Fatigue through declared bodily strain/exposure, not noise, moral offence, debt, delay, darkness or a clock tick by themselves. Printed spell, Knack, forced-march, grave-wound and no-rest costs/triggers remain. Shared exposure is charged once for the party, without double-counting synonymous generic triggers.
- Public packets include Quickstart, The Adventurer, Adventurer's Manual, the complete Candlelight player section through the boundary before Chronicler's Lantern, the public Delvekit summary, the full policies, and the player's own public export plus reviewed equipment/ability/spell notes. Parent and independent preflight both passed before launch; the actual saved initial CLI inputs match the prepared packet inputs byte for byte.

| Packet | Bytes | SHA-256 |
|---|---:|---|
| Mara | 45,791 | `2997f0c74b310daccb8fdba5b6d15614e0a1d73c67241b039c0895e4631a4ce5` |
| Ivo | 46,262 | `aec0a897ca586d7ff2cd09bc8bb3fcefca3593c1fc932e81085c3bb524d5e669` |
| Sera | 46,301 | `36ec44ffd2e59e8e6387fb85526031ddf07e79bfc95fcccc5ce0650822976759` |

## Custodian policies

`policies.md` is identical in the frozen run folder and initial campaign memory. Fortune tests use current coins for genuine blind chance. Shared environmental exposure charges once; printed costs and step-4 tolls remain distinct. An uninterrupted safe pause restores 1 STM, or 2 with good care, once for that pause; Fortune rest recovery requires a warm hearth. A rest consumes a dungeon turn with announced light/threat exposure. Sleep/hearty stew purge 2 Fatigue; a consequential cleansing rite or miracle may purge up to 2 where justified. Torches last six time-eating turns, lantern flasks eight, candles two, only while lit. Medium's first 0-STM event may permit survival with an immediate hard cost if fiction allows; the second in the expedition is death. Return to settlement or sanctuary ends the expedition. Core combat remains unchanged.

## Role histories and costs

Custodian: `01a105ac-50f4-7a52-8438-1e4f49530d55`; Mara: `01a105b7-690b-7673-b08b-7ecdaf1587f7`; Ivo: `01a105b7-690b-7621-b6d7-0b28adc41511`; Sera: `01a105b7-690b-77d2-90ce-82725ce7cc25`.

Three command errors were retained and corrected by the Custodian: a setup help request used a wrapper tool name containing `tools/`, and two metadata appends (one at setup, one while saving the bell inscription) parsed as YAML mappings rather than text. None drew dice or changed a mechanical value. No root intervention was sent during play. One bounded post-close transport intervention is recorded below.

## Completion, verification and costs

Final Custodian reply G021 ended at `2026-10-04T08:05:51.550540+00:00`; the first three closing responses completed at `2026-10-04T08:06:16.221705+00:00`. Elapsed from setup freeze through those responses: **64.70 minutes**. Custodian setup began at `2026-10-04T06:49:00.985664+00:00`.

The session closed with 10 recorded beats (4 + 6), 4 recorded perilous beats (2, 3, 4, 7), 21 dungeon turns, 1 PC roll, 0 Fatigue gained, 0 crises, 0 Luck spent and no Stamina loss. One milestone was awarded after beat 4. Sera recovered the register for the families, Ivo copied the inscription, and Mara obtained evidence to pursue rather than a definitive verdict. The bell remains for later salvage.

All 21 returned public bodies match the saved reply files, message record and checkpoint versions and appear in the public session log. The FINAL prompt requested receipt-only acknowledgements, but Mara and Sera added brief roleplay; Ivo acknowledged receipt. The root preserved those responses and delivered every peer's closing response verbatim in one additional archive batch, with no new game turn. All three then returned exactly `RECEIVED`. This is one post-close transport intervention, not an in-play ruling or state repair. Native traces and exact per-call inputs/outputs are preserved. The closing tracker has no pending action or active combat. The frozen scenario and policies still match their campaign copies. After the as-closed snapshot, the parent rebuilt the derived full agent prompt and validated the campaign (0 errors, 0 warnings); only `prompt.md` differs in the final snapshot. No mechanics were repaired.

Through the captured closing boundary there are 239 completed recorder receipts: 238 tool executions and 1 rejected wrapper request, with the three errors described above. The ledger also contains start records; those must not be counted as additional commands. The only new in-play draw is index 1, seed `131004001`; no retries or tie-break dice were consumed. Three subsequent parent commands produced the summary, refreshed the prompt and validated the final campaign.

Usage below is the last native cumulative counter for each role, including setup, resumed calls and the closing archive, **not a sum of cumulative counters**. Cached input is included in input; reasoning output is included in output. Counts are recorded runtime usage, not a bill or price estimate. Parent orchestration, preflight and P10 audit usage are excluded. Call-wall sums overlap across players and are not total elapsed time.

| Role | Calls | Input | Cached input | Output | Reasoning output | Summed call wall seconds |
|---|---:|---:|---:|---:|---:|---:|
| gm | 22 | 27,085,475 | 26,667,392 | 120,716 | 53,812 | 4018.92 |
| mara_venn | 23 | 1,709,928 | 1,601,792 | 2,868 | 1,241 | 451.95 |
| ivo_pell | 21 | 1,630,673 | 1,545,984 | 5,105 | 3,840 | 448.24 |
| sera_quill | 22 | 1,691,529 | 1,580,800 | 5,114 | 3,687 | 449.03 |

Raw token counters, native context/model records and trace hashes are in `closeout_checks.json`; timings in `role_costs.json`. The independent native transport/access verification is in `independent_evidence_checks.md` and `.json`. Fable's rules audit is in `audit.md`; the post-audit response in `report.md` records accepted errors and one remaining interpretation disagreement.

After Fable identified duplicate Markdown blocks, the parent regenerated the transcript from all 81 unique `messages.jsonl` rows, preserving exact bodies and the closing archive note (82 section headings total). The Custodian and relay had both appended to the original Markdown file from G009 onward. The faulty export is preserved in `transcript_before_audit_correction.md`, with repair hashes and native append-call evidence in `transcript_audit_correction.json`. Raw messages and campaign snapshots were not changed.

The closing archive finished at `2026-10-04T08:10:33.400931+00:00`, **68.99 minutes** after setup freeze. `closing_archive_delivery.json` records the six peer deliveries and literal acknowledgements; original pre-archive checks and costs are preserved separately. `closeout_checks.json` now includes the three parent post-close commands; use `closeout_checks_before_archive.json` for the 239-command original boundary.

**Custodian context limitation:** native evidence shows reads of the aggregate personal memory registry containing prior Hazardry pilot and audit summaries, at setup and near closure. The CLI role had a fresh history, but was not blinded to historical project observations. Do not describe this as strict Custodian context isolation. No player file/tool access or transfer of those registry extracts to players was observed; exact accesses are documented in the independent evidence check.
