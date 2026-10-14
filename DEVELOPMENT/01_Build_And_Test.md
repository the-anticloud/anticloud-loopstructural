# Build and Test

**Project:** `LOOPSTRUCTURAL`
**Upstream:** https://github.com/Loop3D/LoopStructural
**License:** MIT

## Quick Start

```bash
git clone https://github.com/Loop3D/LoopStructural
cd LoopStructural
pip install -r requirements-anticloud.txt
python anticloud_main.py --offline --pax-local
```

## Anticloud Improvements Applied

1. PAX L5 Narrow L2 General 27B local ore grade prediction and equipment anomaly detection
2. AIOSS tamper-evident safety and production log (MSHA aligned)
3. AES-256 encryption for all geological survey and production data
4. Single-binary mine management system for underground/remote deployments
5. Zero-cloud: works in tunnels and remote sites without connectivity
6. GPU/CPU equalizer: seismic and image analysis scales to available hardware
7. Offline satellite imagery analysis for surface mine monitoring
8. Open WITS/WITSML integration replacing proprietary drilling software

## Benchmark Targets

| Metric | Target |
| --- | --- |
| Latency | Primary inference task: <5s on CPU, <1s on GPU |
| Throughput | Batch processing: >100 items/hour on single CPU server |
| Memory | <8GB RAM for standard deployment |
| Accuracy | Task-specific accuracy within 5% of cloud-API baseline |

## Build Status

Not yet measured. Run verified build and record actual figures above.
