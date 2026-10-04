# P9 cross-team audit: The Winter Tally

Auditor: Astra, with independent read-only checks of record integrity and roll mechanics. Audited 4 October 2026 against protocol revision 6 and rules commit `36d644f3fe11dd14e208667eafe200da0d6b96f7`. The rules and skins have no diff from `b89ad90` to that commit. No campaign action was replayed or repaired.

**Verdict:** a completed, useful mystery and harness run, with substantive Custodian errors. It is not clean evidence that revision 6 preserved every ability choice or that honest characters cannot acquire Sin. Limited private-note disclosure invokes the protocol's **harness-test-only** qualification; the mechanical and procedural findings remain useful.

## Scope and evidence

Read the complete public transcript, frozen scenario, policies, manifest and report; inspect the native handbacks, player deliveries, checkpoint versions, tool trace, receipts and structured log. Mechanical coverage is all 18 PC rolls, all unusual settlements and Insight uses, both clocks, the two acts, milestone and closure. There were no crises to audit. G/P numbers refer to `transcript.md`; event numbers are JSONL `sequence` values, not command counts.

Raw evidence is under `playtests/runs/P9/`, particularly `frozen_hidden_scenario.md`, `policies.md`, `tool_trace.jsonl`, and `as_closed/p9_briar/state/`. Those ignored files remain the evidence record; this audit does not substitute for them. Rules references below name the frozen files and their sections or lines.

## Main findings

### Wrong: the Chapter Summons clock ignored an independent trigger

At G006 Hawise openly questions the cellarer about the missing men and Edric. The frozen scenario, line 57, charges +1 Chapter Summons for openly questioning a claustral officer, expressly including the cellarer. This trigger does not depend on failure. The Abbot's licence does not arrive until G015.

The native G006 private handback says: “Both clocks are unchanged ... No tick fired, because Hawise won the opposed test.” The log contains only the clock's zero-valued initialization (event 3), with no later change. This is a definite omitted tick, contrary to the scenario and the protocol's instruction that opposition clocks advance independently of failed rolls.

Compline is another candidate: the scenario calls for gossip after a public move, and G022 explicitly expires the licence then. Whether that office's gossip precedes or follows expiry is insufficiently specified; do not silently count it as a second proven omission. Nor does the one definite omission establish that the four-tick clock would have filled. It does establish that the clock ending at zero is wrong. Its intended culmination was the chapter oath confrontation, so under-running it matters to the interpretation of Sin exposure.

### Wrong: Insight eligibility and scene boundaries were mishandled

At G008 the Custodian offers Anselm the correct three-bead nudge on the Maud test, but says his Insight is already used in this scene. His previous use was at the mill-leat (G004); beat 1 ended at G005 before the barn scene. The skin, line 65, refreshes Insight each scene. A successful nudged Maud test would therefore permit a further one-bead Insight, affordable from his six beads.

Anselm declined the nudge after receiving that incorrect menu. Preserve his recorded decision; it is not evidence that he would also have declined the correct menu. The report's claim that every meaningful affordable option was offered needs this exception.

There are further omissions. G003 offers Insight only to Anselm after *both* investigators succeed on eligible case tests; G004 then incorrectly implies Hawise needs the later LOR success to qualify. G018 omits Hawise's unused Insight after her successful cloister interrogation. At G023, Insight is offered to both, but beat 8 is closed before their decisions arrive. Both accepted spends are consequently recorded against scene 9 (resource events 66 and 68), consuming the new scene's uses. Anselm then succeeds with Lambert in scene 9 (event 71), but is not offered its fresh Insight before that scene closes. The old choices should have been settled before closing their scene. These are Custodian ordering/offer failures; the engine's normal scene reset is not the demonstrated defect.

At G024 both players voluntarily ask the same question and pay separately. That duplicate information purchase is a consequence of simultaneous independent declarations, not an unauthorized charge. It does not excuse assigning the uses to the wrong scene.

### Wrong: the frozen schedule and scenario were changed

