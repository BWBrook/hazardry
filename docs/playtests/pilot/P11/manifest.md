# P11 manifest

| Field | Value |
|---|---|
| Run | P11, pilot protocol revision 8 (second tranche, round 7) |
| Rules commit | `7690e82` (rules unchanged since `b89ad90`); harness entry `core` added in `a2ce6f1` |
| Game | The Hazardry core with no skin, through the play-only manifest entry `core` and `skins/core.md` (default names MGT, REF, INT, EMP, LCK; plain Pressure, Almanac 4; additive core triggers; no experimental mapping) |
| Modules | Condition Tracks (Radiation only, per character) and Wealth & Attention (one party Wealth), Almanac 7 and Toolkit Part II H. All others off. |
| Scenario | The Custodian's own, *The Blue Stack* (Ferrous Gap and the Glass). Frozen as `playtests/runs/P11/frozen_hidden_scenario.md`, SHA-256 `ba10e5930db4403f7a7f63738b03ec781f9e00311657aa96539c1dae374a7124`; policies `a7696b101aa9ccf107d8a3cf083ab384a52caaa1bd5f366fd19e584a25e97897` |
| Orchestrator | Fable (`claude-opus-5-5`), not seated |
| Custodian | a fresh subagent, `claude-sonnet-5-5`, Claude Code general-purpose agent, default settings |
| Players | three fresh subagents, `claude-sonnet-5-5`, one per character |
| Master seed | 111 (seeds 111001–111005, in order, no gaps or reuse; 111004 was a mistaken roll, see the report) |
| Access | instructed, not enforced; checked against the full tool trace |
| Date | 4 October 2026; Custodian launched 09:11 UTC, scenario frozen 09:22, play 09:23–10:07 UTC (about 44 minutes) |
| Outcome | complete: 7 beats, 2 acts (3 + 4), session closed |

## Why a harness change came first

The Manual allows playing "the core with the default names" (2.4), but every tool needed a manifest skin entry, and `campaign_init.py --skin core` failed. With Barry's approval, `a2ce6f1` added a play-only `core` entry and a short `skins/core.md` play sheet. The sheet adds no rules. It is excluded from the release bundles and the published-sample checks, and all 174 tests pass. Astra is asked to review it with this audit.

## Roster

All three were built by `gen_character.py --campaign` at the standard budget, with no adjustments and no re-draws. The primary bias is a weight; Dell's EMP bias produced a flat 11/11/11.

| Character | Seed, bias | MGT | REF | INT | EMP | LCK | STM |
|---|---|---|---|---|---|---|---|
| Dell Okonkwo, broker | 1111, EMP | 10 | 11 | 11 | 11 | 10 | 5 |
| Rue Calder, runner | 1112, REF | 11 | 12 | 10 | 10 | 10 | 5 |
| Hollis Marr, mechanic and radiation tech | 1113, INT | 11 | 10 | 12 | 10 | 10 | 5 |

Gear followed the Manual's 6.1–6.2 tables (edges +1 or +0, soak 1), with a dosimeter badge each, Rue's respirator, rope and flares, and Hollis's counter and three iodine tablets.
- **Dell.** Drive: clear the crew's debt. Temperament: cautious and calculating; he never sells out a client or a crewmate to settle a debt.
- **Rue.** Drive: the haul that buys a way out. Temperament: bold; she never leaves anyone behind in the Glass.
- **Hollis.** Drive: keep the counters honest. Temperament: steady and methodical; he never fakes a reading.

## Setup (revision 8)

- **Contradiction check before the freeze (setup step 5).** I sent four points back to the Custodian, which resolved them before freezing:
  - the hour-4 collision of two clocks;
  - the opening flare distance disagreeing with its clock;
  - ambiguous sale arithmetic;
  - two unstated standing costs: the natural-20 Pressure rule, and the lethal smuggling consequence, which is now telegraphed by signs.
