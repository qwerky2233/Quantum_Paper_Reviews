# Quantum Teardown Candidate Queue
**Published:** April 9, 2026 | **Coverage window:** Mid-March – Early April 2026 | **Papers reviewed:** 12

---

## Scored Paper Queue

### 1. Shor's Algorithm is Possible with as Few as 10,000 Reconfigurable Atomic Qubits
**arXiv:** https://arxiv.org/abs/2603.28627
**Claim:** High-rate quantum error-correcting codes and efficient circuit design reduce the physical qubit requirement for cryptographically relevant Shor's algorithm (RSA-2048, ECC-256) from millions to ~10,000 atomic qubits.
**Tags:** `fault-tolerant` `error-correction` `cryptography` `hardware` `reconfigurable-atoms`

| Dimension | Score (1–5) |
|---|---|
| Technical significance | 5 |
| Industrial relevance | 5 |
| Misinterpretation risk | 5 |

---

### 2. Securing Elliptic Curve Cryptocurrencies against Quantum Attacks (Google Quantum AI Whitepaper)
**arXiv:** https://arxiv.org/abs/2603.28846
**Claim:** Shor's algorithm can break 256-bit ECDLP with fewer than 1,200 logical qubits and ~90 million Toffoli gates, translating to under 500,000 physical qubits — reframing near-term cryptographic risk for blockchain infrastructure.
**Tags:** `cryptography` `fault-tolerant` `error-correction` `industrial-relevance` `blockchain`

| Dimension | Score (1–5) |
|---|---|
| Technical significance | 5 |
| Industrial relevance | 5 |
| Misinterpretation risk | 5 |

---

### 3. Fault-Tolerant Execution of Error-Corrected Quantum Algorithms
**arXiv:** https://arxiv.org/abs/2603.04584
**Claim:** Near-break-even fault-tolerant QAOA execution is demonstrated on 12 logical (97 physical) qubits with logical T-gate infidelity of ~2.6×10⁻³, showing error-corrected circuits can match non-corrected approaches on real hardware.
**Tags:** `fault-tolerant` `error-correction` `QAOA` `near-term` `benchmarking`

| Dimension | Score (1–5) |
|---|---|
| Technical significance | 5 |
| Industrial relevance | 4 |
| Misinterpretation risk | 4 |

---

### 4. Heterogeneous Architectures Enable a 138x Reduction in Physical Qubit Requirements for Fault-Tolerant Quantum Computing
**arXiv:** https://arxiv.org/abs/2604.06319
**Claim:** Mixing processing units with qLDPC quantum memory modules reduces RSA-2048 factoring requirements from ~381,000 to ~190,000 physical qubits, a 138× improvement over naive grid-coupled topologies.
**Tags:** `hardware-architecture` `fault-tolerant` `qLDPC` `error-correction` `resource-estimation`

| Dimension | Score (1–5) |
|---|---|
| Technical significance | 5 |
| Industrial relevance | 5 |
| Misinterpretation risk | 4 |

---

### 5. Reference Architecture of a Quantum-Centric Supercomputer
**arXiv:** https://arxiv.org/abs/2603.10970
**Claim:** IBM's first published QCSC blueprint describes QPU integration alongside CPUs and GPUs in a multi-tiered architecture, validated through a half-Möbius molecule simulation and a 303-atom miniprotein model.
**Tags:** `hybrid-workflows` `HPC` `architecture` `IBM` `quantum-classical`

| Dimension | Score (1–5) |
|---|---|
| Technical significance | 4 |
| Industrial relevance | 5 |
| Misinterpretation risk | 4 |

---

### 6. Exploring Pathways Towards Quantum Advantage in Quantum Chemistry: The Case of a Molecule with Half-Möbius Topology
**arXiv:** https://arxiv.org/abs/2603.08696
**Claim:** Quantum simulations of the first-ever half-Möbius molecule (C₁₃Cl₂) on IBM Heron processors reach active spaces of 50 orbitals (100 qubits), demonstrating scalable simulation of exotic electronic structure verified by a companion Science publication.
**Tags:** `chemistry` `quantum-simulation` `IBM` `utility-scale` `materials`

