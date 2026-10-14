# Educators — LOOPSTRUCTURAL

**Project:** LOOPSTRUCTURAL  
**Category:** MINING  
**Upstream:** see BENCH.json  
**Pinned commit:** `6546d8811ef4d4e3c11b956eed85cd24ee5b3f90`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `e06ce342c9f0c7b0f606655d17a387cbae9b3e5a6a8732c67181fb8b119a298b`  
**Date:** October 2026

## Teaching with LOOPSTRUCTURAL

The project is usable as a worked example of offline-first packaging with a
cryptographic audit chain. It ships with the assurance suite, the evidence
register and the ledger, so students can verify claims rather than take them on
faith.

## Suggested exercises

1. Run `python tools/run_bench.py --out BENCH.json` and read the 16 results.
2. Recompute the SHA3-256 of a row's evidence file and compare to the register.
3. Walk the AIOSS chain from genesis to head `e06ce342c9f0c7b0f606655d17a387cbae9b3e5a6a8732c67181fb8b119a298b` and confirm every link.
4. Break one artifact and observe the chain fail to verify.

## Licence for teaching

Apache 2.0 terms apply to academic and teaching use. See `24_ANTICOMMONS_LICENSE`.
