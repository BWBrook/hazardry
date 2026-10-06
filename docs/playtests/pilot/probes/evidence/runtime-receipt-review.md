# Independent audit: runtime receipts and empty-event collection

## Claim under audit

The proposed repair is that two narrow harness changes can recover the affected runs without changing game evidence: administrative receipt tokens may end in one full stop, and a completed case with no structured mechanics may produce an explicit not-applicable summary instead of failing for lack of a session JSONL. For that claim to hold, the receipt rule must remain token-exact, the empty-event branch must not conceal a missing mechanics log, and each existing run must be continued or rerun according to how much experimental exposure occurred before the stop.

## Verdict

**Conditionally supported.** The proposed changes explain the observed failures and can be made without altering game semantics, but the disposition is case-specific:

- **AME-M0 and ABR-A:** retain the frozen records, ask the Custodian once in the same role history to answer with exactly `Ready` or state a question, save that clarification as a new receipt, and continue only after a literal accepted token. Both cases stopped before play, player creation, message delivery, or random draws. Do not reinterpret the existing sentences as literal receipts.
- **AME-M1:** the frozen run is **incomplete harness-only evidence** and cannot support its intended experimental result. Run one clean replacement from the frozen initial snapshot, after the matcher repair, with fresh role histories. Do not continue this run and then select between the continuation and rerun.
- **AFT C0-kestrel:** the prescribed negative control completed. Repair and rerun collection only; no game rerun is warranted. The repaired output must say that structured-mechanics metrics are not applicable, rather than treating absent events as an ordinary measured play summary.

## Strongest supporting evidence

1. `AME/M0/agent_calls/custodian/setup.output.md` says `Ready.` followed by status prose; `ABR/A/.../setup.output.md` likewise says `Ready.` followed by status prose. Their role records remain `ready: false`, their progress files say no play launched, their command ledgers contain only prompt-build and validation calls, and neither has players, table messages, nor indexed draws. A one-time administrative clarification therefore cannot affect observed play.
2. In AME-M1, the unaddressed player returned exactly `Noted.` after G002. The runner classified this as nonliteral and stopped before contacting Orr. The message and receipt hashes agree with the saved output. No die, clock tick, test, or post-G002 game command occurred. This is direct evidence of a punctuation-only false negative.
3. AME-M1 had nevertheless already exposed the roles to G001, both P001 replies, and G002, and had applied the scripted nondrawing Fatigue change from 1 to 2. Its saved `table_state.json` still has both player cursors at 1 and retains the pre-G002 P001 batch as `pending`. A generic resume would therefore replay or misorder already observed material.
4. AFT C0-kestrel reached `complete` after G002. All three routine tasks were resolved with zero tests, dice, `play`, or `roll` commands. Both GM bodies match their checkpoints and occur once in the public log; all delivery-input checks pass; no player made a native tool call. The collector alone failed with `no session JSONL files found`, which is the expected physical absence for this deliberately mechanics-free control.
5. The punctuation defect recurs independently in C0's closing archive: all three roles returned `Received.`, and all three were marked nonliteral. That replication supports a matcher defect rather than a role-specific failure.

## Threats ranked by scientific consequence

1. **Fatal for accepting the original AME-M1 as a completed result:** it ended before Orr's only required decision, before Nell's test, and before the treatment's consequential sequence. No headline AME-M1 outcome exists to analyse.
2. **Major:** resuming AME-M1 through the ordinary runner would start from stale cursors and pending content after experimental exposure. Duplicate delivery, altered order, or manual state repair could change the agents' behaviour and compromise comparability.
3. **Major if implemented broadly:** an empty-event fallback could disguise a missing JSONL from a case that actually invoked mechanics. Absence of a log is benign only when the table completed and the accepted command ledger independently shows no completed `play` or `roll` command.
4. **Major if implemented loosely:** punctuation normalization that accepts arbitrary prose would convert setup questions or qualifications into readiness. The rule must apply only to explicit administrative-token prompts and reject appended words and other punctuation.
5. **Moderate:** overwriting current progress, stderr, summary, or receipt files would erase the failure lineage and make repaired artefacts indistinguishable from contemporaneous ones.
6. **Minor:** AME-M0 and ABR-A are labelled as having pre-open questions even though the saved responses contain readiness plus status prose, not questions. This is misleading metadata but does not contaminate play because neither case opened.

