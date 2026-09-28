# Reproducibility package: *The Spectral Cost of Detecting Nonequilibrium at Finite Temporal Resolution*

**Author:** Murad Aznagulov, Faculty of Physics, Lomonosov Moscow State University  
**Software version:** v1.0.0  
**Status:** code and numerical records accompanying a manuscript submitted to *Physical Review Letters*.

This repository contains the source code and numerical records used to verify the algebraic identities, reproduce the figures, audit the prespecified power study, and test the finite-resolution nonequilibrium-detection protocol described in the manuscript.

## What is reproduced

- symbolic and numerical checks of the two-clock generator reconstruction;
- diagnostics for normal and nonnormal generators;
- the rigorous analytic information lower curve and the deterministic high-precision two-clock test curve used in Fig. 1;
- all decisions and Clopper--Pearson intervals from the archived Monte Carlo records;
- the power and spectral-timescale figures;
- unit tests of the current-based test protocol.

The archived power study contains 5,200 complete records and accounts for 5,069,097,448 simulated transitions. The default `run_all.sh` **does not** regenerate this large Monte Carlo study; it audits the archived results and reproduces the figures. The full study can be regenerated explicitly with `power_study.py`.

## Environment

Tested with Python 3.13.5. Install the pinned dependencies:

```bash
python -m pip install -r requirements.txt
```

The tested package versions are also recorded in `data/environment.json`.

## Fast complete audit

From the repository root:

```bash
bash code/run_all.sh
```

This runs the verification suite, protocol tests, archived-data audit, deterministic Fig. 1 calculations, nonnormal diagnostics, and figure generation.

## Full Monte Carlo regeneration

The prespecified power study is intentionally separate because it simulates roughly five billion transitions:

```bash
python code/power_study.py --output data --replicates 200 --controls 500 --seed 2026092707
```

After regeneration, rerun:

```bash
python code/audit_results.py
python code/make_figures.py
```

## Main files

- `code/equilibrium_test.py` — finite-sample current test and conservative p-value;
- `code/verify_and_simulate.py` — symbolic and numerical verification suite;
- `code/test_protocol.py` — protocol unit tests;
- `code/sandwich.py` — rigorous product-example curves for Fig. 1(b);
- `code/sandwich_mp.py` — 60-digit deterministic ring calculation for Fig. 1(a);
- `code/fig_sandwich.py` — reproduces Fig. 1;
- `code/nonnormal_check.py` — nonnormal-generator exponent-window diagnostics;
- `code/power_study.py` — full prespecified Monte Carlo study;
- `code/audit_results.py` — recomputes decisions and confidence intervals from archived records;
- `code/make_figures.py` — reproduces the power and timescale figures;
- `data/power_trials.jsonl` — complete archived per-record counts and seeds (included in the Supplemental code archive; the public GitHub snapshot contains compact audit outputs);
- `data/power_design.json` — prespecified simulation design;
- `data/power_results.json` — summarized study results;
- `data/accounting_audit.json` — transition-count accounting audit.

## Numerical-status notes

The main theorem and its constants are proved analytically in the manuscript and Supplemental Material. Numerical scripts are verification/reproducibility aids and do not replace the proofs.

In particular, the blue Fig. 1 curve is computed from the rigorous analytic inequality

```text
max_i D_KL((exp(tG))_i || (exp(tS))_i) <= 24 exp(-9 t)
```

valid for the plotted range. The high-precision orange curve is a deterministic CLT power-budget calculation for the explicit protocol and is not used as a rigorous finite-budget theorem constant.

## Citation

Please cite the accompanying manuscript and, when referring specifically to this code/data release, this repository version (`v1.0.0`) and its immutable Git commit.

## Contact

Murad Aznagulov — amurad12@icloud.com
