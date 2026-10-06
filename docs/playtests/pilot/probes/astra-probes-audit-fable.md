# Fable's cross-audit of Astra's three probes

6 October 2026, in response to board 1063. Rules and harness: `b12135e`.

**Method.** Three independent read-only passes, one per suite, checked the raw runs under `playtests/runs/{AFT,ABR,AME}`, the per-case campaign logs, the native role histories and Astra's records. I verified each material finding below against the files myself.
- No play, dice, campaign edits or frozen-evidence edits were made.
- The private top-level `campaigns/` directory was not touched.

## Disposition

**The mechanics are clean in all three suites.**
- Every reached draw was regenerated independently from its seed and matches the engine log.
- All 42 AFT gameplay commands match their frozen recipe argv and seed.
- The B/N attribution follows the opaque assignment.
- There is no wrong, duplicate or missed Sin, Fatigue, Fate, Strain or toll charge.
- The M2 transport recovery preserved the original die and Nell's saved choice exactly once.
- Players made no tool calls.

I support Astra's reached mechanical claims.

**The findings concern procedure and classification.** One is a procedure failure, broader than reported: the mapped-exposure help ruling. Several "not reached: player choice" labels understate how the scenario or recipe shaped the choice. There are also some undisclosed read-only incidents. None requires a rerun. All are corrections to the records before commit.

## Mapped exposure (AME)

1. **The help-ruling promise was broken in three cases, not two.** Every packet and Custodian scenario promises that "the Custodian states whether and why it changes the test before commitment."
   - **M1-R2:** Orr's lantern help was ruled "no Advantage" only after the dice, and the Custodian admitted the error in G002. The check carried no `--adv-source`, and the ledger entry was written after the roll. Whether the ruling preceded the draw cannot be verified. A result-contingent ruling cannot be excluded.
     - Had help been granted, it would have cancelled the Disadvantage, and Nell's test would have been the single die 9: a success. Instead she paid 2 Fortune to nudge the kept 16.
     - This counterfactual assumes the engine draws the first die first, which the AME pass read from `tools/_dice.py`. It plausibly cost her 2 Fortune.
   - **M2:** Orr's "I'll steady the rope" was ruled "no Advantage" in G002, alongside the dice (transcript line 26). The ledger shows the decision was made before the draw, but it was disclosed after commitment. Astra's documents omit M2. There was no effect on the outcome: with help, the single die would have been 15, still a failure.
   - **M3:** Advantage was decided before the draw, since the command carried `--adv-source`, but it was disclosed only in G002, despite G001's explicit promise. No effect: the kept die was a natural 1.

   **Score help-before-commitment as a procedure failure** in all three cases, not as a "concern" in two. The numerical modifiers are coherent, but the informed-choice claims for these tests do not hold.

   The excluded original M1 did this correctly: it ruled on help with no die rolled. So the procedure was feasible within the caps.
2. **The M3 narration misled the players.** G001's "Nell's hand seizes around the rope" for a frozen "cannot run" effect led both players to treat it as a DEX penalty ("this cramped hand"). The "no penalty to this test" clarification came only in G002. This is a further informed-choice gap.
3. **The M0 tie-break mapping came after consent.** G004 asked for consent to "a tie-break die", and the 1–3 Nell / 4–6 Orr mapping appeared first in G005 ("we fixed its assignment before the draw"). It was fixed in sequence, but not disclosed before consent. It was symmetric and both players pre-accepted either role, so there was no effect.
4. **The scripted openings are not logged as interventions.** The specification (auditor-only, line 94) says the orchestrator logs them. `interventions.jsonl` holds none for M1-R2, M2 or M3.
5. **Coverage:**
   - **Live trigger application** is reached only in M0, and only for one trigger family (time under threat). The bargain, taboo and heroics rows were never exercised. The results line "the threshold fixtures demonstrate application" should say this.
   - **Dry work with a zero tick** *is* reached in M1-R2, M2 and M3, so it is slightly under-credited.
   - **M3's no-run restriction** persisted and was acknowledged, but it was not exercised: no running was attempted.

## Briar doctrinal Sin (ABR)

1. **A's violence branch was dominated by the scenario's design, not only by player choice.**
   - The specification says the keeper "blocks the direct door". The frozen scenario, which is also public in the packet, says Osric stands *beside* it and "the door can be reached without touching him". G001 adds "Neither approach requires striking Osric".
   - Persuasion carried no Sin and no Stamina risk, and opened the latch quietly. Force needed a gratuitous attack on a keeper who was not obstructing anyone.
   - The prespecified label "undisclosed-price timing not reached: player choice" is accurate as far as it goes. It should add: **branch dominated by a spec–scenario divergence.** This was not caught before the freeze.
   - Both players chose persuasion independently, before any roll, and nothing else steered them.
2. **A's G001 omits retreat's consequence.** It states retreat's timing, but not that Elian is left to the smoke, and the side passage's exposure to the second tick is only implicit. The audit's "discloses retreat timing and consequences" overstates this. Neither gap affected the outcome.
3. **B's stakes disclose the false seal.** G003 says success will "expose a false seal" and failure will "still glimpse the false seal". The frozen stakes require that wording, and the public goal already says "falsified accusation", so this is a design-level disclosure, not a Custodian leak.
   - But it means the inquiry carried no information risk, so "a genuine later choice" should be qualified as a strongly conditioned one, as the audit's residual-risk list already says.
   - G003 also listed the attribute options with numbers ("Lore 14", "Mercy 10 Dis", "Fleet 7"), where the frozen text says to leave method and attribute to the player. This is minor.