| Dimension | Score (1–5) |
|---|---|
| Technical significance | 5 |
| Industrial relevance | 4 |
| Misinterpretation risk | 3 |

---

### 7. Utility-Scale Quantum Computational Chemistry
**arXiv:** https://arxiv.org/abs/2603.19081
**Claim:** Accurate quantum chemical calculations require hardware-dependent algorithm design at utility scale, not just demonstration of difficult edge cases — and the paper outlines the principles needed to get there.
**Tags:** `chemistry` `utility-scale` `hybrid-workflows` `roadmap` `quantum-advantage`

| Dimension | Score (1–5) |
|---|---|
| Technical significance | 4 |
| Industrial relevance | 5 |
| Misinterpretation risk | 4 |

---

### 8. Uncertainty Quantification for Quantum Computing
**arXiv:** https://arxiv.org/abs/2603.25039
**Claim:** A review paper connecting scalable uncertainty-aware algorithms with correlated hardware error characterization, bridging theoretical quantum algorithms and practical noise-resilient implementation for computational scientists.
**Tags:** `verification` `benchmarking` `noise` `UQ` `review`

| Dimension | Score (1–5) |
|---|---|
| Technical significance | 3 |
| Industrial relevance | 4 |
| Misinterpretation risk | 3 |

---

### 9. Analog-Digital Quantum Computing with a Superconducting Quantum Annealing Processor
**arXiv:** https://arxiv.org/abs/2603.15534
**Claim:** Coherent gate-based operations including multi-qubit quantum walks and Anderson localization are demonstrated directly on a D-Wave annealing QPU, expanding the operational regime of commercially available annealing hardware.
**Tags:** `hardware` `annealing` `D-Wave` `analog-digital` `near-term`

| Dimension | Score (1–5) |
|---|---|
| Technical significance | 4 |
| Industrial relevance | 4 |
| Misinterpretation risk | 4 |

---

### 10. End-to-End Performance of Quantum-Accelerated Large-Scale Linear Algebra Workflows
**arXiv:** https://arxiv.org/abs/2603.15515
**Claim:** Integrating an Iterative-QAOA quantum solver into Synopsys/Ansys LS-DYNA achieves 7–15% wall-clock time improvement on Finite Element Analysis — a concrete near-term quantum utility result for industrial engineering.
**Tags:** `hybrid-workflows` `HPC` `near-term` `linear-algebra` `industrial-relevance`

| Dimension | Score (1–5) |
|---|---|
| Technical significance | 4 |
| Industrial relevance | 5 |
| Misinterpretation risk | 4 |

---

### 11. Spacetime-Efficient and Hardware-Compatible Complex Quantum Logic Units in qLDPC Codes (RASCqL)
**arXiv:** https://arxiv.org/abs/2602.14273
**Claim:** The RASCqL architecture embeds quantum arithmetic and QROM directly within co-designed qLDPC codes, achieving 2×–7× qubit footprint reductions — recognized by PennyLane's Winter 2026 compilation review.
**Tags:** `qLDPC` `error-correction` `hardware-architecture` `fault-tolerant` `resource-estimation`

| Dimension | Score (1–5) |
|---|---|
| Technical significance | 4 |
| Industrial relevance | 4 |
| Misinterpretation risk | 3 |

---

### 12. High-Performance Syndrome Extraction Circuits for Quantum Codes
**arXiv:** https://arxiv.org/abs/2603.05481
**Claim:** A "left-right circuit" framework enables fast, low-depth syndrome extraction for a wide class of stabilizer codes, directly reducing runtime and error rates for fault-tolerant quantum processors.
**Tags:** `error-correction` `fault-tolerant` `syndrome-extraction` `hardware` `verification`

