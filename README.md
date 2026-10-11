# PSP dust impact viewer

Interactive 3-D view of the dust impact rate measured along Parker Solar Probe's orbit by
the FIELDS Time Domain Sampler, encounters 01–29, in heliocentric ecliptic J2000.

**<https://stuart-bale.github.io/psp-dust-viewer/>**

A dust grain striking the spacecraft makes a plasma cloud that the FIELDS antennas see as a
short voltage spike. In the 100 bps TDS survey product a sample counts as an impact when its
peak stands far enough above the RMS; the rate is those hits divided by the live time.

## What the page shows

* **The orbit**, coloured by impact rate or by measured/model, with an optional rate curtain.
* **A dust model** with two populations — bound grains on circular orbits with n ∝ r^−δ, and
  β-meteoroids released at a source radius whose gravity is reduced by (1 − β) — whose two
  normalisations are fitted to the measurements. Detection follows the impact charge,
  Q ∝ m v³·⁵, giving a factor (|v_rel|/50 km s⁻¹)^(3.5 μ) for cumulative mass index μ.
* **Impact direction**: arrows along v_dust − v_PSP, impact speed, and the angles from the
  ram and Sun directions; measured per-antenna asymmetries beside the predicted arrival
  direction in spacecraft coordinates.
* **Animated grains** on exact Kepler orbits, hyperbolic for β > 0.5.
* **The whole mission** in four frames: time from perihelion, ecliptic longitude, ecliptic
  latitude (where the cloud's symmetry plane sits), and a histogram in PSP's orbital plane.
* **.png snapshot** of the current view, settings and all.

## Data

* FIELDS L3 dust (Malaspina et al. 2023, ApJS 266, 2) — rates through 2024-12-31.
* FIELDS L2 `f2_100bps` TDS peak/RMS — the same selection applied past the end of L3, giving
  encounters 23–29. Validated against L3 over 2024: `raw` agrees to a median ratio of 1.000
  (98 % of bins within 5 %), the Poisson-corrected rate matches L3 `ucc` at 1.002.
* FIELDS full-mission ephemeris for the trajectory.

Counting saturates near perihelion: one peak per TDS sample caps the counted rate at
1/6.99 s ≈ 0.143 s⁻¹, and at E29 82 % of samples already hold a hit.

S. D. Bale, UC Berkeley / Imperial College. Built by `dust_viewer_3d.py`; FIELDS data from
the PSP/FIELDS archive, released under the PSP/FIELDS rules of the road.
