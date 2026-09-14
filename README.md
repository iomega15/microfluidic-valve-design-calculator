# Interactive design tool for 3D-printed microfluidic membrane valves

The geometric closure calculator from *"A Geometry-First Design Framework and Interactive
Design Tool for 3D-Printed Microfluidic Valves Using New Photopolymer Resins."*

**Open `index.html` in any browser.** One self-contained file: no install, no build step,
no network access, no dependencies.

## What it does

The framework reduces a valve's material behavior to a single empirical constant, the
**membrane deflection coefficient kappa** -- the dimensionless sagitta-to-width ratio s/C,
measured on your own resin and printer. Given kappa and your channel geometry, the tool
returns the membrane width and the spherical valve-seat radius and depth needed for the
membrane to seal against the seat.

Inputs (`g` open lumen, `kappa`, `W` channel width, `H_d` seat height, `n` exponent) can be
entered in millimeters or, with **quantized units** enabled, directly in printer pixels and
print layers, so the numbers match what you type into a slicer or into the device
generators. Outputs are `C` (required membrane width), `R` (radius of curvature), `s`
(sagitta), `d`, and `H_c` (total channel height), with a live cross-sectional diagram.

Two constitutive models are provided: the linear default `s = kappa*C`, and a generalized
power law `s = kappa*C^n` whose exponent defaults to n = 4/3, the stretching-dominated
limit of large-deflection membrane mechanics; n = 1 recovers the linear model. A built-in
fitting utility extracts kappa (and optionally n) from your own deflection measurements,
automatically excluding points where the membrane has already reached the channel floor
and the measurement has saturated.

## Measuring kappa for your own setup

kappa is specific to a resin, a printer and an exposure recipe -- it does not transfer from
this paper. Print membranes at several widths, measure each sagitta, and fit the slope of s
against C (the fitting utility does this for you). The test devices for that measurement
are in the companion repository,
`3d-printed-microfluidic-valve-testing-device-generators`.

## Versioning and citation

Each tagged release is archived to Zenodo, which issues a DOI per version plus a "concept"
DOI that always resolves to the newest version. **Cite the concept DOI**, so that a later
fix reaches anyone following the reference.

H. A. M. Nguyen, Q. A. Vuong, N. D. Q. Nguyen, D. J. Martins Cruz, B. Almanzar, A. Goz,
M. Khanna, R. Jitender, A. Kinney, S. Chapek, M. Volosov and R. Voronov, *A geometry-first
design framework and interactive design tool for 3D-printed microfluidic valves using new
photopolymer resins*, engrXiv preprint, 2026, DOI: [10.31224/8053](https://doi.org/10.31224/8053)
(under review at *Lab on a Chip*; the journal reference will replace this line on publication).

This deposit: DOI [10.5281/zenodo.21984175](https://doi.org/10.5281/zenodo.21984175) -- the
concept DOI, which always resolves to the newest release.

## Reporting problems

Please open an issue. Fixes ship as a new tagged release, archived by Zenodo under the same
concept DOI.

## License

MIT -- see LICENSE.
