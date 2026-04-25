# Quantum Paper Teardown

## Thesis
IBM researchers demonstrate that the specific 56-qubit peaked circuits Gharibyan et al. ran on Quantinuum's H2 processor to claim heuristic quantum advantage can be fully classically simulated in ~70 minutes on a single GPU — roughly half the H2 wall-clock time — by exploiting the mirror structure the obfuscation was designed to hide.

## Verdict
Succeeds cleanly and matters significantly: the claimed H2 advantage is refuted for the specific circuit instances presented, and the paper diagnoses *why* the construction is structurally vulnerable rather than just showing a one-off faster classical run.

## Tags
`quantum-advantage`, `classical-simulation`, `tensor-networks`, `trapped-ion`, `verifiable-computation`, `MPO`

---

## Paper Info
- **arXiv link:** https://arxiv.org/abs/2604.21908
- **Date:** 23 April 2026
- **Title:** Efficient Classical Simulation of Heuristic Peaked Quantum Circuits
- **Authors:** David Kremer, Nicolas Dupuis (IBM Quantum, IBM T.J. Watson Research Center)

---

## What the Paper Claims

The paper makes two concrete, falsifiable claims. First, a direct runtime claim: the largest circuit from Gharibyan et al. — `peaked_circuit_P9_Hqap_56x1917`, a 56-qubit circuit with 1,917 two-qubit RZZ gates executed on Quantinuum's H2 trapped-ion processor in under 2 hours — can be fully contracted classically in **4,059 seconds (~1 hour 10 minutes) on a single Nvidia A100 GPU**, approximately half the H2 wall-clock time; the Gharibyan paper had estimated classical runtimes of *years* for this instance. Second, a fidelity claim: the classical simulation recovers the peak bitstring at ~11% probability, consistent with the designed peak weight of ~10% reported in the original paper, confirming the simulation faithfully reproduces the circuit's output distribution rather than approximating it.

## Mechanism in Plain Language

Peaked circuits work by embedding a `UU†` identity block — a unitary followed immediately by its inverse — so that the output distribution collapses onto a single known bitstring. The Gharibyan construction obfuscates this mirror structure with swap permutations, angle sweeping, and masking, aiming to make the bond dimension of any tensor-network simulation explode before the two halves can cancel.

Kremer and Dupuis beat this by never trying to compress the full circuit directly. Instead, they split the circuit at its temporal midpoint, initialize an identity Matrix Product Operator (MPO) there, and absorb gates inward from both sides simultaneously. Because the two halves are approximate inverses, absorbed gates tend to cancel, keeping the MPO small. When the swap obfuscation inflates the bond dimension anyway, they apply a greedy **"unswapping"** step: they identify the highest-bond-dimension links in the MPO, test whether applying a swap from the left, right, or both sides reduces that dimension, and if so, accept the swap, record it as a factored-out permutation, and propagate it back into the remaining circuit via **rewiring**. The cycle of absorb → unswap → rewire repeats until the circuit is fully contracted, at which point sampling is exact up to a tiny SVD cutoff.

The key insight is that the obfuscation permutations are composed of nearest-neighbor swap gates — a structural signature that the unswapping procedure is specifically designed to detect and cancel. The mirror structure that *generates* the peak is inseparable from the structure that *enables* the simulation.

## What Matters Practically

Engineers designing verifiable quantum advantage benchmarks should internalize this: **any circuit whose peak is "designed in" via a mirror/`UU†` construction carries exploitable cancellation structure, regardless of how many obfuscation layers are applied.** The claimed advantage was predicated on classical simulation requiring years; the actual gap was sub-2x (quantum slower). Teams using peaked circuits as a benchmark should immediately evaluate whether their construction relies on a mirror identity block — if so, an MPO-based attack with unswapping is now the baseline to beat, not extrapolated MPS bond-dimension growth. The method is single-GPU, open-source, and reproducible, so the bar for "classically hard" on this class of circuits has effectively reset.

## Likely Misinterpretation

People will read this as "tensor networks beat quantum computers again" and conclude that classical simulation is always competitive — it is not. This paper is tightly scoped: the attack works *because* the circuit has a mirror structure, and the authors are explicit that applying their method to a random circuit without permutation structure would fail. The result says nothing about the hardness of peaked circuits in general (which remains QCMA-complete in the worst case) or about advantage claims built on different peaking mechanisms, such as the Deshpande et al. Hidden Code Sampling proposal that derives hardness from weight enumerators of random codes rather than from obfuscated identity blocks.

## Bottom Line

Peaked circuits built on obfuscated `UU†` mirror constructions are not classically hard — the peaking mechanism and the simulability vulnerability are the same structural feature. If you're using or evaluating HQAP-style circuits as a quantum advantage benchmark, retire them. The next round of peaked circuit designs needs peaking to emerge from problem hardness (e.g., encoded optimization or error-correction structure), not from a designed-in identity block.

---

## What This Changes for the Quantum-Advantage Bar

**Stack layer most affected: the circuit design / benchmark layer, not the hardware layer.** Quantinuum's H2 hardware performed exactly as advertised — the 56-qubit circuit ran correctly and the peak was recovered with the expected ~10% weight. The layer that failed is the classical-hardness argument embedded in the circuit construction itself. The prior H2 narrative from Gharibyan et al. was: "we benchmarked the best known classical methods (MPS, belief propagation, Pauli path), all fail beyond ~700 two-qubit gates, classical runtimes extrapolate to years, therefore H2 achieves heuristic quantum advantage." This paper invalidates that narrative not by improving hardware but by introducing a qualitatively different attack — one that the Gharibyan benchmarking suite never considered — and showing the extrapolation was wrong by a factor of >10,000×. The quantum-advantage bar for *verifiable* computation now requires that the peaking mechanism be *computationally* grounded (i.e., extracting the peak is as hard as solving an independently hard problem) rather than *structurally* grounded in a `UU†` identity that a clever MPO can quietly cancel. Concretely: any advantage claim relying on "no known classical method can do this" must now include an explicit analysis of mirror/permutation structure and MPO unswapping in its classical baseline.

---

## Scores

| Dimension | Score (1–5) | Rationale |
|---|---|---|
| Technical significance | 5 | Closes a specific, high-profile advantage claim with a novel algorithmic idea (unswapping); diagnoses the structural vulnerability rather than just finding a faster brute-force path. |
| Industrial relevance | 4 | Directly affects benchmark design for verifiable quantum advantage — a live engineering concern at every major quantum hardware vendor. Docked one point because the fix (change the peaking mechanism) is already identified and the hardware itself is unaffected. |
| Misinterpretation risk | 4 | High risk of overclaiming ("classical wins again, quantum advantage is dead") when the result is scoped to one construction class; also risk of dismissing it as a narrow academic result when it actually invalidates an active benchmark program. |

---

## Verification
- **arXiv:** https://arxiv.org/abs/2604.21908
- **Authors' code:** https://github.com/d-kremer/peaked-circuit-simulation
- **Teardown date:** 2026-04-24
