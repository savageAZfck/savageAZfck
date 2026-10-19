# Adam Clark (`savageAZfck`)

**My data. My machine. My silicon. My language. My AGI.**

Building a complete, local-first sovereign computing stack from the silicon up: native Apple Neural Engine compilers, a programming language for living models, a 26-crate constitutional standard library, a formal AGI conformance battery, and a dual-brained personal AGI organism running air-gapped on consumer hardware.

---

## Architecture Map (41 Published Crates on crates.io)

```text
+-----------------------------------------------------------------------+
|  Layer 5: Bad_Apple                                                   |
|  Air-gapped dual-brained (GPU + ANE) sovereign AGI organism           |
+-----------------------------------------------------------------------+
|  Layer 4: touchstone (4 crates)                                       |
|  13-organ formal AGI conformance battery + Secure Enclave attestation |
+-----------------------------------------------------------------------+
|  Layer 3: The Sovereign Organ Standard Library (26 crates)            |
|  Audit, reflexes, bounded self-patching, quorum, erasure, federation  |
+-----------------------------------------------------------------------+
|  Layer 2: coyote                                                      |
|  Programming language (.cy -> ANE HWX binaries + organism VM + FFI)   |
+-----------------------------------------------------------------------+
|  Layer 1: mil_spec (10 crates) + haruspex                             |
|  Pure-Rust ANE compiler, HWX Mach-O emitter/decompiler, fuzzer, IR    |
+-----------------------------------------------------------------------+
```

---

### 1. Silicon & Binary Toolchain ([`mil_spec`](https://github.com/savageAZfck/mil_spec) & [`haruspex`](https://github.com/savageAZfck/haruspex))

Zero-Python, pure-Rust replacement for `coremltools` and Apple's private ANE codegen:
- **`mil_infer`**: Native `0xBEEFFACE` HWX Mach-O binary emitter, binary-to-MIL decompiler, differential fuzzer against `ANECompiler.framework`, IOSurface-pooled DAG runtime, and on-chip backpropagation (`emit_avw`, `emit_attn_v`, `emit_outer_t`, `emit_add4d`).
- **`mil_spec` / `mil_passes` / `mil_lint` / `mil_verify` / `mil_compile`**: Hand-rolled MIL protobuf writer/reader, optimizer passes, static ANE/GPU/CPU placement predictor (93% agreement with `MLComputePlan`), and conformance verifier.
- **`mil_convert` / `mil_onnx` / `milc`**: Safetensors, GGUF, and ONNX ingestion, LoRA bake-in, package surgery (`fuse-lora`, `requant`, `graft`, `reshape`), and cryptographic `mil.prov.*` provenance.
- **`mil_machines`**: Non-neural state machines compiled to run on the Neural Engine (Aho-Corasick DFAs, EWMA anomaly sentinels, stateful associative memory banks).
- **`haruspex-macho`**: Read-only pure-Rust Mach-O x-ray and binary security auditor.

---

### 2. The Language ([`coyote`](https://github.com/savageAZfck/coyote))

A two-stratum programming language sharing one static typechecker:
- **Silicon stratum (`fn`, `param`, `state`, `grad`, `adam`)**: Compiles tensor functions and `.safetensors` slices (`f16` / `q4`) directly into native ANE binaries (with `--cpu` reference parity), instances per-layer KV caches (`l0.kv`..`l27.kv`), and synthesizes on-chip forward/backward/update graphs for `grad` and `adam`.
- **Organism stratum (`host fn`, `reflex`, `enum`/`match`)**: Serializable bytecode VM where compiled ANE programs are first-class typed values (`ane(args) -> ret`).
- **Compile-time constitution**: `sealed` weights are physically unnameable in host code; `cap` permissions (`fs`, `patch`, `erase`, `cortex`, `net`) are checked transitively across the call graph; `det`/`stoch` separates deterministic replay from sampling; `reflex` tripwires are forced to be deterministic, permissionless, and non-steering.
- **Native Rust & Swift FFI**: `libcoyote.dylib` + `include/coyote.h` + `extern fn` bindings.

---

### 3. The Sovereign Organ Standard Library (26 Crates)

| Domain | Crates |
|---|---|
| **Audit, Memory & Recovery** | [`sovereign_ledger`](https://github.com/savageAZfck/sovereign_ledger) (HMAC/Ed25519 hash-chained ledger) · [`flight_tape`](https://github.com/savageAZfck/flight_tape) (incident black box) · [`respawn`](https://github.com/savageAZfck/respawn) (versioned state snapshots & rollback) · [`eidolon`](https://github.com/savageAZfck/eidolon) (counterfactual incident replay) · [`dreamcatcher`](https://github.com/savageAZfck/dreamcatcher) (ledger-to-training curation) |
| **Constitutional Governance** | [`axon`](https://github.com/savageAZfck/axon) (sub-deliberative reflex arc) · [`akicita`](https://github.com/savageAZfck/akicita) (bounded autonomy marshal) · [`xipe`](https://github.com/savageAZfck/xipe) (ratified self-modification) · [`tokala`](https://github.com/savageAZfck/tokala) (dissenting quorum) · [`bicameral`](https://github.com/savageAZfck/bicameral) (dual-hemisphere concurrence) · [`wintercount`](https://github.com/savageAZfck/wintercount) (temporal policy provenance) · [`macuahuitl`](https://github.com/savageAZfck/macuahuitl) (streaming Aho-Corasick firewall) · [`nagual`](https://github.com/savageAZfck/nagual) (adaptive immune system) |
| **Cryptographic Epistemology** | [`manitou`](https://github.com/savageAZfck/manitou) (weight provenance) · [`camazotz`](https://github.com/savageAZfck/camazotz) (certified erasure with decrypt-failure proof) · [`tabula`](https://github.com/savageAZfck/tabula) (proof of non-knowledge) · [`sibyl`](https://github.com/savageAZfck/sibyl) (oracle-gated sealed memory) · [`nagi`](https://github.com/savageAZfck/nagi) (Shamir dead-man escrow) · [`mictlan`](https://github.com/savageAZfck/mictlan) (posthumous standing orders) · [`germline`](https://github.com/savageAZfck/germline) (signed organism reproduction) |
| **Multi-Silicon & Federation** | [`smokesignal`](https://github.com/savageAZfck/smokesignal) (ANE-drafter + GPU-verifier speculative handshake) · [`orenda`](https://github.com/savageAZfck/orenda) (federated cognition pooling under owner keys) · [`wolakota`](https://github.com/savageAZfck/wolakota) (inter-organism consent treaties) · [`kola`](https://github.com/savageAZfck/kola) (cross-organism mutual witnessing) · [`potlatch`](https://github.com/savageAZfck/potlatch) (signed compute IOUs) · [`edge_gate`](https://github.com/savageAZfck/edge_gate) (local LLM gateway) |

---

### 4. Verification & Reference Organism ([`touchstone`](https://github.com/savageAZfck/touchstone) & [`Bad_Apple`](https://github.com/savageAZfck/Bad_Apple))

- **[`touchstone`](https://github.com/savageAZfck/touchstone)**: Independent 13-organ conformance harness for personal AGI organisms, grounded in 40 years of agent literature with Secure Enclave / Ed25519 signed attestations.
- **[`Bad_Apple`](https://github.com/savageAZfck/Bad_Apple)**: Air-gapped, dual-brained sovereign organism (GPU cortex + ANE brain/drafter) running on a 16 GB MacBook Air (`brew tap savageAZfck/bad-apple && brew install --cask bad-apple`).
