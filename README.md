# Crystal morphology viewer: original vs GA-optimised

Interactive 3D comparison of the original (CSD VisualHabit) and genetic-algorithm-optimised crystal
morphologies of five pharmaceutical materials, supplementing the static figures in the PhD thesis
*ML Prediction of Pharmaceutical Flow Behavior* (O. El Habbak, University of Strathclyde).

**Open the viewer:** https://omes014.github.io/crystal-morphology-viewer/

Direct links: `#REFCODE/orig`, `#REFCODE/opt` or `#REFCODE/overlay`, for example `#CEKBEZ/overlay`.

| Refcode | Material | Morphology forcefield |
|---|---|---|
| LASCAC01 | L-Ascorbic acid | CSD-OPCS16 |
| CEKBEZ | Lovastatin | CSD-OPCS16 |
| CIMNUJ | Dapagliflozin propanediol monohydrate | CSD-OPCS16 |
| AMPHOL01 | 4-Aminophenol | Gavezzotti |
| HAXHET02 | Probucol | CSD-OPCS16 |

## What is shown

- **Original:** VisualHabit morphology computed with the CCDC CSD Python API.
- **Optimised:** the same shape after the GA-optimised anisotropic scaling (aspect ratios r1, r2) that best
  reproduces the measured particle-shape distribution (lowest Kolmogorov–Smirnov statistic, KS).
- **Overlay:** optimised shape (solid) with the original outline (wireframe).
- Faces are coloured by {hkl} family; the legend gives each family's share of the surface area before and after.
  The scaling is linear, so no faces appear or disappear; faces of the optimised shape are those descended from
  the same (hkl) planes (their normals rotate). Both shapes are scaled to equal volume.

## Data

`data/*.json` holds derived geometry only (vertex coordinates, triangulated facets, {hkl} labels, area fractions)
and the GA results (r1, r2, KS). No experimental measurement data is included.

## Running locally

Serve the folder over HTTP (the page loads its data with `fetch`):

    python -m http.server
    # then open http://localhost:8000/

three.js r160 is loaded from the jsDelivr CDN.

## Citation

DOI: to be added (Zenodo).
