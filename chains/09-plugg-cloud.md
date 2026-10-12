# Plugg Cloud (#9): Lead + Doubles Vocal Chain

> *Soft, buttery, airy: the vocal melts into the beat instead of sitting on top.*

**What this chain does**
- Melts your vocal into the beat: it sits even with the beat instead of on top. On the meter, that's 3.5 LU under the beat's loudness.
- Tunes smooth and hard (fast retune), with soft, natural holds on long notes. Compression is gentle. The body is warm and buttery, and the top is breathy with the esses kept soft.
- Floats you in long, dark ¼-note echoes with a slight cassette-style wobble, plus a soft, darkened plate. The echoes duck only a little, so they stay part of the cloud. The plate never ducks.
- Turns two copy-pasted doubles into a soft, chorused pair (±60%), tucked low. They play the whole song.
- Uses no saturation anywhere. The softness comes from the tone, the space, and the blend.

**You'll use:** FL Studio 2024 or newer (Producer Edition) · Auto-Tune Artist · FabFilter Pro-Q 4, Pro-C 3, Pro-DS, Pro-R 2, Timeless 3, and Pro-L 2 (as a meter only) · Fruity Chorus. Only if your booth is noisy: Edison and FabFilter Pro-G.

**Contents:** 1. Session setup and routing · 2. Lead chain · 3. Doubles · 4. FX returns · 5. Delay and pre-delay times · 6. Final balance · 7. Optional: carve the beat · 8. Troubleshooting

---

## 1. Session setup and routing

### 1.1 How to enter exact values

| Where | How |
|---|---|
| FabFilter knobs | Double-click the knob, type the number, press Enter. A plain number sets the value in the knob's own unit: "45" on a % knob is 45%, "-20" on a dB knob is −20 dB. "1k" = 1000 Hz. Ctrl-click resets a knob. |
| FabFilter knobs with no published unit | Type a percentage with the % sign, like "30%". That puts the knob exactly 30% of the way through its travel. This file only does this where it says "typed travel". |
| FabFilter EQ bands and filters | Double-click the band's dot, then type Frequency, press Tab, type Gain, press Tab, type Q. Ctrl+Alt-click a dot to change its shape. Alt+Shift-click a dot to change its slope. |
| Auto-Tune Artist | Drag each control until its readout shows the value. |
| FL mixer (fader, pan, send level) | Right-click → "Type in value". |
| Fruity Chorus | Drag while reading the hint bar (top-left of FL). Hold Ctrl for fine moves. |

### 1.2 Mixer map

| Insert | Name | What's on it | Pan | Track delay | Routes to |
|---|---|---|---|---|---|
| 1 | BEAT | Optional carve (section 7) | 0% | — | Master |
| 2 | LEAD | L1–L8 (section 2) | 0% | — | Master + sends to 6 and 7 + sidechain link to 6 |
| 3 | DBL L | D1, D2 | −60% | 14 ms | 5 only |
| 4 | DBL R | D1, D2 | +60% | 21 ms | 5 only |
| 5 | DBL BUS | B1–B5 | 0% | — | Master + send to 7 |
| 6 | FX DELAY | R6.1–R6.2 | 0% | — | Master |
| 7 | FX PLATE | R7.1 | 0% | — | Master |

Every insert's stereo separation knob stays at centre (off). Faders are set in section 6.

### 1.3 Build the session

1. Open the Mixer menu → "Plugin delay compensation" → make sure **"Automatic"** is ticked. It keeps every insert in time, including sends and sidechains.
2. Put the beat on its own playlist track. In its channel settings, set **TRACK** to **1**. Put your lead take on another playlist track, with TRACK set to **2**.
3. Name inserts 1–7 as in the map. Right-click each insert → "Rename, color & icon..." (F2).
4. **Beat headroom.** Play only the beat's loudest part. Hover over the Master meter and read the hint bar. Pull the BEAT fader down until the beat peaks at **−6.0 dBFS**. Right-click the fader → "Type in value" to fine-tune it.
5. If your booth is noisy, do the Edison step in L2a now, **before** you make the doubles. That way every copy is clean.
6. Make the doubles (section 3.1).
7. Do the routing in 1.4, then calibrate in 1.5.

### 1.4 Routing walkthrough

