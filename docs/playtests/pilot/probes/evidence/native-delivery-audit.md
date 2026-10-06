# Independent audit: native delivery, access and provenance

## Claim audited

The operational claim is that the accepted 28-case Astra primary set can be traced from frozen inputs and native role histories through every relay, command ledger, checkpoint, public log and final campaign snapshot without missing or duplicated declarations, undeclared history reuse, model drift, seed discontinuity, result-dependent reroll, or silent repair.

The accepted set is AFT C0-C9 under both opaque labels, ABR A/B/C1/C2, and AME M0/M1/M2/M3, with fresh `AME-M1-R2` replacing the excluded original M1, original M2 retained through its declared same-history transport recovery, and unlaunched M2-R2 excluded. For the claim to hold, the applicable execution freezes must match their manifests; role histories must be unique and correctly configured; saved bodies and deliveries must equal the native bytes; mechanics draws must follow the frozen seed schedule; and repairs must not introduce a new game choice or draw.

This audit addresses execution and evidence integrity. It does not establish that every mechanical ruling was correct, that the probes estimate ordinary-play frequencies, or that the same language model would reproduce the same prose or choices on another run.

## Verdict

**Conditionally supported.** The observed 28-case primary set passes the native-delivery, role-lineage, active-input, draw-ledger and final-state checks. I found no missing or duplicate delivered declaration, cross-case thread reuse, model or effort mismatch, player tool call, unaccounted gameplay draw, unsettled action or crisis, or mismatch between a collected final snapshot and its live campaign. The revised controller exited 0, and the corrected root verifier reports all 28 bounded endpoints accepted.

Scientific reliance remains conditional on durable preservation. The central Free Traders treatment protocol and the complete execution tree are currently outside Git: the protocol is untracked, `playtests/` is ignored, and the public evidence export is also untracked. Current hashes establish internal equality but do not make the experiment reconstructible from commit `b12135ec1fa3d89e266ca15c7768b423b72a1b27`.

## Strongest supporting evidence

### Exact transport and native histories

- Parsed all **81 Custodian public bodies** in **187 chronological message rows**. Each body equals the native role output's public block, its `messages.jsonl` row, `received/Gnnn.md`, versioned checkpoint, final public-memory file where used, and exactly one public-session-log entry.
- Reconstructed all **126 ordinary deliveries** from their ordered `message_ids`. Every header and body is complete, chronological and unique, its SHA-256 matches the delivery ledger, and its bytes equal the corresponding native player input.
- Verified **16 closing-peer archives**. Each contains every other player's labelled final declaration once, excludes the recipient's own declaration, equals the native input, and received an accepted administrative token.
- Reconstructed each post-opening Custodian batch from the intervening non-administrative player declarations. Scripted declarations, rather than their eight `Noted.` acknowledgements, were forwarded once.
- All **65 primary role thread IDs** are unique: 28 Custodians and 37 players. Every one of the **276 role-call receipts** points to the declared thread, has matching input/output hashes and return code 0, and records `gpt-6-sol` with `medium` effort. Collection copies of the native traces are byte-identical to their unique live session sources.
- The 37 player histories contain zero tool calls. The 28 Custodian histories contain **683 tool calls**; the recorded accesses remain within the assigned repository, canonical rules/tools, own case inputs and own campaign. No saved Custodian call reads another case, another campaign, player history, controller ledger, external memory, correspondence or another chat.

### Frozen inputs, repairs and final state

- Every active `execution_freeze.json` hash equals the applicable original or V2 manifest entry, and every referenced input retains its recorded hash. The V2 manifest is SHA-256 `0f1cc6b664f31d1c914f8177407e24bde9cfb15b677da333842b7b88c4324047`; the frozen driver and policy hashes also remain exact.
- The 17 unopened AFT cases that were refrozen preserve their V1 freezes. Their initial campaign maps and all gameplay inputs are identical; the only input-byte change is the setup sentence requiring the standalone `Ready` token, plus `controller_revision: 2` in the active freeze.
- All AFT initial trees are exact. ABR's suite-level snapshots preserve all **46** initial files for A/B/C1/C2 with no missing, extra or changed path. M1-R2 preserves its full 12-file initial tree. M0, M2 and M3 omit only the empty transient `.runtime.lock` from `initial/`; its matching final copy completes the recoverable frozen state.
- All **28 collected final directory maps** are byte-identical to the live campaign directories. Every table is complete, every mechanical `pending_action` and `crisis_pending` flag is clear, and all sessions are deliberately left open at their bounded endpoint.
- The corrected final verifier, SHA-256 `d5dff78a4d1200d20be3b5e7d3130a70ffa9180e732deadd9d50fdbb0aa2dd56`, reports all checks true and controller session 13489 exit 0. Its two failed predecessor checks remain preserved: they had incorrectly treated the retained C0 collector error as current failure, looked for archived V1 hashes only at active V2 paths, and read a nonexistent session-status field. The corrections changed verifier logic only, not execution records or game state.

