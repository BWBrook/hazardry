# Pilot protocol: simulated play

Revision 7, 4 October 2026. Drafted by Fable and amended by Astra under Barry's
instruction. Revision 2 governed P1 and P5, revision 3 P2 and P6, revision 4 P3
and P7, revision 5 P4 and P8, and revision 6 P9 and P12. Revision 7 applies the
fifth round's lessons (`pilot/review-5.md`): settle actor collisions quickly,
offer abilities completely, keep private notes private, flag peril by its
stakes, and test skin-distinctive fuse mappings as a labelled experiment. It
governs P10, P13 and P11.

## Purpose

The pilot tests the procedure before the 40-run programme in `PLAN.md`. It asks
three questions:

- Can a table of AI agents play a full session of Hazardry through the harness?
- What goes wrong when they do?
- What does a session cost?

It is not balance evidence. The engine stays settled until the programme reports.

## Runs

| Run | Skin | Party | Scenario | Team |
|---|---|---|---|---|
| P1 | Clanfire | 2: Grak and Tarra | Emberfall, as published | Fable |
| P2 | Clanfire | the same 2 | P1's second session, resumed by a fresh Custodian | Fable |
| P3 | Mournful Shores | 1 | Custodian's own hidden scenario | Fable |
| P4 | Twilight of the Northlands | 3 | Custodian's own; combat positions and Injury on | Fable |
| P5 | Rust & Domes | 2 | Custodian's own | Astra |
| P6 | Candlelight Dungeons | 4 | Custodian's own; Delvekit off | Astra |
| P7 | Iron & Ruin | 1 | Custodian's own | Astra |
| P8 | Free Traders of the Drift Marches | 3 | Custodian's own | Astra |
| P9 | Briar Benedictine | Custodian's choice | Custodian's own mystery | Fable |
| P10 | Service Duct Blues | Custodian's choice | Custodian's own | Fable |
| P11 | none (the base game) | Custodian's choice | Custodian's own; Condition Tracks and Wealth & Attention (Almanac 7) | Fable |
| P12 | Time Odyssey | Custodian's choice | Custodian's own | Astra |
| P13 | Candlelight Dungeons | Custodian's choice | Custodian's own; Delvekit sidecar on | Astra |

The second tranche runs in rounds: P9 and P12, then P10 and P13, then P11.

Fable's subagents run on Claude Sonnet and Astra's on Sol. Each manifest pins the
exact model ID and settings for every role.

## The table

- **Custodian.** One agent, and the system under test: the rules, the harness and
  the quality of AI Custodian play together.
- **Players.** One agent per character, each keeping its own history. Where the
  platform limits concurrent agents, players take turns, but one model never
  plays the whole party.
- **Orchestrator.** Fable or Astra, not seated at the table. It passes public text
  between the agents, keeps the records and applies the stop rules.
- **Auditor.** The other team's model, after play. Astra's audits P1–P4, and
  Fable's audits P5–P8. The rules and the recorded evidence decide, not
  agreement between models.

## Access

Players start with no inherited history and receive their packet verbatim,
either as text or as one read of the packet file. Record the packet's SHA-256.
After that, players must not browse the repository or run tools.

On most platforms this is an instruction, not an enforced restriction, because
subagents share the filesystem and tools. Each manifest states which applies.
- Where players are only instructed, the pilot can show leakage or compliance; it
  cannot prove isolation.
- The audit checks for tool use where it can.
- A clean public transcript is not by itself evidence of secrecy.

**The player packet** contains:
- the Quickstart, The Adventurer and the Adventurer's Manual;
- the player-facing sections of the skin (its attributes, Luck, knacks or tags,
  equipment and abilities) and its Pressure track with the step effects and
  triggers, its crisis and backlash tables where it prints them, but not its
  Custodian advice;