1. **Doubles go to DBL BUS only.** Select insert 3 (DBL L). Left-click the send switch (the arrow at the bottom) of insert 5 (DBL BUS). Then left-click the **Master** track's send switch to turn that route off. Repeat for insert 4.
2. **LEAD sends.** Select insert 2 (LEAD) and left-click the send switches of inserts 6 and 7. With LEAD still selected, right-click each new send knob (it sits on the destination's send switch) → "Type in value": insert 6 = **−9.0 dB**, insert 7 = **−12.0 dB**. LEAD keeps its Master route. FL sends are post-fader, so the effects follow your LEAD fader.
3. **DBL BUS send to the plate.** Select insert 5 (DBL BUS) and left-click insert 7's send switch. Right-click the send knob → "Type in value" → **−16.0 dB**. DBL BUS keeps its Master route. This melts the doubles into the plate too.
4. **Sidechain link for the delay ducking.** Select LEAD, then right-click insert 6's send switch → **"Sidechain to this track"**. The link is silent, and LEAD still goes to Master. The plate is **not** ducked.
5. **Pans and Track delays.** Right-click each pan knob → "Type in value": insert 3 = −60%, insert 4 = +60%. On each double's insert, click the clock icon (**Track delay**) → "Set in ms (milliseconds)": insert 3 = **14**, insert 4 = **21**.
6. **Feed the ducker.** When you load Pro-C 3 on insert 6 (R6.2), open its gear icon → **"Plugin Wrapper Settings"** → **"Processing"** → **"Connections"**. Right-click the plugin's sidechain input number and choose insert 2 (LEAD), or click **"Auto map inputs"**. Then, in Pro-C 3, set **Side Chain Input** to **External**.
7. Both returns stay routed to Master (the default).

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
1. Play your whole lead take from start to finish (a full-song take, not one phrase).
2. Read the **Integrated** loudness, for example −25.0 LUFS.
3. Work out **T = −20.0 − reading**. For example, −20.0 − (−25.0) = **+5.0 dB**. You'll type T into L1 and use it again on DBL BUS.
4. Remove Pro-L 2 from LEAD. Keep these settings handy; you'll use the same meter again in section 6.

---

## 2. Lead chain (insert 2)

| Order | Slot | Plugin | Job |
|---|---|---|---|
| 1 | L1 | Pro-Q 4 | Trim to the calibrated level |
| 2 | L2 | Pro-Q 4 | Cleanup: rumble, booth boxiness, harshness |
| (only if needed) | L2a | Edison (offline) + Pro-G | Room-tone cleanup |
| 3 | L3 | Pro-DS | De-ess |
| 4 | L4 | Auto-Tune Artist | Tune: smooth hard tune |
| 5 | L5 | Pro-C 3 | Gentle, smooth level control |
| 6 | L6 | Pro-Q 4 | Tone: warm body, breathy top |
| — | L7 | (none) | This style has no saturation: the softness comes from the tone, the space, and the blend |
| 7 | L8 | Pro-DS | Second de-ess after the air boost |

### L1 · Pro-Q 4 · trim

| Parameter | Setting | Why |
|---|---|---|
| Bands | None | This instance only sets level |
| Output Gain | **T** (from 1.5), e.g. +5.0 dB | Puts every take at −20 LUFS so every threshold below works as written |
| Processing Mode | Zero Latency | No bands to process, so no latency needed |
| Character | Clean | No saturation anywhere in this chain |
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
| Character | Clean | No saturation |
| Output Gain | 0.0 dB | Level is already set by L1 |
| Output Pan | Centre (L/R mode) | Mono vocal stays centred |
| Auto Gain | Off | Keeps levels predictable |
| Gain Scale | 100% (type 100) | Bands at their stated gain |
| Phase Invert (Ø) | Off | Keeps polarity |

**Dial it in**
1. Double-click the far left of the display to create a Low Cut. Double-click its dot and type 85, then set the slope to 18 dB/oct (Alt+Shift-click the dot to step through slopes).
2. Click the display around 300 Hz to add a bell. Double-click its dot and type 320, Tab, −2.5, Tab, 1.2.
3. Click the display around 4 kHz to add another bell. Type 4.2k, Tab, 0, Tab, 2. Drag the dynamic range ring around its GAIN knob down to **−4.0 dB**. Click **A** on the threshold, and type 50 into both A and R.
4. Play the loudest, brightest lines. Band 3 should dip **0–3 dB on harsh notes only** and stay still on soft lines.

### L2a · only if room tone is audible

**Test:** Solo LEAD and play a gap between phrases at your normal listening level. If you hear booth hiss, hum, or room tone, do both parts below. If not, skip L2a. The long echoes and the plate repeat anything left in the gaps, so check carefully.

**Part 1: Edison (offline, before you copy the doubles).** Open the lead clip in Edison.
1. Select a few hundred milliseconds where you're not singing. Choose Tools > Spectral > **"Aquire noise profile"** (Alt+U; that's FL's own spelling).
2. Open **"Clean up (denoise)"** (Ctrl+U).

| Control | Setting | Why |
|---|---|---|
| Threshold | 0 dB | Image-Line's suggested starting point |
| Amount | 60% (read it on the hint bar) | Removes the hiss without making the voice watery |
| Output noise only | Turn on to check, then off | Lets you hear exactly what's being removed. It should be hiss, not words |

3. Click Preview, check, then click **Accept**.

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
| SIDE CHAIN | In | Triggered by the vocal itself |
| Audition Triggering / Audition | Off / Off | Monitoring only |
| Oversampling | 2x | Cleaner gain changes |
| In: / Out: | 0.0 dB / 0.0 dB, pan centre | Unity |

**Dial it in:** Loop a line with lots of s/sh/t. The gain-reduction readout should show **3–6 dB on esses** and about **0 dB** elsewhere. Click the readout to reset it between checks.

### L4 · Auto-Tune Artist · tune

| Parameter | Setting | Why |
|---|---|---|
| INPUT TYPE | Alto/Tenor | Matches your mid-range voice |
| KEY / SCALE | Your song's key and scale (Chromatic if you don't know it) | Gives Auto-Tune the right target notes |
| CLASSIC | Off | Keeps the modern correction sound |
| FORMANT | Off | No pitch shift on the lead, so no formant correction needed |
| THROAT | 100 (inactive while FORMANT is off) | Neutral |
| TRANSPOSE | 0 | No pitch shift |
| DETUNE | 0 c | Standard A = 440 Hz tuning |
| TRACKING | 50 | Manual's standard pitch-detection setting |
| RETUNE SPEED | **6 ms** | Smooth hard tune: fast enough to lock every note |
| FLEX-TUNE | 0 | Every note gets corrected |
| HUMANIZE | **35** | Soft, natural holds: long notes relax instead of freezing |
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
2. Play a sustained melody. Notes should land clearly tuned, and long notes should sound soft and natural rather than frozen.
3. If a note jumps to the wrong pitch, your key or scale is off. Fix that first.

