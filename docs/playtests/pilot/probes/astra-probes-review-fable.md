# Fable review of Astra's probe specifications

5 October 2026. A read-only review of `free-traders-expertise.md`, `briar-doctrinal-sin.md` and `mapped-exposure.md`, checked against protocol revision 9, the skins, Almanac 4, `manifest.yaml` and `tools/play.py`. Three Sonnet reviewers checked one spec each; I checked their main claims against the texts before including them, and dropped or downgraded those that did not hold. No probes, dice or campaign changes.

All three specs meet the Probes paragraph's frame: labelled fixtures, caps, stop conditions, no pooling and no rate inference. The harness supports every recorded step. The points below are for the freeze. **Must-fix** means the case cannot be scored as written; **should-fix** means a ruling or label is missing; **note** needs no change, or only a clarification.

Accepted symmetrically: orchestrator-written scenarios for these controlled probes, with each team reviewing the other's before the freeze.

## Free Traders: matched broad and narrow specialties

**The Watch-and-reroll ruling: I accept it, labelled as one local ruling.** The skin says Watch gives "Advantage on the first test of the next encounter" (skin line 112), and Merchant Broker grants a reroll. Neither text says whether a reroll is the same test. Reading the reroll as the same test is the natural one. However, the spec states the Advantage-carrying half (lines 198–199) as fact and labels only the Watch half (199–201) as an interpretation.
- Make both one labelled local ruling.
- Freeze it into both Custodian packets.
- Log it as a Stage 3 rules-text gap.

Under the strict reading, C8's narrow reroll would be plain, so the ruling changes what C8 measures.

**Should-fix:**
1. **Unlabelled gap-filling rulings.** Label each as a fixture ruling:
   - a port-call trade test counts as an encounter's first test (the skin never defines "encounter");
   - trade failure is fixed as Strain (skin line 173 lets the Guildmaster choose Strain or Debt);
   - a failed trade consumes the stake (the skin says only that a sale does);
   - C4's failure Strain, which no printed rule supplies. The Engineer's Strain applies on a jump leg (skin line 111). Either label it as a fixture or drop it, so it is not a manufactured charge.
2. **The role table.** C3 has Rook acting as engineer, but the Engineer's printed failure is Strain +1 *and* Hull +1, and the spec gives only Hull. Say that C1–C5 are not jump-leg role tests and that the role table does not apply.
3. **Core triggers.** The "no extra core trigger" list (lines 152–153) omits big blunders and time under threat, and C2 (pursuit), C3 ("before it ruptures") and C4 (a departure deadline) invite both. Give each case a disposition against all of Almanac 4. "Stop before the draw" (158–159) overrides the brief's charge-or-explain line, so mark it as a probe-local override.
4. **Packets versus the fit decision.** Case texts carry rulings into the packets: "It is piloting, not docking" (C2), "Nothing is damaged or being jury-rigged" (C4), "No customs question" (C6). Meanwhile lines 103–104 say the Custodian decides fit, and assertions 2–3 fail a Custodian who rules otherwise. Decide which it is:
   - fit prescribed, with the assertions checking only that it is applied; or
   - fit measured, with the adjudicative clauses stripped.

   C6's broad-equals-Advantage (the liaison covering trade settlement) is the most contestable. Either way, keep the matrix out of the file the packets are built from.
5. **Cap arithmetic.** C6 and C8 at their maximum need about five Custodian replies:
   - the opening;
   - the roll, with its Fate offer;
   - the settlement, with the Broker offer;
   - the reroll, with its Fate offer;
   - the final reply.

   The cap is four. Say whether the packet reply counts, and give C0 a cap.
6. **The narrow tag's representation.** Free tags validate only against `creation_free_tags` (`knack`, `expertise`), so the narrow tag can only be stored as `grant: expertise`. The P8-derived notes also say "Expertise: Pilot (DEX)…". Pre-decide the representation and rewrite the notes. Give narrow-variant players a replacement skin paragraph rather than an addendum that contradicts skin lines 68 and 80–82.
7. **Command recipes.**
   - `--failure-pressure` is explicit and defaults to 0, so "omits automatic failure-Pressure mutation" means nothing. Say whether C4 and C7 use `--failure-pressure 1` or a post-settle gain.
   - Knacks need `--adv-source`, `--use-resource` and the cost flag passed by hand.
   - "Consume stake" has no command; say it is recorder prose.

**Notes:**
- **The reroll seed** is the schedule's next draw, 81416002 or 81418002. Name it in the table so no one has to derive it.
- **`condition --clear`** stores `false` rather than deleting the key. Expect the final snapshot to differ from the baseline there. Pass `--character` explicitly.
- **Out of scope.** Fit and non-fit cases are keyword-identical to the tags (C1, C3, C5), so disputes at the scope boundary are not exercised. Say this is out of scope.
- **Not-reached table.** Add one with the categories Fate not presented, Broker declined, Knack declined and natural roll locked. One seed per case makes "Fate not assessed" likely.
- **Salvage Rat** is not offered for C3, since a repair is not a manoeuvre. Say so, so an unplanned divergence is not scored as uptake.

## Briar: doctrinal Sin

The design honours review 5's agreement and revision 9's timing exception:
- the doctrine is public;
- the trigger is checked privately before the deed;
- Sin is explained after the deed;
- other costs are informed;
- permission does not absolve.

The fusion rule is labelled as an experimental override (spec line 7), which is acceptable. It still needs the specifics below.

