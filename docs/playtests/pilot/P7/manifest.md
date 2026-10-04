# P7 — Iron & Ruin pilot manifest

Status: **complete**, two acts and session closed at G025. Fable's independent cross-team audit is pending. Records remain uncommitted for Barry's review.

## Configuration and roster

- Protocol revision 4; rules/harness/protocol commit `849a8e0982ecb4f59d5e108b38728fb55a6afe07`, verified against origin/main before play. Protocol SHA-256 `70ad97259c177d8017a3b23e4fe3ed7f1b50e1b7f8d032c8db2ff2dec35b024d`.
- Skin: Iron & Ruin, solo, pulp budget 12. Injury, gritty and Wealth off.
- Orchestrator: Astra, not seated. Exact root model/settings unavailable through the collaboration API.
- Custodian: fresh `gpt-6-sol`, reasoning `medium`, `p7_custodian`, no inherited conversation history.
- Player: fresh persistent Codex CLI session `01a10411-b9dd-7d03-9fd8-01c71a1467bd`, `gpt-6-sol`, reasoning `medium`, verified from native `turn_context`. It received only the frozen packet as game material, then public narration. Global CLI instructions still apply; no prior campaign history was inherited.
- Sera Ash: seed 710041, WIL bias and bought `Exiled temple sorcerer` tag fixed before generation. Initial BRN 10, AGI 11, CUN 10, WIL 14, FOR 10, Stamina 5. All 12 build points used; no rerolls or score adjustments.
- Drive: Break the cult's hold over people it treats as property; seize enough power to remain free herself.
- Temperament: Bold and impatient: risks her own blood and forbidden sorcery to break a threat, but will not sacrifice an unwilling innocent or knowingly abandon a captive she can still reach.
- Fixed loadout: broadsword (edge +1), leather jerkin (soak 1), ritual bundle, rope, food/waterskin bundle; five substantial items. Small gear and eight silver in `roster_setup.json` and initial sheet.
- Reviewed sorcery: Exiled temple sorcerer: trained in the skin's four tiers. Known practices include Ember Breath (Whisper: kindle a small flame), Ashen Veil (Weave: hide from one watcher for a heartbeat), Cinder Bolt (Weave: sorcerous bolt, edge +2), and Break the Bronze (Wrack: shatter an iron or bronze barrier). Wyrd effects may be proposed under the printed tier rules; no automatic grant of success or added mechanical bonus. The bought tag gives Advantage only when its specific training fits the action, as judged from fiction.
- Master gameplay seed 71004. Twelve new dice commands used 71004001–71004012 in order; no failed dice command or redraw. Generation seed is separate.

## Freeze and access

Scenario *The Bell Beneath the Gate* and initial state were frozen before opening at 2026-10-03T23:21:24.938323+00:00.

- `playtests/runs/P7/frozen_hidden_scenario.md`, SHA-256 `3c2d8cdab489bda2dd43500671eb1802aae3aa52cc73e4d3e42705750783dca2`; final scenario is byte-identical.
- `playtests/runs/P7/policies.md`, SHA-256 `556323bcbba1bf7fb7f1ff91c90bb931dce84bf142235f117c580fa7d725f12c`. Fortune tests are for pure chance; purges require a declared fictional cost; a shared hazard is charged once per distinct exposure per beat; clocks and Doom have separate triggers. Exact policies are retained for audit.
- `playtests/runs/P7/packet_sera_ash.md`, SHA-256 `30059a73b0eec93853d42ddff1d47fea729a7e64b86c9f2fa4181a3bdc823132`. Includes Quickstart, The Adventurer, Adventurer's Manual, public Iron & Ruin sections excluding Doom crisis table and Custodian advice, reviewed equipment/sorcery, drive/temperament and public export. The printed sorcery backlash table remains in the player-facing sorcery section.
- Access is **instructed, not enforced**. The packet was embedded verbatim in `cli_player_initial.txt`; no file-read tool was required. Player instructions forbid all tools/files. Its full native trace records zero tool calls, including setup and final receipt. This supports compliance, not OS isolation. No full native Custodian trace was available; its recorded harness calls are retained, not represented as an exhaustive access trace.
- Two collaboration-player spawn attempts failed with `agent thread limit reached`, with completed P6 histories occupying slots. A fresh CLI session avoided reusing those histories. No global configuration was changed. Barry was asked about raising capacity before the working alternative was found; play did not depend on an answer.

## Times and costs

- Setup preparation recorded: 2026-10-03T23:16:42.842158+00:00. CLI player ready after its fresh setup invocation at 2026-10-03T23:20:35 UTC.
- First public checkpoint comparison: 2026-10-03T23:22:39.678990+00:00.
- Session-close receipt: 2026-10-04T00:05:22.277019+00:00.
- Final public checkpoint comparison: 2026-10-04T00:06:08.649104+00:00; about 43.5 minutes from first comparison, including orchestration and tool latency.
- Player native cumulative totals, including READY and closed-session receipt: 1,778,663 input tokens, of which 1,674,496 cached; 4,541 output tokens, including 3,346 reported reasoning tokens. The uncached input difference is 104,167. `turn.completed` totals are cumulative and were **not summed across turns**.
- Twenty-five resumed player invocations took 303.1 seconds in aggregate wall time, including process/network overhead; this excludes initial setup and is not model compute time.
- Custodian/root token usage and compute time, and all billed monetary costs, are unavailable. Player usage is not a whole-run cost estimate.

## Completion and evidence

- Eight beats, acts 4 + 4; all eight marked perilous. Ten finalized PC rolls; one combat; twelve dice commands including initiative and an NPC-only opposition.
- Fortune: ten spent (nine nudges, one Heroic Act), minimum zero in act one, ten recovered at first milestone. Two milestones raised WIL 14→15→16 while the session was open. No points remain.
- Doom: two gained (one threatened-time exposure, one successful Wrack), final two; no crisis, backlash, purge or red-line window. The Doom-2 one-test penalty was applied and consumed.
- Final Sera: Stamina 4/5, Fortune 10/10, WIL 16; Heroic Act used. Captives escaped; sealed ledger with Nima; Varkos at large. Dawn Tithe 5/6, retired in fiction in the recap.
- Twenty-five public Custodian replies, twenty-four in-play player replies, and one closed-session receipt. Setup READY is retained separately. No in-play orchestrator intervention, rule correction, state edit or pacing prompt; only verbatim relay.
- Every received public body was independently transcribed from the Custodian's returned block, saved under `received/`, compared before delivery, and retained alongside `checkpoint_versions/`. All 25 compare byte-for-byte with both checkpoint versions and GM body files; all occur in the campaign's public Markdown session log.
- Recorder: 159 calls through final validation, including help/setup/summary calls. Two failures: relative campaign path rejected before generation; invalid `roll.py d20 --help` query. Neither drew dice or altered state.
- `initial/` and `as_closed/` preserve pre-play and exact closed campaign state. Parent rebuilt only the derived prompt with original `--mode agent --full`; final validation passed. `final/` and `final_snapshot_hashes.json` preserve the validated copy. `summary.json` is unmodified `playtest_summary.py --json` output.
- Additional evidence: `commands.jsonl`, `messages.jsonl`, `player_calls.jsonl`, per-turn player JSONL/stdout, `player_native_trace.jsonl`, `closeout_checks.json`, frozen packet/scenario/policies, and original receipts/logs. Native trace contains the player's system context and should remain in the ignored auditor evidence folder.
