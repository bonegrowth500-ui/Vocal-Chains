# Alien Transmission (#4): Lead + Doubles Vocal Chain

> *Eternal Atake's sci-fi world, turned up: wide, modulated, futuristic, beamed in from orbit.*

**What this chain does**
- Keeps your lead dry, clear, and on top. Constant but tasteful FX surround it: a dotted-⅛ ping-pong delay with a slow phaser swirl, plus a quiet octave-up "shimmer" glow.
- Tunes hard but smooth (fast retune, light Humanize). The top end is crisp and glossy, with harshness kept in check.
- Turns three copy-pasted doubles into a chorused wide pair plus a formant-shifted, band-passed "alien" layer. All of them play the whole song.
- Ducks the delay and the glow under your words, so the effects bloom in the gaps.

**You'll use:** FL Studio 2024 or newer (Producer Edition) · Auto-Tune Artist · FabFilter Pro-Q 4, Pro-C 3, Pro-DS, Pro-R 2, Timeless 3, and Pro-L 2 (as a meter only) · Fruity Chorus · Fruity Phaser. Only if your booth is noisy: Edison and FabFilter Pro-G.

**Contents:** 1. Session setup and routing · 2. Lead chain · 3. Doubles · 4. FX returns · 5. Delay and pre-delay times · 6. Final balance · 7. Optional: carve the beat · 8. Troubleshooting

---

## 1. Session setup and routing

### 1.1 How to enter exact values

| Where | How |
|---|---|
| FabFilter knobs | Double-click the knob, type the number, press Enter. A plain number sets the value in the knob's own unit: "38" on a % knob is 38%, "-22" on a dB knob is −22 dB. "1k" = 1000 Hz. Ctrl-click resets a knob. |
| FabFilter knobs with no published unit | Type a percentage with the % sign, like "60%". That puts the knob exactly 60% of the way through its travel. This file only does this where it says "typed travel". |
| FabFilter EQ bands and filters | Double-click the band's dot, then type Frequency, press Tab, type Gain, press Tab, type Q. Ctrl+Alt-click a dot to change its shape. Alt+Shift-click a dot to change its slope. |
| Auto-Tune Artist | Drag each control until its readout shows the value. |
| FL mixer (fader, pan, send level) | Right-click → "Type in value". |
| Fruity Chorus and Fruity Phaser | Drag while reading the hint bar (top-left of FL). Hold Ctrl for fine moves. |

### 1.2 Mixer map

| Insert | Name | What's on it | Pan | Track delay | Routes to |
|---|---|---|---|---|---|
| 1 | BEAT | Optional carve (section 7) | 0% | — | Master |
| 2 | LEAD | L1–L8 (section 2) | 0% | — | Master + sends to 7 and 8 + sidechain links to 7 and 8 |
| 3 | DBL L | D1, D2 | −85% | 15 ms | 6 only |
| 4 | DBL R | D1, D2 | +85% | 23 ms | 6 only |
| 5 | DBL ALIEN | D1, D2 | 0% | 31 ms | 6 only |
| 6 | DBL BUS | B1–B5 | 0% | — | Master |
| 7 | FX DELAY | R7.1–R7.3 | 0% | — | Master |
| 8 | FX SHIMMER | R8.1–R8.3 | 0% | — | Master |

Every insert's stereo separation knob stays at centre (off). Faders are set in section 6.

### 1.3 Build the session

1. Open the Mixer menu → "Plugin delay compensation" → make sure **"Automatic"** is ticked. It keeps every insert in time, including sends and sidechains.
2. Put the beat on its own playlist track. In its channel settings, set **TRACK** to **1**. Put your lead take on another playlist track, with TRACK set to **2**.
3. Name inserts 1–8 as in the map. Right-click each insert → "Rename, color & icon..." (F2).
4. **Beat headroom.** Play only the beat's loudest part. Hover over the Master meter and read the hint bar. Pull the BEAT fader down until the beat peaks at **−6.0 dBFS**. Right-click the fader → "Type in value" to fine-tune it.
5. If your booth is noisy, do the Edison step in L2a now, **before** you make the doubles. That way every copy is clean.
6. Make the doubles (section 3.1).
7. Do the routing in 1.4, then calibrate in 1.5.