### Replacement and recovery lineage

- **Original M1 remains excluded.** A punctuation-only administrative receipt stopped it after opening exposure and player declarations but before any die draw. M1-R2 used fresh roles and the frozen initial state under the declared replacement policy. Its path defect was repaired before its first role call; the active files contain no `_r2_r2` path. Current lineage correctly says that scenario content is identical after the declared campaign path/slug relocation, and the earlier overstatement is preserved in `lineage_before_path_wording_correction.json`.
- **M2 is a same-history recovery, not a rerun.** `transport_recovery.json` has SHA-256 `468295770d3617a36f11216d4433d412a2698d3e6645c5f2f55fefff395650c2`. All 70 protected hashes resolve: 20 archived campaign files, five archived root ledgers and 45 unchanged call artefacts. Original commands/messages/deliveries are exact prefixes of the recovered ledgers (`20->34`, `6->9`, `4->8` rows). The same three role threads were retained; the saved Nell choice appears exactly once in G003 input; and the only draw remains index 1, seed 141012001, rolls 15/12. No new player choice or gameplay draw was requested.
- **M3's clarification is pre-play and same-thread.** The original expanded readiness reply remains preserved; one same-thread clarification returned exactly `Ready` before gameplay and invoked no tool.
- Across all 65 primary setup responses, 21 were `Ready`, 40 were `Ready.`, and four expanded Custodian replies were rejected and preserved. Those four same-thread clarifications returned exactly `Ready`. Closing acknowledgements comprise three `Received` and 13 `Received.`; the optional final period is the declared accepted grammar.

### Draw and command continuity

There are **25 indexed gameplay draws**, all contiguous within case, unreplayed, and equal to `master * 1000 + draw_index`:

| Cases | Recorded seeds |
|---|---|
| AFT C0, both labels | none |
| AFT C1-C8, both labels | one per case/label: `81411001` through `81418001` by case index |
| AFT C9, both labels | none |
| ABR A / B / C1 / C2 | `141021001` / `141022001` / `141023001` / none |
| AME M0 / M1-R2 / M2 / M3 | `141010001` / `141011001-002` / `141012001` / `141013001-002` |

All recorded mechanics commands have paired start/completion rows. C2-lantern has one expected diagnostic return code 1 when validation correctly detected a stale prompt after state change; the Custodian rebuilt the prompt and the next validation passed. Three Custodians invoked `tools/build_prompt.py --help` directly rather than through `record_cli.py`: C5-lantern and C9-kestrel succeeded under `uv`, while C7-kestrel's system-Python attempt failed for missing PyYAML. These were read-only help calls, made no draw or game-state change, and are recorder-discipline exceptions rather than gameplay bypasses. C7-lantern also has one malformed read-only JavaScript batch, immediately retried before play.

## Independent checks performed and outcomes

| Check | Outcome |
|---|---|
| Native output -> message -> received copy -> checkpoint -> public log | Passed for 81/81 Custodian bodies |
| Delivery hash, native input and ordered message coverage | Passed for 126/126 ordinary deliveries and 16/16 archives |
| Thread uniqueness, receipt hashes, model and effort | Passed for 65/65 primary histories and 276/276 role calls |
| Player tool isolation and Custodian path review | Zero player tool calls; 683 Custodian tool calls within the recorded case boundary |
| Active freezes, archived V1 lineage and retained initial bytes | Passed for all 28 cases; 17 readiness-only refreezes verified |
| Indexed draws and seed formula | Passed for all 25 draws; no replay or skipped index |
| M2 protected recovery and ledger prefixes | 70/70 protected hashes and all three prefixes passed |
| Collected final tree -> live campaign | Passed for 28/28 cases |
| Controller and corrected root-verifier endpoint checks | Exit 0; 28/28 accepted, no pending action or crisis |

## Usage accounting

Totals use the final cumulative provider record once per unique thread. They do not add cumulative readings from every call or count recollected trace copies as new activity. Cached input is part of input; reasoning output is part of output.

