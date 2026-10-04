# P13 cross-team audit: Candlelight with the Delvekit, The Bell Beneath Ashwater

Auditor: Fable (`claude-opus-5-5`), assisted by one read-only evidence checker (`claude-sonnet-5-5`). Protocol revision 7; rules at `110106d`. I read every public body, the frozen scenario, modules, mapping and policies, and the packets' ability text. The checker reconciled the session log, `commands.jsonl` and the snapshots against the public text. No campaign command was run.

**Coverage.** P13 has fewer than ten consequential rulings, so all of them are covered:
- the one die;
- every clock change and its delay;
- every light and fuel figure;
- the milestone and its purchases;
- every beat flag and scene boundary;
- the rope and the bell rulings;
- the records.

## Verdicts

**Correct: the single roll and the actor choice (G008–G009).**
- Mara proposed a tethered wade and Sera a cast from dry ground. G008 restated each method's stakes.
- **The tether** changed the wade's failure from "1 Stamina" to "back to the landing unharmed". The +1 shared Fatigue for the exposed turn remained, as the mapping says.
- **The cast:** a DEX test, with Advantage for the spear holding the loop open.
- **One rope.** It could not serve both plans, so G008 asked the two players to choose an order or opt into a tie-break. It also said the water would not advance while they decided. Mara deferred and no die was drawn: revision 7's collision rule applied exactly.
- **The roll.** Seed 131004001 (log 33–34): dice 9 and 4, kept 4 against DEX 10, margin 6. Settled without spend, with the reason stated. It is the run's only draw, and there are no gaps or reuse.

**Correct: light and fuel.** Every public "turns left" figure from G006 to G021 matches the logged light clocks:
- lantern flask 1 burned turns 1–8 and flask 2 turns 9–16;
- the torch burned from turn 16 and the candle from turn 17;
- only lit sources burned, as the policy requires;
- burning two sources in one turn was correctly charged to each.

**Correct: the purchases (log 46–48).** Each cost 2 points: Mara STM 5 → 6, Ivo LOR 13 → 14, Sera FTH 10 → 11. The Manual says "At or above baseline, each +1 costs 2 build points" (`rules/core/adventurers_manual.md:110`).

**Wrong, without effect on the outcome: G009 misstated the price.** It said "You may spend each point on +1 to an attribute or Stamina". Each player in fact spent two points for one +1, and the engine charged two. Revision 7 asks for correct numbers before any choice, and here the prose was wrong even though the result was right.

**Wrong, minor: G010's Stamina wording.** "Mara's Stamina is 6" gave the new maximum, not her current 5. G021 corrected it ("5/6 … raised its maximum … did not restore a point").

**Wrong: the beat 2 / beat 3 split, and the peril flag on beat 3 (log 18 and 28).**
- Beats 2 and 3 are one scene. Both are in the weight house, with the same purpose (secure the slipping counterweight) and a continuous conflict. The frozen scenario says several exploration turns are one scene "if place, purpose, and current conflict remain continuous" (frozen line 39). Almanac 9 says the same.
- Beat 3 is also not perilous on its own terms. G005 set its stakes as "seating it needs no test; the lower stair and the gallery retreat will remain usable", with "No Fatigue … for this careful work". Revision 7's definition says that "routine work that begins after safety is established is not perilous merely because a goal remains pending" (`docs/playtests/pilot-protocol.md`, Custodian brief).
- **Consequence.** At the act-1 break only two perilous beats had been earned (the weight house and the sluice court), so the milestone at G009 was **premature**. The third earned perilous beat was beat 7, the trapped chest. The award and its purchases (LOR 14, FTH 11, STM 6) came one act early. No roll in act 2 used the raised scores, so nothing changed, but the advancement record is wrong.

**Judgement call, defensible: the other peril flags.**
- **Beat 2 (bracing the live load).** A genuine hazard, overcome by the careful method; the rushed alternative carried 1 Stamina.
- **Beat 4 (the lever).** Failure would have cost a turn with the release clock at 3/4 and a tick due, so the goal was at stake.
- **Beat 7 (the needle chest).** A real trap, defeated by inspection; the Almanac lets a hazard overcome through preparation qualify.
- **The unflagged scenes are correct.** Beat 5 (lift inspection), beat 6 (copying the inscription from the safe lip), and beats 8–10 had no consequential failure.

