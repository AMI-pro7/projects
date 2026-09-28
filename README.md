# Reproducibility package: *The Spectral Cost of Detecting Nonequilibrium at Finite Temporal Resolution*

**Author:** Murad Aznagulov, Faculty of Physics, Lomonosov Moscow State University  
**Software version:** v1.0.0

The publication-ready reproducibility package is available here:

**[reproducibility_package_v1.0.0.zip](./reproducibility_package_v1.0.0.zip)**

Immutable manuscript-cited snapshot:  
https://github.com/AMI-pro7/projects/tree/0ba778f5ece327879f656d0778d72449ad180de5

The ZIP contains source code and compact numerical records used to verify the algebraic identities, reproduce the figures, audit the prespecified power study, and test the finite-resolution nonequilibrium-detection protocol.

The complete per-record Monte Carlo archive is distributed with the manuscript Supplemental Material because it is much larger. The archived study contains 5,200 whole records accounting for 5,069,097,448 simulated transitions.

## Quick start

```bash
unzip reproducibility_package_v1.0.0.zip
cd spectral_detection_code
python -m pip install -r requirements.txt
bash code/run_all.sh
```

The default audit does **not** regenerate the full ~5×10^9-transition Monte Carlo study. The explicit regeneration command is documented inside the package.

## Contents

The package includes:

- `README.md` and `README.TXT`;
- `CITATION.cff`;
- pinned `requirements.txt`;
- protocol implementation and unit tests;
- symbolic/numerical verification;
- rigorous analytic Fig. 1 lower-bound calculation;
- 60-digit deterministic two-clock diagnostic;
- nonnormal-generator diagnostics;
- simulation design and compact audit/results files;
- figure-generation scripts.

The main theorem is proved analytically in the manuscript and Supplemental Material; the numerical scripts are verification and reproducibility aids.

## Contact

Murad Aznagulov — amurad12@icloud.com