### L5 · Pro-C 3 · gentle level control

| Parameter | Setting | Why |
|---|---|---|
| Style | **Opto** | FabFilter's slow, very soft-knee opto style: gentle and smooth |
| THRESHOLD | −20 dB | Loud lines get 3–4 dB of reduction at the calibrated level |
| AUTO (threshold) | Off | A fixed threshold makes the readings predictable |
| Audition Triggering | Off | Monitoring only |
| RATIO | **2.5:1** | Gentle: the level settles instead of clamping |
| KNEE | **18 dB** | Very soft onset |
| RANGE | **18 dB** | Far above the 3–4 dB this chain uses, so it never caps the compression |
| Character | Off | No saturation anywhere in this chain |
| DRIVE / POST | Inactive (Character Off) / Post | Character is off |
| ATTACK | **15 ms** | Slow enough to keep the start of each word soft and natural |
| RELEASE | **200 ms** | Smooth, breathing recovery between phrases |
| AUTO (release) | Off | Fixed, predictable release |
| LOOKAHEAD | 0 ms (bottom-bar Lookahead: Off) | Not needed at this attack |
| HOLD | 0 ms | No hold needed |
| GAIN | **+2.5 dB** | Makes up most of the reduction, so bypassing keeps the level about the same |
| AUTO (gain) / GAIN pan ring | Off / centre | Manual, predictable makeup |
| DRY | 0% (typed travel, fully off) | No parallel blend |
| Side Chain Input | Internal | Triggered by the vocal itself |
| LEVEL (side chain) / Audition | 0.0 dB / Off | Unity trigger level |
| STEREO LINK | 100% (scale mark) | Fully linked |
| Side-chain EQ | No active bands (Alt-click any band to bypass it) | Full-range detection |
| Oversampling | 2x | Cleaner gain changes |
| Input / Output | 0.0 dB / 0.0 dB, centre | Unity |
| Mix | 100% (type 100) | Full effect |

