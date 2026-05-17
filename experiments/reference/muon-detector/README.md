# Cosmic-ray muon detector — quantitative time dilation in a box

**Cost:** ~$100 total (CosmicWatch v3X bill of materials)
**Time to build:** weekend, with soldering
**Difficulty:** ★★★☆☆
**What it proves:** Muons are reaching your detector that *should not exist* by
their proper lifetime — they only do because time has slowed for them by a factor
of ~40. You measure the rate and confirm the dilation factor.

This is the cheapest scientifically-rigorous time-dilation experiment you can
build. It's been operated in classrooms worldwide and the design is peer-reviewed.

---

## The physics

Cosmic-ray protons hit the upper atmosphere (~15 km altitude) and shower into
secondary particles, including muons. At sea level:

| Quantity | Value | Source |
|---|---|---|
| Muon proper lifetime τ₀ | **2.1969811 ± 0.0000022 µs** | PDG 2024 |
| Mean energy at sea level | **~4 GeV** | PDG cosmic rays review |
| Muon rest mass | 105.6583755 MeV/c² | PDG |
| Implied Lorentz factor γ | E/m ≈ **38** | (4000 / 105.66) |
| Lab-frame lifetime γτ₀ | **~83 µs** | dilated |
| Distance traveled (v ≈ 0.9997c) | **~25 km** | enough to reach sea level |
| Vertical flux at sea level | ~1 cm⁻² min⁻¹ | PDG |
| Two-detector coincidence flux | **0.756 ± 0.005 cm⁻² min⁻¹** | CosmicWatch v3X paper |

**Without time dilation**, a 4 GeV muon would decay after 0.998c × 2.197 µs =
**660 m** — almost none would survive the 15 km trip. The fact that you can
*count them on your kitchen table* is direct evidence of special-relativistic
time dilation.

## What you'll measure

With **two detectors stacked vertically in coincidence**, you'll see:

- Rate roughly **0.7–0.8 muons per cm² per minute** (CosmicWatch v3X reports
  0.756 ± 0.005 over 26.9 hr at sea level, U. Delaware basement).
- Drop in rate if you put a few cm of lead between them (blocks lower-energy
  particles).
- Increase in rate at higher altitude (mountain, plane). At 9,000 m in a
  commercial aircraft, expect roughly **10–20× sea-level rate**.

The altitude-vs-rate measurement *is* the time-dilation measurement: more muons
than the 2.2 µs naive prediction survive at every altitude, and the ratio
follows `exp(−L/(γβcτ₀))`. You can back-fit γ.

## Bill of materials (CosmicWatch v3X)

Verified late 2025 / early 2026 prices. The official v3X spreadsheet
(`Purchasing_List_v3X_sa.xlsx`) is in the repo linked below.

| Part | Source | Unit price | Notes |
|---|---|---|---|
| SiPM **onsemi MicroFC-60035-SMT** (C-series) | Digikey | ~$30 | Original v3X part. Stock declining. |
| **Drop-in replacement: MICROFJ-60035-TSV-TR** (J-series) | Digikey | **$31.94** | Use this if MicroFC unavailable. |
| Plastic scintillator 5 × 5 × 1 cm (polystyrene + 1% PPO + 0.03% POPOP) | EPIC / Eljen / eBay | ~$40–80 | Eljen EJ-200 or Saint-Gobain BC-408 acceptable; quote-driven |
| Arduino Nano (clone is fine) | Amazon / eBay | ~$3–5 | ATmega328P |
| Custom PCB | JLCPCB / OSH Park (Gerbers in repo) | ~$5 for 5 boards | |
| Passives (resistors, caps, op-amp, comparator) | Mouser/Digikey | ~$5 | BOM in repo |
| Optical coupling grease / wrap | Saint-Gobain / lab supply | ~$5 | wrap scintillator in aluminized mylar |
| OLED display, optional | Adafruit | ~$10 | for standalone use |
| 3D-printed enclosure | print or order | ~$5 | STL files in repo |
| **TOTAL** | | **~$100** | Per the paper's claim |

For two-detector **coincidence** mode (which is what you need for the cleanest
muon measurement), double the SiPM + scintillator + Arduino. Call it **~$180 for
a coincidence rig**.

## References

- **Original (v2):** Axani, Frankiewicz, Conrad, "The CosmicWatch Desktop Muon
  Detector: a self-contained, pocket sized particle detector,"
  [arXiv:1801.03029](https://arxiv.org/abs/1801.03029) (2018).
- **Current (v3X):** Axani, Sarfraz, Garcia, Owens, Frankiewicz, Conrad,
  "CosmicWatch: The Desktop Muon Detector (v3X),"
  [arXiv:2508.12111](https://arxiv.org/abs/2508.12111) (August 2025).
- **Repo:** https://github.com/spenceraxani/CosmicWatch-Desktop-Muon-Detector-v3X
  — actively maintained by Spencer Axani (U. Delaware). Contains Gerbers,
  firmware, parts list, and assembly guide.

## Alternative builds (if CosmicWatch parts hard to source)

- **[MuonPi](https://github.com/MuonPi/muondetector)** — Raspberry Pi + SiPM +
  GNSS for 20 ns timestamps. Built to participate in a global coincidence
  network. Slightly more involved, slightly more capable.
- **[Myolo](https://github.com/nico-entz/Myolo)** by Nico Entz — through-hole
  components only, no SMD soldering. Good if you don't have a hot-air station.
- **[Red Pitaya muon telescope](https://physicsopenlab.org/2024/11/02/muon-decay-measurement-with-redpitaya/)**
  — uses the Red Pitaya FPGA dev board ($350). More expensive, but you also get
  a 125 MHz scope/spectrum analyzer for the price.

## Procedure to confirm time dilation quantitatively

1. **Build two detectors.** Calibrate each one's threshold using the on-board
   pulse-height discriminator until you see ~1 cm⁻² min⁻¹ singles rate.
2. **Stack them vertically**, scintillator faces touching, log coincidences for
   several hours. You should converge on **0.7–0.8 cm⁻² min⁻¹**.
3. **Take them to altitude.** Drive up a mountain (or, if you're brave, fly with
   one on a commercial flight — cabin altitude is ~2,400 m equivalent, real
   altitude is 9,000–12,000 m). Log for at least 1 hour at each elevation.
4. **Compute γ from the altitude profile.** The muon flux follows:
   `I(h) = I₀ · exp(-(h_atm - h) / (γ β c τ₀))`
   Fit your altitude/rate data to extract effective γ. You should get a number
   in the 20–50 range, consistent with the few-GeV mean muon energy.
5. **Compare to the no-dilation prediction.** If γ were 1 (no SR), the rate at
   sea level would be ~10⁻⁹ × the rate at 15 km. The actual ratio is roughly
   0.01. **You just measured time dilation.**

## Honest caveats

- The "altitude profile fit" requires a clear-sky measurement window of hours,
  ideally days. Weather and barometric pressure affect cosmic ray rates too.
- A single detector gives you a count rate; the dilation factor is inferred from
  the count rate, not measured directly. **The measurement is "more muons
  survive than naive physics predicts."**
- If you want to *directly* measure the dilated lifetime, you can build a
  three-detector telescope and tag stopping muons (the muon decay lifetime
  spectrum measured in the lab matches the proper lifetime — i.e., once they
  stop and become at rest in your scintillator, γ = 1 again).
