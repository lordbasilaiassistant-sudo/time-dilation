# Pound-Rebka style — gravitational redshift over a 22 m tower

**Cost:** **$10,000+ minimum** (this is the expensive one)
**Time to build:** months
**Difficulty:** ★★★★★
**What it proves:** A 14.4 keV gamma photon climbing 22 m on Earth gets
redshifted by exactly `gh/c² ≈ 2.5 × 10⁻¹⁵`. You measure that shift with the
Mössbauer effect.

**Most builders should not attempt this experiment.** It requires a radioactive
source, a Mössbauer drive, gamma detection, and shielding — competence with
each. Use [muon-detector](../muon-detector/) for cheap-and-rigorous, or
[GPS](../gps-time-dilation/) for cheap-and-easy. This page exists for
completeness and to honor the 1959 experiment that founded experimental GR.

---

## The original (Pound & Rebka, 1960; Pound & Snider, 1965)

- **Location:** Jefferson Physical Laboratory tower, Harvard University.
- **Height:** **22.5 m (74 ft)** vertical column.
- **Source:** Co-57 → Fe-57 nuclear transition, **14.4 keV gamma**, in an iron
  matrix to lock the Mössbauer effect.
- **Predicted shift:** `gh/c² = 9.81 × 22.5 / (3×10⁸)² = 2.46 × 10⁻¹⁵`
  (fractional frequency).
- **Measured (1965 update):** consistent with GR prediction to ~1%.

The trick was the Mössbauer effect: by embedding both source and absorber in
crystalline iron, the gamma's emission and absorption are recoil-free and the
spectral line is enormously sharp (Q ≈ 10¹²). That's the only reason a
fractional shift of 10⁻¹⁵ is even detectable.

## Why this is hard to replicate

1. **Radioactive source** — Co-57 is regulated. Sealed disk sources (a few mCi)
   need a license in the US (NRC general license for sealed sources under specific
   activity, or a state radioactive materials license). Typical cost: **$500–
   $3,000**.
2. **Mössbauer drive** — precision-controlled vibrating mount that Doppler-
   shifts the source through the absorption line. Used drives on eBay run
   $3,000–8,000. Commercial new: $15,000+.
3. **Gamma detection** — proportional counter or scintillator with MCA; needs
   energy resolution good enough to gate on 14.4 keV. Add ~$1,500–3,000.
4. **22 m vertical column** — you need a building with a ~22 m shaft for the
   path length. Without that, the gh/c² shift becomes proportionally smaller and
   the absorber line shape can no longer resolve it.
5. **Shielding and safety** — lead castles, dose monitoring, regulatory
   compliance.

Realistic minimum: **$10,000 in parts, several months of work, regulatory
approval, and access to an institution with a tall building.**

## If you're determined

Mössbauer spectrometers are commercially available from:
- **WissEL GmbH** (Germany) — turn-key academic Mössbauer setups.
- **SEE Co** (US, now Web Research) — historical supplier.
- **Royal Institute / KFKI lab surplus** on eBay.

For a hobbyist version, the closest thing is a tabletop Mössbauer demonstration
(no GR — just demonstrates the recoil-free emission). Several groups have
published plans:

- Kistner, O.C. & Sunyar, A.W., "Evidence for Quadrupole Interaction of Fe⁵⁷m
  and Influence of Chemical Binding on Nuclear Gamma-Ray Energy," PRL 4, 412
  (1960). The Mössbauer-effect basis.
- Pound, R.V. & Rebka, G.A., "Apparent Weight of Photons," PRL 4, 337 (1960).
  https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.4.337
- Pound, R.V. & Snider, J.L., "Effect of Gravity on Gamma Radiation," Phys.
  Rev. 140, B788 (1965). Improved to ~1%.

## Why we list it anyway

For three reasons:
1. **Historical**: Pound-Rebka was the experiment that turned general relativity
   from theory into an instrument. Every modern test (Gravity Probe A, GREAT,
   NIST 33 cm) is its descendant.
2. **Scale comparison**: notice that this experiment, with $10K+ of equipment
   and a 22 m tower, measures a shift of 2.5 × 10⁻¹⁵. The 2010 NIST experiment
   measured 4 × 10⁻¹⁷ over **33 cm** with $5M Al⁺ optical clocks. The detector
   technology has outrun the requirement.
3. **Sets the floor of what's *possible* in a private lab**. If you have the
   means, this is the path. If you don't, build [muon-detector](../muon-detector/)
   instead — same physics, different effect, ~100× cheaper.

## Don't do this if

- You don't already work in a lab with radiation safety infrastructure.
- You don't have access to a ≥20 m vertical shaft.
- You're not prepared for months of debugging and licensing.
- You expected to spend < $1,000.

For comparison, the **muon detector** measures γ ≈ 38 of *special*-relativistic
time dilation with $100 of parts, no licensing, and a weekend of building.
