# Hafele-Keating mini — two clocks, drive one fast, measure the offset

**Cost:** **$300 (bare minimum, marginal precision) → $3,000 (comfortable margin)**
**Time to build:** weekend setup, multiple measurement runs
**Difficulty:** ★★★★☆
**What it proves:** A clock in motion ticks slower by γ. You'll measure tens of
picoseconds of offset over a day-long high-speed run.

This is the closest a hobbyist can come to repeating the 1971 Hafele-Keating
experiment, where cesium beam clocks were flown around the world on commercial
jets and gained or lost the relativistic amounts predicted to within 10%.

---

## Hafele-Keating's original numbers (Science 177:166–170, 1972)

| Direction | Predicted (SR + GR) | Observed |
|---|---|---|
| Eastward jet | **−40 ± 23 ns** | **−59 ± 10 ns** |
| Westward jet | **+275 ± 21 ns** | **+273 ± 7 ns** |

(Eastward is "with Earth's rotation" so the jet is faster in the inertial frame
→ SR slows it more. Westward is "against rotation" so the jet is slower → SR
slows it less.) Both observed values fall within 1-σ of the prediction. This was
the first direct macroscopic verification of GR-on-clocks via jet.

## What you can realistically build

You're not putting a cesium clock on a 747. You can put a GPS-disciplined
oscillator (GPSDO) in your car. The fundamental challenge: **you need clocks
stable to better than 10⁻¹² over the run duration** to detect the dilation from
non-relativistic vehicle speeds.

### Order-of-magnitude calculation

Time dilation per second for vehicle at velocity `v`:
`Δτ ≈ -(v²/2c²) seconds per second`

| Vehicle | Speed | Δτ per 24 h |
|---|---|---|
| Highway car (30 m/s) | 0.0001 mph_irrelevant | **−43 ps/day** |
| Bullet train (100 m/s) | 360 km/h | **−480 ps/day** |
| Commercial jet (250 m/s) | 900 km/h | **−3.0 ns/day** |
| Supersonic (700 m/s, hypothetical Concorde-like) | | **−24 ns/day** |
| ISS (7,660 m/s) | | **−2.6 µs/day** (SR only; net −28 ns/day after GR) |

**A drive at highway speed for 24 hours nets you ~40 ps of accumulated dilation.**
That's the precision target.

## Bill of materials

### Budget path (~$300, marginal precision)

| Part | Source | Price |
|---|---|---|
| 2× Leo Bodnar Mini Precision GPS Reference Clock | leobodnar.com | $130 each |
| 2× SMA cables | Amazon | ~$10 each |
| Time interval counter (HP/Agilent 5334B used) | eBay | ~$200 used |
| Laptop for logging | | (you have one) |
| **Total** | | **~$480** |

With this setup you can resolve ~100 ps with averaging. Marginal for car-speed
measurements; comfortable for plane/train.

### Comfortable path (~$3,000)

| Part | Source | Price |
|---|---|---|
| 2× Symmetricom S350 / Microsemi 5071A used cesium standard | eBay | $1,500–3,000 each |
| Stanford Research SR620 time interval counter | eBay used | ~$1,500–2,500 |
| Misc cables, mounts | | ~$100 |
| **Total** | | **$4,000–8,500** |

Cesium standards drift ~10⁻¹⁴ per day — easily resolves picosecond-level
dilation from a car.

## Procedure (budget path)

1. Sync both GPSDOs to GPS for several hours at a fixed location until each is
   locked and stable.
2. Disconnect GPS antennas (they'll continue free-running on their internal
   oscillator). Note the start time.
3. Put one in your car, drive 12–24 hours at highway speed (sustained, with
   minimal stopping).
4. Bring back, immediately measure the time interval between the two 1 PPS
   outputs.
5. Subtract the expected drift between the two GPSDOs from the same-location
   pre-trip and post-sync calibration runs.
6. The residual is your time-dilation signal. Expected: ~40 ps per 24 hours at
   highway speed.

**This is at the edge of what GPSDOs can resolve.** Realistically you'll need
multiple runs to beat the noise. The cesium-clock path makes this clean.

## Honest assessment

This is the hardest of the experiments in this folder because the relativistic
signal is so small that you're racing the clock noise floor. The CosmicWatch
muon detector is a much easier way to *demonstrate* time dilation; this
experiment is for builders who want to *replicate the spirit of Hafele-Keating*
specifically.

## References

- Hafele & Keating, "Around-the-World Atomic Clocks: Predicted Relativistic Time
  Gains," Science 177:166–168 (1972). DOI: 10.1126/science.177.4044.166
- Hafele & Keating, "Around-the-World Atomic Clocks: Observed Relativistic Time
  Gains," Science 177:168–170 (1972). DOI: 10.1126/science.177.4044.168
- Delva et al., "Gravitational Redshift Test Using Eccentric Galileo
  Satellites," Phys. Rev. Lett. 121, 231101 (2018). The GREAT experiment — a
  5.6× improvement over Gravity Probe A. arXiv:1812.03711.
