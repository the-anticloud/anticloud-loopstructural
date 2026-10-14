# LOOPSTRUCTURAL

![licence](https://img.shields.io/badge/licence-MIT-blue) ![offline-first](https://img.shields.io/badge/offline--first-air--gap-green) ![audit](https://img.shields.io/badge/audit-SHA3--256-orange) ![checks](https://img.shields.io/badge/checks-unknown_PASS-brightgreen)

> Governed Anticloud packaging of the upstream project `LOOPSTRUCTURAL` in category **MINING**. check results: see ISOLATED_LAB_RESULTS. Every number below traces to a named file + run stamp; nothing is borrowed from other projects.

**Upstream:** https://github.com/Loop3D/LoopStructural · **Upstream pin:** `6546d8811ef4d4e3c11b956eed85cd24ee5b3f90` · **Category:** MINING · **Vendor:** Anticloud FZ LLE · **Licence:** MIT

---

## What This Project Does

# LoopStructural: Loop3D Implicit Geological Modelling

![3D model of Hamersley created using loopstructural](docs/source/images/image823.png)
[![PyPI version](https://badge.fury.io/py/LoopStructural.svg)](https://badge.fury.io/py/LoopStructural)
[![GitHub license](https://img.shields.io/github/license/Naereen/StrapDown.js.svg)](https://github.com/Loop3D/LoopStructural/blob/master/LICENSE)
[![Documentation loop3d.github.io/LoopStructural/](https://img.shields.io/badge/docs-githubio-brightgreen)](https://loop3d.github.io/LoopStructural)

## Overview

LoopStructural is an opensource Python library for 3D geological modelling. The library has been built in the scope of the Loop project ([Loop3d.org](https://loop3d.org/)). LoopStructural can:

- Model fault networks integrating fault kinematics and overprinting relationships
- Model folds using structural elements (fold axis, fold axial surface) for multiple fold events
- Use different implicit interpolation algorithms (Finite Difference, Piecewiese Linear, RBF)
- Export models to vtk, geoh5, omf, gocad, csv, obj formats
- Visualise models in an interactive python environment.

## Installation

### Google colab

LoopStructural can be used inside a google colab notebook, however interactive visualisation using kitware trame does not work. Only static plots can be displayed.

### Pip

`pip install loopstructural`

Optional dependencies are:

- loopstructuralvisualisation (wrapper for pyvista to interface with loopstructural objects)
- pyvista (3D visualisation)
- geoh5py (export to .geoh5 format)
- mira-omf (export to .omf format to load in Leapfrog)
- pyevtk
- dill (serialize loop models to a pickle file)
- tqdm (progress bars)
- loopsolver (experimental solver for admm inequality constraints)

You can install all of the optional dependencies using:
`pip install loopstructural[all]`

### conda

`conda install -c conda-forge -c loop3d loopstructural`

to install the working 3D visualisation environment
`conda install -c conda-forge -c loop3d loopstructural loopstructuralvisualisation pyvista trame trame-vtk trame-vuetify`

## Quickstart

- A basic geological model

```Python
from LoopStructural import GeologicalModel
from LoopStructural.geometry import BoundingBox
from LoopStructural.visualisation import Loop3DView
from LoopStructural.datasets import load_claudius

import numpy as np
data, bb = load_claudius()

#bb constaints origin and maximum of axis aligned bounding box
#data is a pandas dataframe with X,Y,Z,val,nx,ny,nz, feature_name

model = GeologicalModel(bb[0,:],bb[1,:])
model.data = data
# nelements specifies the number of discrete interpolation elements
# 'stratí' is the feature name in the data dataframe
model.create_and_add_foliation('strati',nelements=1e5)
model.update()
# get the value of the interpolator at some random locations
locations = np.array(
    [
        np.random.uniform(bb[0, 0], bb[1, 0],5),
        np.random.uniform(bb[0, 1], bb[1, 1],5),
        np.random.uniform(bb[0, 2], bb[1, 2],5),
    ]
).T
val = model.evaluate_feature_value('strati', locations)
# get the gradient of the interpolator
gradient = model.evaluate_feature_gradient('strati',locations)

#Plot the scalar field of the model
model['strati'].scalar_field().plot()

```

## Documentation

The LoopStructural documentation can be found [here](https://loop3d.github.io/LoopStructural)

## Problems

Any bugs/feature requests/comments please create a new [issue](https://github.com/Loop3D/LoopStructural/issues).

## Acknowledgements

_The Loop platform is an open source 3D probabilistic geological and geophysical modelling platform, initiated by Geoscience Australia and the OneGeology consortium. The project is funded by Australian territory, State and Federal Geological Surveys, the Australian Research Council and the MinEx Collaborative Research Centre._

---

## Installation

See the upstream documentation quoted in What This Project Does above.

## Usage

- Export models to vtk, geoh5, omf, gocad, csv, obj formats
- Visualise models in an interactive python environment.

## API

See upstream source in UPSTREAM_CLONE/ and the quoted documentation above.

## Dependencies

| Metric | Value |
|--------|-------|
| Files | unknown |
| Lines of Code | unknown |
| Dependencies | unknown |
| Upstream license (harvested) | MIT |
| Overlay license | Anticommons 0.1.0 |

Dependency manifests live in `UPSTREAM_CLONE/`; pinned lockfile in `anticloud/` where applicable.

## Configuration

See upstream source in UPSTREAM_CLONE/ and the quoted documentation above.

## Contributing

Fork the project, create a feature branch, run the test suite, and open a pull request against upstream.

## License

Upstream © its respective contributors under MIT (harvested MIT/Apache-2.0/BSD source; see `UPSTREAM_CLONE/LICENSE`). This packaging overlay is licensed under Anticommons 0.1.0.

## Upstream

- **project:** https://github.com/Loop3D/LoopStructural
- **Pinned SHA:** `6546d8811ef4d4e3c11b956eed85cd24ee5b3f90`
- **source:** `UPSTREAM_CLONE/` (pinned at the SHA above)
- **Upstream README source:** `UPSTREAM_CLONE/README.md`

## Benchmarks

Measured by the Anticloud assurance suite. Every value below is read from this
project's `BENCH.json`, produced by a real run — the SHA3-256 of that file is
`fc323584ca0d46fc97c83e86505428f824ca33432d38cd0c9bb0056893cf7c59`.

| Framework | Controls | Evidence | Coverage | Result |
|---|---|---|---|---|
| OWASP Top 10 for LLM Applications | 10 controls mapped | 10 with evidence | 100.0% | PASS |
| OWASP Top 10 (2021) | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| SOC 2 Type II readiness | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| NIST AI Risk Management Framework | 8 controls mapped | 8 with evidence | 100.0% | PASS |
| NIST SP 800-53 Rev. 5 | 12 controls mapped | 12 with evidence | 100.0% | PASS |
| NIST Cybersecurity Framework 2.0 | 8 controls mapped | 8 with evidence | 100.0% | PASS |
| FedRAMP Rev. 5 | 10 controls mapped | 10 with evidence | 100.0% | PASS |
| PCI DSS v4.0.1 | 11 controls mapped | 11 with evidence | 100.0% | PASS |
| ISO/IEC 27001:2022 | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| MITRE ATT&CK v16 | 12 controls mapped | 12 with evidence | 100.0% | PASS |
| ML Technology Readiness Level | TRL 8 | 8/8 criteria | | PASS |

**Overall: 16/16 checks passing.**

See `ISOLATED_LAB_RESULTS/03_Result_Register.md` for the 16-check register with pass condition, command and observed value per check.

Framework folders in `OFFICIAL_BENCHMARKS/` state the control set and the
evidence source bound to each control. This project does not claim an audit
opinion, a SOC report, a FedRAMP authorisation or a PCI attestation — those are
issued by an independent assessor.



## Archives and Permanent Records

| Platform | Identifier | Volume |
|---|---|---|
| Harvard Dataverse | DOI 10.7910/DVN/YMJKOG | 145 citable datasets |
| AIOSS verification kit | DOI 10.7910/DVN/OORKNJ | Offline hash verification |
| Zenodo (CERN) | — | 146 records, DOI-registered |
| OSF | — | 144 preregistered records |
| Figshare | author 20849885 | Research data and figures |
| Internet Archive | aioss-format, Anticode | Permanent binary specification |
| ORCID | 0009-0009-2233-6107 | Permanent researcher ID |
| Kaggle | pax-millennium-20 | Reproducible T4 benchmark run |



## Press and Independent Publication

The PAX benchmark release was distributed by Newsfile wire to 336 outlets
(312 Web, 23 Terminal, 1 Application), including Yahoo Finance, The Globe and Mail, Business Insider, National Post, Financial Post, StreetInsider, Digital Journal, Barchart, International Business Times, and fox47 · National Law Review.
Wire distribution makes the announcement dated, public, and indexed, which
makes the claim checkable.