**Dial it in**
1. Play the loudest section. The gain-reduction meter should move gently and show **3–4 dB** on loud lines.
2. Toggle bypass. The loudness should stay within about **1 dB**. If not, adjust GAIN in 0.5 dB steps.

### L6 · Pro-Q 4 · tone

| Band | Shape | Frequency | Gain | Q | Slope | Placement | Why |
|---|---|---|---|---|---|---|---|
| 1 | Low Shelf | 180 Hz | +1.5 dB | 1.0 | 12 dB/oct | Stereo | Warm, buttery body |
| 2 | Bell | 3.8 kHz | −1.5 dB | 1.5 | 12 dB/oct | Stereo | Softens the edge, right where your mic adds its 4 kHz bump |
| 3 | High Shelf | 12 kHz | **+2.5 dB** | 1.0 | 12 dB/oct | Stereo | Breathy air on top. L8 keeps the esses it brings up soft |

All three bands are static (no dynamic range). Globals as in L2: Zero Latency · Clean · Output Gain 0.0 dB · Output Pan centre · Auto Gain off · Gain Scale 100% · Phase Invert off.

**Dial it in:** A/B with bypass. With the EQ on, the vocal should sound warmer and softer in the middle, with more breath on top and no harshness.

### L8 · Pro-DS · second de-ess

| Parameter | Setting | Why |
|---|---|---|
| MODE | Single Vocal | Solo vocal |
| WIDE BAND / SPLIT BAND | WIDE BAND | Gentle; no added latency |
| THRESHOLD | −32 dB | Catches the esses the air shelf brought up, so the shimmer stays soft |
| RANGE | 6 dB | A full de-ess: breathy, never hissy |
| HP / LP (trigger filters) | 5.5 kHz / 12.0 kHz | Triggers on the esses, not on the breathy air above 12 kHz |
| LOOKAHEAD | On, 10 ms | Catches ess onsets |
| STEREO LINK | 100% (scale mark) | Fully linked |
| SIDE CHAIN | In | Triggered by the vocal |
| Audition Triggering / Audition | Off / Off | Monitoring only |
| Oversampling | 2x | Cleaner gain changes |
| In: / Out: | 0.0 dB / 0.0 dB, pan centre | Unity |

**Dial it in:** On an ess-heavy line, expect **3–6 dB** of reduction on esses only.

---

## 3. Doubles (inserts 3–5)

### 3.1 Make the copies

1. Hold Shift and drag the lead clip straight down onto an empty playlist track. Drop it at exactly the same start position. The playlist snaps to the grid, so drop it in the same grid spot. All timing offsets come from Track delay, never from clip position.
2. Open the copy's clip menu (top-left corner of the clip) → **"Make unique"**. Don't use "Make unique as sample".
3. In the new channel's settings, set **TRACK** to the double's insert (3 or 4).
4. Repeat until you have two copies: DBL L (3) and DBL R (4).
5. Zoom in on the starts: all three clips (lead + 2 doubles) must begin at the same point.

### 3.2 Mixer settings

| Insert | Pan | Fader | Track delay | Route | Why |
|---|---|---|---|---|---|
| 3 DBL L | −60% | 0.0 dB | 14 ms | DBL BUS only | Left side of the soft pair; its own offset makes it sound like a separate take |
| 4 DBL R | +60% | 0.0 dB | 21 ms | DBL BUS only | Right side; a different offset from DBL L |

### 3.3 D1 · Auto-Tune Artist on each double

| Parameter | DBL L | DBL R | Why |
|---|---|---|---|
| INPUT TYPE | Alto/Tenor | Alto/Tenor | Mid-range voice |
| KEY / SCALE | Same as L4 | Same as L4 | Same target notes as the lead |
| CLASSIC | Off | Off | Classic would disable Formant and Throat |
| FORMANT | **On** | **On** | Needed for THROAT to work |
| THROAT | **102** | **98** | Small throat variations make the copies sound like different takes |
| TRANSPOSE | 0 | 0 | Same pitch as the lead |
| DETUNE | **+6 c** | **−5 c** | Each copy sits slightly off the lead's pitch. That's what makes copies sound like real doubles |
| TRACKING | 50 | 50 | Standard |
| RETUNE SPEED | 8 ms | 10 ms | Smooth, and a little different from the lead (6 ms) |
| FLEX-TUNE | 0 | 0 | Full correction |
| HUMANIZE | 40 | 45 | Softer holds than the lead, and different per copy |
| NATURAL VIBRATO | 0.0 | 0.0 | Untouched |
| Vibrato (Advanced view) | As L4 (No Vibrato, amounts 0) | As L4 | No artificial vibrato |
| TARGETING IGNORES VIBRATO / keyboard / MIDI | As L4 | As L4 | Same as the lead |
| Settings | As L4 (Use Low Latency off, Detune Display Cents) | As L4 | Highest quality |