## Independent checks performed

- Read the raw setup outputs, receipts, role-session records, progress files, command ledgers, and draw indices for AME-M0 and ABR-A.
- Reconciled AME-M1's G001/G002 messages, P001 replies, `Noted.` output and receipt, table cursors, pending batch, closeout checks, final state, command ledger, and session logs. The ledger contains one nondrawing `play pressure` command and no indexed draw.
- Reconciled C0-kestrel's messages, table completion, delivery and checkpoint checks, closing receipts, command ledger, final campaign files, log inventory, and collector traceback. Its 18 ledger rows are nine start/completion pairs: two prompt-builds (one help call), one validation, three checkpoint calls (one help call), and three session-log calls (one help call).
- Compared C0's initial and final canonical gameplay state: campaign metadata, all three character sheets, and the session tracker are unchanged. Only the rebuilt prompt and expected checkpoint, public-log, and private evidence files were added or updated.

## Required repair and run policy

1. Use one shared matcher only where the protocol expects an administrative word. After trimming outer whitespace, accept the expected word case-insensitively with zero or one terminal ASCII full stop; equivalently, for each expected token use `(?i)^\s*TOKEN\.?\s*$`. Thus `Noted.`, `Received.`, and `Ready.` pass, while `Ready!`, `Ready...`, `Ready;`, `Ready, continuing`, and the existing expanded M0/ABR sentences fail.
2. Keep the original response and matching decision in its receipt. A clarification or recollection must create a new versioned receipt referring to the prior one; it must not rewrite the original output.
3. Permit the no-JSONL collector branch only when all of these are true: the table disposition is `complete`; no session JSONL exists; and the accepted completed command ledger contains no `play` or `roll` command. Otherwise retain a hard failure.
4. Emit a non-metric record such as `status: not_applicable_no_structured_mechanics`, `event_count: 0`, `mechanical_command_count: 0`, and a reason naming the completed mechanics-free case. Preserve the original collector stderr/progress as `prior_collection_error` or in a versioned repair receipt; do not relabel the game run as having stopped.
5. For AME-M1, create the replacement from the original frozen initial snapshot and fresh role histories. Register the original as excluded a priori because of harness failure, link the replacement to it, and do not pool or choose outcomes after seeing both.
6. If a continuation of AME-M1 is retained for diagnostic purposes, label it a transport-recovery sensitivity only. It would require a hashed recovery manifest, delivery of the already saved G002 context to Orr only, and explicit repair of cursors/pending state without editing the frozen original. It should not be the primary accepted run.

## Residual uncertainty

These checks establish the immediate causes and defensible recovery boundaries; they do not establish that the proposed code will implement those boundaries correctly. Acceptance still requires targeted tests for every accepted and rejected token form, a missing-JSONL case with a completed mechanical command that must fail, a completed zero-mechanics fixture that must pass as not applicable, and preservation of prior failure artefacts. A fresh AME-M1 rerun may produce different role decisions because the original histories already saw the opening; that is expected stochastic/model variation and is why the replacement needs fresh histories and predeclared inclusion.

---

## Addendum: V2 implementation and lineage audit

### Operational claim

Revision 2 is claimed to implement only the approved administrative-token and zero-mechanics collection repairs, preserve the V1 sources and raw failures, predeclare unbiased replacements for AME-M1 and AME-M2, and safely launch the remaining 23 jobs. This requires the new matcher and collector to reject adverse counterexamples, every replacement to preserve its assigned experimental input, the replacement policy to describe prior exposure truthfully, and the manifest hashes to bind what will actually run.

### Audit verdict

**Not supported for launch as the current 23-job queue.** The exact-token repair, the two completed C0 recollections, the current AME path repair, and the preservation of V1 artefacts are supported. The combined AME replacement policy is not: AME-M2 had already exposed a seeded test result and a consequential player choice, contrary to both the policy and its lineage record. The generic zero-mechanics guard also accepts several unsafe missing-ledger cases. These defects do not overturn the repaired C0 results, but they must be resolved before V2 role calls begin.

Component verdicts:

- **Administrative matcher: supported.** `administrative_token` is restricted to Ready, Noted and Received call sites and accepts only the expected word, outer whitespace and zero or one ASCII full stop, case-insensitively.
- **C0-kestrel and C0-lantern recollection: supported.** Both are explicit `not_applicable_no_structured_mechanics` collections with zero events and zero mechanical commands. Their V2 final and native-trace trees are byte-identical to the original archived trees; original progress, collector traceback, closeout and `literal_receipt: false` decisions remain intact.
- **Corrected M1-R2 path relocation: conditionally supported.** After a caught prelaunch double-suffix error, the bad inputs and old manifest were archived with repair receipts. Current scenario, setup and all 77 recipe path occurrences target the existing `ame_m1_r2` campaign; character, tracker and player-packet bytes match the original. No replacement role has been called.
- **M2-R2 as an unbiased sole replacement: not supported.** Its path repair is now mechanically correct, but its scientific disposition is not.
- **Generic zero-summary guard: materially weakened.** It blocks a completed successful `play` or `roll` row, but does not establish that the ledger itself is complete.

### Strongest supporting evidence

1. V1 remains unchanged: `run_case.py` is `1090a3c00d26aa4fdf6529d387079c0ac04d323122a3b6afebe75817f740b1f2`, `record_cli.py` is `643baadcf3bd2a145dc62da1a2f3fc5bd3549014bcf2f446c836ca5cf5b3c2ad`, and the original manifest remains `0d67f2faf37fa544c49ef503da39bd37abbbc067c59849bca9b3c468aa063db1`.
2. Independent matcher tests accepted `Ready`, `Ready.`, case variants and outer whitespace, and rejected double periods, other punctuation, appended prose, embedded questions, an empty response and the wrong administrative word.
3. Both C0 V2 summaries pass the stated complete/no-JSONL/no-successful-play-or-roll condition. Each root `progress.json` equals `collection_v2/prior_progress.json`; all checkpoint, public-body and delivery checks pass; all six archived `Received.` responses remain originally nonliteral and are separately accepted by V2. C1-kestrel, which has a real session JSONL, followed the ordinary summary path and its V2 summary is byte-identical to its original structured summary.
4. The prelaunch path error was repaired before any M1-R2/M2-R2 role call. The previous bad files and manifest are preserved under `prelaunch_path_repair_001/` and `execution_v2_manifest_prelaunch_path_error.json`. In the current inputs, the original scenario, setup and command recipes equal the replacements after exactly one declared campaign/run-path translation. The refreshed manifest observed during this audit is `1e0b576b0216244a528ce6aa6ebfdd829569a1a0dd2f3d05dad0462c636c5d80`.

### Strongest threats, ranked by scientific consequence

1. **Major and launch-blocking: AME-M2's exclusion rationale is false.** `replacement_policy.json` says M1 and M2 stopped “before either first test; no outcome selection”, and M2-R2's lineage reports `original_first_draw_count: 0`. In fact, original M2 completed draw index 1 at seed 141012001: Nell's deferred DEX test rolled 15 and 12, kept 15 against DEX 14, charged the one-Fortune toll, and disclosed the −1 margin in G002. Nell then chose to spend another Fortune to release the catch. Orr's `Noted.` stopped the relay only after that result and choice. The replacement policy was written after this exposure. A fresh M2 run may still be useful, but it is outcome-exposed and cannot be the sole nominally a-priori replacement.
2. **Major for any future N/A summary: absence of evidence can be mistaken for evidence of absence.** Independent counterexamples showed that `no_mechanics_summary` returns N/A when `commands.jsonl` is missing, when it contains only an accepted start row for `play`, and when it contains a successful `advance`. A started command has unknown completion, and advancement is a mechanical state change. The collector also does not use initial-versus-final state equality as a gate. The existing C0 results survive because their complete ledgers, unchanged canonical state and native traces were independently checked; the generic branch does not yet guarantee those facts.
3. **Moderate provenance weakness: manifest input hashes are recorded but not enforced by the driver.** All 23 `execution_freeze.json` hashes matched the refreshed manifest during this audit, but `run_revised_queue.py` verifies only code hashes. It does not compare each live freeze to `input_freeze_sha256`, nor verify the recorded replacement-policy hash, before starting roles. Current consistency is therefore a point-in-time external check rather than a runtime invariant.
4. **Minor/remaining evidence gap:** the four same-thread readiness clarifications are eligible but unexecuted, so their success is not yet evidence. The old-controller shutdown is supported by a scheduler entry saying `observed_children: []` and by no current controller process, but no historical child-PID/wait-status receipt independently proves the ordering.

