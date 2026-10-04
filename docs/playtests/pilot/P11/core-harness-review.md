# P11 core harness review

**Verdict:** `a2ce6f166ad94aab9ed7f5efa1eafd44db019f8a` correctly enables core campaign creation, character creation, prompts and ordinary checks, and preserves the existing published release inputs. One material integration gap remains: a tableless core crisis cannot be recorded through the engine without inventing a d6 table-result value. The 174-test suite passes but does not cover that path. This does not invalidate a run that never reaches Pressure 5; it prevents an unqualified claim that the core harness is complete.

Reviewed on 2026-10-04 at HEAD `a2ce6f1`. Reviewer: delegated harness-contract reviewer, retaining the parent-selected model/effort. This subagent did not independently inspect native metadata identifying its own model, so it makes no exact model claim. Read the supplied global guidance and repository `AGENTS.md`. Audit only: no source changes, no frozen-run changes, no campaign changes outside a temporary scratch directory. This file is the only repository artifact owned by this review.

## Finding

### P2 — Core crisis requires a nonexistent table result

The new `skins/core.md:47` explicitly states that the core prints no crisis table and directs the Custodian to choose a dramatic consequence. However, `tools/play.py:229` rejects `pressure --crisis` unless `--table-result` is supplied, and `tools/_pressure.py:178` requires a nonempty list of d6 faces. After Pressure reaches 5, a valid chosen core consequence therefore returns:

```text
error: supply --table-result and the adjudicated --source before resetting
```

The rejection leaves all campaign bytes unchanged and Pressure correctly pending at 5. The next ordinary action is blocked with `record the pending crisis before the next action`. Supplying a made-up `--table-result 1` unblocks the scratch campaign, but persists `table_result: [1]` despite there being no table. That is a data-contract mismatch, not a supported tableless representation.

The mandatory-table assumption predates this commit; adding a supported `core` entry newly exposes it. The new play sheet does not resolve the mismatch, and the all-skins scaffold test never reaches a crisis. A future remedy should provide an explicit honest representation of an adjudicated tableless crisis while retaining the target/consequence-before-reset contract. No remedy was implemented or prescribed as an authorized change. P11's actual Pressure history is reviewed separately by the parent.

Minimal reproduction, entirely in a temporary directory (the random seed here is only for scratch character creation):

```sh
.venv/bin/python tools/campaign_init.py --skin core --slug crisis-review \
  --base-dir "$SCRATCH_DIR" --random-character Ada --seed 111 --json
.venv/bin/python tools/play.py --campaign "$SCRATCH_DIR/crisis-review" \
  --character ada --event-id gain5 pressure --gain 5 --source 'Hazard escalates'
.venv/bin/python tools/play.py --campaign "$SCRATCH_DIR/crisis-review" \
  --character ada --event-id crisis pressure --crisis --target ada \
  --source 'Chosen core crisis: the supporting wall gives way'
```

`SCRATCH_DIR` denotes an existing disposable temporary directory, not any pilot campaign. The final command reproduces the error above.

## Changed-file and caller review

| File | Result |
|---|---|
| `manifest.yaml` | The core attribute names, LCK pool binding, party Pressure and step-2/3/4 descriptions match Manual 2.1.1 and Almanac 4. Step 4's +1 Luck ability surcharge is represented by the existing `luck_cost`/`ability` contract; unspecified minor penalties remain Custodian decisions. No core-specific free tags, resources or clocks are silently granted. |
| `skins/core.md` | Default names, natural-roll reminder, optional-module descriptions and Pressure summary reproduce the cited core rules. Its no-table statement exposes the crisis finding above. No new mechanical rule was found in the play sheet. |
| `tools/_release_content.py` | `play_only` filters the dynamically collected skin paths for `core_skins`. The full book and other bundles already select their inputs explicitly. For this actual manifest change, every field of all six bundle definitions matches the parent manifest's definitions, and no bundle includes `skins/core.md`. This is input/assembly verification, not a new PDF render. |
| `tools/validate_examples.py` | Skips the play-only entry when parsing published sample characters and when reporting the published skin count. The 20 parsed samples and validation result are identical to the parent manifest's result. |
| `tests/test_book_examples.py` | Changes the membership expectation to the ten published entries; retains exact sample count and existing sample-mechanics assertions. |
| `tests/test_campaign_contract.py` | Still scaffolds and validates every manifest entry, now including core. It separately asserts ten published entries and exactly one play-only entry named core. Core is not excluded from campaign-contract coverage. |
| `examples/campaign_demo/prompt.md` | Only the manifest source hash and aggregate fingerprint change. Prompt body stays unchanged, and `build_prompt.check_prompt` accepts the saved prompt against current sources. |

Inspected callers include campaign scaffolding, manual and random character construction, sheet/campaign validation, runtime skin loading, resume/prompt assembly, advancement/recalculation lookups, repository validation and release assembly. They select entries by manifest slug or attribute definitions rather than assuming one of the old ten names. `build_prompt --list-skins` intentionally includes the playable core. `validate_repo` still checks the core file's manifest/disk presence; only published samples exclude it. Existing generic Luck-target tests also iterate over the new entry.

## Verification

- `.venv/bin/python -m unittest discover -s tests` — **174 tests passed**, 21.323 seconds.
- `.venv/bin/python tools/validate_repo.py` — **ok**.
- `.venv/bin/python tools/validate_examples.py` — **20 published sample characters across 10 skins**.
- Sixteen CLI calls in a disposable scratch campaign exercised core scaffold creation with two generated characters, an additional manually built character, campaign validation, all four agent/chat × compact/full prompt variants with fresh fingerprints, Pressure 4, a deferred ability check and settlement, an ordinary check, Pressure 5, rejected tableless crisis, blocked next action, the explicitly artificial placeholder demonstration, and final campaign validation.
- At Pressure 4 the ability paid exactly one Luck token; settlement did not charge it again, and an ordinary check paid no ability surcharge.
- In-memory assertions compared all six current release bundle definitions to those constructed with the parent manifest, verified exclusion of `skins/core.md`, compared all published-sample results, and validated the tracked demo prompt fingerprint. All passed.

Detailed scratch commands and captured outputs: `/var/folders/2y/0v0ttwy532n0k7m47vvggdm80000gn/T/p11-core-review-7l0hol5g/commands.json`. This temporary evidence is not a permanent campaign record. The tableless-crisis reproduction and observed errors above are retained here for review.

## Scope and readiness

No additional regression was found in the seven-file change. Ordinary core play, prompt generation and current release/sample exclusions are supported by the checks above. Core crisis handling is **not ready as an unqualified tableless workflow**. This review did not rerun P11, inspect its player information boundaries, validate its optional-module adjudications, render release PDFs, or test every hypothetical future use of `play_only`. The separate parent/native-trace audits own P11's evidentiary conclusions. Existing sampled `--dry-run` behavior and NPC argument-help facts were reported separately to the parent; they are not changes introduced by this commit.