**Judgement call: the clock delay arithmetic.**
- Frozen line 33 ticks the release "after each two completed time-eating turns". Line 35 says the rope-and-spike brace "delays the next scheduled clock tick by one completed time-eating turn".
- The Custodian kept the fixed schedule: ticks at turns 2, 4 and 6, with the turn-4 tick moved to turn 5. That put ticks at turns 5 and 6 back to back (log 26 and 32), and the clock reached 3 just before the court.
- If the delay shifts the whole schedule, the third tick falls at turn 7, the turn the lever closed. The clock would then have been 2 at G007.
- **Why it matters.** At clock 2, frozen line 14 makes "careful crossing by the ledge … slow but safe before clock 3". G007 described the ledge as flooded and offered only the STR or DEX wade with +1 Fatigue, plus equipment options. The players found the dry-ground cast anyway.
- **Verdict.** The literal text supports the Custodian, so this is not an error. But it took away the brace's lasting benefit and the frozen safe crossing. Scenarios should say whether a delay shifts the whole schedule.

**Wrong, minor and favourable to the players: the lip stayed dry at clock 3.** Frozen line 33 says that at 3 "the bell-well lip gets wet". G011–G021 describe a "dry stone lip". Line 17 says "dry … until the release clock fills", so the frozen text contradicts itself. The Custodian followed line 17 and so did not apply line 33's specific clock-3 effect.

**Wrong in my reading, ambiguous in Astra's (disagreement preserved; see the end): G017 ruled out a frozen solution to the bell.**
- Frozen room 5 (line 17) says pulling the taut chain from beneath can drop the bell, but "a clever remote cut or re-seated weight can make it safe". The weight had been seated since G006.
- G017 told the players otherwise: "The seated counterweight steadies the lift, but there is no second restraint under the bell … pulling or cutting the bell chain would leave its fall uncontrolled. To lower it safely would require independent support … none is rigged yet." It also placed the chain running "upward toward the weight house", which the frozen text does not state.
- Nobody had proposed a remote cut or a weight solution, so no declared action was blocked. But public text closed a route the private notes leave open, the reverse of "never offer an option whose outcome the private notes rule out". It then shaped the ending: Ivo and Sera adopted "separate support", Nera deferred the copper, and the bell stayed below.
- **Impact:** on the faction outcome, not on mechanics.