### 3.4 D2 · Pro-Q 4 on each double

**DBL L**

| Band | Shape | Frequency | Gain | Q | Slope | Placement | Why |
|---|---|---|---|---|---|---|---|
| 1 | Low Cut | 160 Hz | — | 1.0 | 18 dB/oct | Stereo | Keeps the pair out of the lead's warm low end |
| 2 | High Shelf | 9 kHz | −1.0 dB | 1.0 | 12 dB/oct | Stereo | A touch darker than the lead, so the doubles stay soft |

**DBL R**

| Band | Shape | Frequency | Gain | Q | Slope | Placement | Why |
|---|---|---|---|---|---|---|---|
| 1 | Low Cut | 180 Hz | — | 1.0 | 18 dB/oct | Stereo | A different low corner from DBL L |
| 2 | Bell | 2.2 kHz | −1.0 dB | 1.0 | 12 dB/oct | Stereo | A slightly different colour from DBL L, and a little room for the lead's words |

Globals on both D2s: Zero Latency · Clean · Output Gain 0.0 dB · Output Pan centre · Auto Gain off · Gain Scale 100% · Phase Invert off.

### 3.5 DBL BUS (insert 5)

| Order | Slot | Plugin | Settings |
|---|---|---|---|
| 1 | B1 | Pro-Q 4 trim | As L1, but Output Gain = **T − 1.0 dB**. Cancels the extra level of the two doubles summing, so B4 sees the same level as L5 |
| 2 | B2 | Pro-Q 4 cleanup | L2's bands 2 and 3 only (Bell 320 Hz −2.5 dB Q 1.2; dynamic Bell 4.2 kHz, Range −4.0 dB, Threshold A, A/R 50%), with L2's globals. No Low Cut: each D2 already cuts higher |
| (only if L2a used) | B2a | Pro-G | Identical to L2a's Pro-G |
| 3 | B3 | Pro-DS | Identical to L3 |
| 4 | B4 | Pro-C 3 | Table below |
| 5 | B5 | Fruity Chorus | Table below |

**B4 · Pro-C 3** (same as L5 except where marked)

| Parameter | Setting | Why |
|---|---|---|
| Style | Opto | The same gentle style as the lead |
| THRESHOLD | **−22 dB** | Steady, gentle control of the summed pair |
| RATIO | 2.5:1 | Gentle |
| KNEE | 18 dB | Very soft onset |
| RANGE | 18 dB | Never caps the compression |
| ATTACK / RELEASE | 15 ms / **220 ms** | A touch slower release than the lead, so the pair breathes smoothly |
| GAIN | +2.5 dB | Level-matched makeup |
| All other parameters | As L5 (Character Off, Internal side chain, Lookahead Off, HOLD 0 ms, DRY off, Oversampling 2x, In/Out 0 dB, Mix 100%) | Same clean setup |

**B5 · Fruity Chorus**

| Parameter | Setting | Why |
|---|---|---|
| DELAY | 10.0 ms | Base chorus delay, inside its 0–30 ms range |
| DEPTH | 2.5 ms | Constant, soft pitch motion: the dreamy part |
| STEREO | 120° | The left and right LFOs run a third of a cycle apart, so the sides move differently and the pair stays wide |
| LFO 1 FREQ. / LFO 2 FREQ. / LFO 3 FREQ. | 0.30 Hz / 0.70 Hz / 1.30 Hz | Slow, non-repeating drift: dreamy, not seasick |
| LFO 1 WAVE / LFO 2 WAVE / LFO 3 WAVE | sin / sin / sin | Smooth motion |
| CROSS TYPE | Process HF | Only the part above the cutoff is chorused |
| CROSS CUTOFF | 250 Hz | Keeps the doubles' low end steady |
| WET ONLY | no | Dry doubles plus the chorus |

**DBL BUS send:** → FX PLATE **−16.0 dB** (set in 1.4).

