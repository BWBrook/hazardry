# Design note: the book chapters after the pilot

Fable, 6 October 2026. Barry: "Start on the book chapters, good. I agree."

The pilot (P1–P13) and the labelled probes are done and committed (`09993c9`). They changed no rules. What they produced is evidence about *running* the game: which Custodian habits make play work, and which take the game away from the players. That evidence belongs in the book as craft. It does not go in as new rules. This is Barry's parked idea of 4 October: a chapter teaching how to run Hazardry and make it come alive, with examples from simulated play, for human and AI Custodians alike.

## What changes

1. **A new chapter, Custodian Craft.** It is placed after the Custodian's Almanac in the Core Rules part, as chapter 7, with the later chapters renumbered in `tools/_release_content.py`.
   - **Its job:** the Custodian chapter says what the job is, and the Almanac gives the procedures. Custodian Craft shows them working, and failing, in play.
   - **Its sections** each pair a short principle with one or two worked exchanges and the pitfall the pilot actually saw:
     1. open in motion;
     2. price the way forward;
     3. the choice stays with the players;
     4. threats move on their own;
     5. Pressure as the fuse;
     6. people, not obstacles;
     7. honest hazards;
     8. when you get it wrong;
     9. ending a scene.
   - **Its length:** about 3,000 words. The preface promises a book "cut lean on purpose", so each example has to earn its place.
2. **AI as Custodian: "Where AI drifts".** It gains the failure modes the pilot actually observed, in a few lines each, pointing to the craft chapter for examples:
   - taking choices from the players (picking the roller, withholding a costly spend as "not meaningful");
   - letting secrets slip into summaries;
   - stakes first appearing with the dice;
   - inventing compensation after a mistake;
   - ruling out approaches that the private notes allow.

   It also gains one observation: AI players route around Pressure whenever the fiction lets them, so the scenario has to price the way forward.
3. **Preface, "How to use this book".** The Custodian line adds the new chapter.
4. **AI Play Notes:** no change in this tranche. The harness procedure lives in the repository documentation, and Stage 4 owns harness changes.

## Rules for the examples

Barry's assessment of the first draft (9 October 2026): it was "fine for ingestion for an AI, and pretty ordinary for a human player", and "badly pitched for the book". The book chapter must read "as though the examples are snapshots from real games happening", with humans at the table, "appealing to a green wannabe human custodian". Whether the play was simulated is irrelevant.

- **The book chapter** (`rules/book/custodian_craft.md`) follows four invented human tables across several evenings:
  - Priya, running Service Duct Blues;
  - Callum, running Candlelight Dungeons;
  - Moana, running the core game at Ferrous Gap;
  - Ben, a first-time Custodian running Twilight of the Northlands.

  It shows what works, what falls flat and what a Custodian learns. Each skin uses its own terms. The pilot evidence supplies the lessons and the situations, and the source map below traces each one.
- **The first draft is kept for AI Custodians,** as `docs/custodian_craft_reference.md`, linked from `skills/agent_dm_handbook.md`. It is flatter and closer to the evidence, and says plainly that its examples are from the simulated pilot.
- **An example shown as good practice must not have been contradicted by an audit.**
- **No new rules, no new numbers.** Where a snapshot shows a mechanic, it uses the printed rule of that skin.
- **The Quickstart is untouched.**
- **The chapter teaches habits, not the harness.**

## Process

Fable drafts and Astra reviews, as in Stage 3. Barry assesses the draft before it is polished. Layout waits for GOLD, as before.

## Source map

Base: `docs/playtests/pilot/`. Runs P3, P9 and P11 are harness-test-only, and F1a is too. F2a is noncompliant. Examples from them are used only for the exchange cited, which no audit contradicts, or else as cautionary.

| Section | Example | Source | Audit verdict |
|---|---|---|---|
| Open in motion | coolant pulse and countdown | P10 G001 | correct |
| | preparation openings, 1–2 rolls | P6 G001, P5 G001 | not errors; low rolls |
| | false urgency | P13 G001–G002 | low uncertainty noted |
| Price the way forward | corridor bribe, counter-offer | P10 G016–G017 | correct; review-6 book example |
| | "do you commit?" replies | P7, 8 of 25 replies | review-3 |
| | "as stated" with dice | P2 G003, G016 | wrong |
| Fiction settles | dragging him out, no roll | P10 G002 | correct |
| | inscription, no test | P13 G011 | correct |
| | generous finale | P9 G027 | judgement call |
| Choice stays with players | one rope, two plans | P13 G008 | correct (both audits) |
| | roller by odds or vote | P4 G016, G018; P8 G003, G005 | error |
| | 7 tokens "not meaningful"; retry by second speaker | P4 G013 | wrong |
| | withdrawn action ticked a clock | P4 G004–G005 | wrong |
| | "No." for a player | P10 G020 | error; rule added in rev 8 |
| Threats move | bells and plumes | F2a G003, G005 | undisputed (run noncompliant on other grounds) |
| | bell timetable | P3 G007–G010 | credited |
| | clock filled with no interrupt | P10 G007, G015 | weak signposting |
| Pressure | look and pay, or look away | P3 G027–G028 | correct exchange |
| | routing around Pressure | review-4, review-7 | review finding |
| | dust devil crisis | F2a G005 | confirmed (AUD2) |
| | stumble with no lasting effect | F1c-1 G002 | wrong (Astra) |
| | cramp narrated as hand seizing | AME M3 G001–G002 | informed-choice gap |
| People | Redd's proverb | P11 G014 | exchange fine (error elsewhere) |
| | Nera's line | P13 G017–G021 | correct |
| | "at the works" | P9 G006 | not flagged |
| | ghoul and tales; sexton's names | F1b G002–G003; P6 G013–G014 | correct |
| | Wren summary leak | P11 G012, G017 | wrong; review-7 teaching case |
| | lay brother line leak | P9 G016 | wrong |
| | foe condition | F1a G019 against G027 | leak (Astra) |
| Honest hazards | needle trap | P13 G012–G015 | correct |
| | bell lowering refusal | P13 G017 | disputed: Fable wrong, Astra over-categorical |
| | offered option withdrawn | P11 G007–G008 | application error |
| | unmentioned light cantrip | P13 G016–G017 | judgement; review-6 rule |
| | Advantage before roll | P11 G006 | correct |
| | help ruled with the dice | AME M1-R2, M2, M3 G002 | procedure failure (Fable's cross-audit) |
| | wrong damage before choice | P4 G008–G009 | wrong; correction owned |
| When you err | disclosure, then invented rebate | P11 G014 | disclosure right; rebate wrong |
| | stakes fixed before the dice | P11 G015 | endorsed |
| | post-end roll | F1b G009 | inadmissible (AUD2) |
| Ending a scene | continuous work split | P13 G005–G009 | wrong |
| | timed repair not perilous | P10 beat 6 | wrong |
| | NPC life, no test | P11 beat 5 | wrong |
| | milestone is not a rest | P3 G036 | correct |
| | closing ledger | P13 close | accepted |
