# P3 manifest

| Field | Value |
|---|---|
| Run | P3, pilot protocol revision 4 |
| Rules commit | `849a8e0` (rules unchanged since `b89ad90`) |
| Skin | Mournful Shores (`whispers_in_the_fog`); Insanity is personal Pressure |
| Scenario | The Custodian's own, *Third Ebb* (Dunmore, 1924). Frozen as `playtests/runs/P3/frozen_hidden_scenario.md`, SHA-256 `3cb05bf8d2d7ef4669307d591db439e618e3dfca62692ee1ea71b64011154685`; policies SHA-256 `4c3de591b69a213971232f16c9686b2ea46f31fad4e3cbf05dc4bf0a17b56e74` |
| Modules | none (the skin's lantern clock was used) |
| Orchestrator | Fable (`claude-opus-5-5`), not seated |
| Custodian | a fresh subagent, `claude-sonnet-5-5`, Claude Code general-purpose agent, default settings |
| Player | a fresh subagent, `claude-sonnet-5-5`, same settings |
| Master seed | 103 (seeds 103001–103030; the crisis table draw used 103024) |
| Access | instructed, not enforced; checked against the full tool trace |
| Date | 3 October 2026; setup about 12:20 UTC, play 12:40–13:41 UTC (about 61 minutes) |
| Outcome | complete: 6 beats, 2 acts, session closed |

## Roster

**Nell Carrow.**
- Built by `gen_character.py`, seed 1031, primary SCH, with the free knack Occult Scholar. No adjustments to scores.
- VIG 9, AGI 9, SCH 12, FRT 11, Fate 10, Stamina 6.

The orchestrator added gear and one known Rite with `update_sheet.py` before play:
- hooded oil lantern, woollen coat, satchel of notebooks with a borrowed copy of the *Dunwater Psalter*;
- pocket-knife, matches with a spare oil flask, chalk;
- *Sign of Warding*, a Rite, added to give the Rite tier an opportunity.

The Custodian defined the other rites in its scenario:
- Salt-Sight (Murmur);
- Hush of Slack Water (Incantation);
- The Ebb Unspoken (Unspeakable, discoverable).

**Drive:** "Recover the truth her university buried about the Dunmore drownings, whatever it costs her."

**Temperament:** "Bold: goes into the dark first and will read a forbidden page aloud if it might save a life; the line she keeps is that she never abandons a living witness."

## Packet and access

`packet_nell.md`, 6,388 words, SHA-256 `f479772f9ea8815d18f2ff8756097d8791065582fd361ee300bde70f2b4b417a`. It contains:
- the drive and temperament;
- the public export, with reviewed notes on the knack and the known rite;
- the Quickstart, The Adventurer and the Adventurer's Manual;
- Mournful Shores lines 1–107 and 124–158. These include the Insanity steps, its gain and purge triggers, the knacks and the lantern clock. They exclude the crisis table and the Keeper's Quill.

The tool trace (`playtests/runs/P3/tool_trace.jsonl`):

| Agent | Tool calls |
|---|---|
| Custodian | 123 Bash and 39 hand-backs. No command touched `playtests/runs/`, `docs/playtests/` or `campaigns/`. |
| Player | 1 Read (her packet), then hand-backs only |

## Custodian policies

These were declared before play, in `policies.md`.
- **Fate tests:** called only for pure chance, at most two. None was called.
- **Purges:**
  - hypnosis: 2 Fate for 1 point, once per act;
  - grounding ritual: 1 point, once per act, never during a live threat;
  - sanitarium: between sessions.
- **Witnessing:** +1 for a new class of horror, at most one gain per scene.
- **Reading:** +1 for reading the Cut Leaves or the Dean's margin notes in earnest.
- **The choir:** +1 per beat once the Tide Turns stands at 4 or more, unless her ears are stopped.
- **Backlash:** the skin prints no backlash table, so the Custodian declared a d6 backlash table of its own. It was never drawn.

## Interventions

- **Setup messages:**
  - The player was told to read her packet once and reply "Ready".
  - The Custodian was told "your scenario and policies are frozen as written… open session play now", after it wrote the scenario. In the same message it was told "the orchestrator gives no rulings", because it had asked the orchestrator to confirm its backlash table.
- **In play:** no other orchestrator message beyond verbatim relay. There were no reminders, no rule corrections and no relay errors.

## Relay and records

The orchestrator saved each public body to `replies/gm_NNN.md` and compared it with the campaign's `last.md` before forwarding. All 38 matched (`checkpoint_checks.jsonl`). Player answers are in `replies/pNNN_nell.md`.

## Costs

Input tokens are from the stored subagent transcripts. Output tokens are not reliable there and are omitted.

| Role | Replies | Written to cache | Read from cache | Notes |
|---|---|---|---|---|
| Custodian | 38 (plus the scenario-writing turn) | 364k | 33.9M | about 30–200 s per reply |
| Nell | 37 answers and "Ready" | 85k | 3.5M | about 4–8 s per reply |
| Orchestrator | n/a | unavailable | unavailable | relay and records |

Billed money is unavailable.

## Files

**Committed in this folder:** `manifest.md`, `transcript.md`, `summary.json` and `report.md`, and `audit.md` (Astra) when it is done.

**Kept in the ignored `playtests/runs/P3/`:**
- `initial/` and `final/` campaign state, including the log, receipts, checkpoints and memory (with `keeper_notes.md`);
- `frozen_hidden_scenario.md` and `policies.md`;
- `packet_nell.md` and `nell_public.json`;
- `replies/`, `checkpoint_checks.jsonl` and `check_reply.sh`;
- `custodian_brief.txt`;
- `tool_trace.jsonl`;
- `orchestrator_notes.md`.
