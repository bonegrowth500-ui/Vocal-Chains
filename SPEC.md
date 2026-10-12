# Vocal Chain Spec: Underground / Uzi-Type Lead Vocal

> **Status:** Spec locked from your 44 answers. **Waiting for your cue.** No chain files have been written yet.
> **Last updated:** 2026-10-12

---

## 1. Deliverables

Four Markdown files, each a full lead + doubles chain for one style, saved in `chains/`:

| File | Style | Identity |
|---|---|---|
| `chains/04-alien-transmission.md` | #4 Alien Transmission | Eternal Atake's sci-fi world, turned up: wide, modulated, futuristic, beamed in from orbit |
| `chains/05-rage-blowout.md` | #5 Rage Blowout | Grimy, blown-out vocal that sounds like it's screaming through the synth lead |
| `chains/06-melodic-rage-anthem.md` | #6 Melodic Rage Anthem | Huge, bright, arena-wide: the melody rides on top of the rage chaos instead of fighting it |
| `chains/09-plugg-cloud.md` | #9 Plugg Cloud | Soft, buttery, airy: the vocal melts into the beat instead of sitting on top |

---

## 2. Your setup (fixed facts)

| Item | Your answer | What it means for the chains |
|---|---|---|
| DAW | FL Studio, **Producer Edition** | FL mixer routing steps; only Producer Edition native plugins |
| Plugins | FL stock + **Auto-Tune Artist** + **full FabFilter bundle (latest)** | Nothing else: no free third-party plugins |
| Computer | Powerful | Oversampling on where it helps; several Pro-R 2 / Auto-Tune instances are fine |
| Voice | Mid-range | EQ and de-ess frequencies set for a mid-range voice |
| Mic | Lewitt LCT 440 PURE | Detailed condenser that leans bright, so every chain gets a de-esser plus dynamic harshness control |
| Room | Makeshift treatment (closet / blankets / reflection filter) | Every chain starts with a cleanup stage for boxiness and room tone |
| Recording level | Peaks −12 to −6 dBFS | Healthy; only a light trim stage is needed |
| Doubles | Copy-pasted from the lead | Every chain includes a "fake real double" recipe (see §6) |
| Beat | 2-track stereo beat | The vocal wins its space through its own EQ and level; beat carve is optional (§6) |

---

## 3. Scope

**In**
- Lead vocal chain + doubles processing. Doubles play the **whole song** in all 4 styles.
- The FX returns each style needs: reverb, delay, parallel buses, and the shimmer send.
- An FL routing walkthrough and a troubleshooting section in every file.
- An optional beat carve on the 2-track, as an add-on section.

**Out**
- Ad-libs, harmonies, background vocals, and an overall vocal bus.
- Tracking/monitoring chains. These are mix chains only; you record dry.
- Master chain or mastering (vocals only).
- Section automation map and signal-flow diagram (not selected).

---

## 4. Document format rules

| Rule | Setting |
|---|---|
| Detail | An exact value for **every** parameter, plus a one-line "why" |
| Layout | A settings table per plugin, followed by a short "Dial it in" step list |
| Extras | Troubleshooting ("if it sounds X, do Y") + FL routing walkthrough |
| Level | Intermediate: no beginner explanations, but FL-specific clicks are spelled out |
| Delay times | Tempo-synced note values + an ms reference table, since your BPM varies a lot |

---

## 5. Toolkit (verified)

Checked against Image-Line's edition comparison, FabFilter's current product list and news page, and the Auto-Tune Artist feature list and manual.

**FabFilter (latest):** Pro-Q 4, Pro-C 3, Pro-DS, Pro-G, Pro-MB, Pro-L 2, Pro-R 2, Saturn 2, Timeless 3, Volcano 3, Simplon, Micro

**Auto-Tune Artist:** Key/Scale, Retune Speed, Humanize, Flex-Tune, vibrato controls, Classic Mode, Formant correction, Throat modeling, Transpose, Detune

**FL Studio Producer Edition natives:** Fruity Parametric EQ 2, Fruity Limiter, Fruity Delay 3, Fruity Delay Bank, Multiband Delay, Fruity Reeverb 2, Fruity Convolver, Fruity Chorus, Fruity Flanger, Fruity Phaser, Fruity Stereo Shaper, Fruity Stereo Enhancer, Fruity Love Philter, Fruity Soft Clipper, Fruity Fast Dist, Fruity Blood Overdrive, Fruity WaveShaper, Fruity Squeeze, Frequency Splitter, Frequency Shifter, Maximus, Vocodex, Effector, Patcher, Edison