**Dial it in (DBL BUS)**
1. Solo DBL BUS. The pair should sound soft, wide, and gently drifting.
2. B4's gain-reduction meter should show **3–5 dB** on loud lines.
3. The DBL BUS fader is set in section 6.

---

## 4. FX returns

### 4.1 FX DELAY (insert 6)

**R6.1 · Timeless 3**

| Parameter | Setting | Why |
|---|---|---|
| Delay Sync | On, **quarter-note entry** (click the sync icon at the top-right of DELAY) | Locks the echoes to your tempo |
| DELAY (Delay Offset while synced) | **100** (type the number) | Exactly a **¼ note** |
| Delay Time Pan | Centre (the L and R readouts under DELAY show the same time) | Equal times |
| Delay Read Mode (tape-reel icon) | **Tape** | Time changes bend the pitch like a tape echo. The XLFO below uses this to make the wobble |
| Freeze (snowflake icon) | Off | Normal delay |
| Ping Pong (icon below Freeze) | Off | The echoes stay centred behind the vocal |
| FEEDBACK | 45 | Long trails: about 3–4 audible repeats |
| Feedback Pan | Centre (Ctrl-click) | Even repeats |
| ± invert (both) | Off | Normal polarity |
| CROSS | 0 | Normal feedback (no ping-pong) |
| WIDTH | 70 | Medium width: the echoes stay mostly centred |
| WET | Ctrl-click to reset, then hover: it should read **0.0 dB** (if not, type 0) | Unity; amount is set by the send instead |
| WET pan ring | Centre | Balanced |
| MIX | 100 | Wet only (this is a send return) |
| Lock Mix | Off | Not needed |
| Filter 1 | Low cut (high-pass), style **Clean**, 250 Hz, Q 0.7, 12 dB/oct, pan centre | Keeps the echoes out of the lows |
| Filter 2 | High cut (low-pass), style **Clean**, 3.2 kHz, Q 0.7, 12 dB/oct, pan centre | Highs rolled off: dark echoes that sit behind the beat. Clean = no saturation |
| Filter Routing | Serial | Both filters shape every repeat |
| DRIVE / LO-FI | 0 / 0 | No saturation or degradation in this chain |
| DIFFUSE | 15 | A light smear: softer, cloudier repeats |
| DYNAMICS | Centre: Ctrl-click to reset, pointer at 12 o'clock | Neutral (no gating or pumping) |
| PITCH | Off | No pitch shifting in the delay |
| Input / Output | 0.0 dB / 0.0 dB, centre | Unity |
| Channel Mode | Left/Right | Normal stereo |
| Auto Mute Self-Osc (bottom bar) | On | Silences any filter ringing once the input goes quiet. The Clean filters here shouldn't ring, so it's only a safety net |
| Modulation | One XLFO on DELAY: two-step sine, Free, 0.50 Hz, slot Level **+3%** (steps below) | The slight tape-style wobble: one slow drift every 2 seconds |

To make the filters: double-click the far left of the filter display for the low cut and the far right for the high cut. Then double-click each dot to type Frequency and Q, and choose the **Clean** style in its value display.

**Add the wobble (XLFO)**
1. First, while the delay time is still steady, check the L and R readouts under DELAY against section 5 for your BPM. If they don't match, turn Delay Sync off and type the ms value from section 5.
2. In the modulation section at the bottom, click **+** → **New XLFO**. It starts as two steps that make a sine wave. Keep that shape.
3. Click the sync options at the top-right of the XLFO's frequency knob and choose **Free**. Then set the frequency knob to **0.50 Hz** (double-click it and type 0.5).
4. Drag the XLFO's source dot (at the top of the source) and drop it on the **DELAY** knob.
5. In the slot panel that pops up, drag **Level** up to **+3%**. Hold Shift for fine moves. Leave **+/-** (invert) off.

**R6.2 · Pro-C 3 · ducker**

