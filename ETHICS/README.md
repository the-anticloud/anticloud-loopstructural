# Ethics — LOOPSTRUCTURAL

**Project:** LOOPSTRUCTURAL  
**Category:** MINING  
**Upstream:** see BENCH.json  
**Pinned commit:** `6546d8811ef4d4e3c11b956eed85cd24ee5b3f90`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `e06ce342c9f0c7b0f606655d17a387cbae9b3e5a6a8732c67181fb8b119a298b`  
**Date:** October 2026

## Position

LOOPSTRUCTURAL is packaged for offline deployment with a verifiable audit trail. The
ethical questions this raises are answered by making the system's behaviour
checkable rather than by policy statements.

## The four commitments

1. **No hidden egress.** The deployment has no external API dependency; this is
   testable by running it with the network disconnected.
2. **Attributable output.** Every artifact is recorded in a hash chain, so what
   the system produced can be reconstructed.
3. **Operator control.** The institution owns the hardware and the keys.
4. **Refusal to overclaim.** Where a certification is not held, the project says
   so rather than implying it.

## Dual use

This project is packaged for civilian and public-sector deployment. Where an
upstream has dual-use characteristics, the licence gate and the reference-only
marking in `BENCH.json` record that.
