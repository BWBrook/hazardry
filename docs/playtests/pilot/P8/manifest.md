# P8 — Free Traders pilot manifest

Status: completed and frozen; independent rules audit pending. Revision 5, rules/harness pin 7cc705c4b02971817b7996113193439027f9fbd8. Cross-checked against origin/main; 174 tests passed before setup. Orchestrator Astra does not adjudicate. All table roles are separate fresh persistent Codex CLI sessions, gpt-6-sol with medium effort, with no inherited campaign history. Complete CLI events/native role traces are retained for later audit. Access is instructed, not OS-enforced.

Master gameplay seed 81004; Nth new dice command uses 81004000+N; retry same event ID and seed only. Roster fixed before seeded generation; no outcome selection or score edits. Standard six-point creation budget with one free Knack and Expertise each. Modules: Injury, gritty, Wealth, quick ship-to-ship combat and missiles off. Ordinary personal combat remains available.

- **Kest Vale**, Astrogator and pilot, generation seed 810041, primary bias EDU; Scout Surveyor; Pilot (DEX). Drive: Keep the Wayward Sun free and bring every crewmate home with a paid berth ahead. Temperament: Bold: accepts a dangerous jump or exposed manoeuvre when it can save the crew or a stranded traveller; will not knowingly abandon someone to vacuum.
- **Rook Fen**, Engineer and EVA specialist, generation seed 810042, primary bias EDU; Salvage Rat; Engineer (EDU). Drive: Keep the ship serviceable and prove that patient repairs can beat a creditor's replacement bill. Temperament: Cautious and methodical: checks the failure path before committing, but will enter a dangerous compartment to avert a larger loss; will not disable life support around occupied berths.
- **Mira Quill**, Broker and watch officer, generation seed 810043, primary bias SOC; Merchant Broker; Liaison (SOC). Drive: Make the crew's next job pay enough to preserve their independence without selling out the people who trust them. Temperament: Opportunistic negotiator: risks Ship Shares, reputation and personal Fate for a worthwhile bargain, but will not trade an unwilling person or conceal a lethal danger from a buyer.

Ship/loadouts and gear scope: playtests/runs/P8/roster_setup.json. Public ship clocks start at zero; Ship Shares 2. Public packets contain the three core texts, entire player-facing skin including crisis table, own export, own drive/temperament, reviewed gear/Knack and shared ship/crew roles. No other character instructions or private scenario. Exact hashes in packet_manifest.json and freeze.json. Frozen scenario/policies and initial snapshot are in playtests/runs/P8/. Freeze UTC 2026-10-04T01:45:29.745379+00:00.

The passive run_table.py relay extracts the actual CLI-returned PUBLIC body, independently saves it, compares it to the saved checkpoint and keeps a historical copy before forwarding. It batches addressed player calls with no pending-answer disclosure, then delivers exact labelled completed answers to the Guildmaster. Each player receives all queued completed public dialogue before another decision. Parsing errors, mismatches and protocol caps stop the relay for inspection; it gives no game rulings. Every CLI call stores exact input, final output, event stream, status and timestamp. Cumulative native usage must not be summed across turns. Results and costs follow below.


## Frozen evidence and policies

Scenario: `playtests/runs/P8/frozen_hidden_scenario.md`, SHA-256 `5cb8c318b2e6d97385f5d25cac88c223040c90e62d9a7391555209a69e61a1d5`. Policies: `playtests/runs/P8/policies.md`, SHA-256 `72c5862171ada7e5a3f7fd5e212a9852715ea06616c0a59d9a58548836533462`. Both remain byte-identical at closure.

Fate tests were reserved for blind chance. Shared hazards were charged once per distinct occurrence per beat, with core triggers additive to skin triggers; twenty minutes of threatened work was the declared ambient trigger, separate from ten-minute patrol ticks. Purges required a stated, earned fictional reprieve or sacrifice, not automatic arrival. No Fate test or purge occurred. The complete frozen policies retain cargo, net payment, resource and jump conventions.

Packet hashes:

| Player | SHA-256 |
|---|---|
| Kest | `8993d1dfc99046f8b2076dd8b2f61fe4a7eef293d51429dd2b6d60ba22d26f89` |
| Rook | `868bcfa083f78459c7e0060b7585751874e4b44457dbf8c8922f0687541f9fee` |
| Mira | `bf2b231acf35c22be3cd6ea731a397c1b16b60769fe0f0f51544c150bc7ef98b` |

