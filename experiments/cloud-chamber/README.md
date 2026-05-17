# DIY Cloud Chamber — see time dilation in your kitchen

**Cost:** $15–20, single Walmart/Kroger trip
**Time:** 30 min setup, 10 min wait, then it runs for ~1 hour
**Difficulty:** ★☆☆☆☆ (no electronics, no soldering, no programming)
**What you get:** White streaks crossing your tank every minute or so. Each is a
cosmic muon that should not exist by its naked lifetime — it only made the trip
to your kitchen because time slowed for it by ~40×.

---

## Walmart shopping list

| Item | Where | Price |
|---|---|---|
| Clear plastic container, ~15×15 cm, ~5 cm deep (Tupperware, Snapware, fish-tank lid, glass bake dish) | kitchen aisle | **$3–5** (you may have one) |
| 99% isopropyl alcohol, 16 oz bottle | pharmacy aisle | **~$5** |
| Black felt or thick black cloth, ~30×30 cm strip | crafts aisle or scrap | **~$3** |
| Aluminum baking sheet or pie tin | kitchen aisle | **~$3** (you may have one) |
| Strong flashlight | hardware aisle (you have one) | $0 |
| **Dry ice, ~2–3 kg** | gas station, Kroger, Publix, Walmart freezer; CALL AHEAD | **$10–15** |
| Thick gloves (oven mitts work) | (you have these) | $0 |
| Black permanent marker (Sharpie) | school supplies | ~$2 |
| **TOTAL** | | **$15–25** |

Dry ice: not every store carries it. Call ahead. In US: Kroger / Publix / Safeway
usually do. Some Walmarts do. Also try a local welding/gas supply company
(cheaper, ~$1–2 per pound, but you need to bring a cooler).

## Build

1. **Cut the felt** to fit inside the lid of your container.
2. **Saturate the felt** with isopropyl alcohol — pour until it can't soak any
   more, then let the excess drip out. The felt should be wet but not pooling.
3. **Stick the felt to the lid** (tape it, or just let surface tension hold it).
4. **Paint the bottom of the container black** with the Sharpie, OR put a sheet
   of black paper at the bottom. You're looking at the floor of the chamber
   under a flashlight, and contrast is everything.
5. **Crush the dry ice flat** on the baking sheet. Aim for an even ~2 cm
   thickness layer. Wear gloves — dry ice is −78°C.
6. **Invert your container** (lid down, with the alcohol-soaked felt on the bottom
   when inverted — wait, do this carefully) so:
   - The black-painted bottom of the container is now the *top* (you'll look
     through it from above)
   - The alcohol-felt lid is now the *floor*
   - Press the alcohol-felt lid down onto the crushed dry ice
   - The container is now sealed, with cold floor + warm top + saturated alcohol
     vapor in between
7. **Wait 10 minutes** for the temperature gradient to stabilize and vapor
   saturation to build up.
8. **Turn off the lights.** Let your eyes adjust to dark for 2 minutes.
9. **Shine the flashlight horizontally** across the bottom of the chamber
   (which is now the top when inverted — ugh, this language. The point is: shine
   light parallel to the felt layer, looking down through the clear top of the
   container).
10. **Look.** Within 5 minutes you should see straight white streaks appearing
    and fading. Each streak is a particle ionizing a track that becomes alcohol
    droplets.

Easier alternative geometry: don't invert. Use the container right-side-up with
the alcohol felt taped to the lid, then sit the container on top of the dry ice
on the baking sheet. The dry ice cools the bottom of the container, the felt at
the top releases vapor downward, and the cold bottom creates the supersaturated
layer. **CERN's S'Cool LAB has photos:** https://scoollab.web.cern.ch/cloud-chamber

## What you'll see

| Track type | Source | Look |
|---|---|---|
| **Muon** (your target) | Cosmic ray, ~75% of ground radiation | Long, very straight, full chamber crossings |
| **Alpha** | Radon decay (background in any room) | Short, thick, intense |
| **Electron / beta** | Beta decay or cosmic electron | Wiggly, often curved |
| **Cosmic shower** | High-energy primary fragmenting in atmosphere | Multiple tracks from one point |

Rate at sea level: roughly **1 muon visible per minute** in a 15×15 cm chamber.
Less if you're indoors with concrete shielding above, more at altitude or near a
window.

## Why this is a time-dilation experiment

The straight tracks crossing your chamber are muons created ~15 km above your
house when cosmic ray protons hit the atmosphere. A muon's proper lifetime is
**2.197 µs** (PDG 2024 measurement, accurate to parts per million).

If muons didn't experience time dilation, at v ≈ 0.998c they'd travel
0.998 × 3×10⁸ × 2.197×10⁻⁶ = **658 m** before decay. They'd never reach you.
Almost zero should hit the ground.

But they do — by the hundreds per square meter per second.

The reason: from your frame, a 4 GeV muon (typical) has Lorentz factor
γ = E/mc² = 4000/105.7 ≈ **38**. Its lifetime in your frame is 38 × 2.197 = 83
µs. Distance traveled: 0.998c × 83 µs = **25 km**, easily making the 15 km trip.

**So when you see a straight white streak in your tank, you are seeing a
particle that has time-dilated by γ ≈ 40 to reach you.** The cloud chamber is
the cheapest, most viscerally direct time-dilation experiment one human can do
in their kitchen.

## If it doesn't work

- Not enough alcohol → felt is dry → no vapor → no tracks. Re-saturate.
- Container too cold all the way through → vapor froze out → no saturated layer.
  Wait longer for the gradient to stabilize, or reduce dry ice.
- Lights on, eyes not dark-adapted → tracks invisible. Let your eyes adjust for
  2+ minutes.
- Too much background light → bright surface reflections drown out the tracks.
  Black floor / dark room critical.

## References

- C.T.R. Wilson, "On a Method of Making Visible the Paths of Ionising
  Particles through a Gas," Proc. Roy. Soc. A 85, 285 (1911) — Nobel Prize
  1927 invention of the cloud chamber.
- PDG 2024 muon listing for τ = 2.1969811(22) µs:
  https://pdg.lbl.gov/2024/listings/rpp2024-list-muon.pdf
- PDG cosmic rays review for sea-level flux ~1 cm⁻²·min⁻¹.
- CERN S'Cool LAB cloud chamber plans:
  https://scoollab.web.cern.ch/cloud-chamber