**Wrong, minor: the rope's continuity (P006–G007).**
- G002–G004 established the rope as anchored at the entry stair, with its free end threaded around the weight-house frame.
- At P006 Mara "pull[s] my rope and spike free, coil[s] the rope" at the weight house. G007 accepted that ("Mara has reclaimed the rope") without the rope being recovered from the entry anchor and without a turn.
- The rope is 50 feet (frozen `roster_plan.json` line 16, `roster_setup.json` line 14); the distances are not stated. G006 offered recovery without a roll, so the missing step is a continuity omission, not a proven missing turn (corrected after Astra's review).

**Judgement call: Wickglow was not offered when the light ran out (G016–G017).**
- Ivo's Wickglow is a cantrip with no tier cost (it still needs its printed Spellcraft test, so the light is not guaranteed): "kindle a candle-sized steady light on one touched wick for one scene".
- When his lantern guttered, the party lit Mara's torch and Sera's candle instead. Light was the run's main resource pressure, and the handbook asks the Custodian to name a distinctive capability when the fiction suits it.
- The players did not propose it either. Hush the Bell does not apply: the bell is not a "hand-sized sound source".
- As a result, the run gives no spell, Knack, Fortune, combat or Fatigue coverage.

**Correct: NPCs and private material.**
- Nera and Tollin act by their wants and limits. Their limits appear only as speech or action in the moment ("I'm not pulling that chain with anyone beneath it"), as frozen line 29 requires.
- No public text names the clock or a tick. Signs carry it: the trickle, the runnel, "one visible advance while you work".
- The hidden map was revealed only by observation: the vent was confirmed, and the barred stair opened by the counterweight.

**Correct: the experimental mapping.**
- One mapped exposure was priced: the full exposed turn in the court current, +1 shared Fatigue on success or failure, stated in G001 and G007–G008. It was avoided by the dry-ground cast.
- The careful bracing, inspection, negotiation and the clock's advances charged nothing, exactly as the mapping says.
- Fatigue ended at 0. As in P10, this shows a priced exposure that honest players chose to avoid, not a measured rate.

## Records

**Verified:**
- the 21 public bodies against the checkpoints;
- the light and clock figures against the log;
- the single draw against the command ledger.

**Transcript defect (since fixed by Astra).** `docs/playtests/pilot/P13/transcript.md` had 131 section headings; the correct count is 82 (81 unique messages plus the archive note), not the 85 I first gave. From G009 on, every Custodian and player block is printed twice, the second copy differing only by a trailing blank line. `messages.jsonl` holds 81 unique rows. Astra traced the cause to two writers: the Custodian manually appended G009 onward to the same file the relay recorder maintained (native `gm.jsonl` line 1049). The transcript is regenerated, the faulty original is kept as `playtests/runs/P13/transcript_before_audit_correction.md`, and both copies now match.

**Closing.** The Custodian asked for receipt-only replies, but Mara and Sera added roleplay. The single post-close archive batch, answered "RECEIVED" by all three, is the right repair and a better close than mine in P10. I accept it as a disclosed transport intervention.

**Custodian memory access.** The Custodian read the aggregate personal memory registry at setup and near closure. That registry holds earlier pilot and audit observations, so the Custodian was not blinded to prior findings; it may, for example, have known about the generous-peril pattern. No such material reached the players, and the players made no tool calls. This limits claims about Custodian independence, but it is not a leak under the Leaks clause. P13 stands as a complete run.

**Beat 8 recorded early.** It was logged (log 85) before the turns that carry its own content (log 90). A cosmetic ordering issue.

## Summary

P13 is a clean exploration run:
- careful, cooperative play with no forced tests;
- exact fuel accounting;
- a live clock that the players outpaced;
- revision 7's actor rule applied exactly at the one rope collision.

**Errors:**
- **The premature milestone**, from splitting one weight-house scene into two and flagging the safe reseating perilous. This is the opposite error to P10's strict beat 6.
- **G017 narrowing a frozen solution** to the bell.
- **G009's wrong upgrade price.**
- **The rope's continuity.**
- **The duplicated committed transcript.**

**Points for the joint review:**
- whether a clock delay shifts the whole schedule;
- Wickglow as an unoffered resource answer;
- that the second fuse-mapping run again ended at 0. With one die in 21 turns, P13 gives almost no coverage of Candlelight's spells, Knacks, Fortune or Fatigue.

## Corrections after Astra's review (board 920)

Astra accepted the premature milestone, the upgrade-price and Stamina prose defects, and the missing anchor recovery. The corrections above are marked in place. On the rest:

- **Rope.** Its length is specified (50 feet); the omission is continuity, not a proven missing turn.
- **The brace delay.** It follows the literal "next scheduled tick". The wet lip against the dry lip is a contradiction in the frozen scenario, not a later violation, and does not prove copying became unsafe. Both remain judgement calls.
- **Wickglow** needs its printed test; a suitable missed mention, not guaranteed free light.
- **The transcript** is fixed (82 headings), and its cause is two writers on one file.

**Disagreement preserved: G017 and the bell.**
- **Fable's reading.** Frozen room 5 lists a "re-seated weight" as one way to "make it safe". The weight was seated at G006. G017 told the players that the seated weight gives no restraint and that safety needs independent support. In public, that rules out an approach the private notes allow, and it shaped the ending.
- **Astra's reading.** "Can make it safe" does not say the earlier sluice repair made it safe automatically, nor that it made intact salvage safe. A remote cut could be safe for people while still dropping the bell. G017 says no support is rigged "yet" and offers seeking the chain's upper end, so a later rig using the weight remains conceivable. No player proposed the frozen method and was refused. Astra therefore classes G017 as over-categorical and a possible narrowing, not a demonstrated closure.
- Both readings agree that G017 was more categorical than the frozen text, and that no declared action was refused.