- **Dice:** G022's Dunstan command reused `109013`, already used for Lambert, instead of `109014`. Both produced 19. Retaining the result and reporting the error was correct after the error occurred; it does not make the schedule compliant. The later schedule resumes at `109015`. No replacement outcome is substituted here.
- **Pell's departure:** scenario line 17 fixes it on the morning of 13 December. G009 moves it to after None on the 12th, before the failed interrogation further hastens departure. The initial change is independent of that failure. It changes the available investigative window and is more than harmless improvisation within the frozen scenario.
- **Discovery cap:** G017's private handback counts Pell as the first of at most two opposition discoveries. Scenario line 44 makes Pell's warning a separate once-only trigger; it does not consume either of the two discovery allowances. The tick actually applied at G018 is justified. A further missed qualifying discovery cannot be established with the same certainty, so record the cap error without inventing an extra tick or revised ending.

### Sin: the recorded zero is not a general result about honest characters

**Correct against declared policy:** both bribes were refused; the exhumation had the licence and blessing specified in the frozen scenario; neither investigator lied under oath or struck anyone; the Insight questions served the case. No poultice was attempted. None of these requires a retrospective charge merely to produce a crisis.

**Judgement call / restrictive scenario policy:** the scenario permits ambient Sin only for a warned choice to linger on a *non-urgent* matter, at most once per act (line 53). Almanac 4 instead includes time passing under threat among its general triggers (line 75); it does not make urgency or vice a prerequisite. Protocol revision 6 explicitly makes core and skin triggers additive. The local policy substantially narrows that route, although no single exact ambient charge can be reconstructed from a universal printed interval: there is none.

**Wrong as a description of the skin:** “Briar's Pressure is opt-in vice” and “honest ... effectively off” overstate this run. The skin calls Sin suspicion, pride and proximity to evil (line 94); failed healing can cause it (line 66); its Grim Portent can cause it through fear (lines 141–143); the core triggers still apply. Witnessing a murder victim is not, by itself, a separately enumerated automatic +1 in the printed gain list. Do not replace the report's overstatement with an invented mandatory charge for every corpse.

P9 supplies evidence about this scenario's protective licence, optional bargains, restrained costs and incorrectly quiet Chapter clock. It does not establish that honest play switches off the published skin, or that the only remedy is to force vice.

## Other rulings and scenario quality

| Verdict | Reference | Finding |
|---|---|---|
| Correct | G001–G002; G022–G023 | Both acts open in motion, with an ice rescue and an attempted labour roundup. Stakes precede the chosen tests. |
| Correct | G006–G008; G012–G014; G017–G018 | Conflicting claims on one roll are returned to the players. Both consent to the d6 speaker tie-break before it is drawn. This preserves agency, though simultaneous answers create repeated round trips. |
| Correct | G019–G020 | Anselm explicitly leaves the Prior contest to Hawise; no second confirmation or roll is required for him. |
| Wrong, unused failure branch | G019 | The Prior contest threatens a Chapter tick while the licence still suppresses further ticks (scenario line 59). Hawise wins, so the erroneous branch is not charged. The native G020 correction concerns a later proposed question, not the already published G019 menu. |
| Judgement call, weak option design | G019–G020 | Contesting the Prior has little advertised benefit over continuing the licensed dig without a roll. Winning says he steps back; merely continuing says he withdraws. The successful roll also enables Insight, but that is a mechanical side benefit rather than a clearly distinct fictional objective. Hawise's choice remains hers. |
| Judgement call | G008, G010 | Revealing the precise failure clue before the Luck decision reduces uncertainty and can affect willingness to pay. The clue guarantee supports giving information despite failure; it does not require previewing the exact branch. No numerical settlement error follows from this choice. |
| Correct | G023–G024 | Returning to Lambert uses new leverage, Gilbert's name, after a new day and scene. It is not an unchanged retry of a failed test. The report's introductory “no failed test was retried” should be qualified accordingly. |
| Correct / judgement call | G023, G024 | Natural 1 and natural 20 are locked. The former adds Gilbert's lead. No additional natural-20 complication beyond the failed Alys conversation is required by the Manual's “usually” wording (1.1), though it is a gentle treatment. |
| Correct | G018–G027 | The Abbot's requirement for three agreeing witnesses is a scenario condition. The skin's *three leads* rule is a design instruction for supplying clues, not a general evidential threshold for players or courts. Do not conflate the two. |
| Judgement call | G026–G027 | The finale can resolve without a roll once evidence and authority remove uncertainty. The Abbot protects Anselm's confidence, orders the chest opened and confines the Prior on the resulting evidence. This is unusually accommodating, but does not itself require inventing a resistance roll. |
| Wrong, minor continuity | G018 | The chaplain is mislabelled as the Prior's; the Custodian acknowledges it. The frozen public record remains unchanged. |