| Dimension | Score (1–5) |
|---|---|
| Technical significance | 4 |
| Industrial relevance | 4 |
| Misinterpretation risk | 2 |

---

## 🏆 Top 3 Teardown Candidates

### #1 — Shor's Algorithm is Possible with as Few as 10,000 Reconfigurable Atomic Qubits
https://arxiv.org/abs/2603.28627

**Teardown angle:** The headline claim — 10,000 qubits for RSA-2048 — will be repeated without the fine print: it assumes high-rate codes, specific reconfigurable atom hardware, and an efficient logical instruction set that isn't yet experimentally validated end-to-end. I would emphasize what "10,000 qubits" actually requires in terms of connectivity, gate fidelity, and reconfiguration speed, and stress-test whether this translates outside the atomic qubit regime. This matters practically because policymakers and financial institutions are already using this number to set post-quantum migration timelines — if the assumptions are fragile, the timelines are wrong.

---

### #2 — Heterogeneous Architectures Enable a 138x Reduction in Physical Qubit Requirements
https://arxiv.org/abs/2604.06319

**Teardown angle:** The 138× figure is real but architecture-conditional: the gains require tight co-design of qLDPC memory with processing modules, which no current fabrication pipeline can deliver at scale. I would focus on which of the three headline topologies (grid-coupled, heterogeneous-classical, qLDPC-memory) is actually on a plausible 5-year roadmap, and what engineering constraints cap the improvement in practice. This matters because hardware investment decisions — and qubit count benchmarks used in vendor comparisons — are directly downstream of papers like this one.

> **Network-task potential:** Yes — the paper's resource estimation methodology (tracking logical qubit overhead across architecture variants) is directly analogous to scoring contributor output quality under constrained observability, and the topology comparison framework could inform validator scoring rubrics.

---

### #3 — End-to-End Performance of Quantum-Accelerated Large-Scale Linear Algebra Workflows
https://arxiv.org/abs/2603.15515

**Teardown angle:** A 7–15% wall-clock improvement in LS-DYNA FEA is the most credible near-term utility claim in this batch, but the devil is in the problem-size scaling: QAOA solvers for linear systems are still exponentially hard in general, and this result likely holds for specific sparse matrix structures that happen to be favorable. I would focus the teardown on whether the speedup survives problem generalization and what FEA problem classes would *not* benefit, to prevent overgeneralization by industrial quantum teams. This matters because it is one of the first honest end-to-end HPC benchmarks in the literature and sets a precedent for how quantum utility should be measured.

---

## Selection Rule I Will Use Going Forward

- **Include** any paper that materially shifts the physical qubit count, timeline, or architecture requirements for fault-tolerant quantum computing at cryptographic or chemistry-relevant scale.
- **Include** any paper that provides a concrete end-to-end benchmark integrating quantum hardware into a real industrial workflow (FEA, molecular simulation, optimization), with wall-clock or accuracy measurements against a classical baseline.
- **Include** any paper introducing a new error-correction or syndrome-extraction method with demonstrable depth or overhead improvements beyond incremental gate-count reduction.
- **Include** any paper that introduces a new verification, uncertainty quantification, or benchmarking framework that could transfer to evaluating quantum algorithm performance under realistic noise.
- **Include** review or roadmap papers only if they synthesize a genuinely underappreciated bottleneck or contain new experimental data — not if they restate known challenges with new formatting.
- **Skip** any paper whose primary contribution is a numerical simulation of a small toy system (<20 qubits, no error correction) without a clear scaling argument or architectural implication.
- **Validation-focused shortlisted papers:** Paper #2 (Heterogeneous Architectures) and Paper #8 (Uncertainty Quantification) are both validation-adjacent; Paper #2 has direct network-task potential via its resource estimation framework; Paper #8 has indirect potential through its noise characterization methodology.
