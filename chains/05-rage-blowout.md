# Rage Blowout (#5): Lead + Doubles Vocal Chain

> *Grimy, blown-out vocal that sounds like it's screaming through the synth lead.*

**What this chain does**
- Makes your lead crunchy: obvious distortion that stays controlled. It's built for a mix of melodic and yelled delivery.
- Clamps your level with fast compression **before** the distortion, so yells don't explode and sung parts still get crunch.
- Blends clean and dirty: a light crunch on the lead itself, plus a heavier parallel crunch bus that only distorts the mids. The lows stay tight and the highs don't fizz.
- Sits on top and cutting: a forward placement, level with the beat. It's mid-forward and aggressive, with the top end controlled (no airy shine).
- Tunes hard, with Flex-Tune nudged so yells and unpitched shouts don't warble.
- Adds a short dark room plus a ducked delay that blooms on line endings, and a tight, dirty pair of doubles that forms a "halo" around the lead for the whole song.

**You'll use:** FL Studio 2024 or newer (Producer Edition) · Auto-Tune Artist · FabFilter Pro-Q 4, Pro-C 3, Pro-DS, Saturn 2, Pro-R 2, Timeless 3, and Pro-L 2 (as a meter only). Only if your booth is noisy: Edison and FabFilter Pro-G.

**Written for:** a mid-range voice on a Lewitt LCT 440 PURE in a makeshift booth, raw takes peaking around −12 to −6 dBFS, and a 2-track beat. "Your mic" in this file means the LCT 440 PURE.

**Contents:** 1. Session setup and routing · 2. Lead chain · 3. Doubles · 4. FX returns · 5. Delay and pre-delay times · 6. Final balance · 7. Optional: carve the beat · 8. Troubleshooting

---

## 1. Session setup and routing

### 1.1 How to enter exact values

| Where | How |
|---|---|
| FabFilter knobs | Double-click the knob, type the number, press Enter. A plain number sets the value in the knob's own unit: "30" on a % knob is 30%, "-24" on a dB knob is −24 dB. "1k" = 1000 Hz. Ctrl-click resets a knob. |
| FabFilter knobs with no published unit | Type a percentage with the % sign, like "22%". That puts the knob exactly 22% of the way through its travel. This file only does this where it says "typed travel". |
| FabFilter EQ bands and filters | Double-click the band's dot, then type Frequency, press Tab, type Gain, press Tab, type Q. Cut bands have no Gain: type Frequency, then Tab to Q. Ctrl+Alt-click a dot to change its shape. Alt+Shift-click a dot to change its slope. |
| Auto-Tune Artist | Drag each control until its readout shows the value. |
| FL mixer (fader, pan, send level) | Right-click → "Type in value". In the entry box, pick the context-aware unit (dB for faders and send knobs, % for pan), not the normalized one, then type the value. |
| On a Mac | Use Cmd where this file says Ctrl, and Option where it says Alt. |

### 1.2 Mixer map

| Insert | Name | What's on it | Pan | Track delay | Routes to |
|---|---|---|---|---|---|
| 1 | BEAT | Optional carve (section 7) | 0% | — | Master |
| 2 | LEAD | L1–L7 (section 2) | 0% | — | Master + sends to 6, 7, and 8 (the send to 8 also keys its ducker) (+ a sidechain link to 1 if you do section 7) |
| 3 | DBL L | D1, D2 | −45% | 12 ms | 5 only |
| 4 | DBL R | D1, D2 | +45% | 19 ms | 5 only |
| 5 | DBL BUS | B1–B6 | 0% | — | Master |
| 6 | FX CRUNCH | R6.1–R6.3 | 0% | — | Master |
| 7 | FX ROOM | R7.1 | 0% | — | Master |
| 8 | FX DELAY | R8.1–R8.2 | 0% | — | Master |

Every insert's stereo separation knob stays at centre (off). Faders: BEAT is set in 1.3, the doubles in 3.2, FX CRUNCH in 4.1, everything else in section 6.

### 1.3 Build the session

1. Open the Mixer menu → "Plugin delay compensation" → make sure **"Automatic"** is ticked. It keeps every insert in time, including sends and sidechains.
2. Put the beat on its own playlist track. In its channel settings, set **TRACK** to **1**. Put your lead take on another playlist track, with TRACK set to **2**. Then set FL's project tempo to the beat's BPM: every synced delay in this file follows it.
3. Name inserts 1–8 as in the map. Right-click each insert → "Rename, color & icon..." (F2).
4. **Beat headroom.** Load Pro-L 2 in BEAT's first slot with the meter settings from 1.5 (TP metering on), and play the beat's loudest part. Read the maximum true peak shown above its output meter. Set the BEAT fader to **−6.0 dB minus that reading** (a peak of −0.4 dB gives −5.6 dB), so the beat peaks at about −6.0 dBFS. Then remove the meter.
5. Run the L2a **Test** now. If you hear room tone, do L2a Part 1 (Edison) now, **before** you make the doubles, so every copy is clean. Part 2 (Pro-G) goes in later with the lead chain.
6. Make the doubles (section 3.1).
7. Do the routing in 1.4, then calibrate in 1.5.

### 1.4 Routing walkthrough

