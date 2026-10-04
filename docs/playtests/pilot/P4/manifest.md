# P4 manifest

| Field | Value |
|---|---|
| Run | P4, pilot protocol revision 5 |
| Rules commit | `7cc705c` (rules unchanged since `b89ad90`) |
| Skin | Twilight of the Northlands (`twilight_of_the_northlands`); Dread is shared Pressure; Companionship 3 |
| Modules | the skin's optional combat module: combat positions, and injurious blows with the grittier margin-8 option |
| Scenario | The Custodian's own, *The Lamplighter of Harrow Ford*. Frozen as `playtests/runs/P4/frozen_hidden_scenario.md`, SHA-256 `da7f2e586c7b2d378c16a9680819295ac2ac13bb8b6fde2f2103a54f6152e8b6`; policies SHA-256 `e6a0e308c9dd1236b08a34a8973cda120b230b2caae90b30399ce12a0c3f574d` |
| Orchestrator | Fable (`claude-opus-5-5`), not seated |
| Custodian | a fresh subagent, `claude-sonnet-5-5`, Claude Code general-purpose agent, default settings |
| Players | three fresh subagents, `claude-sonnet-5-5`, same settings, one per character |
| Master seed | 104 (seeds 104001–104026; crisis draw 104026, backlash draw 104025) |
| Access | instructed, not enforced; checked against the full tool trace |
| Date | 4 October 2026; agents launched 01:42 UTC, play 01:48–02:36 UTC (about 48 minutes) |
| Outcome | complete: 9 beats, 2 acts (5 + 4), session closed |

## Roster

All three were built by `gen_character.py --campaign` at the heroic tone (16 build points, the skin's suggestion), with no adjustments to scores.

| Character | Seed, primary, knack | STR | NIM | WIS | HRT | Hope | STM |
|---|---|---|---|---|---|---|---|
| Hild Ironwater, Dwarf road-guardian | 1041, STR, Stout-Heart | 15 | 12 | 11 | 10 | 10 | 5 |
| Merewen Starhollow, Elf lore-singer | 1042, WIS, Starlit Memory | 12 | 11 | 14 | 11 | 10 | 5 |
| Corwen Ashby, Warden archer | 1043, NIM, Keen Eyes | 10 | 15 | 12 | 10 | 11 | 5 |

The orchestrator added gear and notes with `update_sheet.py` before play:
- Hild: heavy war-axe (+2), hauberk and shield (soak 2), rope;
- Merewen: ash spear (+1), leather (soak 0), harp, dagger, and three known spells from the skin's examples: Silence the Footfall (Cant), Kindle Hearth-Fire (Oath), Banish a Tomb-Wight (Invocation);
- Corwen: longbow (+2), leather (soak 0), long knife, map, signal horn.

**Drives and temperaments** (temperaments differ; one is bold):
- **Hild.** Drive: "Recover her clan's lost oath-stone from the barrow-lands, and see her road-companions home alive." Temperament: bold. She takes the Vanguard and the first blow, and will walk onto tainted ground if a companion is there; she never leaves a living companion behind.
- **Merewen.** Drive: "Learn what woke the dead on the Old Road this autumn, and lay them to rest." Temperament: measured and curious. She will pay Dread for true knowledge, not for convenience; she never breaks a spoken oath.
- **Corwen.** Drive: "Keep the travellers on his stretch of the Old Road alive, and find out who is luring them off it." Temperament: cautious and practical. He prefers the bow from cover and falls back to better ground; he never abandons anyone in his charge.

## Packets and access

Each packet contains:
- the drive and temperament;
- the public export with reviewed notes;
- a one-line list naming the other two characters;
- the table settings;
- the Quickstart, The Adventurer and the Adventurer's Manual;
- Twilight lines 1–163: the player sections, including the Dread crisis table, now allowed under revision 5;
- Twilight lines 194–235: the optional combat module, which sits in the Custodian section of the book but which players need in order to declare positions.

| Packet | Words | SHA-256 |
|---|---|---|
| `packet_hild.md` | 7,220 | `ab7bfa06ceb085768c4cfc5a9703905bc97f88838fe620cd88169c0a5a7f12f0` |
| `packet_merewen.md` | 7,327 | `dffeb632806ae1b9b069b1ec7f2deb15cd5355675d8e23c77ed6de5ce2b05f0b` |
| `packet_corwen.md` | 7,235 | `8776e2e95623c5d17a9d5e4774c4cc78eddb2628213e976265854a1addc3cf13` |

The tool trace (`playtests/runs/P4/tool_trace.jsonl`):

| Agent | Tool calls |
|---|---|
| Custodian | 88 Bash and 22 hand-backs. No command touched `playtests/runs/`, `docs/playtests/` or `campaigns/`; the only matches for those paths are in its own hand-back statements that it had not read them. |
| Each player | 1 Read (their own packet), then hand-backs only |

## Custodian policies

These were declared before play, in `policies.md`. They cover:
- Hope tests;
- purges: sanctuary, a song in a sanctuary, a grave confession;
- Dread triggers: the skin's list and Almanac 4's general triggers, taken as additive;
- a declared d6 backlash table for failed Invocations;
- how Injury and Deflection are judged.

## Interventions

- **Setup.** Players were told to read their packet once and reply "Ready". The Custodian wrote its scenario and policies, then was told "Your scenario and policies are frozen as written. Open session play now."
- **In play.** There was no orchestrator message beyond verbatim relay: no reminders, no rulings, no relay errors.
- **Queued deliveries.** A player not due to answer received the other players' answers and the Custodian's replies verbatim, in order, with their next turn.
- **One deviation.** The closing public body (G021, `TO: none`) was not relayed to the players, because no further decisions remained.

## Relay and records

The orchestrator saved each public body to `replies/gm_NNN.md` and compared it with the campaign's `last.md` before forwarding.
- **G001–G020:** all matched.
- **G021:** failed the comparison. The final `last.md` ends with one extra newline; the text is otherwise identical. The transcript entry for G021 was appended by hand from `gm_021.md`.

Player answers are in `replies/pNNN_<name>.md`. The public session log (`session_001.md`) was written throughout.

## Costs

Input tokens are from the stored subagent transcripts. Output tokens are unreliable there and are omitted.

| Role | Replies | Written to cache | Read from cache | Notes |
|---|---|---|---|---|
| Custodian | 21 (plus the scenario-writing turn) | 311k | 21.5M | about 30–160 s per reply |
| Hild | 17 answers and "Ready" | 195k | 1.5M | about 6–11 s per reply |
| Merewen | 17 answers and "Ready" | 201k | 3.2M | about 7–12 s per reply |
| Corwen | 15 answers and "Ready" | 252k | 2.8M | about 7–11 s per reply |
| Orchestrator | n/a | unavailable | unavailable | relay and records |

Billed money is unavailable.

## Files

**Committed in this folder:** `manifest.md`, `transcript.md`, `summary.json` and `report.md`, and `audit.md` (Astra) when it is done.

**Kept in the ignored `playtests/runs/P4/`:**
- `initial/` and `final/` campaign state, including the log, receipts, checkpoints and memory;
- `frozen_hidden_scenario.md` and `policies.md`;
- the three packets and public exports;
- `custodian_brief.txt` and `player_brief.txt`, taken verbatim from the protocol;
- `replies/`, `checkpoint_checks.jsonl`, `check_reply.sh` and `add_player.sh`;
- `tool_trace.jsonl`;
- `orchestrator_notes.md`.