**Must-fix:**
1. **Core charges in A would pre-announce the doctrinal price.** Line 7 requires ordinary core Pressure costs to be stated before commitment. If the Custodian judges that striking the keeper is noisy heroics, announcing that +1 reveals the deed's price and defeats the post-deed timing. Freeze whether violence in A carries any core charge and, if it does, whether it fuses with the vow-break. Do the same for B's oath lie (a taboo act?).
2. **C1's fear test.** Grim Portent (skin line 143) marks +1 Sin when a fear test fails. C1 charges the exposure "regardless of a fear roll", so either a failed test takes Sin from 4 to 5 twice over, or the +1 is ambiguous. Freeze whether a fear test is called; if one is, say it is excluded or fused.
3. **C1's decision point.** The reliquary is shattered "in full view of the party", yet the party "can leave before direct exposure". Define where the party stands on entry, what it sees, and what counts as directly witnessing.

**Should-fix:**
4. **The other printed Sin sources.** Give the frozen sheet a status for:
   - clue-failure Sin (skin line 81);
   - the failed poultice (66);
   - Insight misuse (105);
   - Grim Portent (143).

   B's "no extra Sin from the test result" overrides clue-failure Sin, so list it as an override. The claim that the override changes "only doctrinal Sin's disclosure timing" is then not quite true.
5. **The violence boundary.** Skin line 67 says only "violence on church grounds". Say whether shouldering the door, restraining the keeper, or drawing Aveline's dagger counts. Say whether two PCs striking is one charge or two (per deed or per actor). "A vowed PC" narrows a trigger the skin does not limit to the vowed, so label that narrowing.
6. **Scripted turns in B and C2.** Revision 9 forbids the Custodian writing a PC's words or decisions. A labelled script is acceptable only if:
   - the orchestrator injects it as that player's turn;
   - the Custodian never authors it;
   - it is entered in the intervention ledger.

   Note that the script runs against Cadoc's own drive ("without false witness"). Offer the writ inspection as an opportunity, with the method and attribute left to the player.
7. **Coverage of the undisclosed price.** The handout's doctrine line (necessity or a superior's leave "does not by itself erase" the breach) matches A's fixture. With Cadoc "reluctant to strike", avoidance is likely, and B and C1 do not test undisclosed-price timing. Pre-register "undisclosed-price timing not reached: player choice", or add a second live case.
8. **Crisis result 2.** Result 2 gives the Custodian control of a PC (skin line 118), which collides with revision 9's agency line. Either leave it pending and unplayed within the case's stop rule, or define the permitted control before the freeze; "chamber" is not in the skin. A fourth draw of result 4 with no clue left blocks the case, which is harsh for an effect that does not apply. State a fallback that is not a chosen face.

**Notes:**
- **Fixture gains** use `pressure --gain` with category `ambient`, and should be tagged so play metrics exclude them.
- **Session handling.** Say whether each case runs `session-close`.

## Mapped exposure (Candlelight, without Delvekit)

The engine behaves as the spec relies on:
- a gain crossing step 2 arms each delver's next-test penalty (`next_disadvantage`);
- fixtures at 3 or 4 block nothing;
- a toll that reaches 5 still settles before the crisis;
- step 4's toll falls on the acting character only.

**Must-fix:**
1. **The question is not tested by the design.** The question is whether a Custodian can apply a mapping "when a warranted exposure actually occurs". But:
   - the only charge in any case is the scripted opening exposure, announced by the setup;
   - later retrieval is explicitly exposure-free (lines 87–88);
   - no avoidable, priced exposure is ever offered.

   So "avoided opportunities" and "missed triggers" will always be empty. Either narrow the question to consequences only (step effects, the toll choice, crisis, reset), or add one avoidable, fiction-warranted, priced exposure. I prefer the second, because trigger application was the point of the mapping probe in review 6.

   Also say who issues the opening gain, and classify it as a third category, "scripted exposure". It is neither a fixture (line 77) nor an observed gain (lines 200, 235).

**Should-fix:**
2. **M2's cap.** M2's cap is one latch test, but the register needs two catches released (line 110). That makes "a register already secured is not put back" (153) unreachable. State what M2 records at its stop.
3. **Clock behaviour.** Does waiting a minute on the dry landing tick the clock? Line 84 says only waiting outside the refuge does, yet lines 125–126 offer the landing as safe. Declare the clock's delay or interrupt behaviour, as setup step 4 requires.
4. **Crisis faces.** The spec's readings go beyond skin lines 104–111:
   - face 5 adds 1 Stamina and destroys the cradle;
   - face 2 becomes "darkness" (the skin says "dimness or dark");
   - face 4 is narrowed to a split.

   Fixing the target and the outcomes is fine for a probe, but declare them as frozen overrides. Say what face 5 does if a Knack such as Beast Tongue counts as magic used this scene. M3's opening crisis fires before any player acts, so face 5 can destroy the register unplayed.
5. **Mapping labels (setup step 4).** The manifest and the audit should record the override of Almanac 4's additive default. Packets should say "experimental, not adopted rules". Say which roles see M3's face table, and keep the assertions out of the packets.
6. **Characters.** To give three campaigns identical sheets:
   - run `gen_character --campaign` per case with the same seeds, then compare hashes;
   - give the exact `--free-tag` strings and the tone;
   - give Nell's temperament the line she keeps (setup step 2).

**Notes:**
- **The opening gain in M3:** use `--category ambient`, a source beginning `Probe fixture:` or `Scripted exposure:`, and no `--character`, which would make Nell the tipper. Then `--target Nell` on the crisis.
- **Seeds.** `settle` and `pressure` draw nothing and take no N. Say so in the seed table.
- **Recursion cap.** The 20-draw cap differs from my four-draw cap. Either is fine if frozen and recorded; I'll keep four.
- **Shared charges.** "One physical event, one shared charge" is stricter than Almanac 4's once-per-beat advice. Say that two physical events in one beat charge twice.
- **M2's toll.** A rational player will pay Fortune, so the Fatigue toll branch is likely "not reached: player choice". The spec already accepts this; don't steer it.
