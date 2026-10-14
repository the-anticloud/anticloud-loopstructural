# Technical Architecture — LOOPSTRUCTURAL

**Upstream:** [https://github.com/Loop3D/LoopStructural](https://github.com/Loop3D/LoopStructural)
**License:** MIT
**Category:** MINING
**Anticloud Integration:** PAX L5 Narrow L2 General 27B + AIOSS + Offline-First

## Upstream Description

3D geological modeling for mining

## Anticloud Architectural Changes

1. PAX L5 Narrow L2 General 27B local ore grade prediction and equipment anomaly detection
2. AIOSS tamper-evident safety and production log (MSHA aligned)
3. AES-256 encryption for all geological survey and production data
4. Single-binary mine management system for underground/remote deployments
5. Zero-cloud: works in tunnels and remote sites without connectivity
6. GPU/CPU equalizer: seismic and image analysis scales to available hardware
7. Offline satellite imagery analysis for surface mine monitoring
8. Open WITS/WITSML integration replacing proprietary drilling software

## Integration Points

- **PAX Inference Socket:** Local HTTP endpoint at `127.0.0.1:11434/v1/chat` — same OpenAI-compatible API, zero cloud
- **AIOSS Hook:** Every write operation calls `aioss_append(event, payload)` before commit
- **Encryption Layer:** All file I/O routed through `anticloud_crypto.encrypt_at_rest()`
- **Single Binary Build:** `pyinstaller anticloud_loopstructural.spec` or `go build -o loopstructural`

## Deployment Modes

| Mode | Hardware | Notes |
| --- | --- | --- |
| Edge CPU | Raspberry Pi 4 / Intel NUC | Full feature set, PAX on CPU |
| Desktop GPU | RTX 3060 / A10 | PAX GPU inference, <1s latency |
| Server | 2× A100 | Full batch throughput |
| Air-gapped | Any x86/ARM | Zero network dependency |