- the character's public export (`resume_pack.py --public --character NAME
  --json`), completed with reviewed descriptions of its equipment, abilities,
  spells and the resources it controls;
- the character's drive and temperament, fixed at setup: one line on what they
  want, and one on how they act, including how much risk they will take;
- for P1–P2, the Emberfall player handout;
- the public narration, as play goes on.

Players never receive hidden notes, private state or the other agents'
instructions.

## Role briefs

**Custodian.** "You are the Custodian for a session of Hazardry, running the
campaign at PATH through the harness in this repository.
- Before you start, read `AGENTS.md` and `skills/agent_dm_handbook.md`, and
  rebuild and read the campaign prompt.
- Use `tools/play.py` and `tools/advance.py` for every roll, cost, Pressure change
  and milestone.
- Draw crisis and backlash tables with `tools/roll.py table`. Where a printed rule
  lets you choose a table result, say that you chose it.
- Never invent a die.
- Use the seed schedule in your setup notes.
- Open in motion: start the session, and each act, in the middle of something
  already happening, with a clear and immediate stake, like a film's pre-credit
  scene, not with quiet preparation. Honour rests and decisions already agreed;
  an act need not open with a forced fight.
- Threats move on their own. When enough fictional time passes for the active
  threat to advance, or the opposition makes its move, advance its clock as
  declared in the scenario, whether or not anyone rolls. A clock tick is not
  automatically a Pressure charge, though both may apply.
- Keep the frozen scenario's triggers and timetable. A trigger that does not
  depend on failure fires on success too.
- Apply Pressure when a fictional trigger occurs. A skin's triggers add to the
  core triggers in Almanac 4; they do not replace them, unless the frozen
  scenario declares an experimental fuse mapping (setup step 4), which then
  governs. When a trigger first
  arises, charge it, or say plainly that it will be charged if the characters
  stay, look or wait. Never charge for real-world deliberation or to reach a
  target rate.
- Give each named NPC a want, a manner and a line they will not cross, kept in
  your private notes, and play them by it. Narrate what the characters observe:
  never publish an NPC's private boundary, or a private clock's name or value,
  as fact; show signs.
- Put everything the players should see between a line `=== PUBLIC ===` and a
  line `=== END PUBLIC ===`. After the closing marker, put a `TO:` line naming
  who should answer (or `TO: none` when the session is closed). The checkpoint
  contains exactly the public body between the markers, with its final newline;
  neither marker nor routing line belongs in it. Anything outside the block goes
  to the orchestrator only. Keep private notes in the campaign files.
- The orchestrator relays and keeps records. It gives no rulings; the rules and
  your judgement decide.
- State the stakes before the player commits. When you offer options, give each
  risky one its test and its consequences on success and failure, so that
  choosing it is the commitment. When the stakes are already public, the
  player's declared action is the commitment. Otherwise state the test and its
  consequences, and get commitment before you roll. Stakes must never first
  appear in the reply that shows the dice.
- Never offer an option that depends on something only your private notes
  know; options may follow leads the characters have found.
- Never offer an option whose advertised outcome your private notes rule out.
- Give players correct numbers before any choice. Damage uses the attacker's own
  margin; a skin's effective margin applies only to the thresholds it names.
- Make the roll with `--defer`, then show the dice, the kept result and the
  margin, and the meaningful legal post-roll choices, to the players who can act
  on them. Offer any affordable legal spend that changes the declared outcome or
  a meaningful degree of success, however costly, with its exact price; cost is
  the player's decision.
  Wait for those decisions before settling; never issue the roll again. If no
  eligible player has a meaningful post-roll choice, explain why and settle
  without discretionary spending in the same reply.
- Before rolling, check relevant tags and modifiers and offer optional powers at
  their costs; after resolution, offer newly eligible abilities. Preserve the
  player's choice, and settle all offered once-per-scene abilities before
  closing the scene.
- In combat, ask only the combatant or decision now due.
- When players' declarations conflict, preserve each player's intent.
  Adjudicate compatible actions in fictional or initiative order, and ask only
  for a decision needed to settle a truly incompatible pair. Never override one
  declaration to make another succeed, and keep deferred Luck and ability
  choices open. When declarations need different actors for one roll or role,
  ask the players to choose, and offer an opt-in tie-break die (a scheduled
  harness draw, used only if all claimants agree); compatible help needs no new
  confirmation. Never choose the roller silently, by odds or by an unagreed
  vote.
- One spokesperson means one roll: settle who speaks before rolling. Another
  character does not retry a failed test in the same scene unless the situation
  or the leverage has really changed.
- An action withdrawn before commitment causes none of that action's
  consequences. Withdrawing it does not undo what was already done or fictional
  time already spent.
- Record each scene as a beat as it ends, and mark act breaks with `--act-end`.
  A cut to another place or time starts a new beat; keep Almanac 9's scene
  definition. Do not start a beat merely because another test is called, or to
  refresh a power or reach a milestone.
- Flag a beat perilous when failure at its consequential choice could cost
  Stamina, a life or the goal. A safeguard earned within the beat does not erase
  the peril already overcome; routine work that begins after safety is
  established is not perilous merely because a goal remains pending.
- Save every public body with `tools/checkpoint.py`, and add the turn's public
  narration to the session log with `tools/session_log.py`.
- Keep each public reply to about 400 words. Cut description before stakes or
  options.
- Follow the table discipline and session evidence in the handbook, and the
  pacing card. After the second act, award any milestones still due, write the
  recap and close the session."

**Player.** "You play CHARACTER in a session of Hazardry, using only the packet you
were given. If setup explicitly gives a packet-file path, read that exact file
once as instructed. Otherwise, and after that read, do not use tools or read files.
- Each turn, say in character what your character does and how. Speak to the
  other characters as well as the Custodian, and play to your character's drive
  and temperament, including the risks they would take.
- Play cooperatively. Ask about unclear stakes or rules, and change or abandon an
  intent before committing to the roll. Once resolved, accept the result without
  seeking a reroll.
- When a companion may want the same roll or role, say in your answer who should
  take it, or say that you accept a tie-break.
- When offered a Luck choice after a roll, decide how many tokens to spend, if
  any.
- Keep replies to two to five sentences."

## Setup (orchestrator)

1. Create the campaign under `playtests/campaigns/` with `campaign_init.py
   --base-dir playtests/campaigns`. The folder is git-ignored. Never use
   `campaigns/`.
2. Fix the roster and loadouts before play.
   - P1–P2 use Emberfall's Grak and Tarra, with their gear on the sheets
     (`examples/command_snippets.md` for a new party; the continuation procedure
     below for P2).
   - The other runs use seeded random characters. Each must have the
     capabilities its run should exercise: a sensitive in Rust, named spells in
     Candlelight, a plausible sorcerous option in Iron & Ruin, assigned crew
     roles in Free Traders. Record any adjustment.
   - Give each character a one-line drive and a one-line temperament, consistent
     with the sheet, and record them in the manifest. A temperament states the
     risk the character will take and the line they keep. In multi-character
     runs, temperaments differ and at least one character is bold. A solo
     character gets an explicit temperament too.
3. Set the dice schedule:
   - Pick a master seed M for the run.
   - The Nth harness command that draws dice uses seed M×1000+N, with N counting
     up from 1.
   - A retry reuses its event ID and seed, including commands that produce a
     Deflection roll.
   - The orchestrator checks the draw index of every new dice command, tie-breaks
     included, against the schedule.
   - Seeding makes the mechanics reproducible from the command sequence. It does
     not make the narrative deterministic.
4. For runs without a published scenario, the Custodian writes its hidden
   scenario to `state/memory/hidden_scenario.md` before play.
   - The scenario opens in motion, at a moment of action or decision.
   - It includes at least one active threat with a clock that advances with time
     or with the opposition's own moves, not only on a player's failure. The
     scenario declares what advances the clock, what happens when it fills, what
     can interrupt or delay it, and which core or skin Pressure triggers the
     threat can set off.
   - It gives concrete, telegraphed Pressure-bearing dangers and consequential
     choices; alternatives carry honest fictional costs where appropriate. A
     scene may have unavoidable exposure where its fiction warrants it, but it
     is not a quota. If players avert the costs, record how; never manufacture a
     charge to satisfy coverage.
   - Its named NPCs each have a want, a manner and a line they will not cross.
   - The scenario gives the skin's distinctive procedures a chance to occur; it
     never forces them.
   - **Experimental fuse mapping (P10, P13; Barry-approved direction, not
     adopted rules).** The scenario declares which core triggers feed the skin's
     Pressure fuse, in what fictional form, and any exclusions. The mapping is
     frozen with the scenario; player-relevant parts go in the packets; the
     manifest and audit record the override of the additive default.
   - Never pick seeds to produce an outcome. A guaranteed outcome, such as a
     failed Unspeakable rite, belongs in a separately labelled probe.
5. Freeze a copy of the scenario, the roster and the optional modules, and start
   the manifest.
6. Before launching any role, inspect each packet's skin sections, public
   boundaries and own-character content, then verify the bytes actually sent by
   hash.

## Turn loop

1. The Custodian replies in the public-block format above. The orchestrator
   extracts the public body without rewriting it; private text and routing
   metadata are never sent to players.
2. The orchestrator gives the same frozen reply to every player who should
   answer.
   - Players answer independently. No player sees another's pending answer until
     all have answered.
   - Every player receives the public reply and the other players' completed
     answers verbatim, including when they are not due to answer. Delivery may be
     queued until that player's next turn, in chronological order. Each player
     must receive all completed public dialogue before making a new decision.
   - Build each relay from the record, not by hand, so that every completed
     answer reaches every player.
   - When the reply asks one player for a decision, only that player answers.
   - Every public body goes to every player, including the closing one; `TO:
     none` means no decision is asked, not that the narration is withheld.
3. The orchestrator passes the answers to the Custodian, labelled by character.
4. The Custodian adjudicates through the harness, records what changed, saves the
   checkpoint and replies again. The orchestrator saves the reply's public block
   as its own file and checks it against the saved checkpoint before forwarding.
5. The run ends at the beat that closes the second act. The Custodian awards
   milestones, writes the recap and closes the session.

## Stop rules and interventions

- **Normal end:** the second act closes, usually after 10–12 beats.
- **Cap:** 16 beats or 150 Custodian replies. At the cap, keep the checkpoint and
  any pending state, and mark the run incomplete. Do not invent a second act or a
  session close.
- **Early ending:** a genuine ending before the cap, such as a party wipe, is
  recorded with its reason.
- **Stall:** if three replies pass without progress, the orchestrator may send one
  neutral prompt ("The scene needs a decision."). A deferred roll waiting on a
  Luck decision counts as progress.
- **Harness error:** the orchestrator may correct a malformed command, never a
  die or a state value.
- **Interventions:** any orchestrator message other than a relay counts as one,
  and goes in the manifest with its reason. Rules mistakes are not corrected
  during play; the auditor finds them afterwards.
- **Leaks:** if private material reaches the players, record it. The run then
  counts as a harness test only.

## Records

**Committed**, under `docs/playtests/pilot/RUN/`:

- **`manifest.md`:**
  - the run id, protocol revision and rules commit;
  - the skin, the frozen scenario reference, the roster and loadouts, and the
    modules;
  - the exact model ID and settings for every role;
  - the master seed;
  - whether access was enforced or only instructed;
  - the Custodian's policies on Luck tests, purges and shared hazards;
  - the start and end times, the interventions, and token and time costs for
    every role (marked estimated or unavailable where so).
- **`transcript.md`:** every exact player input and every public Custodian
  output, in order.
- **`summary.json`:** the output of `playtest_summary.py --campaign PATH --json`.
- **`audit.md`:** the auditor's verdicts, each marked correct, wrong (citing the
  rule), judgement call or not assessable. The audit covers:
  - every crisis and every unusual settlement path;
  - a declared sample of ordinary rulings; if there are fewer than ten
    consequential rulings, all of them;
  - event and message references, with citations to the rules;
  - a check that the saved checkpoints match the public text;
  - a check for leaks and tool use.
- **`report.md`:** the orchestrator's notes:
  - stalls and invented rules;
  - harness gaps and errors;
  - pacing against Almanac 9, as description, not a target, including Pressure
    gained, rolls per beat and Luck spent to avoid Pressure;
  - coherence and fun;
  - procedures offered but not exercised;
  - what to change before the programme.

**Kept for the auditor** in the ignored run folder:
- the initial and final campaign state, the JSONL logs and the receipts;
- the frozen scenario and the exact packets delivered, with their hashes;
- each public reply as its own file, with the checkpoint comparisons and a copy
  of each checkpoint version; any mismatch or transport intervention is kept,
  not overwritten;
- each player's exact incoming messages;
- a command record;
- where the platform stores agent transcripts, a tool trace and token usage for
  every role.

## The continuation (P2)

Before opening session 2, reconcile the previously empty inventory fields with
P1's final fiction and receipts. Record retained, gained, traded and consumed
items and the evidence for each change; do not replenish the starting handout
gear by default. Keep P1's frozen final snapshot unchanged and put this setup
adjustment in P2's manifest.

A fresh Custodian receives only the documented bootstrap materials
(`skills/agent_bootstrap.md`). It rebuilds the prompt and loads the resume pack
and the checkpoint. The player agents carry on from P1 where the platform keeps
them; otherwise fresh players get character-filtered public packets. P2 tests
resuming, Pressure carried across sessions, and once-per-session powers
refreshing.

## After the pilot

Fable and Astra compare the reports and propose changes for Barry before the
40-run programme: to this protocol, to the briefs, and any harness fixes. No rule
changes follow from the pilot alone. Targeted probes for procedures that ordinary
play leaves unexercised are run and labelled separately.