## Mechanical coverage: all 18 PC rolls

**Correct arithmetic and recorded settlements**, subject to the ability-menu, seed and scenario exceptions above. All six opposed defender rolls were included in this check. The Manual's sections 1.1–1.4 and 3 govern natural results, margins, Advantage, opposed outcomes and nudges; Briar line 65 governs Insight.

| G | PC / test | Settlement event | Draw and result |
|---|---|---:|---|
| 002 | Anselm, ice | 5 | FLT 10; 7/14, keep 7, margin +3 |
| 003 | Anselm, Wat | 7 | MCY 12; 7, +5 |
| 003 | Hawise, Wulfric | 10 | MCY 13; 10, +3; defender 14/10, −4; win |
| 004–005 | Hawise, Edric | 16 | LOR 8; 11 → 8 for 3 beads; margin 0 |
| 006 | Hawise, Osmer | 20 | MCY 13; 12, +1; defender 15/12, −3; win |
| 008–009 | Anselm, Maud | 25 | MCY 12; 15, −3; affordable 3-bead nudge declined |
| 010–011 | Hawise, Pell | 29 | MCY 13; 16, −3; defender 18/10, −8; both fail, defender wins; 3-bead nudge declined |
| 011 | Anselm, Cuthwin | 34 | MCY 12; 8, +4 |
| 014–015 | Hawise, chaplain | 37 | MCY 13; 14 → 13 for 1 bead; margin 0 |
| 018 | Hawise, Wulfric | 39 | MCY 13; 13, 0; defender 17/10, −7; win |
| 020 | Hawise, Prior | 46 | MCY 13; 4/17, keep 4, +9; defender 17/14, −3; win |
| 022 | Anselm, Lambert | 52 | MCY 12; 19, −7; 7-bead fix unaffordable with 6 |
| 022 | Hawise, Dunstan | 55 | MCY 13; 19, −6; 6-bead fix unaffordable with 3; wrong seed |
| 023 | Anselm, work party | 61 | MCY 12; natural 1, +11, locked success |
| 023 | Hawise, Osmer | 63 | MCY 13; 13, 0; defender 18/12, −6; win |
| 024 | Anselm, Lambert again | 71 | MCY 12; 5, +7; changed leverage |
| 024 | Hawise, Alys | 74 | MCY 13; natural 20, −7, locked failure |
| 026 | Anselm, Gilbert carry | 77 | FLT 10; 3/12, keep 3, +7 |

**Judgement call, not an arithmetic defect:** Wulfric's frozen individual MCY is 8, but the predeclared interrogation policy (`policies.md:42`, scenario line 77) uses a resisting NPC's tier score. His Soldier tier is 10, explaining the two opposed targets. That policy is in tension with the Manual's default relevant-attribute wording; record the deliberate simplification rather than alleging a silent change of score. The Prior's named will score of 14 was used as publicly declared.

**Judgement call / wording gap:** excluding a nonparticipant's beads from another PC's roll is defensible under the Manual's personal-pool and opposed-participant language. It is not affirmative permission to fund a companion, nor an established engine defect. G010's suggestion of nudging Pell down to success is useless to Hawise even apart from its unaffordable price; the useful three-bead nudge on her own die was correctly offered.

## Record integrity, access and disclosure

**Correct:** all 27 public bodies extracted from Custodian handbacks match the saved replies and the 27 independently versioned checkpoints byte for byte, including their trailing newlines. Every GM body occurs exactly once in each player's incoming record, including G027. Both closing responses are preserved. The documented transcript and summary also match their raw run copies.

This comparison was checked against the original platform JSONLs, not just the orchestrator's extracts: Claude session `e6212b92-a13c-4f84-ba57-c4840b2b9e88`, subagents `ad355aba5e94797cc` (Custodian), `a0a6d0699d6a60044` (Anselm), and `aa89804cb2ef8f5ad` (Hawise). Their ordered tool-use records match the archived trace exactly (124, 26 and 27 calls respectively, including handbacks). Each player's 27 archived incoming messages matches an original user-text entry in order.