- **Packets.** Each packet holds:
  - the drive, temperament and public export;
  - the crewmates' names;
  - the Quickstart, The Adventurer and the Manual;
  - `skins/core.md`;
  - the printed Condition Tracks and Wealth & Attention text;
  - the Custodian's declared module details.

  I removed one sentence from the Custodian's summary because it gave the hidden rival clock's rate and order. I also reworded the Attention line so that it does not name the hidden Heat clock. The packets were inspected before launch.

| Packet | Words | SHA-256 |
|---|---|---|
| `packet_dell.md` | 6,492 | `742681024be171e0ea0aff9468f4554890c8827d5317d1981bd5b2e8c9080585` |
| `packet_rue.md` | 6,490 | `d786fc9d57f17d7af1faf771902c922584180ed0c623ff5e0a8617a67c7d09ad` |
| `packet_hollis.md` | 6,486 | `2ac6a202e0ef6dc954aa06b42b1a4a24d8a99f2f205dbdd5c60ec97275527bc9` |

## Tool trace

| Agent | Tool calls |
|---|---|
| Custodian | 73 Bash, 3 Read, 2 Write, 2 Edit, 21 hand-backs. All reads were of rules, the handbook and its own campaign; all writes and edits were to its own scenario and policies, and to draft files in the session scratchpad. **One access deviation:** at 09:11, before play, `ls playtests/runs/P11 \| head` listed file names in the run folder; it read no file there. |
| Each player | 1 Read (their own packet), then hand-backs only |

## Interventions

- **Setup.** One pre-freeze contradiction message (the four points above), and the "frozen, open play" message, which also told the Custodian about the packet edit.
- **In play.** None beyond verbatim relay. When a reply went to a subset of players, the relay to the Custodian carried one line on which players had it queued.
- **Closing (revision 8, turn-loop step 6).** The closing body went to all three, each of whom gave one closing line. The three lines were then relayed once as an archive, and each player replied "Received".

## Relay and records

- **Checkpoints.** All 19 public bodies matched their checkpoints. Each checkpoint version is kept. The Custodian re-saved two checkpoints after correcting a word (G011, G015) and noted each correction in the public log; the matched versions are the corrected ones.
- **Relays.** All 45 deliveries, the archive included, were composed by `relay.py` from `transcript.md`. Each matches the subagent's actual incoming message exactly (`incoming_<player>.jsonl`).
- **Transcript.** Only the orchestrator wrote it.
- **Seeds.** `seeds.py` checked the draw index after every dice turn.
- **Snapshots.** The frozen scenario and policies are unchanged at close, and `validate_campaign.py` returns ok. `as_closed/` and `final/` are identical, both taken after the session closed.

## Costs

Tokens are from the stored subagent transcripts. Output tokens are unreliable there and are omitted.

| Role | Replies | Written to cache | Read from cache |
|---|---|---|---|
| Custodian | 19 (plus the scenario turn and its revision) | 864k | 36.0M |
| Dell | 16 answers, "Ready", a closing line and a receipt | 120k | 4.6M |
| Rue | 12 answers, "Ready", a closing line and a receipt | 353k | 3.1M |
| Hollis | 11 answers, "Ready", a closing line and a receipt | 356k | 2.8M |

## Files

**Committed in this folder:**
- `manifest.md`, `transcript.md`, `summary.json` and `report.md`;
- `audit.md` and `core-harness-review.md` (Astra).

**Kept in the ignored `playtests/runs/P11/`:**
- the `initial/`, `as_closed/` and `final/` campaign states;
- the frozen scenario and policies;
- `modules_public.md`;
- the packets, public exports and briefs;
- `replies/`, `checkpoint_versions/` and `checkpoint_checks.jsonl`;
- `incoming/` (deliveries, hashes and cursors) and `incoming_<player>.jsonl`;
- the scripts `relay.py` (now with closing and archive modes), `seeds.py`, `build_packets.py`, `check_reply.sh` and `add_player.sh`;
- `tool_trace.jsonl` and `orchestrator_notes.md`.
