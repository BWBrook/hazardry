# P8 cross-team audit: Free Traders, Greyhook and Mercy Reach

Auditor: Fable (`claude-opus-5-5`). Protocol revision 5; rules at `7cc705c`. I did not run commands against the campaign.

**Evidence.**
- The committed transcript, manifest, report and summary.
- In the ignored `playtests/runs/P8/`:
  - the frozen scenario and policies;
  - the final log, `final/p8_drift/state/logs/session_001.jsonl`;
  - the Guildmaster replies and checkpoint comparisons;
  - the independent integrity check.

**References.** "Event N" is the log's `sequence`; G and P numbers are message IDs. The skin is `skins/free_traders_of_the_drift_marches.md`.

**Scope.** P8 has fewer than ten consequential rulings, so this audit covers all of them: all seven rolls, both knack uses, the nudge, both clocks, the milestone, every beat flag, the jump and the trade.

## Verdicts

**Correct: the opening (G001).**
- It opens in motion: a courier on a failing tether, nine minutes of air, a cutter about forty minutes out.
- Every risky option names its test and both outcomes: pilot, EVA, and Salvage Rat at its printed cost.
- The ambient trigger, "twenty fictional minutes … one shared Strain", is declared up front, as the frozen policies require.
- The job terms match the skin's trade-stake and patron-job rules (`skin:162-186`). The job is one stake, settled once, with no acquisition cost.

**Correct: the rescue (G002, events 4–6).**
- Kest's piloting: DEX 10 with Pilot Expertise Advantage, dice 10 and 1, kept 1. A natural 1 is locked; settled with no offer.
- Rook's Salvage Rat: automatic success, 1 Fate in vacuum, no gravity surcharge (`skin:78`).
- The two declarations were compatible and were resolved in fictional order.
- The pilot test was not redundant. It was an option chosen with stated stakes, and its success put the lock within Ilya's reach.

**Correct, with an agency judgement call: the scan and the cross-check (G003, G005; events 9 and 17).**
- Both Kest and Rook declared the scan (P002), and both declared the cross-check (P004). Each time, the Guildmaster folded their methods into one roll by Rook: EDU 10 with Engineer Expertise Advantage. Kest also has EDU 13, but no fitting Expertise.
- One task, one test is correct, and Rook's roll was the better chance (about 0.75 against 0.65).
- **Judgement call:** the Guildmaster chose the roller without saying so. Kest twice declared he would run the test and was not asked. Under the conflicting-declarations rule, choosing between two players' bids for one roll is the "truly incompatible pair" case, where the brief says to ask. The narration kept Kest in the fiction, so his intent was partly preserved.
- The mechanics:
  - G003 kept 7 (margin 3) and 4 (margin 9), both settled with no useful nudge.
  - G005 kept 11 against EDU 10, a miss by 1, with the unkept 20 correctly ignored. It was deferred, offered at the exact 1-Fate price, and settled at margin 0 after Rook paid (event 17).

**Judgement call against the frozen scenario: the standoff hold (G002–G004).**
- The frozen scenario (line 17) says a truthful medical call makes Brant "hold the cutter at standoff for ten minutes while she verifies".
- The Guildmaster narrated it as holding "the interdiction order" while the cutter kept burning:
  - "a little under forty minutes" at G002;
  - "does not stop its burn" at G003;
  - "roughly twenty-five minutes away" at G004.
- This is harsher than the scenario's wording. It cost nothing in play, because no deadline was reached, but it departs from the frozen text.

**Correct: the clock and ambient Strain (G003–G006, event 13).**
- The patrol sweep ticked once at the first ten-minute mark, during an unrolled successful transfer. Threats moved on their own, as revision 5 asks.
- Telegraphed exactly as revision 5 asks. At about 15 minutes in, G004 warned that five more minutes would mark +1 Strain, and both the "wait" and "fail" options carried that cost.
- Rook's 1-Fate nudge let the crew leave at about 17 minutes, so no Strain was owed. **No missed charge.**

**Judgement call: scene granularity and the milestone (events 19–24).**
- Act 1 was recorded as four beats: rescue, scan, transfer and permit, flagged perilous, perilous, not perilous, and perilous. All four are one continuous 17-minute operation at one buoy, with no cut in place or time.
- The handbook (`skills/agent_dm_handbook.md`, Session evidence) treats a fight as one beat however long it runs, and starts a new beat at a cut. A continuous rescue-and-recovery is arguably one or two scenes, not four.
- **Beat 2's perilous flag is generous.** The scan's failure stakes were a lost reading and ten minutes, not Stamina, a life or the goal.
- Under a stricter count, the milestone after beat 4 would have come one beat later, after the jump, or not at all in this session.
- **Consequence:** the finer split and the generous flag brought the act 1 milestone, three purchases and a Fate refill (Rook +2) earlier than a strict reading. It is the same pattern as P1's beat-splitting finding.

