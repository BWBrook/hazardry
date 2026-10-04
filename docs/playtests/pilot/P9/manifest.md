# P9 manifest

| Field | Value |
|---|---|
| Run | P9, pilot protocol revision 6 (the second tranche, round 5) |
| Rules commit | `36d644f` (rules unchanged since `b89ad90`) |
| Skin | Briar & Benedictine (`briar_benedictine`), grim tone (0 build points, the skin's suggestion); Sin is shared Pressure. The optional plug-ins Insight, Herbal poultice and Vow-break were in use. |
| Scenario | The Custodian's own mystery, *The Winter Tally* (Wyckmere Abbey, December 1142). Frozen as `playtests/runs/P9/frozen_hidden_scenario.md`, SHA-256 `e5ee6b36a8081a704351f3479b0b8d547eb9904b76009cd45b7e1baf3a3c2233`; policies SHA-256 `9fbbe72fa26b09194513ba1fc47b81886b3562030ba6bca10275bce4aee1e642` |
| Modules | none |
| Orchestrator | Fable (`claude-opus-5-5`), not seated |
| Custodian | a fresh subagent, `claude-sonnet-5-5`, Claude Code general-purpose agent, default settings |
| Players | two fresh subagents, `claude-sonnet-5-5`, same settings, one per character |
| Master seed | 109 (seeds 109001–109019; the tie-break d6 drew 109009; 109013 was used twice by a Custodian slip, see the report) |
| Access | instructed, not enforced; checked against the full tool trace |
| Date | 4 October 2026; agents launched 04:13 UTC, play 04:21–05:07 UTC (about 46 minutes) |
| Outcome | complete: 12 beats, 2 acts (7 + 5), session closed |

## Roster

Both characters were built by `gen_character.py --campaign` at the grim budget. Scores were not adjusted and no seed was redrawn. The LOR bias is only a weight and did not produce a Lore character, so the concepts were fitted to the scores. The skin has no knacks.

| Character | Seed, bias | HEW | FLT | LOR | MCY | Providence | STM |
|---|---|---|---|---|---|---|---|
| Brother Anselm Gray, almoner | 1091, LOR | 9 | 10 | 8 | 12 | 7 | 6 |
| Sister Hawise of Ely, guest-house sister | 1092, MCY | 9 | 6 | 8 | 13 | 9 | 6 |

The orchestrator added gear with `update_sheet.py` before play:
- Anselm: staff, cowl, almoner's satchel, almonry key, candle, rosary;
- Hawise: cowl, guest-house keys, rosemary and yarrow, wax tablets, a hidden dagger (+1), rosary.

**Drives and temperaments:**
- **Anselm.** Drive: "Protect the poor who come to the abbey gate, and find whoever is preying on them." Temperament: cautious and merciful. He will not accuse anyone without proof from three sides; he never betrays a confidence given at the almonry gate.
- **Hawise.** Drive: "Learn what the abbey's powerful men are hiding, even from the Abbot himself." Temperament: bold. She presses suspects to their faces and goes where she is forbidden; she never lies under oath.

## Packets and access

Each packet contains:
- the drive and temperament;
- the public export;
- reviewed notes (no knack; plug-ins in use; Sin is shared);
- a one-line description of the companion;
- the Quickstart, The Adventurer and the Adventurer's Manual;
- skin lines 1–71: the player section with its plug-ins;
- skin lines 92–120: the Sin track, its triggers, purge rules and crisis table, which sit in the Custodian section of the book.

| Packet | Words | SHA-256 |
|---|---|---|
| `packet_anselm.md` | 5,947 | `165534cd3954fb1df17e8ae1edce6b4bd90b3ceaafc5eee0e922c08ed83bd31e` |
| `packet_hawise.md` | 5,936 | `6a77266f9fffd919554cf0b6017428cadc5f5f4383c491db94b23feb0e741001` |

The tool trace (`playtests/runs/P9/tool_trace.jsonl`):

| Agent | Tool calls |
|---|---|
| Custodian | 94 Bash, 2 Write (its own scenario and policies) and 28 hand-backs. No call touched `playtests/runs/`, `docs/playtests/` or `campaigns/`. |
| Each player | 1 Read (their own packet), then hand-backs only |

## Custodian policies

These were declared before play, in `policies.md`. They cover:
- Providence tests;
- purges;
- Sin triggers, from the skin and Almanac 4 combined;
- one named cost per failed clue test;
- the step-3 open-defiance toll;
- Insight, interrogation, damage and milestones.

## Interventions

- **Setup.** Players were told to read their packet once and reply "Ready". The Custodian wrote its scenario, then was told "Your scenario and policies are frozen as written. Open session play now."
- **In play.** There was no orchestrator message beyond verbatim relay. Queued answers and Custodian replies were delivered in order to any player not due to answer. The closing body was delivered to both players, each of whom gave one closing line in character.
- **At close-out.** `validate_campaign.py` reported a stale prompt, because the Custodian had edited the run-log line of the campaign's copy of the scenario after its last rebuild. `as_closed/` was preserved first. The orchestrator then rebuilt the derived prompt with default options, and validation passed.

## Relay and records

The orchestrator saved each public body to `replies/gm_NNN.md` and compared it with the campaign's `last.md`. It copied each `last.md` to `checkpoint_versions/gNNN.md` before comparing, and all 27 matched. Player answers are in `replies/pNNN_<name>.md`. Each player's exact incoming messages were extracted from their subagent transcript into `incoming_<name>.jsonl`. The public session log was written throughout.

## Costs

Input tokens are from the stored subagent transcripts. Output tokens are unreliable there and are omitted.

| Role | Replies | Written to cache | Read from cache |
|---|---|---|---|
| Custodian | 27 (plus the scenario-writing turn) | 334k | 26.2M |
| Anselm | 23 answers, "Ready" and a closing line | 149k | 2.2M |
| Hawise | 24 answers, "Ready" and a closing line | 149k | 2.2M |
| Orchestrator | n/a | unavailable | unavailable |

Billed money is unavailable.

## Files

**Committed in this folder:** `manifest.md`, `transcript.md`, `summary.json` and `report.md`, and `audit.md` (Astra) when it is done.

**Kept in the ignored `playtests/runs/P9/`:**
- `initial/`, `as_closed/` and `final/` campaign state;
- the frozen scenario and policies;
- the packets and public exports;
- the briefs;
- `replies/`, `checkpoint_versions/` and `checkpoint_checks.jsonl`;
- `incoming_*.jsonl`;
- `tool_trace.jsonl`;
- `orchestrator_notes.md`.
