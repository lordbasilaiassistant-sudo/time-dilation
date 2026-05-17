# Experiments — what you can actually do

The two things one normal person with no lab and limited budget can do to
*experience* time dilation:

| # | Experiment | Cost | Time | What you get |
|---|-----------|------|------|--------------|
| 1 | [Personal time tracker (this repo, `tracker.html`)](../tracker.html) | **$0** | 0 min | Open on your phone, watch your own SR + GR dilation in real time |
| 2 | [DIY cloud chamber](cloud-chamber/) | **~$20** | 2 hours | SEE cosmic muons in your kitchen — particles that prove time dilation by *existing* |

That's the practical menu for a regular human. Pick one or both.

---

## "Why so short? You had five experiments before."

The other three (muon detector with SiPM + Arduino, Hafele-Keating with atomic
clocks, Pound-Rebka with radioactive sources) are real and well-documented, but
they require thousands of dollars, soldering, regulatory licenses, or 22 m of
vertical building. They belong in a university lab, not in *your* life.

If you ever want them anyway, they're in [`reference/`](reference/) — kept for
completeness, not as suggestions.

---

## How the two main experiments map to the physics

**Personal tracker (digital):**
- Tracks `Δτ_SR = ∫ v²/(2c²) dt` from your phone's GPS speed
- Tracks `Δτ_GR = ∫ g·h/c² dt` from your phone's GPS altitude
- Shows the running net dilation in attoseconds → microseconds
- *Best case for one day:* drive several hours at highway speed, spend a few
  hours above 300 m elevation. Expect picoseconds to nanoseconds of net
  dilation. The numbers are small but they're **your numbers**, computed from
  GPS data the satellites send you.

**Cloud chamber (physical):**
- You see straight white tracks from muons hitting your chamber at ~1 per minute
- Each muon was created ~15 km up, has proper lifetime 2.197 µs, traveling at
  0.998 c
- *Without time dilation* it would decay in 660 m and never reach you
- *With time dilation* (γ ≈ 40), it lives ~83 µs in your frame and travels 25 km
- You are watching real time dilation happen, by eye

These two are the cheapest fact-based ways for one human to engage with the
real physics. Everything else in this folder is documentation, not a TODO.