### 1.4 Routing walkthrough

1. **Doubles go to DBL BUS only.** Select insert 3 (DBL L). Left-click the send switch (the arrow at the bottom) of insert 6 (DBL BUS). Then left-click the **Master** track's send switch to turn that route off. Repeat for inserts 4 and 5.
2. **LEAD sends.** Select insert 2 (LEAD) and left-click the send switches of inserts 7 and 8. With LEAD still selected, right-click each new send knob (it sits on the destination's send switch) → "Type in value": insert 7 = **−8.0 dB**, insert 8 = **−16.0 dB**. LEAD keeps its Master route. FL sends are post-fader, so the effects follow your LEAD fader.
3. **Sidechain links for the ducking.** With LEAD selected, right-click insert 7's send switch → **"Sidechain to this track"**. Do the same on insert 8. These links are silent, and LEAD still goes to Master.
4. **Pans and Track delays.** Right-click each pan knob → "Type in value": insert 3 = −85%, insert 4 = +85%, insert 5 = 0%. On each double's insert, click the clock icon (**Track delay**) → "Set in ms (milliseconds)": insert 3 = **15**, insert 4 = **23**, insert 5 = **31**.
5. **Feed the duckers.** When you load Pro-C 3 on inserts 7 and 8 (R7.3, R8.3), open each one's gear icon → **"Plugin Wrapper Settings"** → **"Processing"** → **"Connections"**. Right-click the plugin's sidechain input number and choose insert 2 (LEAD), or click **"Auto map inputs"**. Then, in Pro-C 3, set **Side Chain Input** to **External**.
6. DBL BUS and both returns stay routed to Master (the default).

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
2. Read the **Integrated** loudness, for example −24.3 LUFS.
3. Work out **T = −20.0 − reading**. For example, −20.0 − (−24.3) = **+4.3 dB**. You'll type T into L1 and use it again on DBL BUS.
4. Remove Pro-L 2 from LEAD. Keep these settings handy; you'll use the same meter again in section 6.

---

## 2. Lead chain (insert 2)

| Order | Slot | Plugin | Job |
|---|---|---|---|
| 1 | L1 | Pro-Q 4 | Trim to the calibrated level |
| 2 | L2 | Pro-Q 4 | Cleanup: rumble, booth boxiness, harshness |
| (only if needed) | L2a | Edison (offline) + Pro-G | Room-tone cleanup |
| 3 | L3 | Pro-DS | De-ess |
| 4 | L4 | Auto-Tune Artist | Tune: hard but smooth |
| 5 | L5 | Pro-C 3 | Level control |
| 6 | L6 | Pro-Q 4 | Tone: bright, crisp, glossy |
| — | L7 | (none) | This style lives in the returns and doubles, and has no saturation |
| 7 | L8 | Pro-DS | Second de-ess after the air boost |

### L1 · Pro-Q 4 · trim

| Parameter | Setting | Why |
|---|---|---|
| Bands | None | This instance only sets level |
| Output Gain | **T** (from 1.5), e.g. +4.3 dB | Puts every take at −20 LUFS so every threshold below works as written |
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

**Test:** Solo LEAD and play a gap between phrases at your normal listening level. If you hear booth hiss, hum, or room tone, do both parts below. If not, skip L2a.

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
| RETUNE SPEED | **10 ms** | Hard but smooth: clearly tuned without the instant robot snap of 0 |
| FLEX-TUNE | 0 | Every note gets corrected |
| HUMANIZE | **15** | Light: keeps held notes from sounding frozen |
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
2. Play a melodic line. Notes should land clearly tuned, and long notes should sound smooth rather than frozen.
3. If a note jumps to the wrong pitch, your key or scale is off. Fix that first.

### L5 · Pro-C 3 · level control

| Parameter | Setting | Why |
|---|---|---|
| Style | Clean | Low distortion and feedforward: transparent control under constant FX |
| THRESHOLD | −22 dB | Loud lines get 4–6 dB of reduction at the calibrated level |
| AUTO (threshold) | Off | A fixed threshold makes the readings predictable |
| Audition Triggering | Off | Monitoring only |
| RATIO | 3.0:1 | Firm but natural |
| KNEE | 12 dB | Smooth onset |
| RANGE | 24 dB | High enough to never cap normal compression |
| Character | Off | No saturation in this chain |
| DRIVE / POST | Inactive (Character Off) / Post | Character is off |
| ATTACK | 5 ms | Lets consonants through, so words stay crisp |
| RELEASE | 80 ms | Recovers between words |
| AUTO (release) | Off | Fixed, predictable release |
| LOOKAHEAD | 0 ms (bottom-bar Lookahead: Off) | Not needed at this attack |
| HOLD | 0 ms | No hold needed |
| GAIN | +3.0 dB | Makes up about 60% of the reduction, so bypassing keeps the level about the same |
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
1. Play the loudest section. The gain-reduction meter should show **4–6 dB** on loud lines and **1–2 dB** on soft ones.
2. Toggle bypass. The loudness should stay within about **1 dB**. If not, adjust GAIN in 0.5 dB steps.

### L6 · Pro-Q 4 · tone

| Band | Shape | Frequency | Gain | Q | Slope | Placement | Why |
|---|---|---|---|---|---|---|---|
| 1 | Bell | 200 Hz | −1.5 dB | 0.8 | 12 dB/oct | Stereo | Clears low-mid fog so the FX don't cloud the words |
| 2 | Bell | 2.8 kHz | +1.5 dB | 1.0 | 12 dB/oct | Stereo | Crisp diction, placed just below your mic's 4 kHz bump |
| 3 | High Shelf | 10 kHz | +2.0 dB | 1.0 | 12 dB/oct | Stereo | Glossy top. Kept moderate because your mic already lifts about 12 kHz |

All three bands are static (no dynamic range). Globals as in L2: Zero Latency · Clean · Output Gain 0.0 dB · Output Pan centre · Auto Gain off · Gain Scale 100% · Phase Invert off.

**Dial it in:** A/B with bypass. The lead should sound crisper and shinier with no added harshness. If you hear harshness, see Troubleshooting.

### L8 · Pro-DS · second de-ess

| Parameter | Setting | Why |
|---|---|---|
| MODE | Single Vocal | Solo vocal |
| WIDE BAND / SPLIT BAND | WIDE BAND | Gentle; no added latency |
| THRESHOLD | −30 dB | Catches the esses the L6 shelf brought up |
| RANGE | 4 dB | Lighter touch than L3 |
| HP / LP (trigger filters) | 6.0 kHz / 14.0 kHz | Covers the boosted region |
| LOOKAHEAD | On, 10 ms | Catches ess onsets |
| STEREO LINK | 100% (scale mark) | Fully linked |
| SIDE CHAIN | In | Triggered by the vocal |
| Audition Triggering / Audition | Off / Off | Monitoring only |
| Oversampling | 2x | Cleaner gain changes |
| In: / Out: | 0.0 dB / 0.0 dB, pan centre | Unity |

**Dial it in:** On the same ess-heavy line, expect **2–4 dB** of reduction on esses only.

---

## 3. Doubles (inserts 3–6)

### 3.1 Make the copies

1. Hold Shift and drag the lead clip straight down onto an empty playlist track. Drop it at exactly the same start position. The playlist snaps to the grid, so drop it in the same grid spot. All timing offsets come from Track delay, never from clip position.
2. Open the copy's clip menu (top-left corner of the clip) → **"Make unique"**. Don't use "Make unique as sample".
3. In the new channel's settings, set **TRACK** to the double's insert (3, 4, or 5).
4. Repeat until you have three copies: DBL L (3), DBL R (4), and DBL ALIEN (5).
5. Zoom in on the starts: all four clips (lead + 3 doubles) must begin at the same point.

### 3.2 Mixer settings

| Insert | Pan | Fader | Track delay | Route | Why |
|---|---|---|---|---|---|
| 3 DBL L | −85% | 0.0 dB | 15 ms | DBL BUS only | Wide left half of the pair; its own offset makes it sound like a separate take |
| 4 DBL R | +85% | 0.0 dB | 23 ms | DBL BUS only | Wide right half; a different offset from DBL L |
| 5 DBL ALIEN | 0% | **−7.0 dB** | 31 ms | DBL BUS only | Blended low under the lead |

### 3.3 D1 · Auto-Tune Artist on each double

| Parameter | DBL L | DBL R | DBL ALIEN | Why |
|---|---|---|---|---|
| INPUT TYPE | Alto/Tenor | Alto/Tenor | Alto/Tenor | Mid-range voice |
| KEY / SCALE | Same as L4 | Same as L4 | Same as L4 | Same target notes as the lead |
| CLASSIC | Off | Off | Off | Classic would disable Formant and Throat |
| FORMANT | **On** | **On** | **On** | Needed for THROAT to work |
| THROAT | **104** | **96** | **111** | Small throat variations make the pair sound like different takes. The alien layer gets the bigger shift (Auto-Tune's own screenshots show 111) |
| TRANSPOSE | 0 | 0 | 0 | Same pitch as the lead |
| DETUNE | **+7 c** | **−8 c** | **−4 c** | Each copy sits slightly off the lead's pitch. That's what makes copies sound like real doubles |
| TRACKING | 50 | 50 | 50 | Standard |
| RETUNE SPEED | 14 ms | 18 ms | 12 ms | Each copy tunes slightly differently from the lead (10 ms) |
| FLEX-TUNE | 0 | 0 | 0 | Full correction |
| HUMANIZE | 20 | 25 | 10 | Different holds per copy |
| NATURAL VIBRATO | 0.0 | 0.0 | 0.0 | Untouched |
| Vibrato (Advanced view) | As L4 (No Vibrato, amounts 0) | As L4 | As L4 | No artificial vibrato |
| TARGETING IGNORES VIBRATO / keyboard / MIDI | As L4 | As L4 | As L4 | Same as the lead |
| Settings | As L4 (Use Low Latency off, Detune Display Cents) | As L4 | As L4 | Highest quality |

### 3.4 D2 · Pro-Q 4 on each double

**DBL L**

| Band | Shape | Frequency | Gain | Q | Slope | Placement | Why |
|---|---|---|---|---|---|---|---|
| 1 | Low Cut | 140 Hz | — | 1.0 | 18 dB/oct | Stereo | Keeps the wide pair out of the lead's low end |
| 2 | Bell | 1.2 kHz | +1.0 dB | 1.0 | 12 dB/oct | Stereo | Gives this side its own colour |
| 3 | High Shelf | 8 kHz | −1.5 dB | 1.0 | 12 dB/oct | Stereo | Slightly darker than DBL R, so the two sides differ |

**DBL R**

| Band | Shape | Frequency | Gain | Q | Slope | Placement | Why |
|---|---|---|---|---|---|---|---|
| 1 | Low Cut | 160 Hz | — | 1.0 | 18 dB/oct | Stereo | A different low corner from DBL L |
| 2 | Bell | 2.4 kHz | −1.0 dB | 1.0 | 12 dB/oct | Stereo | A different colour from DBL L |
| 3 | High Shelf | 8 kHz | −0.5 dB | 1.0 | 12 dB/oct | Stereo | A touch brighter than DBL L |

**DBL ALIEN (the band-pass)**

| Band | Shape | Frequency | Gain | Q | Slope | Placement | Why |
|---|---|---|---|---|---|---|---|
| 1 | Low Cut | 500 Hz | — | 1.0 | 24 dB/oct | Stereo | Lower edge of the band-pass |
| 2 | High Cut | 5.0 kHz | — | 1.0 | 24 dB/oct | Stereo | Upper edge: a thin "transmission" band |
| 3 | Bell | 1.6 kHz | +2.0 dB | 1.4 | 12 dB/oct | Stereo | A radio-like peak in the middle of the band |

Globals on all three D2s: Zero Latency · Clean · Output Gain 0.0 dB · Output Pan centre · Auto Gain off · Gain Scale 100% · Phase Invert off.

### 3.5 DBL BUS (insert 6)

| Order | Slot | Plugin | Settings |
|---|---|---|---|
| 1 | B1 | Pro-Q 4 trim | As L1, but Output Gain = **T − 0.5 dB**. Cancels the slight extra level of the doubles summing, so B4 sees the same level as L5 |
| 2 | B2 | Pro-Q 4 cleanup | L2's bands 2 and 3 only (Bell 320 Hz −2.5 dB Q 1.2; dynamic Bell 4.2 kHz, Range −4.0 dB, Threshold A, A/R 50%), with L2's globals. No Low Cut: each D2 already cuts higher |
| (only if L2a used) | B2a | Pro-G | Identical to L2a's Pro-G |
| 3 | B3 | Pro-DS | Identical to L3 |
| 4 | B4 | Pro-C 3 | Table below |
| 5 | B5 | Fruity Chorus | Table below |

**B4 · Pro-C 3** (same as L5 except where marked)

| Parameter | Setting | Why |
|---|---|---|
| Style | **Smooth** | Built to stay smooth and glue at low ratios: keeps the doubles steady behind the lead |
| THRESHOLD | **−24 dB** | Steady control of the summed doubles |
| RATIO | 3.0:1 | Firm, natural |
| KNEE | **18 dB** | Softer than the lead |
| RANGE | 24 dB | Never caps normal compression |
| ATTACK / RELEASE | **10 ms / 150 ms** | Slower and smoother than the lead |
| GAIN | +3.0 dB | Level-matched makeup |
| All other parameters | As L5 (Character Off, Internal side chain, Lookahead Off, HOLD 0 ms, DRY off, Oversampling 2x, In/Out 0 dB, Mix 100%) | Same clean setup |

**B5 · Fruity Chorus**

| Parameter | Setting | Why |
|---|---|---|
| DELAY | 8.0 ms | Base chorus delay, inside its 0–30 ms range |
| DEPTH | 2.0 ms | Constant but gentle pitch motion |
| STEREO | 90° | The left and right LFOs run a quarter-cycle apart, so the sides move differently and the pair stays wide |
| LFO 1 FREQ. / LFO 2 FREQ. / LFO 3 FREQ. | 0.35 Hz / 0.80 Hz / 1.70 Hz | Slow, non-repeating motion: tasteful, not seasick |
| LFO 1 WAVE / LFO 2 WAVE / LFO 3 WAVE | sin / sin / sin | Smooth motion |
| CROSS TYPE | Process HF | Only the part above the cutoff is chorused |
| CROSS CUTOFF | 250 Hz | Keeps the doubles' low end steady |
| WET ONLY | no | Dry doubles plus the chorus |

**Dial it in (DBL BUS)**
1. Solo DBL BUS. The pair should sound wide and gently moving, with the alien layer as a thin, radio-like voice in the middle.
2. B4's gain-reduction meter should show **3–5 dB** on loud lines.
3. The DBL BUS fader is set in section 6.

---

## 4. FX returns

### 4.1 FX DELAY (insert 7)

**R7.1 · Timeless 3**

| Parameter | Setting | Why |
|---|---|---|
| Delay Sync | On, **quarter-note entry** (click the sync icon at the top-right of DELAY) | Locks the echoes to your tempo |
| DELAY (Delay Offset while synced) | **75** (type the number) | 75% of a quarter note = **dotted ⅛** |
| Delay Time Pan | Centre (the L and R readouts under DELAY show the same time) | Equal times for the ping-pong |
| Delay Read Mode (tape-reel icon) | Stretch | Clean, steady echoes |
| Freeze (snowflake icon) | Off | Normal delay |
| Ping Pong (icon below Freeze) | On, starting from the **left** | Echoes bounce L → R around the dry lead |
| FEEDBACK | 38 | About 2–3 audible repeats |
| Feedback Pan | Centre (Ctrl-click) | Even repeats |
| ± invert (both) | Off | Normal polarity |
| CROSS | 100 | Full cross-feedback (Ping Pong uses cross-feedback only) |
| WIDTH | 100 | Fully stereo |
| WET | Ctrl-click to reset, then hover: it should read **0.0 dB** (if not, type 0) | Unity; amount is set by the send instead |
| WET pan ring | Centre | Balanced |
| MIX | 100 | Wet only (this is a send return) |
| Lock Mix | Off | Not needed |
| Filter 1 | Low cut (high-pass), style **Clean**, 350 Hz, Q 0.7, 12 dB/oct, pan centre | Keeps the echoes out of the lows |
| Filter 2 | High cut (low-pass), style **Clean**, 6.5 kHz, Q 0.7, 12 dB/oct, pan centre | Softer echoes behind a bright lead. Clean = no saturation |
| Filter Routing | Serial | Both filters shape every repeat |
| DRIVE / LO-FI | 0 / 0 | No saturation or degradation in this chain |
| DIFFUSE | 12 | Slight smear for a spacier, less clicky echo |
| DYNAMICS | Centre: Ctrl-click to reset, pointer at 12 o'clock | Neutral (no gating or pumping) |
| PITCH | Off | No pitch shifting in the delay |
| Input / Output | 0.0 dB / 0.0 dB, centre | Unity |
| Channel Mode | Left/Right | Normal stereo |
| Modulation | None | Steady repeats |

To make the filters: double-click the far left of the filter display for the low cut and the far right for the high cut. Then double-click each dot to type Frequency and Q, and choose the **Clean** style in its value display.

**R7.2 · Fruity Phaser**

| Parameter | Setting | Why |
|---|---|---|
| SWEEP FREQ. | 0.10 Hz | One slow sweep every 10 seconds: constant motion, never wobbly |
| FREQ. RANGE | small | The 0–2 Hz range gives fine control of slow sweeps |
| MIN DEPTH / MAX DEPTH | 0.20 / 0.75 | A wide, smooth sweep |
| STEREO | 90° (if the hint bar shows "phase", 0.25) | Left and right swirl differently, adding width |
| NR. STAGES | 6 | Classic stompbox depth: clear but not aggressive |
| FEEDBACK | 0.30 | Some resonance for a sci-fi colour |
| DRY-WET | 40% wet | Tasteful, not swamped |
| OUT GAIN | 0.0 dB | Unity |

**R7.3 · Pro-C 3 · ducker**

| Parameter | Setting | Why |
|---|---|---|
| Style | Clean | Precise, transparent ducking |
| THRESHOLD | −30 dB | Every sung word triggers it |
| AUTO (threshold) / Audition Triggering | Off / Off | Predictable |
| RATIO | 4.0:1 | Reaches the full range quickly |
| KNEE | 6 dB | Smooth onset |
| RANGE | **8 dB** | Echoes drop 8 dB under your words but never vanish: "constant but tasteful" |
| Character / DRIVE / POST | Off / inactive / Post | No saturation |
| ATTACK | 5 ms | Ducks as soon as you sing |
| RELEASE | 250 ms | Echoes swell back in the gaps |
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
1. Solo FX DELAY while LEAD plays. You should hear bouncing dotted-⅛ repeats with a slow swirl.
2. Check the L and R readouts under DELAY against section 5 for your BPM. If they don't match, turn Delay Sync off and type the ms value from section 5.
3. R7.3's meter should show **6–8 dB** of reduction while you sing and **0 dB** in the gaps.

### 4.2 FX SHIMMER (insert 8)

**R8.1 · Auto-Tune Artist · octave up**

| Parameter | Setting | Why |
|---|---|---|
| INPUT TYPE / KEY / SCALE | Alto/Tenor / same as L4 / same as L4 | Same targets as the lead |
| CLASSIC | Off | Classic would disable Transpose |
| FORMANT | **On** | Keeps the octave-up natural instead of chipmunk-like |
| THROAT | 100 | Neutral formants |
| TRANSPOSE | **+12** | One octave up: the shimmer source |
| DETUNE | 0 c | In tune |
| TRACKING | 50 | Standard |
| RETUNE SPEED | 20 ms | Smooth: the glow shouldn't snap |
| FLEX-TUNE / HUMANIZE / NATURAL VIBRATO | 0 / 0 / 0.0 | Steady glow |
| Vibrato, keyboard, MIDI, Settings | As L4 | No vibrato, Use Low Latency off |

**R8.2 · Pro-R 2**

| Parameter | Setting | Why |
|---|---|---|
| Style | Modern | Natural, clean space for the glow |
| SPACE | **3.5 s** (yellow readout) | Long, floating tail |
| Decay Rate | 100 (SPACE then shows a single time) | Uses SPACE's decay as is |
| PREDELAY | Sync **32th Note** (FabFilter's spelling), Offset 100 (type the number) | A short gap that keeps the glow behind the words; it follows your tempo |
| CHARACTER | 55 | Gentle movement in the tail (modulation starts at 50%) |
| THICKNESS | 0% (typed travel) | Minimum: no added density or saturation |
| DISTANCE | 40 | Pushes the glow back behind the lead |
| BRIGHTNESS | 60% (typed travel) | Airy |
| WIDTH | 100 | Fully stereo, surrounding the lead |
| DUCKING | 0% (typed travel) | Ducking is done by R8.3 instead |
| MIX | 100 | Wet only (this is a send return) |
| Lock Mix / Auto Gate / Freeze | Off / Off / Off | Normal reverb |
| Decay Rate EQ | One band: Low Shelf 300 Hz, decay rate 50%, Q 1.0 | Low end decays twice as fast, so the glow stays airy |
| Post EQ band 1 | Low Cut 400 Hz, Q 1.0, 24 dB/oct, Stereo | No low mud from the octave-up |
| Post EQ band 2 | High Cut 12 kHz, Q 1.0, 12 dB/oct, Stereo | Smooths any fizz from the pitch shift |
| Input / Output | 0.0 dB / 0.0 dB, centre | Unity |

To make the EQ bands: in the Decay Rate EQ, drag the curve at the far left to make the low shelf. In the Post EQ, double-click the far left for the low cut and the far right for the high cut.

**R8.3 · Pro-C 3 · ducker:** same as R7.3, except RATIO **3.0:1** · RANGE **4 dB** · ATTACK **10 ms** · RELEASE **400 ms**. It's a light duck so the glow is always there but never covers a word.

**Dial it in (FX SHIMMER)**
1. Solo FX SHIMMER. You should hear a soft, airy reverb an octave above your voice.
2. Unsolo it. The glow should be felt more than heard; you'd miss it if it were muted.
3. R8.3 should show about **4 dB** of reduction while you sing.

---

## 5. Delay and pre-delay times

The synced settings follow your tempo automatically. Use this table to check the readouts, or to type ms values if you ever turn sync off.

| BPM | Dotted ⅛, R7.1 delay (ms) | 1/32, R8.2 pre-delay (ms) |
|---|---|---|
| 130 | 346.2 | 57.7 |
| 135 | 333.3 | 55.6 |
| 140 | 321.4 | 53.6 |
| 145 | 310.3 | 51.7 |
| 150 | 300.0 | 50.0 |
| 155 | 290.3 | 48.4 |
| 160 | 281.3 | 46.9 |
| 165 | 272.7 | 45.5 |
| 170 | 264.7 | 44.1 |

For tempos between rows: dotted ⅛ = 45000 ÷ BPM; 1/32 = 7500 ÷ BPM.

---

## 6. Final balance

### 6.1 Place the lead (target: 1.5 LU under the beat)

1. Load the **Pro-L 2 meter** (settings from 1.5, but time scale **Short Term**) as the last slot on BEAT and as the last slot on LEAD.
2. Play the loudest 8 bars. Read **Beat ST** and **Lead ST**. These readings are pre-fader.
3. Set the **LEAD fader = (Beat ST + BEAT fader − 1.5) − Lead ST**.
   - Example: Beat ST −9.0, BEAT fader −6.0 dB, Lead ST −18.5 → (−9.0 − 6.0 − 1.5) − (−18.5) = **+2.0 dB**.
4. Remove both Pro-L 2 meters.

### 6.2 Doubles and returns

| Fader | Setting | Why |
|---|---|---|
| DBL L / DBL R / DBL ALIEN | 0.0 / 0.0 / −7.0 dB | Set in 3.2 |
| DBL BUS | **LEAD fader − 9.0 dB** (e.g., +2.0 → −7.0 dB) | Width and the alien layer sit around the lead, not over it |
| FX DELAY / FX SHIMMER | 0.0 dB / 0.0 dB | Amounts come from the sends (−8.0 and −16.0 dB) |

### 6.3 Final listen

- The words are clear and on top. The delay and glow are always there, and they swell in the gaps.
- Mute DBL BUS. The stereo image should collapse noticeably. Unmute.
- Mute FX DELAY and FX SHIMMER together. The lead should feel dry and close, and you should miss the space. Unmute.

---

## 7. Optional: carve the beat

Skip this section if the lead already sits clearly. It dips the beat slightly in the vocal's presence range, only while you sing.

1. Load **Pro-Q 4** on BEAT (insert 1).
2. Select LEAD → right-click BEAT's send switch → **"Sidechain to this track"**.
3. In the BEAT Pro-Q 4: gear icon → "Plugin Wrapper Settings" → "Processing" → "Connections". Map its sidechain input to insert 2 (or click "Auto map inputs").

| Band | Shape | Frequency | Gain | Q | Slope | Dynamic range | Threshold / A / R | Triggering | External side chain | Why |
|---|---|---|---|---|---|---|---|---|---|---|
| 1 | Bell | 2.5 kHz | 0.0 dB | 1.0 | 12 dB/oct | **−3.0 dB** | A / 50% / 50% | Band | **On** (click "expand >>" to see the button) | Clears room for your diction |
| 2 | Bell | 4.5 kHz | 0.0 dB | 1.4 | 12 dB/oct | **−2.0 dB** | A / 50% / 50% | Band | **On** | Clears room for your presence |

Globals: Zero Latency · Clean · Output Gain 0.0 dB · Output Pan centre · Auto Gain off · Gain Scale 100% · Phase Invert off. Spectral off on both bands.

**Dial it in:** The beat's 2.5 and 4.5 kHz regions should dip up to 3 and 2 dB **only while you sing**, and stay flat in the gaps.

---

## 8. Troubleshooting

| If it sounds… | Do this |
|---|---|
| Words get lost in the echoes | R7.3 RANGE 8 → **11 dB**, or LEAD → FX DELAY send −8 → **−10 dB** |
| The FX disappear while you sing (not "constant") | R7.3 RANGE 8 → **6 dB** |
| The echoes pile up or get muddy | R7.1 FEEDBACK 38 → **30**; Filter 1 350 → **500 Hz** |
| The swirl is too obvious or seasick | R7.2 DRY-WET 40% → **25% wet**, or SWEEP FREQ. 0.10 → **0.06 Hz** |
| The shimmer sounds chipmunky or harsh | Check R8.1 FORMANT is **on**; R8.2 Post EQ High Cut 12 → **9 kHz**; LEAD → FX SHIMMER send −16 → **−20 dB** |
| The shimmer glitches between notes | R8.1 RETUNE SPEED 20 → **35 ms**, and confirm its KEY/SCALE match L4 |
| The lead is harsh around 3–5 kHz | L2 band 3 Range −4 → **−6 dB**; L6 band 2 +1.5 → **+0.5 dB** |
| Esses spit after the air shelf | L8 THRESHOLD −30 → **−34 dB** |
| Tuning sounds robotic on long notes | L4 HUMANIZE 15 → **25** |
| The doubles sound phasey or hollow | DBL BUS fader to **LEAD − 11 dB**; DBL R Track delay 23 → **27 ms** |
| The alien layer is too loud or too buried | DBL ALIEN fader −7 → **−10 dB** or **−5 dB** |
| The chorus wobbles too much | B5 DEPTH 2.0 → **1.4 ms** |