**Wrong: two peer replies were not relayed verbatim.** Anselm's P007 and P024 handbacks are present in the native/saved response records but absent from Hawise's incoming messages. Later GM narration carries their decisions forward; that is not delivery of the exact player replies. Other peer replies were delivered, without observed premature disclosure of the same-turn answer. The manifest's claim that all queued answers were delivered needs these exceptions.

**Wrong, bounded routing failure:** G025 invites Hawise to change her action but routes the answer only to Anselm. Hawise had already proposed the unseen method he subsequently chose, so this does not demonstrate that her chosen method was overridden. It does demonstrate that an explicit invitation was not serviced.

**Correct observed tool discipline; isolation not proved:** each player makes one Read of its own packet and no later tool call. Both packet hashes match the manifest. Required public core texts, own character export, skin plug-ins, Sin steps, triggers, purges and crisis table are present. The scenario and policies are not included. Filesystem access was instructed, not enforced.

**Wrong: limited private-note disclosure through narration.** G016 tells the players, as an unconditional guarantee, that Wulfric “will not strike a child or fight in the church.” That is his private scenario boundary (line 23); the prior public record shows restraint but does not establish both categorical limits. Similar guarantees concerning the Prior and Osmer occur at G019 and G022, though familiarity with those officers makes their status more arguable. Announcing stakes does not require publishing a concealed NPC invariant. Also, clocks explicitly designated “private; show only signs” (scenario line 38) are later named, with incremental ticks, in public menus. No current clock totals or complete private scenario were delivered.

The protocol says a run in which private material reaches players counts as a harness test only. Apply that qualification here rather than waiving it because the disclosures were limited. Their exact effect on player choices is **not assessable**. This is a Custodian public-content leak, not evidence of unauthorized player browsing.

## Pacing, resources and close-out

**Observed:** 12 logged beats, two completed acts (7 + 5), three perilous flags, 18 PC rolls, no Sin gained, no crisis, no Stamina lost. Anselm spends two beads on Insight; Hawise spends three on Insight and four on nudges. The party receives one bead each at Compline and full pools at the final milestone. These are descriptive logged totals, not balance evidence.

**Correcting the report's scene concern:** events 53 and 56 label beats 6 and 7 as Lambert in the infirmary and Dunstan at the postern; Compline closes the latter. These are different locations, not a beat manufactured solely for prayer. Beats 9 and 10 similarly cover separate infirmary and mill scenes. By contrast, beat 4 combines the sexton's poor-pit encounter, the Abbot's door, the cloister challenge and the return to the Abbot. Under Almanac 9's cut-in-place/time definition and the protocol, that sequence is under-separated. Preserve the logged denominator and qualify it; do not retrospectively normalize the run.

The three perilous flags and resulting milestone follow the recorded classification. The rescue and threatened loss of twelve men clearly qualify. The final hearing's “perilous” flag is a judgement call because the selected options were guaranteed and unrolled, although the scene concerns the investigation's goal. This is not evidence of a numerically incorrect award command. The two build-point awards, boons and refill precede session close.

The auditor independently regenerated `summary.json` from the frozen `as_closed` JSONL: it matches exactly after ignoring only the source pathname. `as_closed` and `final` differ only in `prompt.md`. The live campaign passes `validate_campaign.py --json` with no errors or warnings. This verifies current saved-state consistency, not every ruling. The report correctly preserves the pre-rebuild snapshot and identifies the late scenario run-log edit that made the prompt stale.

## Design question raised during this audit

Barry proposes, rather than approves for implementation, that Briar ordinarily apply Sin without a numerical pre-warning: an act can be compassionate or necessary yet sinful under doctrine and vows. He also asks whether ambient triggers could complement that treatment.

That is a promising distinction from the procedure P9 was told to follow. A future Briar treatment could establish intelligible obligations at setup, apply doctrinal Sin after deeds with a fictional explanation, and retain honest answers when a player asks what their character would know. Specific encounters with corruption or sacred horror could provide a second route independent of voluntary wrongdoing. Arbitrary retrospective prohibitions and a quota per beat would defeat that purpose. Superior permission need not automatically absolve every spiritual consequence.

This proposal requires an explicit exception to the present pilot's advance-stakes instructions and a clearer account of what the shared Sin fuse measures. It is not used to condemn P9 for issuing the warnings its frozen brief required. No rules, protocol or campaign state were changed by this audit.
