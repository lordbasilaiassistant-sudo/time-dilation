# Experiments — making time dilation real with your own hands

The honest truth about a "time machine" using time dilation:

> **You cannot build a device that creates a perceptible time-dilation field at any
> price humans can pay.** The math forbids it — kinetic energy scales as `(γ−1)mc²`,
> and `c²` is `9×10¹⁶ m²/s²`. For a 100 kg human to time-travel at γ=2 (one year
> forward per year experienced), you need ~9×10¹⁸ J ≈ 1.5% of *world annual energy
> consumption*. The closest thing to a "real" time machine humans have access to is
> a high orbit or a long fast trip — cosmonaut Sergei Krikalev is the human record
> holder at ~20 ms of accumulated forward dilation from 803 days in orbit.

What you *can* do, and what this folder is for: **observe time dilation that's
already happening, with cheap equipment, and prove it's real with your own data.**

---

## Pick your experiment

Ordered cheapest → most expensive, easiest → hardest, qualitative → most precise.

| # | Experiment | Cost | What it proves | Difficulty |
|---|-----------|------|----------------|------------|
| 1 | [Cloud chamber](cloud-chamber/) | **$15–80** | You can SEE muons crossing your living room that shouldn't be alive | ★☆☆☆☆ |
| 2 | [GPS time-dilation decoder](gps-time-dilation/) | **$60–80** | The 38 µs/day SR+GR correction is in the GPS signal you receive | ★★☆☆☆ |
| 3 | [Muon detector (CosmicWatch v3X)](muon-detector/) | **~$100** | Quantitative measurement: muons live 8-40× longer than they should | ★★★☆☆ |
| 4 | [Mini Hafele-Keating](hafele-keating-mini/) | **$300–3,000** | Two clocks, drive one fast, measure the offset | ★★★★☆ |
| 5 | [Pound-Rebka style gravitational redshift](pound-rebka/) | **$10,000+** | GR shifts 14.4 keV gamma over a 22 m tower | ★★★★★ |

## The principle each experiment exploits

- **#1, #3:** Cosmic muons created 15 km up at γ ≈ 38 (4 GeV mean) have proper
  lifetime 2.197 µs. Without dilation, they'd travel 0.998 c × 2.197 µs = 660 m
  and never reach you. They do reach you (0.756 cm⁻²·min⁻¹ in coincidence at sea
  level), because in Earth's frame their lifetime stretches to ~84 µs — they
  travel 25 km and punch through your roof.
- **#2:** GPS satellites at ~20,200 km altitude experience SR slowing (−7 µs/day)
  and GR speeding (+45 µs/day), net +38 µs/day fast. The broadcast nav message
  carries the correction; without it, GPS would be off by ~10 km/day.
- **#4:** Move a precise clock relative to a stationary one. Special relativity
  says the moving one ticks slower by γ. Atomic-clock grade gear shows this
  directly; GPS-disciplined oscillators do it on a hobbyist budget.
- **#5:** A photon climbing a gravitational potential redshifts by `gh/c²`.
  At 22 m on Earth, that's ~2.5×10⁻¹⁵ — only detectable because the Mössbauer
  effect with Fe-57 gives you a Q ≈ 10¹² spectral line.

Every one of these is forward time dilation, the same effect, just measured at
different scales of precision.

## What about a "real" time machine?

The cheapest, highest-leverage forward-time-travel humans currently use is **a
fast jet at high altitude** — pilots accumulate small amounts of dilation
(faster motion = SR slowing; higher altitude = GR speeding, net depends on flight
profile). Astronauts on ISS accumulate roughly **−10 ms/year** vs Earth surface
(SR dominates LEO). The all-time record is Sergei Krikalev's ~20 ms.

If you're serious about *being* in the future relative to everyone else, your
choices are:
1. Spend a long time on the ISS or a future LEO station (~10 ms/year).
2. Get launched on a relativistic-flyby probe (none exist; theoretical only).
3. Find a black hole and hover (no nearby black holes; would also kill you).

There is no fourth option. There is no material, alloy, geometry, or device that
makes this cheaper. The fact-check is in the energy column of the simulator.

## Add a new experiment

Pull requests welcome. The bar for inclusion:
1. Real physics, citation to a peer-reviewed source.
2. BOM with current prices and supplier URLs.
3. Quantitative prediction so the builder knows if it worked.
4. Honest cost — don't lowball.
