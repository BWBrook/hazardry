# P12 attempt A — stopped; harness test only

The orchestrator mistakenly delivered the entire Free Traders skin, including its generic Custodian-facing section, to all three Time Odyssey players. A copied packet builder retained the wrong path and a changed, nonexistent split marker. Hashes correctly recorded wrong content. An independent delivery audit found the error after G010 had been relayed. G011 completed during the stop race and reached all three players. Their P011 output files remain, but those replies were not recorded or forwarded to the GM; no G012 was started. The P12 hidden scenario was not found in packets.

All original files remain in playtests/runs/P12 and playtests/campaigns/p12_time, with an as_stopped snapshot, native traces, exact incoming messages and historical checkpoints. G001–G009 byte equality and all25 corresponding player inputs were independently checked. No game rule, die or played state was repaired.

This attempt is excluded from clean play conclusions. Restart uses corrected public packets, completely fresh role histories, and the same predetermined roster, scenario and seed schedule. Attempt A costs remain separate.

## Retained cost and access evidence

Native token counters are cumulative per role, not sums of cumulative turn totals. Billed money and root-orchestrator costs unavailable. Wall totals cover receipted calls only; interrupted P011 receipts are absent.

| Role | Input (cached subset) | Output | Reasoning subset | Receipted seconds | Tool calls |
|---|---:|---:|---:|---:|---:|
| gm | 11564381 (11378816) | 58793 | 30560 | 1725.1 | 88 |
| ada_mercer | 501706 (436992) | 1549 | 819 | 126.0 | 0 |
| gideon_vale | 793253 (720000) | 2491 | 1717 | 176.6 | 0 |
| miriam_ash | 794885 (731776) | 2488 | 1696 | 165.9 | 0 |

The failed packet-content check is not repaired by zero player tool use or exact relay copies. Attempt A remains excluded.
