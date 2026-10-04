# P10 manifest

| Field | Value |
|---|---|
| Run | P10, pilot protocol revision 7 (second tranche, round 6) |
| Rules commit | `110106d` (rules unchanged since `b89ad90`) |
| Skin | Service Duct Blues (`service_duct_blues`), standard tone (6 build points, the skin's suggestion); Stress is shared Pressure |
| Scenario | The Custodian's own episode, *Hot Loop* (UEV Marigold Ascent, Deck 9). Frozen as `playtests/runs/P10/frozen_hidden_scenario.md`, SHA-256 `a0203737516058a1941ae5fa22c3ea75775109cfe1c8a4c86ec90f6ba080f164`; policies `42d6f3aecee420143389afa923e5bb8a308373737c104b378bfa8ca8d07a31a9`; public fuse mapping `ecb35e6bcf255dd63b7e4c5337068cd546cf4799bdb3f216907158649c6b8218` |
| Experimental variant | **Fuse mapping (revision 7, setup step 4; Barry-approved direction, not adopted rules).** The frozen scenario overrides the additive default: the core triggers feed Stress only in the declared shipboard forms below, and risky rituals are excluded. The skin's printed triggers stand. |
| Modules | none |
| Orchestrator | Fable (`claude-opus-5-5`), not seated |
| Custodian | a fresh subagent, `claude-sonnet-5-5`, Claude Code general-purpose agent, default settings |
| Players | three fresh subagents, `claude-sonnet-5-5`, same settings, one per character |
| Master seed | 110 (seeds 110001–110014, in order, no gaps or reuse; two tie-break dice were offered and declined, so their reserved seeds passed to the next real roll) |
| Access | instructed, not enforced; checked against the full tool trace |
| Date | 4 October 2026; Custodian launched 06:41 UTC, scenario frozen 06:47, play 06:49–07:31 UTC (about 42 minutes) |
| Outcome | complete: 10 beats, 2 acts (6 + 4), session closed |

## Roster

All three were built by `gen_character.py --campaign` at the standard budget. Scores were not adjusted and no seed was redrawn. Imre's SYS bias is a weight, and his HAR came out higher, so the concept was fitted to the scores. The skin has no knacks and no tags were bought.

| Character | Seed, bias | MSC | REF | SYS | HAR | RES | STM |
|---|---|---|---|---|---|---|---|
| Crewman Imre Vass, maintenance crewman | 1101, SYS | 10 | 10 | 11 | 12 | 10 | 5 |
| Medtech Sefa Rahim, medical technician | 1102, HAR | 10 | 8 | 10 | 13 | 10 | 6 |
| Specialist Jun Kowal, security and operations | 1103, REF | 10 | 13 | 10 | 10 | 10 | 5 |

Gear was added with `update_sheet.py` before play:
- **Imre:** engineering kit (edge 0), torque wrench (+1), coveralls (soak 1), hand scanner; headlamp, sealant foam, chit case.
- **Sefa:** field medkit, coveralls (soak 1), medical scanner, stun baton (0); burn gel, spare comm badge, chit case.
- **Jun:** beam sidearm (stun +1, lethal +2), tactical vest (soak 2), stun baton (0), security comm; restraint ties, a logged security-door fob, chit case.

Drives and temperaments:
- **Imre.** Drive: keep the lower decks breathing and fed. Temperament: steady and pragmatic; he never falsifies a maintenance log.
- **Sefa.** Drive: get every casualty to sickbay alive, and find out why the injuries don't match the incident reports. Temperament: cautious about procedure and fierce about patients; she never leaves a patient to save herself.
- **Jun.** Drive: earn a place on the away-team roster. Temperament: bold; he never fires lethal where crew could be hit.

## The experimental fuse mapping

Frozen with the scenario; the player-facing version was in every packet.

| Core trigger | Verdict | Shipboard form |
|---|---|---|
| Time passing under threat | narrowed | "The deadline lapses": +1 once per act, when an announced Command deadline passes with the threat standing |
| Desperate bargains | included | "Off-book deals": borrowed authority, traded access, covering a breach, promises you cannot keep; fair favours between crew are free |
| Taboo acts | included | "Breaking the log": falsifying or deleting records, abandoning a post or patient, unauthorised entry; at most one per beat |
| Noisy heroics | narrowed | "In the public eye": open channel, crowded space or in front of the brass; at most one per beat |
| Risky rituals | excluded | none in this skin; the step-4 toll covers risky tests |
| Big blunders | included | "Failure on the record": a failed test that hurts a crewmate, damages a system or sets off an alarm, once seen or logged |

## Packets and access

Each packet contains:
- the drive and temperament, and the public export;
- reviewed notes (no tags; Operations and Scanner open to all; Stress shared, experimental mapping below);
- one-line descriptions of the crewmates;
- the Quickstart, The Adventurer and the Adventurer's Manual;
- skin lines 1–99, the player section;
- skin lines 106–136, the Stress track, its triggers and crisis table, which sit in the Custodian section of the book;
- the public fuse mapping.

The packets were inspected before launch (own sheet, crewmates, skin boundaries, no Showrunner advice or scenario content) and hashed (revision 7 setup step 6).

| Packet | Words | SHA-256 |
|---|---|---|
| `packet_imre.md` | 6,890 | `df576324d857ad0100fc58bebda878c32ebad16ac34729eb8ef6f4004f65d920` |
| `packet_sefa.md` | 6,900 | `c7f4187c148441c8d4125e0377648e4586a28790aa97e8197a1dd89f242b077d` |
| `packet_jun.md` | 6,895 | `955b7afc99546986ebcb6e0247383a0996abbd1808b84b84d8df13a153c5794e` |

Tool trace (`playtests/runs/P10/tool_trace.jsonl`):

| Agent | Tool calls |
|---|---|
| Custodian | 87 in total: Bash, Write and Read on the repository, its campaign and its own notes, plus hand-backs. **One access deviation:** at 06:55 a shell command listed the first three file names in `playtests/runs/P10/` (`ls … | head -3`) while it checked a failed append of its own; it read no file there. Nothing touched `docs/playtests/` or `campaigns/`. |
| Each player | 1 Read (their own packet), then hand-backs only |

## Custodian policies

Declared before play in `policies.md`:
- "Test your Resourcefulness": at most two, for pure chance only (none was called);
- Stress reduction: a spotless inspection and a captain's commendation, −1 each, conditional; no shore leave this episode;
- triggers under the mapping, including the safety regs;
- failure costs, time-sensitive repairs (step 2), risky tests (the step-4 toll), and perilous beats.

## Interventions

- **Setup.** The Custodian wrote its scenario, public mapping and policies (phase 1), then was told the files were frozen with their hashes and to open play. Players read their packet once and replied "Ready".
- **Relay notes.** When a reply went to a subset of players, the relay to the Custodian carried one factual line saying which players had the reply queued (first at P002, recorded as intervention 1; thereafter a standard header). At G003 the Custodian's public text repeated it ("you have not yet seen what Imre suggested").
- No other orchestrator message beyond verbatim relay. Every public body, including the closing one, was delivered to all three players, who each gave a closing line.

## Relay and records

- Each public body was saved to `replies/gm_NNN.md` and compared with the campaign's `last.md`, which was first copied to `checkpoint_versions/gNNN.md`. All 20 matched.
- Every relay to a player was composed by `relay.py` from `transcript.md` with a per-player cursor and saved to `incoming/<player>_NNN.md`, with its SHA-256 in `incoming/log.jsonl` (51 deliveries). After the run, each saved delivery was compared with the player's actual incoming message from the subagent transcript (`incoming_<player>.jsonl`): all 51 matched.
- `seeds.py` checked the draw index against the session log after each dice turn; the final check shows 110001–110014 in order, no reuse.
- The public session log was written throughout. The campaign copy of the hidden scenario was unchanged at close. `validate_campaign.py` returned ok; `as_closed/` and `final/` are identical.

## Costs

Tokens from the stored subagent transcripts. Output tokens are unreliable there and are omitted.

| Role | Replies | Written to cache | Read from cache |
|---|---|---|---|
| Custodian | 20 (plus the scenario-writing turn) | 505k | 32.1M |
| Imre | 19 answers, "Ready" and a closing line | 104k | 3.6M |
| Sefa | 15 answers, "Ready" and a closing line | 189k | 3.2M |
| Jun | 14 answers, "Ready" and a closing line | 188k | 3.9M |
| Orchestrator | n/a | unavailable | unavailable |

Billed money is unavailable.

## Files

**Committed in this folder:** `manifest.md`, `transcript.md`, `summary.json`, `report.md`, and `audit.md` (Astra) when it is done.

**Kept in the ignored `playtests/runs/P10/`:**
- `initial/`, `as_closed/` and `final/` campaign state;
- the frozen scenario, policies and public fuse mapping;
- the packets, public exports and briefs (`custodian_setup_prompt.md`, `custodian_brief.txt`, `player_brief.txt`);
- `replies/`, `checkpoint_versions/` and `checkpoint_checks.jsonl`;
- `incoming/` (composed deliveries, hashes, cursors) and `incoming_<player>.jsonl` (as received);
- `relay.py`, `seeds.py`, `build_packets.py`, `check_reply.sh`, `add_player.sh`;
- `tool_trace.jsonl` and `orchestrator_notes.md`.