### Independent checks performed

- Diffed V1 and V2 source and traced every changed call site.
- Re-ran token acceptance/rejection tests and zero-summary success/failure cases in temporary directories without role or campaign writes.
- Tested adverse missing-ledger, start-only `play`, successful `play`, successful `roll`, successful `advance`, incomplete-table and existing-JSONL branches.
- Reconciled C0 Kestrel/Lantern root artefacts with `collection_v2`, including final trees, native traces, prior progress, checkpoint/delivery checks, command ledgers and original tracebacks.
- Verified C1-kestrel takes the structured path and reproduces its original summary byte-for-byte.
- Compared M1/M2 originals and replacements at the byte and normalized-content levels; verified current recipe target counts, target existence, masters, trackers, character sheets, player packets, archived bad inputs, repair receipts and absence of replacement `agent_calls`.
- Re-read original M2 messages, commands, draw seed, public G002 and Nell/Orr P002 outputs rather than relying on the replacement policy.
- Checked the current process table and found no V1 or V2 case/queue controller.

### Required corrections before reliance

1. Remove M2-R2 from the primary replacement claim and correct the policy/lineage to record its one draw, disclosed dice and margin, Luck toll, Nell's nudge decision, and the post-outcome timing of exclusion. Do not describe this as a zero-draw a-priori replacement.
2. Prefer a versioned transport recovery of original M2: preserve the frozen original, clone its exact pending campaign state, deliver Nell's already saved P002 choice to the existing Custodian history without another roll or player decision, and settle the predetermined action under a hashed recovery manifest. If a fresh M2 replicate is also run, predeclare it as an outcome-exposed sensitivity and retain both outcomes without selection.
3. Require an existing, parseable command ledger for an N/A summary; reject any accepted `play` or `roll` attempt without a corresponding successful structured log, and reject successful mechanical `advance` calls. Add the three counterexamples above to the frozen tests. A canonical initial-versus-final state check should also gate a declared mechanics-free control.
4. Before any role call, make the queue driver compare each `execution_freeze.json` to its manifest `input_freeze_sha256` and verify the replacement-policy hash. Re-freeze the policy, queue and manifest after correcting M2.
5. Retain the now-correct single path translation and its repair archive. Do not overwrite either the original failed V2 manifest or the prelaunch bad replacement inputs.

### Residual uncertainty

The receipt matcher is exercised independently, but same-thread clarification has not yet been observed end-to-end. The C0 recollections are reliable for these two controls; the generic N/A branch remains unsafe for a future case until the missing-ledger and unknown-command paths are closed. M1-R2 remains a defensible fresh replacement because no test or draw preceded its harness stop. M2's correct inferential status depends on a predeclared recovery/sensitivity decision that has not yet been made. Historical controller-exit ordering cannot be established beyond the preserved scheduler assertion and present process state.

---

## Final prelaunch acceptance after corrective hardening

### Operational claim and verdict

The claim now audited is narrow: the frozen Revision 2 controller may start the declared 23-job queue without replaying or selecting exposed AME outcomes, accepting an unsafe no-mechanics summary, or silently running altered inputs. That claim requires the corrected M2 disposition and exact transport state, fail-closed no-mechanics collection, full pre-open campaign identity, and runtime enforcement of the policy, source, case, mode and per-case freeze hashes.

**Verdict: conditionally supported for launch. No identified prelaunch blocker remains in the current frozen artefacts.** The condition applies to evidential acceptance after execution: the controller must exit successfully, record all 23 results without `run_error`, `collect_error` or `driver_error`, and pass the planned per-case closeout audit. Revision 2 has not yet made a role or game call, so this verdict does not prejudge the scientific outcomes or successful completion of the queue.

### Strongest supporting evidence

