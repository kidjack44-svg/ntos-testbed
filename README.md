NTOS Testbed — Verified Systems Without Vendor Trust

NTOS (New Testament Operating System) is a hardware-rooted, behaviorally attested systems architecture designed to operate under minimal trust assumptions. This repository contains the public NTOS testbed: attestation primitives, field-governed computation (FGC) modules, and the Transplanter execution pipeline, benchmarked against conventional Linux kernel paths and post-quantum cryptographic baselines.

NTOS explicitly rejects opaque management engines, unverifiable firmware trust anchors, and speculative security guarantees. All claims in this repository are tied to observable artifacts and reproducible measurements.


---

Threat Model

NTOS assumes the following adversarial conditions:

Compromised firmware (UEFI, SMM, Intel ME / AMD PSP–class subsystems)

Hostile or untrusted hypervisors

Adversarial or partially compromised supply chains

Partial hardware honesty at best


NTOS does not assume:

Vendor-managed roots of trust

Proprietary sealed coprocessors

Firmware or silicon self-attestation claims

Blind trust in platform declarations



---

Architectural Overview

NTOS is built from first principles around observable behavior, not declared identity.

Core Primitives

Trait-based behavioral attestation

Hardware identity imprinting without vendor keys

Continuous verification across lifecycle transitions

Deterministic execution and migration pipelines


Major Components

Attestation

Attestor trait

Deterministic MockAttestor


Field-Governed Computation (FGC)

Transplanter execution pipeline

Reproducible benchmark harness



---

Attestation Model

NTOS attestation is behavioral, not declarative.

Instead of asking:

> “Does the hardware claim to be genuine?”



NTOS asks:

> “Does the system behave in ways that only a genuine, untampered system can?”



Properties

No TPM dependency

No vendor certificates

Replay-resistant behavioral proofs

Continuous (runtime) validation, not boot-only checks

Explicit, observable failure modes


Attestation is treated as a living property of the system, not a one-time ceremony.


---

Field-Governed Computation (FGC)

Field-Governed Computation constrains execution using field-derived invariants rather than policy alone. Computation is permitted only when system state conforms to externally verifiable physical, temporal, and behavioral constraints.

This enables:

Runtime confinement without hypervisors

Deterministic degradation under attack

Cryptographically provable execution envelopes

Reduced reliance on scheduler or privilege trust


FGC modules are independently verifiable and benchmarkable.


---

Transplanter Pipeline

The Transplanter is NTOS’s execution and migration mechanism.

It enables:

Migration of computation across trust boundaries

Preservation of identity and attestation state

Elimination of conventional process and context-switch assumptions


The Transplanter is benchmarked against:

Linux kernel syscall paths

IPC mechanisms

Cryptographic verification pipelines

Post-quantum cryptographic candidates



---

Benchmarks

All benchmarks in this repository are:

Reproducible

CPU-pinned

Warmed prior to measurement

Published with raw data


See: docs/benchmarks.md

Comparisons Include

NTOS Transplanter vs Linux kernel syscall and IPC paths

NTOS attestation vs classical cryptographic baselines

NTOS verification paths vs post-quantum candidates


Performance claims are always accompanied by methodology and data.


---

Breakthrough Claims (Traceable)

NTOS makes approximately 65 discrete, testable technical contributions. Each claim maps directly to code, benchmarks, or documentation in this repository.

A. Trust & Attestation

1. Trait-based attestation decoupled from hardware vendors


2. Behavioral proofs replacing declarative trust anchors


3. Deterministic mock attestation for adversarial testing


4. Continuous attestation beyond boot-time guarantees


5. Identity imprinting without TPMs or vendor certificates


6. Anti-replay attestation via temporal invariants


7. Attestation survivability across execution migration


8. Explicit rejection of opaque management engines


9. Observable failure modes under attestation violation


10. Hardware fingerprinting via behavioral convergence


11. Zero reliance on firmware honesty


12. Attestation composability across modules


13. Attestation usable in no_std environments


14. Attestation compatible with PQ crypto transitions


15. Attestation measurable via benchmarks



B. Field-Governed Computation

16. Computation constrained by field invariants, not policy


17. Runtime enforcement without hypervisors


18. Deterministic degradation under constraint violation


19. Field-derived execution envelopes


20. Cryptographically sealed computation fields


21. Elimination of privilege escalation assumptions


22. Stateless verification of field compliance


23. Side-channel resistance through constrained execution


24. Reduced attack surface via invariant collapse


25. Field constraints portable across hardware


26. Independently verifiable FGC modules


27. Execution refusal as a first-class behavior


28. Embedded-compatible FGC design


29. Measurable enforcement cost vs Linux


30. Scheduler-independent confinement



C. Transplanter & Execution

31. Execution migration without kernel context-switch assumptions


32. Identity-preserving computation transplant


33. Attestation continuity during migration


34. Deterministic pipeline entry and exit


35. Elimination of conventional “process” dependency


36. Reduced syscall boundary overhead


37. IPC replacement via transplant primitives


38. Pipeline reproducibility across machines


39. Transplant-safe cryptographic state


40. Measurable performance delta vs Linux


41. Minimal runtime trusted computing base


42. Execution survivability under partial compromise


43. Rollback-resistant migration


44. Stateless pipeline verification


45. Scheduler-independent execution paths


46. Reduced kernel attack surface


47. Migration without hypervisor mediation


48. PQ-compatible execution pipelines


49. Amenable to formal analysis


50. Fully observable execution paths



D. Measurement & Methodology

51. Benchmarks published with raw data


52. CPU-pinned deterministic measurements


53. Warm-up enforcement


54. Linux kernel comparisons on identical hardware


55. Cryptographic baselines disclosed


56. PQ candidate comparisons disclosed


57. CI-integrated benchmarks (non-blocking)


58. Artifact-backed claims only


59. No speculative security assertions


60. Reproducibility prioritized over peak numbers


61. Open licensing for auditability


62. Explicit failure semantics


63. Reusable benchmark harness


64. Documented measurement methodology


65. Claims falsifiable by design




---

Reproducibility

git clone https://github.com/Guzcomtechnologies-ops/ntos-testbed
cd ntos-testbed
cargo test --all
cargo bench

Results should match published data within statistical variance.


---

License

This project is licensed under the Apache License 2.0.


---

Citation

@misc{ntos2025,
  title={NTOS: Behavioral Attestation and Field-Governed Computation},
  author={Guzman, G.},
  year={2025},
  url={https://github.com/Guzcomtechnologies-ops/ntos-testbed}
}
