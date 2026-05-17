# GPS time-dilation decoder — watch the +38 µs/day correction in real signals

**Cost:** **~$60** (RTL-SDR v4 + active GPS antenna)
**Time to build:** evening
**Difficulty:** ★★☆☆☆
**What it proves:** The GPS navigation message broadcasts a relativistic clock
correction. You decode it from raw L1 signals and watch the SR+GR engineering
fix go by in your terminal.

GPS is the largest, most expensive, longest-running experimental confirmation of
both special and general relativity. Without the +38 µs/day correction, your
phone's blue dot would drift ~10 km/day within hours of any satellite launch.
Every GPS receiver corrects for this every fix.

You don't need a $20M ground station to see it. A $40 USB dongle works.

---

## The physics

Each GPS satellite carries a cesium or rubidium atomic clock and orbits at:

| Quantity | Value |
|---|---|
| Altitude | 20,200 km (above Earth's surface) |
| Orbital radius from Earth center | 26,600 km |
| Orbital velocity | 3,874 m/s = 0.00001292 c |
| Orbital period | ~11h 58m (twice per sidereal day) |

Two relativistic effects fight each other:

1. **Special relativity (orbital speed slows the satellite clock):**
   `Δt_SR/t = -v²/(2c²) = -8.349 × 10⁻¹¹`
   Daily: **-7.21 µs/day** (satellite clock loses)

2. **General relativity (weaker gravity at altitude speeds it up):**
   `Δt_GR/t = g·h/c² + higher-order = +5.288 × 10⁻¹⁰`
   Daily: **+45.69 µs/day** (satellite clock gains)

**Net: +38.48 µs/day fast** for the satellite vs Earth-surface clocks.

This is engineered out in two ways:
- The satellite onboard frequency is offset by `(-Δf/f) = +4.4647 × 10⁻¹⁰` *before
  launch* (the cesium beam is intentionally tuned ~4.46 parts in 10¹⁰ slow).
- The navigation message carries a residual relativistic correction term `Δt_r`
  for the satellite's actual (slightly eccentric) orbit. **This is the term you
  can decode.**

The eccentricity correction varies over each orbit. Formula in IS-GPS-200:
```
Δt_r = F · e · √A · sin(E_k)
F = -2 · √μ / c² = -4.442807633 × 10⁻¹⁰ s/m^(1/2)
```
where `e` = orbit eccentricity, `A` = semi-major axis, `E_k` = eccentric anomaly.

For typical GPS orbits this correction oscillates between roughly **±25 ns** over
the orbital period. **You can plot this oscillation from raw signal data.**

## Bill of materials

| Part | Source | Price |
|---|---|---|
| RTL-SDR Blog V4 dongle | rtl-sdr.com or Amazon | **$39.95** |
| Active GPS antenna (Adafruit #960 or equivalent, ~28 dB gain, SMA) | Adafruit | **$21.50** |
| MCX-to-SMA adapter (if dongle is MCX) | Amazon | ~$5 |
| Bias-T or USB power injector for active antenna | included in many SDR kits | ~$10 |
| **TOTAL** | | **~$60–80** |

Many SDR kits ship with bias-T and antenna mount. You can also use a more
sensitive antenna (a re-purposed Trimble or u-blox patch antenna) for ~$30.

## Software

Open-source GNSS receivers that decode L1 C/A and let you inspect ephemeris and
clock-correction terms:

- **[gnss-sdr](https://gnss-sdr.org)** — full open-source software-defined GNSS
  receiver. Has built-in support for RTL-SDR. Dumps decoded navigation message
  to RINEX, including all clock correction parameters. Linux/Mac.
- **[GNSS-SDRLIB](https://github.com/taroz/GNSS-SDRLIB)** — Windows alternative.
- **[gps-sdr-sim](https://github.com/osqzss/gps-sdr-sim)** — for simulating
  signals you can decode, useful for testing.
- **[goGPS-Project / RTKLIB](http://www.rtklib.com/)** — converts raw output to
  RINEX nav files; the broadcast clock-correction parameters `af0`, `af1`, `af2`,
  `Δt_r` are right there in plain text.

## Procedure

1. Plug dongle in, set the GPS antenna outside or by a window, power the active
   antenna (bias-T or USB).
2. Run gnss-sdr with the L1 C/A config (sample config files are in the gnss-sdr
   repo).
3. Wait a few minutes for ephemeris download from at least 4 satellites.
4. Look at the RINEX nav file output — for each satellite, the relativistic
   correction `Δt_r` is computed per epoch.
5. Plot `Δt_r` vs time for one satellite over a full orbit (12 hours). You should
   see a sinusoidal-like oscillation with amplitude ~10–25 ns, depending on the
   specific satellite's eccentricity.

**That's it. You've decoded a number from a navigation broadcast that exists
solely because special and general relativity are both real.**

## Sanity checks

- The constant offset (the ~4.46 × 10⁻¹⁰ ground-frequency tuning) is built into
  the satellite clock at the factory and doesn't show in `Δt_r`. It's only
  visible if you compare the satellite signal to a reference cesium clock —
  needs a much more expensive setup.
- The variation you see in `Δt_r` IS due to the orbital eccentricity term
  (relativistic), separate from any clock drift.
- Some receivers apply `Δt_r` silently before exposing data; check the RINEX
  output format.

## References

- IS-GPS-200N (March 2022), "NAVSTAR GPS Space Segment / Navigation User
  Interfaces." Public spec from gps.gov. Section 20.3.3.3.3 has the
  relativistic correction formula.
- Ashby, N., "Relativity in the Global Positioning System," Living Reviews in
  Relativity 6, 1 (2003).
  https://link.springer.com/article/10.12942/lrr-2003-1
- Petit & Luzum (eds.), "IERS Conventions 2010" — full geodetic-relativistic
  framework.