**Not in your kit (won't be used):**

| Missing | Needs | Replacement in your chains |
|---|---|---|
| Pitch Shifter | All Plugins Edition | Auto-Tune Artist **Transpose** (octave layers, shimmer send) |
| Gross Beat | Signature Bundle | Not needed for these 4 styles |
| Vintage Chorus / Vintage Phaser | Signature Bundle | Fruity Chorus / Fruity Phaser |
| Pitcher / NewTone | Signature Bundle | Auto-Tune Artist |
| LuxeVerb | All Plugins Edition | Pro-R 2 |
| Transient Processor | All Plugins Edition | Pro-C 3 / Pro-G |
| Xfer OTT (free) | Third-party | Pro-MB (upward + downward), Pro-C 3 Upward style, or Maximus |
| Valhalla Supermassive (free) | Third-party | Pro-R 2 + Timeless 3 |

---

## 6. Shared conventions (all 4 files)

1. **Mixer layout.** The lead sits on its own insert. Each double gets its own insert, feeding a Doubles bus. Each reverb, delay, or parallel effect lives on its own FX return insert. Ducking is done with Pro-C 3 on the FX return, sidechained from the Lead insert.
2. **Cleanup first.** For the LCT 440 PURE in a makeshift booth: trim gain → high-pass → boxiness dip → dynamic harshness control (Pro-Q 4 dynamic band) → Pro-DS. Add Edison denoise or Pro-G expansion only if room tone is audible.
3. **Chain skeleton.** Cleanup → Auto-Tune Artist → compression → tone shaping → style processing → sends. Each file changes the order where its style needs it.
4. **Making copy-pastes sound like real doubles.** Each double gets:
   - its own time offset
   - its own detune, set with Auto-Tune Artist's **Detune** on that double. Detuning *before* Auto-Tune would just get snapped back.
   - a throat/formant variation
   - its own EQ and pan

   Exact values are set per style.
5. **Throws.** Delays are always on and ducked by the dry lead, so echoes appear in the gaps automatically. No automation needed.
6. **Delay timing.** Tempo-synced note values, plus an ms table for 130–170 BPM in each file.
7. **Optional beat carve.** Pro-Q 4 on the 2-track beat, with dynamic dips in the vocal's presence range, sidechained from the Lead. It's a separate add-on section you can skip.

---

## 7. Per-style specs

The **Source** column shows who made each call. **You** = your answer. **Claude** = my call, wherever you chose "vary by style", "unsure", or "your design choice". You can veto any Claude call before giving the cue.

### #4 Alien Transmission

| Decision | Value | Source |
|---|---|---|
| FX amount | **Constant but tasteful.** FX always present, words always clear | You |
| Placement | On top and clear; the FX surround the lead rather than cover it | Claude |
| Tone | Bright and crisp, glossy top, harshness controlled | Claude |
| Tuning feel | Hard but smooth (fast retune, light Humanize) | Claude |
| Modulation | Chorus/detune on the doubles for constant width + a slow phaser on the delay return | Claude |
| Main space | Dotted-⅛ ping-pong delay (Timeless 3), always on, ducked by the lead | Claude |
| Secondary space | Quiet octave-up "shimmer" glow: Auto-Tune Artist Transpose +12 on a send → Pro-R 2 | Claude |
| Alien layer | Formant-shifted double (Auto-Tune Artist throat modeling), band-passed and blended low | Claude |
| Doubles | Chorused wide L/R pair + the alien layer | Claude (whole song: You) |

### #5 Rage Blowout

| Decision | Value | Source |
|---|---|---|
| Dirt amount | **Crunchy.** Obvious distortion, still controlled | You |
| Delivery to design for | **Mix of melodic + yelled** | You |
| Dirt flavor | Clean + dirty blend: light crunch on the lead itself + a heavier parallel crunch bus that only distorts the mids, so the lows stay tight and the highs don't fizz | Claude |
| Dynamics | Fast compression **before** the distortion, so yells don't explode and sung parts still get crunch | Claude |
| Placement | On top and cutting: the most forward of the 4 | Claude |
| Tone | Mid-forward and aggressive, top end controlled (no airy shine) | Claude |
| Tuning feel | Hard (fast retune), with Flex-Tune nudged so yells and unpitched shouts don't warble | Claude |
| Space | Short dark room + a ducked delay that blooms on line endings | Claude |
| Doubles | Tight L/R pair (about ±40–50%), dirtier and more band-limited than the lead, forming a "dirty halo" around it | Claude (whole song: You) |

### #6 Melodic Rage Anthem

| Decision | Value | Source |
|---|---|---|
| Grit | **Light warmth.** Subtle saturation for thickness | You |
| Placement | On top and clear: the melody rides over the chaos | Claude |
| Tone | Bright and airy (arena shine), harshness controlled | Claude |
| Tuning feel | Hard but smooth | Claude |
| Space | Arena-sized hall (Pro-R 2) + ¼-note ping-pong delay (Timeless 3) | Claude |
| Wet behavior | Ducked: dry and clear while you sing, the space blooms in the gaps | Claude |
| Doubles | 4-double wall: Pair A wide (±100%) + Pair B inner (about ±50%). Each pair has its own detune, offset, throat, and EQ, and both are tucked low so verses stay clear | Claude (whole song: You) |

### #9 Plugg Cloud

| Decision | Value | Source |
|---|---|---|
| Placement | Melted in: even with the beat, not on top | Claude |
| Tone | Soft and airy: warm, buttery body with a breathy, de-essed shimmer on top | Claude |
| Tuning feel | Smooth hard tune (fast retune with Humanize) | Claude |
| Compression | Gentle and smooth (opto-style) | Claude |
| Delay | Long ¼-note echoes with the highs rolled off and a slight tape-style wobble (Timeless 3), sitting behind the beat | Claude |
| Reverb | Medium soft plate, darkened (about 2 s), supporting the delays | Claude |
| Width | Medium dreamy: mostly centered lead, chorused L/R doubles | Claude |
| Doubles | Chorused L/R pair, tucked low | Claude (whole song: You) |

---

## 8. Answer log (all 44)

| # | Batch | Question | Answer |
|---|---|---|---|
| 1 | Setup | DAW | FL Studio |
| 2 | Setup | Plugins | FL Studio stock + Auto-Tune Artist + all FabFilter plugins |
| 3 | Setup | Pitch correction | Auto-Tune Artist (stated in Q2) |
| 4 | Setup | Natural voice | Mid-range |
| 5 | Plugins | FL edition | Producer |
| 6 | Plugins | Free plugins | Only what I own |
| 7 | Plugins | Computer | Powerful |
| 8 | Plugins | FabFilter versions | Latest |
| 9 | Recording | Mic | Lewitt LCT 440 PURE |
| 10 | Recording | Room | Makeshift treatment |
| 11 | Recording | Raw level | Peaks −12 to −6 dBFS |
| 12 | Recording | Doubles method | Copy-paste the lead |
| 13 | Scope | Coverage | Lead + doubles |
| 14 | Scope | Tracking chain | No, mix chains only |
| 15 | Scope | Mixing against | 2-track beat |
| 16 | Scope | Beyond vocals | Vocals only |
| 17 | Format | Detail | Every knob + short why |
| 18 | Format | Layout | Tables + steps |
| 19 | Format | Extras | Troubleshooting, FL routing walkthrough |
| 20 | Format | Level | Intermediate |
| 21 | Taste | Overall tone | Unsure → Claude's call per style |
| 22 | Taste | Placement vs beat | Vary by style |
| 23 | Taste | Auto-Tune feel | Vary by style |
| 24 | Taste | Doubles usage | Vary by style |
| 25 | #4 Alien | FX amount | Constant but tasteful |
| 26 | #4 Alien | Modulation | Your design choice |
| 27 | #4 Alien | Main space | Your design choice |
| 28 | #4 Alien | Alien layer | Your design choice |
| 29 | #5 Rage | Dirt amount | Crunchy |
| 30 | #5 Rage | Dirt flavor | Your design choice |
| 31 | #5 Rage | Delivery | Mix of melodic + yelled |
| 32 | #5 Rage | Space | Your design choice |
| 33 | #6 Anthem | Space size | Your design choice |
| 34 | #6 Anthem | Wet behavior | Your design choice |
| 35 | #6 Anthem | Hook stack | Your design choice |
| 36 | #6 Anthem | Grit | Light warmth |
| 37 | #9 Plugg | Tone | Your design choice |
| 38 | #9 Plugg | Delay | Your design choice |
| 39 | #9 Plugg | Width | Your design choice |
| 40 | #9 Plugg | Reverb | Your design choice |
| 41 | Finishing | Beat carve | Optional section |
| 42 | Finishing | Delay throws | Your design choice → always on + ducked |
| 43 | Finishing | Where doubles play | Whole song |
| 44 | Finishing | Typical BPM | Varies a lot → delay-time table |

---

## 9. Assumptions (say the word to change any before the cue)

- FL Studio 2024 or newer. Any recent version with the Producer Edition natives works.
- FabFilter **Pro-C 3**, since you said "latest". Tell me if you're still on Pro-C 2.
- Auto-Tune Artist runs in Auto mode, with Key/Scale set per song (Chromatic as a fallback).
- Doubles sit on separate mixer inserts, not stacked on the lead's insert.
- Reverbs and delays run as send effects on FX return inserts, not on the lead insert.
- Wherever a trick would normally use FL's Pitch Shifter, Auto-Tune Artist's Transpose is used instead.

---

## 10. Next step

Say **"start"**, or change anything above first. I'll then write the 4 chain files into `chains/`.

---

<sub>Toolkit sources: [Image-Line edition comparison](https://www.image-line.com/flstudio/compare) · [FabFilter products](https://www.fabfilter.com/products) · [FabFilter Pro-C 3 release](https://www.fabfilter.com/news/1768435200/fabfilter-releases-pro-c-3-compressor-plug-in) · [Auto-Tune Artist overview (Gearnews)](https://www.gearnews.com/antares-releases-auto-tune-artist-for-real-time-pitch-correction/) · [Auto-Tune Artist manual](https://www.barryrudolph.com/recall/manuals/auto-tune_artist.pdf)</sub>