| Parameter | Setting | Why |
|---|---|---|
| Style | Clean | Precise, transparent ducking |
| THRESHOLD | −30 dB | Every sung word triggers it |
| AUTO (threshold) / Audition Triggering | Off / Off | Predictable |
| RATIO | **3.0:1** | A gentle duck |
| KNEE | 6 dB | Smooth onset |
| RANGE | **5 dB** | The echoes dip only a little under your words, so they stay part of the cloud |
| Character / DRIVE / POST | Off / inactive / Post | No saturation |
| ATTACK | 10 ms | Ducks smoothly as you start a phrase |
| RELEASE | **350 ms** | The echoes drift back up slowly in the gaps |
| AUTO (release) | Off | Predictable |
| LOOKAHEAD | 0 ms (bottom-bar Lookahead: Off) | Not needed |
| HOLD | 40 ms | Keeps it from fluttering between syllables |
| GAIN / AUTO (gain) / pan ring | 0.0 dB / Off / centre | No makeup on a ducker |
| DRY | 0% (typed travel, fully off) | Ducked signal only |
| Side Chain Input | **External** (fed from LEAD, see 1.4) | Ducks to your voice |
| LEVEL (side chain) / Audition | 0.0 dB / Off | Unity |
| STEREO LINK | 100% (scale mark) | Linked ducking |
| Side-chain EQ | No active bands | Full-range trigger |
| Oversampling | 2x | Clean gain changes |
| Input / Output | 0.0 dB / 0.0 dB, centre | Unity |
| Mix | 100 | Full effect |

**Dial it in (FX DELAY)**
1. Solo FX DELAY while LEAD plays. You should hear long, dark ¼-note repeats.
2. The echoes should drift slightly in pitch, like an old cassette, never like vibrato. The readouts under DELAY now move with the wobble. That's expected: you checked them before adding the XLFO.
3. Unsolo it. R6.2 should show about **5 dB** of reduction while you sing. The echoes stay audible under your words and swell a little in the gaps.

### 4.2 FX PLATE (insert 7)

**R7.1 · Pro-R 2** (not ducked)

