# Students — LOOPSTRUCTURAL

**Project:** LOOPSTRUCTURAL  
**Category:** MINING  
**Upstream:** see BENCH.json  
**Pinned commit:** `6546d8811ef4d4e3c11b956eed85cd24ee5b3f90`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `e06ce342c9f0c7b0f606655d17a387cbae9b3e5a6a8732c67181fb8b119a298b`  
**Date:** October 2026

## What this project gives you

A complete worked example of offline-first packaging with a cryptographic audit
chain: source pinned at `6546d8811ef4d4e3c11b956eed85cd24ee5b3f90`, a 16-check assurance suite, an evidence register
with per-check hashes, and an AIOSS ledger chain ending at `e06ce342c9f0c7b0f606655d17a387cbae9b3e5a6a8732c67181fb8b119a298b`.

## Learn by verifying

```
python tools/run_bench.py --out BENCH.json
```

Then take any row from `ISOLATED_LAB_RESULTS/03_Result_Register.md`, recompute
the SHA3-256 of its evidence file, and confirm it matches. If it does not match,
the record has been altered — that is the whole point of the chain.

## Licence

Apache 2.0 terms apply to study and teaching use.
