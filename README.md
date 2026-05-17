# Time Dilation — Two-Observer Simulator

A fact-based browser simulator that answers one question:

> **Can you use time dilation to travel to the future?**

**Short answer: yes, unambiguously. It is one-way forward time travel and it has been
experimentally confirmed since 1971.** The sim shows you exactly how much, under which
conditions, with numbers you can check against published experiments.

Live demo: enable GitHub Pages after first push (see below), then this repo will serve at
`https://lordbasilaiassistant-sudo.github.io/time-dilation/`.

---

## What time dilation actually is

Two effects, both real, both measured, both load-bearing for technology you use today:

### 1. Special-relativistic (velocity-based)

If observer B moves at velocity `v` relative to observer A, B's clock ticks slower by

```
γ = 1 / sqrt(1 - v²/c²)
```

| `v / c`   | γ        | What 1 year for B costs everyone else |
|-----------|----------|---------------------------------------|
| 0.10      | 1.005    | 1.005 years                           |
| 0.50      | 1.155    | 1.16 years                            |
| 0.866     | 2.000    | 2 years                               |
| 0.99      | 7.09     | 7 years                               |
| 0.999     | 22.4     | 22 years                              |
| 0.9999    | 70.7     | 70 years                              |
| 0.99999   | 224      | 224 years                             |

There is no upper limit short of `c` itself. At 0.99999999 c, one year of your life =
~7,000 years on Earth. *In principle* a sufficiently fast ship could carry you to the
heat death of the universe in a human lifetime. The cost is the kinetic energy required,
which goes to infinity as v → c.

### 2. General-relativistic (gravity-based)

A clock at radius `r` from a non-rotating mass of Schwarzschild radius `r_s` ticks slower
than a distant clock by

```
sqrt(1 - r_s / r)
```

| `r / r_s` | factor    | What 1 year deep in the well costs the distant observer |
|-----------|-----------|---------------------------------------------------------|
| 10        | 0.949     | 1.05 years                                              |
| 3         | 0.816     | 1.22 years                                              |
| 2         | 0.707     | 1.41 years                                              |
| 1.1       | 0.302     | 3.31 years                                              |
| 1.01      | 0.0995    | 10 years                                                |
| 1.0001    | 0.0100    | 100 years                                               |

The factor goes to zero at the horizon (`r = r_s`), which is why distant observers see
infalling clocks freeze. *If* you could hover stably just above a stellar-mass black hole
horizon — which is a big "if" because hovering requires either infinite thrust at the
horizon or a stable orbit at `r > 3 r_s`/2 for ISCO — you could time-travel as far into
the future as you like.

### Both effects together: how GPS works

Each GPS satellite orbits at ~14,000 km/h and ~20,200 km altitude. Two effects compete:

- **SR (orbital speed):** satellite clock loses **−7 µs/day** to Earth-surface clocks.
- **GR (weaker gravity at altitude):** satellite clock gains **+45 µs/day**.
- **Net: +38 µs/day fast.** GPS receivers correct for this every fix.

Without that correction, GPS positions would drift by roughly **10 km per day** within
hours of launch. The fact that your phone's blue dot is accurate to a few meters is
*direct, daily, operational proof of both special and general relativistic time dilation.*

---

## Experimentally confirmed cases (citations)

| Year | Experiment              | What was measured | Result |
|------|-------------------------|-------------------|--------|
| 1941 | Rossi & Hall (muons)    | Cosmic-ray muons reaching ground | Lifetime extended by γ ≈ 8.8 — matched theory. Without dilation, almost none would reach sea level. |
| 1971 | Hafele–Keating          | Cesium clocks on commercial jets, eastward + westward | Eastward clock lost 59 ± 10 ns vs ground; westward gained 273 ± 7 ns. Both within ~10% of SR+GR prediction. |
| 1976 | Gravity Probe A         | Hydrogen maser on Scout rocket, 10,000 km altitude | GR shift measured to 1.4 × 10⁻⁴ precision — matched prediction. |
| 2010 | NIST optical clocks     | Two Al⁺ clocks at 33 cm height difference | Detected gravitational time dilation from a *staircase step*. ~4 × 10⁻¹⁷ shift. |
| ongoing | GPS / GLONASS / Galileo | All operational satellite navigation | Built-in 38 µs/day correction; would fail in hours without it. |
| ongoing | ISS / Mir astronauts    | Cumulative time on orbit | Krikalev: ~803 days on Mir/ISS → ~20 ms younger. Whitson, Polyakov, Avdeyev all similar. |

Sources: NIST PML, NASA TM-2003-212791 (GPS relativity), Hafele & Keating *Science* 1972
(177:166–170), Chou et al. *Science* 2010 (329:1630–1633).

---

## What the sim is doing

`index.html` shows two **light clocks** — a photon bouncing between mirrors. One bounce
= one tick. This is the canonical Einstein-thought-experiment proof:

- For the lab observer A, the photon goes straight up and down.
- For a moving observer B, from A's frame, the photon traces a *diagonal* (longer) path.
- Since `c` is the same in all frames, B's clock *must* tick slower by exactly γ.

You can read the ratio τ_B / τ_A live in the bottom panel and confirm it converges to
the theoretical value. The simulation has no hidden constants — the only physics inputs
are `v/c` (or `r/r_s`) and the formula above.

The "Future Travel" panel shows realistic engineering scenarios and the answer to
"how far into the future do I land, and what did it cost?"

---

## Open questions this sim is meant to explore

- [ ] **Practical future-jump regimes.** At what `v` or `r` does dilation start to feel
  like real time travel rather than a metrology curiosity?
- [ ] **The asymmetry / return problem.** You can fast-forward yourself, but you arrive
  in a future you can never go back from. Sim should make this visceral.
- [ ] **Twin paradox.** B leaves at relativistic speed, turns around, returns. A and B
  are at the same place at the end — A is older. The "paradox" is resolved by which
  twin accelerated. (Planned mode.)
- [ ] **Gravitational redshift visualization.** Light climbing out of a well loses
  energy — the same thing as B's clock ticking slow, just photographed in wavelength.

---

## Running locally

It's one HTML file. Open `index.html` in any modern browser. No build, no deps, no
server required.

## Deploying

This repo is set up for GitHub Pages. After enabling Pages in the repo settings
(Settings → Pages → Source: `main` branch, `/` root), the sim will be live at
`https://lordbasilaiassistant-sudo.github.io/time-dilation/`.

## License

MIT.