| Parameter | Setting | Why |
|---|---|---|
| Style | **Plate** | FabFilter's plate style: a fast build-up and the classic vocal-plate sound |
| SPACE | **2.0 s** (yellow readout) | A medium plate that supports the delays instead of competing with them |
| Decay Rate | 100 (SPACE then shows a single time) | Uses SPACE's decay as is |
| PREDELAY | Sync **32th Note** (FabFilter's spelling), Offset 100 (type the number) | A short gap, so the plate blooms just behind the words. It follows your tempo |
| CHARACTER | 35 | A little life in the tail, below the 50% point where modulation starts |
| THICKNESS | 0% (typed travel) | Minimum: no added density or saturation |
| DISTANCE | 30 | A softer, more diffuse plate than a close, splashy one |
| BRIGHTNESS | **30%** (typed travel) | Dark: more high-frequency absorption |
| WIDTH | 100 | Fully stereo |
| DUCKING | 0% (typed travel) | The plate isn't ducked: it's the cloud |
| MIX | 100 | Wet only (this is a send return) |
| Lock Mix / Auto Gate / Freeze | Off / Off / Off | Normal reverb |
| Decay Rate EQ | No bands | Flat decay |
| Post EQ band 1 | Low Cut 200 Hz, Q 1.0, 24 dB/oct, Stereo | No low mud |
| Post EQ band 2 | High Cut 6.0 kHz, Q 1.0, 12 dB/oct, Stereo | Darkened, so the plate stays soft and behind |
| Input / Output | 0.0 dB / 0.0 dB, centre | Unity |

To make the Post EQ bands: double-click the far left of the Post EQ display for the low cut, and the far right for the high cut.

**Dial it in (FX PLATE)**
1. Solo FX PLATE. You should hear a soft, dark, smooth plate, about 2 seconds long.
2. Unsolo it. The plate should glue the vocal, the doubles, and the echoes together without washing out any words.

---

## 5. Delay and pre-delay times

The synced settings follow your tempo automatically. Use this table to check the readouts, or to type ms values if you ever turn sync off.

| BPM | ¼, R6.1 delay (ms) | 1/32, R7.1 pre-delay (ms) |
|---|---|---|
| 130 | 461.5 | 57.7 |
| 135 | 444.4 | 55.6 |
| 140 | 428.6 | 53.6 |
| 145 | 413.8 | 51.7 |
| 150 | 400.0 | 50.0 |
| 155 | 387.1 | 48.4 |
| 160 | 375.0 | 46.9 |
| 165 | 363.6 | 45.5 |
| 170 | 352.9 | 44.1 |

For tempos between rows: ¼ = 60000 ÷ BPM; 1/32 = 7500 ÷ BPM.

---

## 6. Final balance

### 6.1 Place the lead (target: 3.5 LU under the beat)

1. Load the **Pro-L 2 meter** (settings from 1.5, but time scale **Short Term**) as the last slot on BEAT and as the last slot on LEAD.
2. Play the loudest 8 bars. Read **Beat ST** and **Lead ST**. These readings are pre-fader.
3. Set the **LEAD fader = (Beat ST + BEAT fader − 3.5) − Lead ST**.
   - Example: Beat ST −9.0, BEAT fader −6.0 dB, Lead ST −19.0 → (−9.0 − 6.0 − 3.5) − (−19.0) = **+0.5 dB**.
4. Remove both Pro-L 2 meters.

### 6.2 Doubles and returns

| Fader | Setting | Why |
|---|---|---|
| DBL L / DBL R | 0.0 / 0.0 dB | Set in 3.2 |
| DBL BUS | **LEAD fader − 11.0 dB** (e.g., +0.5 → −10.5 dB) | Tucked low: the pair is felt more than heard |
| FX DELAY / FX PLATE | 0.0 dB / 0.0 dB | Amounts come from the sends (LEAD −9.0 / −12.0 dB; DBL BUS → PLATE −16.0 dB) |

### 6.3 Final listen

- The vocal sits inside the beat, even with it rather than on top, and you can still follow every word.
- The echoes trail softly behind the beat with a slight cassette-style drift. The plate glues the vocal, the doubles, and the echoes into one cloud.
- Mute DBL BUS. The vocal should lose its soft width. Unmute.
- Mute FX DELAY and FX PLATE together. The cloud should disappear, and the vocal should sound dry and exposed. Unmute.

---

## 7. Optional: carve the beat

Skip this section if the vocal already sits clearly inside the beat. This style melts in, so the carve is light: it makes a little room in the vocal's presence range, only while you sing.

1. Load **Pro-Q 4** on BEAT (insert 1).
2. Select LEAD → right-click BEAT's send switch → **"Sidechain to this track"**.
3. In the BEAT Pro-Q 4: gear icon → "Plugin Wrapper Settings" → "Processing" → "Connections". Map its sidechain input to insert 2 (or click "Auto map inputs").

| Band | Shape | Frequency | Gain | Q | Slope | Dynamic range | Threshold / A / R | Triggering | External side chain | Why |
|---|---|---|---|---|---|---|---|---|---|---|
| 1 | Bell | 2.5 kHz | 0.0 dB | 1.0 | 12 dB/oct | **−1.5 dB** | A / 50% / 50% | Band | **On** (click "expand >>" to see the button) | A little room for your diction |
| 2 | Bell | 4.5 kHz | 0.0 dB | 1.4 | 12 dB/oct | **−1.0 dB** | A / 50% / 50% | Band | **On** | A little room for your presence |

Globals: Zero Latency · Clean · Output Gain 0.0 dB · Output Pan centre · Auto Gain off · Gain Scale 100% · Phase Invert off. Spectral off on both bands.

**Dial it in:** The beat's 2.5 and 4.5 kHz regions should dip up to 1.5 and 1 dB **only while you sing**, and stay flat in the gaps.

---

## 8. Troubleshooting

| If it sounds… | Do this |
|---|---|
| The vocal sits on top instead of melting in | LEAD fader down **1.0 dB**, and move DBL BUS with it (keep it at LEAD − 11 dB) |
| The words get lost in the beat | LEAD fader up **1.0 dB** (DBL BUS with it), or use the carve in section 7 |
| The wobble sounds seasick or like vibrato | R6.1 XLFO slot Level +3% → **+1%** |
| You can't hear any wobble | R6.1 XLFO slot Level +3% → **+5%** |
| The echoes pile up into mush | R6.1 FEEDBACK 45 → **35** |
| The echoes cover your words | R6.2 RANGE 5 → **8 dB** |
| The echoes are too dull to hear | R6.1 Filter 2 3.2 → **4.5 kHz** |
| The plate is too bright or splashy | R7.1 BRIGHTNESS 30% → **20%** (typed travel), or Post EQ High Cut 6.0 → **5.0 kHz** |
| The plate washes out the words | LEAD → FX PLATE send −12 → **−15 dB** |
| The top gets harsh or the esses hiss | L8 THRESHOLD −32 → **−36 dB**; L6 band 3 +2.5 → **+1.5 dB** |
| The body gets muddy instead of buttery | L6 band 1 +1.5 → **+0.5 dB** |
| The doubles sound seasick | B5 DEPTH 2.5 → **1.5 ms** |