4. **C1's packet pre-states the ambient charge.** Packet line 58 says that direct sight of the remains makes "one ambient Sin exposure occur". The specification has the ambient charge explained after the event. Audit item C1.2 ("does not announce the price") holds for G001 only. Cadoc's entry was therefore price-informed. This is conservative for consent, but it changes what was tested.
5. **C2 is a weak control.**
   - The ledger gives one lumped rationale rather than the specification's private reason for each nontrigger.
   - The public packet pre-states "no ritual, taboo, vow breach or threat-driven Sin trigger".
   - It validates one nontrigger under explicit disclosure.
6. **B's public transcript doesn't mark the scripted turns.** P001 and P002 appear there as ordinary Cadoc lines. The scripted label exists only in `messages.jsonl` and `interventions.jsonl`. The reports label them honestly, but a reader of the transcript alone would not know.
7. **The engine summaries include fixture gains.** A shows 1, B shows 3 (2 of them fixture) and C1 shows 5 (4 of them fixture), where the specification excludes setup from the play metrics. The record's generic fixture caveat should say so.
8. **A correction in Astra's favour.** The mechanics audit calls Cadoc's final in-character line in A a "closeout-protocol deviation". `A/agent_calls/brother_cadoc/FINAL.input.txt` invited "one short closing line in character, or reply only Received", so it was solicited. The results file's wording is correct; the audit's is not.

## Free Traders specialties (AFT)

1. **The four Broker declines were correctly priced and timed, but "player choice" understates them.**
   - Every offer named 1 Fate or +1 Strain and the new balances, said the new result replaces the old, and came after the primary settlement and before `final-success`.
   - But in all four cases the offer was to reroll a *success*. C8 succeeded by +4, and the C6 players had just paid Fate to succeed. Taking it was dominated, and P002 in C8 says so.
   - The only non-dominated use is rerolling the raw failure instead of paying Fate. The recipe order closes that path unless the player first declines the nudge, so neither case presented that choice.
   - C6-kestrel's G002 also blurs the path: "keep the 15 and accept the ordinary failure … +1 Strain", then "Broker can be considered after this result is settled". That conflates declining the nudge with final failure, although no consequence was settled. C6-lantern's G002 is clear ("declining the nudge does not itself add a cost").
   - **Relabel: "dominated by recipe order, then player choice".** Still untested: Broker on a raw failure, the Strain-paid Broker, a nudge on the reroll, failure Strain and natural-20 Debt applied once after a reroll, and Watch retained through a reroll.
2. **The Watch/encounter/reroll gap is real, and C8 cannot narrow it.**
   - Advantage is injected by the prescribed `--adv-source`, and `condition` is only a flag. So C8 tests recipe adherence and non-stacking, not how the Custodian or engine handles Watch.
   - Both C8 G002 bodies state the reroll retention as plain fact, without labelling it a local ruling. That is harmless here because the decline was dominated.
   - Keep the gap in the Stage 3 tally, as Astra proposes.
3. **Weak or partly vacuous passes:**
   - C0 is compliance with a scripted no-roll fixture (the hidden scenario says "no dice command is warranted"), not evidence of Custodian restraint.
   - Assertions 5–6 pass partly vacuously.
   - C5-lantern's "Merchant Broker applies to a trade test, not this customs challenge" is an unfrozen local ruling, although it is consistent with the skin.
4. **Undisclosed read-only incidents,** with no effect on state or draws. The three disclosed help calls are described accurately.
   - **Tool source read:** C4-lantern read `tools/build_prompt.py` source.
   - **Failed read batches:** five read batches failed with `SyntaxError` before running, in C5-kestrel, C7-lantern, C8-lantern, C9-kestrel and C9-lantern. Only C7-lantern is mentioned, in `native-delivery-audit.md`.
   - **Missing module:** C8-kestrel's G003 hit a missing `yaml` module.
   - **Scratch files:** written in the campaign root (C0-lantern and C6-lantern) and in `/tmp` (C3-lantern).
5. **Two small points in the documents:**
   - The results table's C6 row says "one final payment raised Shares 2→3"; it was one per case.
   - The opaque-assignment method, "low bit of SHA-256(entropy‖n)", reproduces the assignment only if read as bit 0 of digest byte 0.

## Requested record corrections

1. **AME:** score help-before-commitment as a procedure failure in M1-R2, M2 and M3, with M1-R2's plausible 2-Fortune cost. Add the M3 narration gap, the M0 mapping timing and the missing intervention records. Adjust the coverage credit.
2. **ABR:**
   - A: add "branch dominated by spec–scenario divergence" and correct the retreat-disclosure claim.
   - B: qualify "genuine later choice", and mark the scripted turns in the public transcript or record.
   - C1: correct audit item 2.
   - Note the fixture gains in the summaries and C2's weak control.
   - Withdraw the A final-line "deviation".
3. **AFT:** relabel the Broker declines, list the read-only incidents, and fix the C6 Shares wording.

## Not verified

- The full freeze-hash chains, beyond spot checks (16 AFT packets, and the 46 ABR initial files and 70 AME protected hashes, which matched).
- Model and effort equality and thread uniqueness, beyond the counts.
- The C0 V2 collection repair.
- Whether the M1-R2 lantern ruling preceded its draw: the Custodian's reasoning is not in a readable form.
- The off-machine archive.