| Evidence set | Cases | Threads | Calls | Input | Cached input | Output | Reasoning output | Total tokens | Receipt-seconds |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| AFT accepted | 20 | 44 | 160 | 34,777,864 | 33,044,096 | 128,137 | 30,026 | 34,906,001 | 4,313.867 |
| ABR accepted | 4 | 9 | 46 | 9,033,256 | 8,608,000 | 41,143 | 12,451 | 9,074,399 | 1,237.850 |
| AME accepted | 4 | 12 | 70 | 18,963,379 | 18,348,032 | 67,701 | 14,024 | 19,031,080 | 1,900.324 |
| **Accepted primary set** | **28** | **65** | **276** | **62,774,499** | **60,000,128** | **236,981** | **56,501** | **63,011,480** | **7,452.040** |
| Excluded original M1 overhead | 1 excluded run | 3 | 8 | 2,281,193 | 2,128,512 | 8,799 | 1,900 | 2,289,992 | 221.725 |
| **All executed histories** | **28 accepted + 1 excluded** | **68** | **284** | **65,055,692** | **62,128,640** | **245,780** | **58,401** | **65,301,472** | **7,673.766** |

M2's pre- and post-recovery artefacts are one continuous history and are counted once. M2-R2 launched no role call and contributes zero usage. Summed receipt-seconds are role-call durations, not elapsed wall time; concurrent roles overlap.

## Strongest threats, ranked by consequence

1. **Major: the evidence is not durably reconstructible from the cited commit.** `docs/playtests/pilot/probes/free-traders-expertise.md` is a 30,790-byte untracked file with SHA-256 `a1ff6948a29f926ab1bbf12d1644e17e7885b575cfd3317f9f8b89eaa60cba15`; it is absent from commit `b12135e`. The complete `playtests/` execution tree is gitignored, and the current public export under `docs/playtests/pilot/probes/` is untracked. Case hashes prove current byte equality, but a hash cannot reconstruct missing bytes and local files remain mutable.
2. **Major: scope is bounded and descriptive.** The two C0 negative controls correctly contain zero mechanics events and use `not_applicable_no_structured_mechanics`. Each of the other 26 summaries records one incomplete, open session and zero completed sessions. The evidence supports the prescribed endpoints only; it cannot support full-session rates, midpoint or beat behaviour, ordinary-play frequencies, population claims, or general model reliability.
3. **Moderate: access isolation is observed, not enforced.** Role boundaries were instructions rather than an OS sandbox. Native stderr records 31 automatic Codex runtime plugin-catalog HTTP attempts across nine cases; every attempt returned HTTP 503 and retrieved no catalogue content. No agent tool initiated those requests, but the runs were not strictly offline. Saved traces cannot prove the absence of an access the runtime failed to log.
4. **Moderate/minor: status metadata can mislead downstream selection.** All 20 AFT `run.json` files still say `prepared_not_run`. The original C0 progress files retain their failed pre-repair summary error even though the guarded V2 summaries and closeouts are accepted. M2's older root closeout describes the pre-recovery stop. Consumers must use the authoritative case disposition and V2 collection where present.
5. **Minor: three help calls bypassed recorder discipline.** The direct `build_prompt.py --help` invocations described above were harmless and observable, but a future direct call need not be. The runner should distinguish and reject direct state-changing or dice-drawing tool execution while permitting or recording help reads.

## Audit correction

An earlier version of this report incorrectly claimed that ABR-A, ABR-B and ABR-C2 lacked retained initial bytes because it looked only for case-local `initial/` directories. ABR stores immutable starts at suite level under `playtests/runs/ABR/initial/{A,B,C1,C2}`. Independent hashing confirms all 46 files match the four execution-freeze maps, with no missing or extra file. The earlier warning is superseded; there is no ABR initial-byte gap.

## Required corrections before scientific reliance

1. Commit or content-addressably archive the exact treatment protocols, active and archived freezes, command/message/delivery ledgers, native traces, final campaign trees, repair records, audit reports and public exports. Generate an external SHA-256 manifest and verify it after copying.
2. Make the authoritative completion source explicit. Reconcile the 20 stale AFT `run.json` files, or ensure every downstream tool selects accepted `progress`/`table_state`/closeout state and preserves the two documented C0 errors as prior errors only.
3. Label every result as a bounded probe observation. Exclude these records from completed-session analyses unless a separate, valid session-close record exists.
4. Preserve original M1 as excluded harness evidence, use only M1-R2 as the M1 primary result, count M2 once as the declared same-history recovery, and keep M2-R2 at zero calls.
5. If strict offline or enforced information isolation is required, rerun under a sandbox that denies network and disallowed paths. For the present evidence, disclose the automatic HTTP attempts and instructional isolation.

Under the present bounded transport claim, no gameplay rerun is required for the transport or provenance defects detected here. Durable archival and metadata reconciliation are evidence-management corrections.

## Residual uncertainty

After those corrections, the saved execution chain would be strong evidence for these exact bounded cases. Residual uncertainty remains about mechanical interpretation outside this audit, run-to-run and future-model reproducibility, unlogged runtime access, and any inference beyond the prescribed endpoints. Absence of another detected mismatch is not proof that no mismatch exists.