Role sessions (each fresh, persistent `gpt-6-sol`, `model_reasoning_effort="medium"`; confirmed by every retained native turn context): Guildmaster `01a10492-534a-7ae2-98b7-546202b05d7c`; Kest `01a10493-2aaf-7ce0-8ef0-204bb42b339d`; Rook `01a10493-2aa1-7d42-8ede-e22660913649`; Mira `01a10493-2aa1-7e33-b28a-596d54e869b1`. The CLI role sessions were launched from the local shared workspace; no OS access isolation is claimed. The orchestrator was the existing Astra Codex chat; its exact model ID, reasoning setting and allocated task cost were not measured in this run.

All three player native traces contain zero tool calls, including setup and final receipts. The Guildmaster's complete native trace records 110 tool calls. `agent_calls/` retains exact inputs, outputs, CLI event streams, stderr and timestamped receipts for every invocation. `messages.jsonl` and the copied `transcript.md` retain eight public Guildmaster outputs, nineteen player decisions and three separately labelled closed-session receipts. The transcript intentionally excludes private routing and setup instructions.

## Timing and costs

All times UTC, 4 October 2026. Campaign setup began 01:37:24.516; Guildmaster setup invocation began 01:41:00.439. Initial state was frozen and play released 01:45:29.745. The final Guildmaster invocation ended 02:05:23.848; all closure receipts completed by 02:05:35.122. Play plus final receipts took approximately 20 minutes 5 seconds; campaign setup through receipts took 28 minutes 11 seconds.

Native counters below are the last cumulative counters for each role, including setup, all resumed turns and closure receipts. They are not sums of repeated cumulative samples. Cached input is a subset of input; reasoning output is a subset of output.

| Role | CLI invocations | Summed invocation wall seconds | Input tokens | Cached input | Output tokens | Reasoning output |
|---|---:|---:|---:|---:|---:|---:|
| Guildmaster | 9 | 1323.030 | 14,527,577 | 14,331,904 | 41,991 | 17,326 |
| Kest | 8 | 91.702 | 404,667 | 338,048 | 993 | 473 |
| Rook | 9 | 98.376 | 484,709 | 431,616 | 975 | 479 |
| Mira | 8 | 96.049 | 402,894 | 336,128 | 1,201 | 674 |

Invocation wall times include waiting and tool work, not just model compute. Player calls overlapped, so their times do not add to total elapsed time. Billed monetary costs, root/orchestration token usage and model compute times are unavailable. Exact counters and per-role timing are in `role_costs.json`; these measurements are not a complete cost estimate for the pilot.

## Closure and verification

Six beats, acts 4 + 2, five perilous; seven finalized PC rolls; no combat, Strain, crises, purge or injury. Fate spending 3, recovery 2. One milestone per character after beat 4; all purchased one attribute increase before close. Final ship: Fuel 1/4, Hull 0/6, Debt 0/6, Medkit 0/4, Shares 3 and Strain 0. Final Fate: Kest 9/10, Rook 11/11, Mira 10/10. Final attributes purchased: Kest EDU 14, Rook EDU 11, Mira SOC 14.

Zero in-play orchestrator interventions, stalls or replayed dice commands. Recorder: 95 commands, zero failures; gameplay draws 1–7 use seeds 81004001–81004007. Every actual returned public body equals the corresponding historical checkpoint, the Guildmaster's saved body and the transcript message; all eight appear in the public log. The scenario and policies were unchanged.

`initial/` preserves the setup snapshot; `as_closed/` was copied before any parent prompt refresh. The parent rebuilt the derived prompt with the original `--mode agent --full`; final validation passed with no errors or warnings. This produced no byte changes because the Guildmaster had already refreshed the prompt. `final/` and `final_snapshot_hashes.json` preserve the verified final copy. Session is closed, with no pending action or active combat. `summary.json` is the unmodified `playtest_summary.py --json` output. Raw records, native traces and scripts remain in the ignored run folder for Fable; the source pin and this manifest identify the experiment independently of later report commits.

A separate read-only delegate independently replayed every relay input from message/cursor history and verified the checkpoint, access, role-setting and seed claims above; no inconsistency was found. Its bounded evidence-integrity note is retained as `playtests/runs/P8/independent_integrity_check.md`. This does not replace Fable's rules and leakage audit.