1. **Doubles go to DBL BUS only.** Select insert 3 (DBL L). Left-click the send switch (the arrow at the bottom) of insert 5 (DBL BUS). Then left-click the **Master** track's send switch to turn that route off. Repeat for insert 4.
2. **LEAD sends.** Select insert 2 (LEAD) and left-click the send switches of inserts 6, 7, and 8. With LEAD still selected, right-click each new send knob (it sits on the destination's send switch) → "Type in value": insert 6 = **0.0 dB**, insert 7 = **−13.0 dB**, insert 8 = **−12.0 dB**. LEAD keeps its Master route. FL sends are post-fader, so the effects follow your LEAD fader.
3. **The delay ducking needs no extra link.** In FL, every send also carries a sidechain feed, so the LEAD send to insert 8 from step 2 already lets its ducker hear your voice. Don't use "Sidechain to this track" on that send: that option turns a send into a sidechain-only link (its level drops to 0): the ducker could still hear your voice, but no audio would reach the delay. The crunch bus and the room are **not** ducked.
4. **Pans and Track delays.** Right-click each pan knob → "Type in value": insert 3 = −45%, insert 4 = +45%. On each double's insert, click the clock icon (**Track delay**) → "Set in ms (milliseconds)": insert 3 = **12**, insert 4 = **19**.
5. **Feed the ducker.** When you load Pro-C 3 on insert 8 (R8.2), open its gear icon → **"Plugin Wrapper Settings"** → **"Processing"** → **"Connections"**. Right-click the plugin's sidechain input number and choose insert 2 (LEAD), or click **"Auto map inputs"**. Then, in Pro-C 3, set **Side Chain Input** to **External**.
6. DBL BUS and all three returns stay routed to Master (the default).

**Soloing for the checks.** A plain solo (right-click a track's mute switch) plays that track alone. Where a check in this file says **Alt-solo**, Alt+left-click the mute switch instead: FL then solos the track together with every track routed to and from it, so a bus or return still hears what feeds it. To undo any solo, Ctrl+right-click any mute switch (this unmutes everything).

### 1.5 Calibrate your take (find T)

Load **Pro-L 2** temporarily in LEAD's first slot, above everything else, with these settings. It only measures; nothing gets limited.

| Parameter | Setting | Why |
|---|---|---|
| Gain | 0.0 dB | No level change |
| Output Level | 0.0 dB | With True Peak Limiting off, nothing below 0 dBFS gets limited |
| True Peak Limiting | off | Keeps Pro-L 2 transparent (FabFilter's meter-only setup) |
| Oversampling | Off | Transparent setup |
| Dither | Off | No added noise |
| DC (DC offset filter) | off | Leaves the signal untouched |
| Unity Gain (1:1) | off | Not needed with Gain at 0 dB |
| Audition Limiting | off | You want to hear the vocal, not the difference signal |
| Style | Transparent | Not used here; nothing is being limited |
| Lookahead / Attack / Release / Channel Linking | Minimum / minimum / minimum / 100% | Not used here; nothing is being limited |
| Meter Scale | Loudness | Shows the LUFS readouts |
| Loudness time scale | Integrated | Measures the whole take |
| TP metering | on | Display only |

**Dial it in**
1. Click the loudness reset button, then play your whole lead take from start to finish (a full-song take, not one phrase).
2. Read the **Integrated** loudness, for example −23.0 LUFS.
3. Work out **T = −20.0 − reading**. For example, −20.0 − (−23.0) = **+3.0 dB**. You'll type T into L1 and use it again on DBL BUS.
4. Remove Pro-L 2 from LEAD. Keep these settings handy; you'll use the same meter again in section 6.

---

## 2. Lead chain (insert 2)

| Order | Slot | Plugin | Job |
|---|---|---|---|
| 1 | L1 | Pro-Q 4 | Trim to the calibrated level |
| 2 | L2 | Pro-Q 4 | Cleanup: rumble, booth boxiness, harshness |
| (only if needed) | L2a | Edison (offline) + Pro-G | Room-tone cleanup |
| 3 | L3 | Pro-DS | De-ess |
| 4 | L4 | Auto-Tune Artist | Tune: hard, without warbling on yells |
| 5 | L5 | Pro-C 3 | Fast level control **before** the distortion |
| 6 | L6 | Saturn 2 | Light crunch on the lead itself |
| 7 | L7 | Pro-Q 4 | Tone, placed **after** the distortion so it can also tame the fizz the crunch creates |

There's no second de-esser in this chain. L7 cuts the top instead of boosting it.

### L1 · Pro-Q 4 · trim

| Parameter | Setting | Why |
|---|---|---|
| Bands | None | This instance only sets level |
| Output Gain | **T** (from 1.5), e.g. +3.0 dB | Puts every take at −20 LUFS so every threshold and drive below works as written |
| Processing Mode | Zero Latency | No bands to process, so no latency needed |
| Character | Clean | Grit comes from Saturn 2, where you can control it |
| Output Pan | Centre (L/R mode) | Keeps the mono vocal centred |
| Auto Gain | Off | It would fight the trim |
| Gain Scale | 100% (type 100) | Neutral |
| Phase Invert (Ø) | Off | Keeps polarity |

**Dial it in**
1. Load Pro-Q 4 in LEAD's first slot.
2. Double-click Output Gain and type your T.
3. Optional check: put the Pro-L 2 meter right after L1 and replay the take. Integrated should read **−20.0 LUFS (±0.5)**. Then remove the meter.

### L2 · Pro-Q 4 · cleanup

| Band | Shape | Frequency | Gain | Q | Slope | Placement | Dynamic | Why |
|---|---|---|---|---|---|---|---|---|
| 1 | Low Cut | 85 Hz | — | 1.0 | 18 dB/oct | Stereo | Off (static) | Removes rumble and handling noise below a mid-range voice. The LCT 440 PURE has no low-cut of its own |
| 2 | Bell | 320 Hz | −2.5 dB | 1.2 | 12 dB/oct | Stereo | Off (static) | Takes out the boxy sound a makeshift booth adds |
| 3 | Bell | 4.2 kHz | 0.0 dB | 2.0 | 12 dB/oct | Stereo | **Range −4.0 dB** | Dips only when that note gets harsh. Your mic has a +3.5 dB presence bump near 4 kHz |

| Band 3 dynamics | Setting | Why |
|---|---|---|
| Threshold | **A** (auto) | Follows your level, so it only reacts to harsh peaks |
| A (attack) | 50% (type 50) | 50% = automatic attack |
| R (release) | 50% (type 50) | 50% = automatic release |
| Triggering | Band | Reacts to the 4.2 kHz region itself |
| External side chain | Off | Triggered by the vocal itself |
| Spectral | Off | Spectral mode adds about 100 ms of latency; not needed |

| Globals | Setting | Why |
|---|---|---|
| Processing Mode | Zero Latency | No added latency |
| Character | Clean | Grit is controlled in Saturn 2 |
| Output Gain | 0.0 dB | Level is already set by L1 |
| Output Pan | Centre (L/R mode) | Mono vocal stays centred |
| Auto Gain | Off | Keeps levels predictable |
| Gain Scale | 100% (type 100) | Bands at their stated gain |
| Phase Invert (Ø) | Off | Keeps polarity |

**Dial it in**
1. Double-click the far left of the display to create a Low Cut. Double-click its dot, type 85, Tab to Q and type 1, then set the slope to 18 dB/oct (Alt+Shift-click the dot to step through slopes).
2. Click the display around 300 Hz to add a bell. Double-click its dot and type 320, Tab, −2.5, Tab, 1.2.
3. Click the display around 4 kHz to add another bell. Double-click its dot and type 4.2k, Tab, 0, Tab, 2. Drag the dynamic range ring around its GAIN knob down to **−4.0 dB**. Click **expand >>** to open the band's dynamics panel. Click the threshold's **A** (auto) button, then type 50 into the attack (A) and release (R) fields (50% = automatic).
4. Play the loudest, brightest lines. Band 3 should dip **0–3 dB on harsh notes only** and stay still on soft lines.

### L2a · only if room tone is audible

**Test:** Solo LEAD (right-click its mute switch) and play a gap between phrases at your normal listening level. If you hear booth hiss, hum, or room tone, do both parts below. If not, skip L2a. If you already ran this Test in 1.3, keep that answer: don't re-test after Edison. Distortion brings up quiet noise, so take this test seriously in this chain.

**Part 1: Edison (offline, before you copy the doubles).** Skip this part if you already did it in 1.3. If you made the doubles without doing it first, delete them now and make them again in 3.1 afterwards. Open the lead clip's menu (top-left corner of the clip) → **"Edit sample"** (E). Edison opens with your take.
1. Drag across a few hundred milliseconds where you're not singing (the longest noise-only stretch you can find). Choose Tools > Spectral > **"Aquire noise profile"** (Alt+U; that's FL's own spelling).
2. Press the **Up arrow** (Select > "Deselect") so nothing is selected. With no selection, the cleanup processes the whole take.
3. Open **"Clean up (denoise)"** (Ctrl+U) and make sure its **Denoiser** button is on.

| Control | Setting | Why |
|---|---|---|
| Threshold (Windows) | 0 dB | Image-Line's suggested default |
| Smoothing (macOS, in place of Threshold) | As it opens | Only needed to smooth artifacts at high Amount settings |
| Amount | 10 dB (read it on the hint bar) | Image-Line advises only as much as needed, and less for a mix. Pro-G handles the gaps |
| Output noise only | Turn on to check, then off | Lets you hear exactly what's being removed. It should be hiss, not words |

4. Click **Preview**, check, then click **Accept**.
5. Play a gap in the lead clip: the hiss should be gone. If it isn't, select the lead's Audio Clip channel in the Channel rack and right-click Edison's **Send sample to Playlist** button. That replaces the selected Audio Clip with the cleaned take.

**Part 2: Pro-G**, placed between L2 and L3.

| Parameter | Setting | Why |
|---|---|---|
| Style | Vocal | Gating behaviour made for vocals |
| THRESHOLD | −50 dB | Above the room tone, well below your softest syllables at the calibrated level |
| RATIO | 2.0:1 | Gentle downward expansion, not a hard gate |
| RANGE | 10 dB | Lowers the gaps by at most 10 dB, so it never sounds chopped |
| ATTACK | 1 ms | Opens instantly when you start a word |
| HOLD | 60 ms | Stays open through short pauses between words |
| RELEASE | 180 ms | Closes smoothly after phrase endings |
| KNEE | 6 dB | Soft transition |
| LOOKAHEAD | On, 2 ms | Catches word onsets so first consonants aren't clipped |
| Expert | Off | 100% wet, internal side chain, no side-chain filtering, which is what you want here |
| Oversampling | 2x | Cleaner gain changes |
| In: / Out: | 0.0 dB / 0.0 dB, pan centre | Unity |

**Dial it in:** Play a gap. The gain-reduction meter should show up to **10 dB** in the gaps and **0 dB** while you sing. If you use L2a, also add the identical Pro-G on DBL BUS (B2a, section 3.5).

### L3 · Pro-DS · de-ess

| Parameter | Setting | Why |
|---|---|---|
| MODE | Single Vocal | Built for a solo vocal |
| WIDE BAND / SPLIT BAND | WIDE BAND | Gentler on a lead. Split Band is linear-phase and adds latency |
| THRESHOLD | −26.0 dB | Triggers on esses at the calibrated level |
| RANGE | 6.0 dB | Never removes more than 6 dB, so esses stay natural |
| HP (trigger filter) | 5.5 kHz | Listens above your mic's 4 kHz bump |
| LP (trigger filter) | 11.0 kHz | Stops below the mic's 12–13 kHz air peak, so air isn't mistaken for esses |
| LOOKAHEAD | On, 10 ms | FabFilter's suggestion for vocals: catches the start of each ess |
| STEREO LINK | 100% (the "100%" mark at the top of the scale) | Fully linked; the vocal is mono anyway |
| SIDE CHAIN | In (not Ext) | Triggered by the vocal itself |
| Audition Triggering / Audition | Off / Off | Monitoring only |
| Oversampling | 2x | Cleaner gain changes |
| In: / Out: | 0.0 dB / 0.0 dB, pan centre | Unity |

**Dial it in:** Loop a line with lots of s/sh/t. The gain-reduction readout should show **3–6 dB on esses** and about **0 dB** elsewhere. De-essing before the crunch matters here: distortion makes esses spit.

### L4 · Auto-Tune Artist · tune

| Parameter | Setting | Why |
|---|---|---|
| INPUT TYPE | Alto/Tenor | Matches your mid-range voice |
| KEY / SCALE | Your song's key and scale (Chromatic if you don't know it) | Gives Auto-Tune the right target notes |
| CLASSIC | Off | Classic would switch off Flex-Tune, which this chain needs |
| FORMANT | Off | No pitch shift on the lead, so no formant correction needed |
| THROAT | 100 (inactive while FORMANT is off) | Neutral |
| TRANSPOSE | 0 | No pitch shift |
| DETUNE | 0 c | Standard A = 440 Hz tuning |
| TRACKING | 50 | Manual's standard pitch-detection setting |
| RETUNE SPEED | **2 ms** | Hard: sung notes snap to pitch |
| FLEX-TUNE | **15** | Only corrects as you approach a note, so yells and unpitched shouts pass through without warbling |
| HUMANIZE | **0** | Hard tune: no softening of held notes |
| NATURAL VIBRATO | 0.0 | Leaves your natural vibrato as it is |
| Advanced view: SHAPE | No Vibrato | No artificial vibrato |
| RATE / ONSET DELAY / ONSET RATE / VARIATION | 5.0 Hz / 0 ms / 0 ms / 0 | Inactive with No Vibrato |
| PITCH.AMT. / AMPLITUDE AMT. / FORMANT AMT. | 0 / 0 / 0 | Nothing changes even if SHAPE is touched by mistake |
| TARGETING IGNORES VIBRATO | Off | Plain target detection |
| Keyboard | No notes removed or bypassed | All scale notes stay available |
| MIDI: TARGET NOTES / LEARN SCALE | Off / Off | Not used |
| Settings (gear): Use Low Latency | Off | Highest-quality processing for mixing |
| Settings: Enable Auto-Key Detection | Off | Not used: KEY and SCALE are set by hand |
| Settings: Detune Display | Cents | Matches the values in this file |
| Settings: Select Pitch Reference | Either channel | Your vocal is mono, so both channels are identical |

**Dial it in**
1. Set KEY and SCALE to the beat's key.
2. Play a sung part: notes should snap hard to pitch. Play a yelled part: it should come through raw, without a robotic warble.
3. If a note jumps to the wrong pitch, your key or scale is off. Fix that first.

### L5 · Pro-C 3 · fast level control before the dirt

| Parameter | Setting | Why |
|---|---|---|
| Style | **Punch** | Traditional, analog-like compression: aggressive and in your face |
| THRESHOLD | −24 dB | Sung lines get 3–6 dB of reduction; yells get much more |
| AUTO (threshold) | Off | A fixed threshold makes the readings predictable |
| Audition Triggering | Off | Monitoring only |
| RATIO | **6.0:1** | Clamps yells hard, so they don't explode into the distortion |
| KNEE | 6 dB | Firm onset |
| RANGE | 30 dB | Room for big yells |
| Character | Off | Grit comes from Saturn 2 next |
| DRIVE / POST | Inactive (Character Off) / Post | Character is off |
| ATTACK | **1.0 ms** | Fast enough to catch the front of a yell |
| RELEASE | **60 ms** | Recovers quickly, so sung parts stay up and keep their crunch |
| AUTO (release) | Off | Fixed, predictable release |
| LOOKAHEAD | 0 ms (bottom-bar Lookahead: Off) | The 1 ms attack does the job |
| HOLD | 0 ms | No hold needed |
| GAIN | **+5.0 dB** | Makes up the reduction and drives L6 consistently |
| AUTO (gain) / GAIN pan ring | Off / centre | Manual, predictable makeup |
| DRY | 0% (typed travel, fully off) | No parallel blend here (that's FX CRUNCH's job) |
| Side Chain Input | Internal | Triggered by the vocal itself |
| LEVEL (side chain) / Audition | 0.0 dB / Off | Unity trigger level |
| STEREO LINK | 100% (scale mark) | Fully linked |
| Side-chain EQ | No active bands (Alt-click any band to bypass it) | Full-range detection |
| Oversampling | 2x | Cleaner gain changes |
| Input / Output | 0.0 dB / 0.0 dB, centre | Unity |
| Mix | 100% (type 100) | Full effect |

**Dial it in**
1. Play a sung section. The gain-reduction meter should show **3–6 dB**.
2. Play a yelled section. It should show **8–14 dB**, and the yells should come out only a little louder than the singing.
3. If the yells still jump out, see Troubleshooting.

### L6 · Saturn 2 · light crunch

| Parameter | Setting | Why |
|---|---|---|
| Bands | 1 (no crossovers) | The whole lead gets the same light crunch |
| Style | **British Rock** (in the **Amp** section of the Style menu) | A light amp crunch rather than warm tape |
| DRIVE | **22%** (typed travel) | Obvious grit that stays controlled |
| DRIVE pan ring | Centre | Even on both channels |
| MIX (band) | 100% (typed travel) | The full crunch on the lead; the heavy parallel crunch is FX CRUNCH |
| FEEDBACK | 0% (typed travel) | No feedback colouring |
| FREQ | 1k (inactive at FEEDBACK 0%) | Feedback is off |
| DYNAMICS | Centre: Ctrl-click to reset, pointer at 12 o'clock | Neutral (no extra pumping) |
| TONE (four sliders: bass, mid, treble, presence) | Centre: Ctrl-click each to reset | Flat. The tone is shaped in L7 instead |
| LEVEL | **−3.0 dB** | Offsets the loudness the drive adds, so bypass sounds the same level |
| LEVEL pan ring | Centre | Balanced |
| Band power | On | The band is active |
| Input / Output (global) | 0.0 dB / 0.0 dB | Unity |
| Mix (global) | 100% (type 100) | Full effect |
| High Quality | Good | Oversampled distortion: less harsh aliasing |
| Linear Phase | Off | One band, so no crossovers to correct |
| Channel Mode | Stereo | Normal |
| FB (unrestricted feedback) | Off | Safe |
| Modulation | None (no sources added) | Steady crunch |

**Dial it in**
1. The lead should sound clearly driven, but every word should stay readable.
2. Check the level with the Pro-L 2 meter (settings from 1.5) right after L6: reset it and play the same loud 8 bars with L6 on, then reset and play them again with L6 bypassed. The two Integrated readings should be within about **1 dB**. If not, adjust LEVEL in 0.5 dB steps. Remove the meter.

### L7 · Pro-Q 4 · tone (after the dirt)

| Band | Shape | Frequency | Gain | Q | Slope | Placement | Why |
|---|---|---|---|---|---|---|---|
| 1 | Bell | 180 Hz | −1.5 dB | 0.9 | 12 dB/oct | Stereo | Tightens the low-mids the crunch thickens |
| 2 | Bell | 1.3 kHz | **+2.5 dB** | 0.8 | 12 dB/oct | Stereo | Mid-forward bite: the "screaming through the synth" zone |
| 3 | High Shelf | 9.0 kHz | **−2.5 dB** | 1.0 | 12 dB/oct | Stereo | No airy shine. Counters your mic's +5 dB air peak and the crunch's top end |
| 4 | High Cut | 16 kHz | — | 1.0 | 12 dB/oct | Stereo | Removes distortion fizz above the useful range |

All four bands are static. Globals as in L2: Zero Latency · Clean · Output Gain 0.0 dB · Output Pan centre · Auto Gain off · Gain Scale 100% · Phase Invert off.

**Dial it in:** A/B with bypass. With the EQ on, the lead should sound more aggressive and forward, and less fizzy and shiny.

---

## 3. Doubles (inserts 3–5)

### 3.1 Make the copies

If you already made the copies in 1.3, skip to 3.2.

1. Hold Shift and drag the lead clip straight down onto an empty playlist track. Drop it at exactly the same start position. The playlist snaps to the grid, so drop it in the same grid spot. All timing offsets come from Track delay, never from clip position.
2. Open the copy's clip menu (top-left corner of the clip) → **"Make unique"**. Don't use "Make unique as sample".
3. In the new channel's settings, set **TRACK** to the double's insert (3 or 4).
4. Repeat until you have two copies: DBL L (3) and DBL R (4).
5. Zoom in on the starts: all three clips (lead + 2 doubles) must begin at the same point. If one doesn't, turn snapping off (the magnet icon in the playlist toolbar) and drag it into line.

### 3.2 Mixer settings

Pans and Track delays were set in 1.4. The faders are new here.

| Insert | Pan | Fader | Track delay | Route | Why |
|---|---|---|---|---|---|
| 3 DBL L | −45% | 0.0 dB | 12 ms | DBL BUS only | Tight left side of the halo; its own offset makes it sound like a separate take |
| 4 DBL R | +45% | 0.0 dB | 19 ms | DBL BUS only | Tight right side; a different offset from DBL L |

### 3.3 D1 · Auto-Tune Artist on each double

| Parameter | DBL L | DBL R | Why |
|---|---|---|---|
| INPUT TYPE | Alto/Tenor | Alto/Tenor | Mid-range voice |
| KEY / SCALE | Same as L4 | Same as L4 | Same target notes as the lead |
| CLASSIC | Off | Off | Classic would disable Formant, Throat, and Flex-Tune |
| FORMANT | **On** | **On** | Needed for THROAT to work |
| THROAT | **103** | **97** | Small throat variations make the copies sound like different takes |
| TRANSPOSE | 0 | 0 | Same pitch as the lead |
| DETUNE | **+6 c** | **−7 c** | Each copy sits slightly off the lead's pitch. That's what makes copies sound like real doubles |
| TRACKING | 50 | 50 | Standard |
| RETUNE SPEED | 4 ms | 6 ms | Hard, but a little different from the lead (2 ms) |
| FLEX-TUNE | 15 | 15 | Same yell handling as the lead |
| HUMANIZE | 0 | 5 | Different holds per copy |
| NATURAL VIBRATO | 0.0 | 0.0 | Untouched |
| Vibrato (Advanced view) | As L4 (No Vibrato, amounts 0) | As L4 | No artificial vibrato |
| TARGETING IGNORES VIBRATO / keyboard / MIDI | As L4 | As L4 | Same as the lead |
| Settings | As L4 (Use Low Latency off, Detune Display Cents) | As L4 | Highest quality |

### 3.4 D2 · Pro-Q 4 on each double

**DBL L**

| Band | Shape | Frequency | Gain | Q | Slope | Placement | Why |
|---|---|---|---|---|---|---|---|
| 1 | Low Cut | 220 Hz | — | 1.0 | 24 dB/oct | Stereo | Band-limited: keeps the halo out of the lead's low end |
| 2 | High Cut | 6.0 kHz | — | 1.0 | 24 dB/oct | Stereo | Band-limited: no fizz on the doubles |
| 3 | Bell | 1.1 kHz | +1.5 dB | 1.0 | 12 dB/oct | Stereo | Mid-forward colour for this side |

**DBL R**

| Band | Shape | Frequency | Gain | Q | Slope | Placement | Why |
|---|---|---|---|---|---|---|---|
| 1 | Low Cut | 250 Hz | — | 1.0 | 24 dB/oct | Stereo | A different low corner from DBL L |
| 2 | High Cut | 5.5 kHz | — | 1.0 | 24 dB/oct | Stereo | A different high corner from DBL L |
| 3 | Bell | 1.6 kHz | +1.5 dB | 1.0 | 12 dB/oct | Stereo | A different mid colour from DBL L |

Globals on both D2s: Zero Latency · Clean · Output Gain 0.0 dB · Output Pan centre · Auto Gain off · Gain Scale 100% · Phase Invert off.

**Dial it in (D1 and D2)**
1. Alt-solo each double in turn (it plays through DBL BUS). It should follow your delivery, tuned like the lead, and yells should pass without warbling.
2. Compare them. DBL L and DBL R should sound like two slightly different, band-limited singers (THROAT and the D2 cuts), each a few cents off the lead (DETUNE).
3. Check each D1's DETUNE readout against the table (+6 c, −7 c). When you're done, unsolo (Ctrl+right-click any mute switch).

### 3.5 DBL BUS (insert 5)

| Order | Slot | Plugin | Settings |
|---|---|---|---|
| 1 | B1 | Pro-Q 4 trim | As L1, but Output Gain = **T − 1.5 dB**. Cancels the extra level of the two doubles summing, so B4 and B5 see the same level as L5 and L6. It's a starting point: do Dial it in step 1 right after loading B1, before B2 |
| 2 | B2 | Pro-Q 4 cleanup | L2's bands 2 and 3 only (Bell 320 Hz −2.5 dB Q 1.2; dynamic Bell 4.2 kHz, Range −4.0 dB, Threshold A, A/R 50%), with L2's globals. No Low Cut: each D2 already cuts higher |
| (only if L2a used) | B2a | Pro-G | Identical to L2a's Pro-G |
| 3 | B3 | Pro-DS | Identical to L3 |
| 4 | B4 | Pro-C 3 | Identical to L5 (Punch, −24 dB, 6.0:1, 1.0 ms / 60 ms, GAIN +5.0 dB). Clamps the doubles' yells before their dirt |
| 5 | B5 | Saturn 2 | Table below |
| 6 | B6 | Pro-Q 4 | Table below |

**B5 · Saturn 2** (same as L6 except where marked)

| Parameter | Setting | Why |
|---|---|---|
| Style | **Crunchy Amp** (in the **Amp** section of the Style menu) | Dirtier than the lead's British Rock: the "dirty halo" |
| DRIVE | **45%** (typed travel) | Clearly dirtier than the lead (22%) |
| LEVEL | **−5.0 dB** | Offsets the louder drive |
| All other parameters | As L6 (1 band, MIX 100%, FEEDBACK 0%, FREQ 1k, DYNAMICS centre, TONE flat, pans centre, High Quality Good, Linear Phase off, Stereo, FB off, no modulation) | Same clean setup around a dirtier style |

**B6 · Pro-Q 4 · band-limit after the dirt**

| Band | Shape | Frequency | Gain | Q | Slope | Placement | Why |
|---|---|---|---|---|---|---|---|
| 1 | Low Cut | 250 Hz | — | 1.0 | 12 dB/oct | Stereo | Keeps the distorted doubles out of the low end |
| 2 | High Cut | 5.0 kHz | — | 1.0 | 24 dB/oct | Stereo | Removes the fizz the crunch adds; more band-limited than the lead |

Globals: Zero Latency · Clean · Output Gain 0.0 dB · Output Pan centre · Auto Gain off · Gain Scale 100% · Phase Invert off.

**Dial it in (DBL BUS)**
1. **Check the bus level right after you load B1**, before B2 and the rest, with nothing soloed: put the Pro-L 2 meter (settings from 1.5) in the next slot, click its loudness reset button, and play the whole take. Integrated should read **−20.0 LUFS (±0.5)**, the same level LEAD has after L1. If it doesn't, add (−20.0 − reading) to B1's Output Gain: a reading of −21.5 means +1.5 dB. Then remove the meter.
2. Alt-solo DBL BUS. You should hear two gritty, narrowed copies, darker and dirtier than the lead.
3. B4 should show the same readings as L5 (**3–6 dB** sung, **8–14 dB** yelled).
4. Unsolo (Ctrl+right-click any mute switch). The DBL BUS fader is set in section 6.

---

## 4. FX returns

### 4.1 FX CRUNCH (insert 6), the parallel crunch bus

This return is **never ducked**: it's part of the lead's sound, not a space effect.

**R6.1 · Pro-Q 4 · only the mids go in**

| Band | Shape | Frequency | Gain | Q | Slope | Placement | Why |
|---|---|---|---|---|---|---|---|
| 1 | Low Cut | 300 Hz | — | 1.0 | 24 dB/oct | Stereo | No lows reach the distortion, so the lows stay tight |
| 2 | High Cut | 4.0 kHz | — | 1.0 | 24 dB/oct | Stereo | No highs reach the distortion, so the highs don't fizz |

Globals: Zero Latency · Clean · Output Gain 0.0 dB · Output Pan centre · Auto Gain off · Gain Scale 100% · Phase Invert off.

**R6.2 · Saturn 2 · heavy crunch** (same as L6 except where marked)

| Parameter | Setting | Why |
|---|---|---|
| Style | **Crunchy Amp** (in the **Amp** section of the Style menu) | Heavy, aggressive amp crunch |
| DRIVE | **60%** (typed travel) | The heavier crunch, on the mids only |
| LEVEL | **−6.0 dB** | Offsets the loudness the heavy drive adds |
| All other parameters | As L6 (1 band, MIX 100%, FEEDBACK 0%, FREQ 1k, DYNAMICS centre, TONE flat, pans centre, High Quality Good, Linear Phase off, Stereo, FB off, no modulation) | Same setup, heavier style and drive |

**R6.3 · Pro-Q 4 · clean up the crunch's edges**

| Band | Shape | Frequency | Gain | Q | Slope | Placement | Why |
|---|---|---|---|---|---|---|---|
| 1 | Low Cut | 250 Hz | — | 1.0 | 12 dB/oct | Stereo | Removes low growl the distortion creates |
| 2 | High Cut | 5.0 kHz | — | 1.0 | 24 dB/oct | Stereo | Removes the fizz the distortion creates above the mids |

Globals: as R6.1.

**FX CRUNCH fader:** **−3.0 dB**.

**Dial it in (FX CRUNCH)**
1. Hear FX CRUNCH on its own: select LEAD and left-click Master's send switch to turn LEAD's direct route off (its sends keep feeding the returns), then Alt-solo FX CRUNCH. It should sound like a distorted telephone: all mids, no lows, no fizz. Turn LEAD's route to Master back on afterwards.
2. Unsolo it. The lead should sound clearly dirtier and more aggressive, with lows still tight.
3. Mute FX CRUNCH for a moment. The lead should sound cleaner and smaller. Unmute.

### 4.2 FX ROOM (insert 7)

**R7.1 · Pro-R 2** (not ducked)

| Parameter | Setting | Why |
|---|---|---|
| Style | Modern | A natural, realistic small space |
| SPACE | **0.6 s** (yellow readout) | Short room |
| Decay Rate | 100 (SPACE then shows a single time) | Uses SPACE's decay as is |
| PREDELAY | **8 ms** (sync Off) | Almost no gap: the room is glued to the voice |
| CHARACTER | 0 | Transparent: no modulation in a tight room |
| THICKNESS | 0% (typed travel) | Minimum. The grit comes from the crunch, not the room |
| DISTANCE | 15 | Close, in-your-face space |
| BRIGHTNESS | **25%** (typed travel) | Dark room |
| WIDTH | 80 | A bit narrower than full, keeping the energy central |
| DUCKING | 0% (typed travel) | This room isn't ducked |
| MIX | 100 | Wet only (this is a send return) |
| Lock Mix / Auto Gate / Freeze | Off / Off / Off | Normal reverb |
| Decay Rate EQ | No bands | Flat decay |
| Post EQ band 1 | Low Cut 250 Hz, Q 1.0, 24 dB/oct, Stereo | No low mud in the room |
| Post EQ band 2 | High Cut 5.0 kHz, Q 1.0, 12 dB/oct, Stereo | Dark: keeps the room behind the crunch |
| Input / Output | 0.0 dB / 0.0 dB, centre | Unity |

To make the Post EQ bands (the yellow curve): double-click the far left of the display for the low cut, and the far right for the high cut. Then double-click each dot to type its values (Tab steps through the fields; cut bands have no Gain).

**Dial it in:** Alt-solo FX ROOM. Around the lead you should hear a small, dark, gritty space. Unsoloed, it's felt rather than heard.

### 4.3 FX DELAY (insert 8)

**R8.1 · Timeless 3**

| Parameter | Setting | Why |
|---|---|---|
| Delay Sync | On: click the sync icon at the top-right of DELAY and choose its **quarter-note** entry | Locks the echoes to your tempo |
| DELAY (Delay Offset while synced) | **100** (type the number) | Exactly a **¼ note** |
| Delay Time Pan | Centre (the L and R readouts under DELAY show the same time) | Equal times |
| Delay Read Mode (tape-reel icon) | Stretch | Clean, steady echoes |
| Freeze (snowflake icon) | Off | Normal delay |
| Ping Pong (icon below Freeze) | Off | Echoes stay central behind the aggressive lead |
| FEEDBACK | 30 | A couple of repeats at line endings |
| Feedback Pan | Centre (Ctrl-click) | Even repeats |
| ± invert (both) | Off | Normal polarity |
| CROSS | 0 | Normal feedback (no ping-pong) |
| WIDTH | 50 | Narrow: keeps the energy central |
| WET | Ctrl-click to reset, then hover: it should read **0.0 dB** (if it shows another dB value, type 0) | Unity; amount is set by the send instead |
| WET pan ring | Centre | Balanced |
| MIX | 100 | Wet only (this is a send return) |
| Lock Mix | Off | Not needed |
| Filter 1 | Low cut (high-pass), style **Clean**, 400 Hz, Q 0.7, 12 dB/oct, pan centre | Thin, dark echoes that don't clutter the low end |
| Filter 2 | High cut (low-pass), style **Clean**, 3.5 kHz, Q 0.7, 12 dB/oct, pan centre | Dark echoes, out of the way of the bite |
| Filter Routing | Serial | Both filters shape every repeat |
| DRIVE / LO-FI | Off / Off (amounts 0 / 0) | The echoes inherit the lead's crunch; no extra dirt needed |
| DIFFUSE | Off (amount 0) | Clear, defined repeats |
| DYNAMICS | Off (amount at centre: Ctrl-click to reset, pointer at 12 o'clock) | Neutral |
| PITCH | Off | No pitch shifting |
| Input / Output | 0.0 dB / 0.0 dB, centre | Unity |
| Channel Mode | Left/Right | Normal stereo |
| Auto Mute Self-Osc (bottom bar) | On | Silences any filter ringing once the input goes quiet. The Clean filters here shouldn't ring, so it's only a safety net |
| Modulation | None | Steady repeats |

To make the filters: double-click the far left of the filter display for the low cut and the far right for the high cut. Then double-click each dot to type Frequency and Q, and choose the **Clean** style in the filter's value display (the settings panel for the selected filter). The five effect knobs (DRIVE, LO-FI, DIFFUSE, DYNAMICS, PITCH) switch on or off when you click the power icon at the knob's centre; dragging sets the amount.

**R8.2 · Pro-C 3 · ducker**

| Parameter | Setting | Why |
|---|---|---|
| Style | Clean | Precise, transparent ducking |
| THRESHOLD | **−32 dB** | Every word triggers it, sung or yelled |
| AUTO (threshold) / Audition Triggering | Off / Off | Predictable |
| RATIO | **8.0:1** | Reaches the full range fast |
| KNEE | 6 dB | Smooth onset |
| RANGE | **18 dB** | Echoes almost vanish while you sing or yell, then bloom on line endings |
| Character / DRIVE / POST | Off / inactive / Post | No saturation on the ducker |
| ATTACK | 2 ms | Ducks instantly |
| RELEASE | 180 ms | The echo blooms right after each line |
| AUTO (release) | Off | Predictable |
| LOOKAHEAD | 0 ms (bottom-bar Lookahead: Off) | Not needed |
| HOLD | 30 ms | No flutter between syllables |
| GAIN / AUTO (gain) / pan ring | 0.0 dB / Off / centre | No makeup on a ducker |
| DRY | 0% (typed travel, fully off) | Ducked signal only |
| Side Chain Input | **External** (fed from LEAD: map it as in 1.4 step 5) | Ducks to your voice |
| LEVEL (side chain) / Audition | 0.0 dB / Off | Unity |
| STEREO LINK | 100% (scale mark) | Linked ducking |
| Side-chain EQ | No active bands | Full-range trigger |
| Oversampling | 2x | Clean gain changes |
| Input / Output | 0.0 dB / 0.0 dB, centre | Unity |
| Mix | 100 | Full effect |

**Dial it in (FX DELAY)**
1. Alt-solo FX DELAY and play. You should hear the lead with dark ¼-note repeats at the ends of lines.
2. Check the L and R readouts under DELAY against section 5 for your project tempo. If they don't match, turn Delay Sync off and type the ms value from section 5.
3. Unsolo it. R8.2's meter should show about **13–18 dB** of reduction while you sing or yell (the most on yells), so the echoes appear only on line endings. If it shows no reduction at all, recheck the side-chain mapping (1.4 step 5).

---

## 5. Delay and pre-delay times

The synced delay follows the project tempo you set in 1.3. Use this table to check the readouts, or to type ms values if you ever turn sync off. The room's pre-delay is a fixed 8 ms, so it doesn't change with tempo.

| BPM | ¼, R8.1 delay (ms) |
|---|---|
| 130 | 461.5 |
| 135 | 444.4 |
| 140 | 428.6 |
| 145 | 413.8 |
| 150 | 400.0 |
| 155 | 387.1 |
| 160 | 375.0 |
| 165 | 363.6 |
| 170 | 352.9 |

For any other tempo: ¼ = 60000 ÷ BPM.

---

## 6. Final balance

### 6.1 Place the lead (target: level with the beat, 0.0 LU)

1. Load the **Pro-L 2 meter** (settings from 1.5) as the last slot on BEAT and as the last slot on LEAD. On each, set the max readout above the loudness meter to **Max S** (Max Short Term), then click the loudness reset button.
2. Play the loudest 8 bars where you sing all the way through (a hook, for example) once. Read **Max S** on each meter: that's **Beat ST** on BEAT and **Lead ST** on LEAD. These readings are pre-fader.
3. Set the **LEAD fader = (Beat ST + BEAT fader + 0.0) − Lead ST**. BEAT fader is the value you set in 1.3, not the −6.0 dBFS peak target.
   - Example: Beat ST −9.0, BEAT fader −4.5 dB, Lead ST −15.0 → (−9.0 − 4.5 + 0.0) − (−15.0) = **+1.5 dB**.
4. If the result is more than the LEAD fader can reach, pull the BEAT fader down by another 3.0 dB and redo the formula with the new BEAT fader value. Repeat if needed.
5. Remove both Pro-L 2 meters.
6. Re-check R8.2 against its section 4 readings: it hears LEAD after its fader. If the LEAD fader ended up below 0 dB and R8.2 now shows less than about 13 dB while you sing, lower R8.2's THRESHOLD by the same number of dB.

### 6.2 Doubles and returns

| Fader | Setting | Why |
|---|---|---|
| DBL L / DBL R | 0.0 / 0.0 dB | Set in 3.2 |
| DBL BUS | **LEAD fader − 7.0 dB** (e.g., +1.5 → −5.5 dB) | A present but tucked dirty halo |
| FX CRUNCH | −3.0 dB | Set in 4.1 |
| FX ROOM / FX DELAY | 0.0 dB / 0.0 dB | Amounts come from the sends (−13.0 and −12.0 dB) |

### 6.3 Final listen

- The vocal sits level with the beat and leads it, and yells are big without jumping out.
- The crunch is obvious, the lows stay tight, and there's no fizz on top.
- Echoes appear only on line endings.
- Mute DBL BUS. The vocal should lose its dirty halo and get narrower. Unmute.

---

## 7. Optional: carve the beat

Skip this section if the lead already sits clearly. It dips the beat slightly in the vocal's presence range, only while you sing.

1. Load **Pro-Q 4** on BEAT (insert 1).
2. Select LEAD → right-click BEAT's send switch → **"Sidechain to this track"**.
3. In the BEAT Pro-Q 4: gear icon → "Plugin Wrapper Settings" → "Processing" → "Connections". Map its sidechain input to insert 2 (or click "Auto map inputs").

| Band | Shape | Frequency | Gain | Q | Slope | Dynamic range | Threshold / attack (A) / release (R) | Triggering | External side chain | Why |
|---|---|---|---|---|---|---|---|---|---|---|
| 1 | Bell | 2.5 kHz | 0.0 dB | 1.0 | 12 dB/oct | **−4.0 dB** | Auto (A) / 50% / 50% | Band | **On** (click "expand >>" to see the button) | A deeper carve, because the vocal sits level with the beat |
| 2 | Bell | 4.5 kHz | 0.0 dB | 1.4 | 12 dB/oct | **−3.0 dB** | Auto (A) / 50% / 50% | Band | **On** | Clears room for the bite |

Globals: Zero Latency · Clean · Output Gain 0.0 dB · Output Pan centre · Auto Gain off · Gain Scale 100% · Phase Invert off. Spectral off on both bands.

**Dial it in:** The beat's 2.5 and 4.5 kHz regions should dip up to 4 and 3 dB **only while you sing**, and stay flat in the gaps.

---

## 8. Troubleshooting

Each fix changes only the slots it names. "or" means pick one; ";" means do both.

| If it sounds… | Do this |
|---|---|
| Not crunchy enough | L6 DRIVE 22% → **30%** (typed travel), or FX CRUNCH fader −3.0 → **−1.0 dB** |
| Fuzzy or fizzy on top | R6.3 High Cut 5.0 → **4.0 kHz**; L7 band 3 −2.5 → **−4.0 dB** |
| The lows get flabby when the crunch is in | R6.1 Low Cut 300 → **400 Hz** |
| Yells explode or jump out | L5 THRESHOLD −24 → **−27 dB**, or RATIO 6.0 → **8.0:1** |
| Sung parts lose their crunch | L6 DRIVE 22% → **28%** (typed travel; sung lines hit the drive less hard than yells) |
| Yells warble or glitch in the tuning | L4 FLEX-TUNE 15 → **25** |
| Sung notes don't sound hard enough | L4 RETUNE SPEED 2 → **0 ms** |
| Echoes step on your words | R8.2 RANGE 18 → **22 dB** |
| You can't hear the echoes even at line ends | R8.2 RANGE 18 → **12 dB**, or LEAD → FX DELAY send −12 → **−9 dB** |
| The room makes it muddy or boxy | R7.1 Post EQ Low Cut 250 → **350 Hz**, or LEAD → FX ROOM send −13 → **−16 dB** |
| The doubles smear the words | DBL BUS fader to **LEAD − 9 dB** |
| Esses spit through the distortion | L3 THRESHOLD −26 → **−30 dB** |