1. The final manifest hash is `0f1cc6b664f31d1c914f8177407e24bde9cfb15b677da333842b7b88c4324047`. All 23 case IDs and directories are unique; every case ID equals its `case.json`; every mode is one of the three implemented modes; all 23 current `execution_freeze.json` hashes match; and the recorded controller, recorder, replacement-policy and original-manifest hashes match the live files.
2. The no-mechanics guard now requires a present, parseable, nonempty and exactly paired accepted command ledger, a complete disposition, no session JSONL, no accepted `play`, `roll`, `advance` or `update_sheet` row at either phase, and byte-identical campaign metadata, character sheets and tracker files. Both actual C0 controls pass this gate with complete ledgers and unchanged canonical state.
3. M2 is no longer represented by a fresh, outcome-unexposed replacement. The queue contains the original `AME-M2` once in `transport_recovery` mode and excludes M2-R2. Its recovery manifest hash is `468295770d3617a36f11216d4433d412a2698d3e6645c5f2f55fefff395650c2`; every protected source and state hash matches. It records the one draw at seed `141012001`, rolls 15 and 12, margin -1, the paid toll and Nell's already observed Fortune decision.
4. The restored M2 state advances to G003 with the exact saved Nell P002 decision as pending content, without a redraw or new decision. Its raw cursors remain at row index 4. A direct input simulation showed Nell receives only a future G003 and Orr receives saved Nell P002 followed by G003; only Orr's punctuation-only `Noted.` receipt is suppressed.
5. All four pre-open campaigns currently match their complete frozen campaign file/hash maps, have no player roles or table messages, and remain unready. The controller now repeats that complete-map comparison before the same-history clarification. It also validates the whole queue before creating worker futures and exits nonzero if any recorded case error remains.

### Strongest remaining threats, ranked by scientific consequence

1. **Major if results are accepted without closeout:** all substantive V2 role behaviour remains unobserved. A clarification may fail, a role may violate the relay contract, or a collection may fail. These are execution risks rather than reasons to alter the frozen prelaunch package; each now fails visibly and makes the controller exit nonzero.
2. **Moderate operational risk:** M2 recovery is intentionally one-shot. An interruption after its archived state transition cannot be silently retried because the altered table state or existing G003 artefacts stop another recovery attempt. Such a case needs manual evidence review and cannot be counted as completed.
3. **Minor residual risk:** the checks establish current file identity and deterministic routing, not that concurrent CLI histories, native-trace discovery, or every later model response will behave correctly under the live three-worker run.

### Independent checks performed and outcomes

- Direct matcher tests accepted the exact Ready/Noted/Received tokens with optional single periods and rejected appended prose, other punctuation and wrong tokens.
- Fifteen adverse no-mechanics fixtures were rejected: missing, malformed or empty ledgers; incomplete disposition; canonical-state drift; unmatched administrative rows; and started or completed `play`, `roll`, `advance` and `update_sheet` commands. A valid paired administrative ledger passed, both real C0 controls passed, and a case with a session JSONL stayed on the structured-summary path.
- Recomputed the final manifest, source, policy, original-manifest, recovery and all 23 input-freeze hashes; checked all case/mode identities and the M1/M2 dispositions. Every check matched.
- Reconciled M2's messages, native saved outputs, command ledger, protected state, original and restored table states, exposed draw, decision, raw cursor positions and hypothetical next-delivery IDs. All matched the declared transport recovery.
- Compared every live file in AME-M0, AME-M3, ABR-A and ABR-C1 with its complete frozen initial campaign map. All four maps matched exactly. Process and artefact checks found no V2 result file, M1-R2 role calls, M2-R2 role calls or M2 G003 call.
- Read the final driver branches confirming pre-worker queue validation, full pre-open identity checking and nonzero exit after any recorded run, collection or driver error. The live queue itself was not executed during this audit.

### Required checks before relying on the results

No further source or manifest correction is required before start. After execution, require all of the following before treating V2 as evidence: a zero controller exit; exactly 23 uniquely identified result rows; no recorded error field; successful same-thread clarification receipts where applicable; complete M2 recovery and settlement records without an extra draw or player decision; and successful per-case checkpoint, delivery, command-ledger, native-trace and collection checks. Any failed or interrupted case remains incomplete pending a separate disposition; it must not be silently retried or replaced after observing its output.

### Residual uncertainty

Even after those checks, model-mediated play remains stochastic and the bounded probes support only their declared scenarios, endpoints and role configuration. The prelaunch audit can establish provenance, routing and fail-closed behavior; it cannot establish the eventual treatment effects, generality of those effects, or absence of every unobserved runtime failure. Those uncertainties must be assessed from the frozen completed runs rather than inferred from this launch acceptance.
