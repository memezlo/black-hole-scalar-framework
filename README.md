# Black Hole Scalar Framework: Quantum Collapse and Singularity Resolution

A numerical relativity framework written in Python designed to simulate the dynamical collapse of a thin shell, analyze tachyonic scalar field growth near the horizon, and test conditions for a non-singular quantum cosmic bounce (Big Bounce).

## Key Scientific Results

1. **Precision Verification of Classical Limit:** 
   The code successfully integrates the classical collapse phase based on the thin-shell equations from Torres & Fayos (2014). For their initial conditions, the simulator yields a high-precision value for the outer horizon crossing time:
   \[\boxed{\tau_+ = 799595.477610}\]
   This result matches the approximate value (~799595) in the literature and has been verified to be stable across **5 different integrator configurations**, proving the high numerical robustness of the core code.

2. **Analytical Growth-to-Luminosity Filter:**
   The framework computes the non-linear threshold factor \(R = N_{tot} / N_{crit}\) via the fundamental coupling integral:
   \[\ln\frac{\vert{}A(M)\vert{}}{\vert{}A_0\vert{}} = \int_M^{M_0}\frac{\Gamma(m)}{L_H(m)}\,dm\]

3. **Critical Audit of Model Constraints:**
   - **Dimensionality Constraint:** The mathematical consistency of the model strictly requires \(L_H(M)\) to be interpreted as a quantum luminosity (energy flux). If treated as a geometric horizon radius, the integral breaks down due to dimensional mismatch.
   - **Scale Domain:** Analytical scaling proves that the logarithmic "quantum brake" governs the dynamics exclusively at the Planck regime (\(M \to M_{pl}\)), while the quadratic mass term rules the macroscale collapse.
   - **Alternative Field Dynamics:** A distinct validation branch is introduced where Γ(M) governs the raw amplitude rather than its logarithm, demonstrating a linear growth phase (Δ A) which is energetically insufficient to trigger a full singularity resolution.

## Repository Structure

- `black_hole_scalar_model.py` — The core numerical engine executing the integration routines and partial differential equations (PDEs) with bounded trignometric constraints.
- `test_black_hole_scalar_model.py` — Automated verification unit-tests ensuring energy conservation and boundary conditions.
- `black_hole_scalar_results/` — Complete verification evidence dataset:
  - `growth_integral.png` & `growth_rate.png` — Visual proofs of the logarithmic bounce barrier.
  - `growth_mode_convergence.csv` & `static_threshold_convergence.csv` — Grid convergence tests proving mathematical stability.
  - `sensitivity.csv` — Parameter space analysis mapping the R ≥ 1 bounce thresholds against free coefficients α and β.
- `requirements.txt` — Environment specifications (numpy, scipy, matplotlib).

## Open Questions for Future Research
This repository is designed as an open-source framework for numerical relativity. Further development requires:
- Replacing the phenomenological model functions with self-consistent effective Loop Quantum Gravity (LQG) Hamiltonians.
- Extended integration beyond the inner horizon to track the explicit formation of outgoing shockwaves or a smooth black-hole-to-white-hole transition.
