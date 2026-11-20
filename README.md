# Physical-ASI Seed — Falsifiable Test Harness

A minimal, free-Colab-runnable harness that tests the **necessity** and **mechanism**
claims of the GRAIL + CEAS + Ψ triad and the RSI loop, and emits a **certification report
(Levels 1–4)**. It is built around your lecture-notes v18 and the MECE claim inventory.

## What this proves — and what it deliberately does NOT

**In scope (provable on classical GPU/CPU):** each module's mechanism and necessity
(Categories B–F of the inventory), the 8-corner triadic ablation, a real ≥20-cycle RSI
loop with a non-vacuous deviation certificate.

**Out of scope, marked `NOT TESTABLE HERE` (not attempted):** A3 (is-ASI / ≫ best human),
embodiment, meta-RSI, the physics correspondence (Category G), and post-quantum security.
The report's **maximum verdict is Level 4** and it **cannot print "this is ASI."**

## Layout

```
configs/registry.py        pre-registered thresholds + ablation flags (frozen, hashed)
core/utils.py              seeding, NumPy-2 shim, metrics log, verdict vocabulary
core/grail.py              hyperboloid invariant I(q,k), group actions, twin transport
core/ceas.py               predictive beta*, entropy thermostat, rank-one collective channel
core/psi.py                SCM do-calculus, counterfactuals, D+N split, infeasibility cert
core/seed_model.py         switchable triad model (all 8 ablation corners from one class)
core/rsi.py                7-step expansion + NON-VACUOUS deviation certificate
domains/                   six task domains (scm, orbit, coordination, inverse, symbolic, token)
experiments/ceas_psi_grail per-module necessity (E_C*, E_P*, E_G*)
experiments/triadic.py     E_B1 (triad wins) + E_B2 (superadditivity, honestly reported)
experiments/rsi.py         E_F1 (closed loop) + E_F2 (certificate) + E_F3 (scaling)
os_layer/capabilities.py   four OS capabilities an n8n-class wrapper cannot do
os_layer/llm_compare.py    Qwen2.5-0.5B adapter + E_L1/E_L2 comparison
report/certify.py          Levels 1–4 report; NOT-TESTABLE rows; cannot certify "ASI"
notebooks/                 the two generated Colab notebooks
build_notebooks.py         regenerates the notebooks from the verified .py sources
```

## How to run

Open `notebooks/Notebook1_seed_harness.ipynb` in free Colab and Run All (~3–5 min, T4 or CPU).
Then `notebooks/Notebook2_os_and_llm.ipynb` (loads Qwen2.5-0.5B; falls back to a mock if
transformers/the model is unavailable so it still runs).

## Experiment → claim map

| Experiment | Claim(s) | Result in-sandbox |
|---|---|---|
| E_C1 β-calibration | C2, C3 | PASS (CEAS tracks β*, fixed drifts) |
| E_C2 diameter collapse | C6, B2 | PASS (T_CEAS/T_local ≈ 0.8%, shrinks in N) |
| E_C3 susceptibility | C9 | PASS |
| E_P1 intervention gain | D6, B3 | PASS (do beats observe by ~0.32) |
| E_P2 counterfactual | D6 | PASS |
| E_P3 non-commutativity | D1 | PASS (‖[T_a,T_b]‖ = 0.95) |
| E_P4 causal transfer | D3 | PASS (mechanism transfers via contrast) |
| E_G1 twin exactness | E1 | PASS (≈1e-30 fp64) |
| E_G2 orbit generalization | E4, E6, B4 | PASS (GRAIL generalizes, Euclidean fails) |
| E_G3 classical recovery hardness | E5 (classical only) | PASS (NOT a post-quantum claim) |
| **E_B1 triad wins** | **B5, B10** | **PASS, robust (margin ≈ +0.5)** |
| **E_B2 superadditivity** | **B5, B10** | **MARGINAL / seed-sensitive — reported with spread** |
| E_F1 closed RSI loop | F1 | PASS (≥20 cycles, monotone frac ≥ 0.6) |
| E_F2 non-vacuous certificate | F4 | PASS (valid passes, oversized fails) |
| E_F3 scaling evidence | F | PASS (capability rises with capacity) |
| E_L1 per-domain vs LLM | E_L1 | LLM competitive only on token domain |
| E_L2 architectural class | E_L2 | LLM cannot enter Level 2+ (no ablatable triad) |

## Honest findings (read these)

1. **The strong, defensible result is NECESSITY**, not superadditivity. E_B1 (the full
   triad strictly beats all seven ablations) is robust across seeds. **E_B2
   (superadditivity — "more than a bundle of tricks") is empirically marginal**: the excess
   hovers near zero and flips sign across seeds with this composite objective. The report
   discloses this rather than asserting it. If the tex/website needs the strong
   superadditivity claim, it needs either a task where the modules interact more, or
   honest softening.

2. **Several flaws from the original notebooks were fixed here**: the NumPy-2 `trapz`
   crash; the unlearnable reversal task (now learns); the inverse domain that didn't
   isolate Ψ (now scores action-correctness under the true causal model); the vacuous RSI
   certificate (now non-vacuous: δ measured, new units actually wired into forward, can
   fail); and the "single expansion called RSI" (now a real ≥20-cycle loop). The
   compute-efficiency ratio is labeled an algebraic identity, not a measured speedup.

3. **Scope discipline is enforced in code**, not just prose: A3/embodiment/meta-RSI/physics
   correspondence/post-quantum are hard-coded `NOT TESTABLE HERE` and the max verdict is
   capped at Level 4.