**Correct, with a judgement call on Expertise: the jump (G006–G007, events 28–34).**
- Two hazards were declared before roles were assigned, which the leg rule allows (`skin:100-112`).
- Astrogation: Scout Surveyor for Advantage at 1 Fate (`skin:75`), EDU 14 after the purchase, kept 6. A clean emergence; Fuel +1.
- Unfilled Engineer role: correctly no benefit and no penalty, because no wear hazard was declared.
- **Judgement call:** Mira's watch-officer test was SOC with Advantage from her Liaison Expertise ("permit liaison work"). The watch-officer role is early warning (`skin:112`), and keeping a quarantine relay open and sending a permit is a stretch for liaison. The Advantage was generous, though this test's success did not depend on it: it kept 6 against 14.

**Correct: the trade (G007–G008, events 38–39).**
- One concrete stake, with the job's terms agreed earlier and its conditions met.
- SOC 14 with Advantage: the watch benefit and Liaison Expertise do not stack, which is correct (Adventurer's Manual, line 40). Kept 11, margin 3, a success: +1 Ship Share, since Debt was 0. The stake is consumed and the watch benefit spent.
- The failure and natural-20 consequences stated before the roll match the skin.
- Merchant Broker was offered and correctly not needed.

**Correct: the milestone purchases (P006, events 19–27).**
- Kest EDU 13 → 14 and Mira SOC 13 → 14, each for 2 points at or above baseline.
- Rook EDU 10 → 11.
- All made while the session was open.

**Not exercised:** the Strain steps, crisis and purge; misjump; Engineer wear; Merchant Broker's reroll; Medkit; combat; Ship Shares at 0.

## Procedure

- **Revision 5, options with consequences.** Every risky option carried its test and its consequences. There were **no pure commitment pauses**; G005 was a legal post-roll Fate decision. This is the clearest example in the pilot of the options rule working.
- **Dice shown from the first roll.** Every roll shows its dice, kept result and margin.
- **Pacing.** 6 beats (4 + 2) in 8 Guildmaster replies. Act 2 was two beats, a clean jump and a successful trade, with no new setback.
- **Low risk throughout.**
  - All seven tests had Advantage, from Expertise or a paid knack, and every kept result succeeded after one 1-Fate nudge.
  - Two things together kept the risk low: the skin's broad Expertise tags matched to crew roles, and the Guildmaster routing each test to the character with fitting Expertise.
  - This is a design observation for the joint review, not an error. It is also why zero Strain says little about the additive-trigger revision, as Astra's report notes.
- **NPCs** acted from their declared wants and lines: Brant's verification, Sela's proof-before-payment, Ilya's protection of the route log.
- **The temperaments rarely diverged.** The three players agreed on nearly everything, as Astra's report notes.
- **Records.** The recap's append-only threads keep superseded entries. The final thread still calls Ilya's introduction owed after G008 sent it. This is the known `recap.py` limitation.

## Records and access

- **Checkpoints.** The recorder reports 8 of 8 comparisons true, with historical copies. I compared the log against the transcript for every roll and Fate change, and found no discrepancy. Event 17 confirms G005's numbers exactly: rolls [11, 20], raw 11, nudge −1, final 10.
- **Draws.** Seven sequential seeds, 81004001–81004007, in event order.
- **Leaks.** Nothing hidden was disclosed before it was lawfully discovered. The recorder's route-log risk came from Ilya in the fiction. The packets include the crisis table, which revision 5 allows.
- **Access.** The native traces record zero tool calls for all three players. Player access was instructed, not enforced.

## Summary

P8's mechanics are clean and reconciled. Its findings for the joint review:
- **Scene granularity.** A continuous 17-minute operation was split into four beats, with a generous perilous flag on the scan. Together these brought the milestone forward.
- **Choosing the roller.** The Guildmaster twice chose which of two volunteers rolled, without asking.
- **The standoff hold.** Narrated as harsher than the frozen scenario's wording.
- **Expertise breadth plus role routing.** Every test had Advantage and Strain never moved. This is a design observation for Barry, alongside P4's finding that AI players route around Pressure until the only way forward costs it.
