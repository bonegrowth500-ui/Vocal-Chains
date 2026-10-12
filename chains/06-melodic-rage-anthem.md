# Melodic Rage Anthem (#6): Lead + Doubles Vocal Chain

> *Huge, bright, arena-wide: the melody rides on top of the rage chaos instead of fighting it.*

**What this chain does**
- Keeps your melody on top and clear over chaotic rage beats. The tone is bright and airy (arena shine), with harshness controlled.
- Tunes hard but smooth, and adds light warmth: subtle saturation for thickness, no audible grit.
- Puts you in an arena-sized hall plus a ¼-note ping-pong delay. Both are **ducked**: dry and clear while you sing, blooming in the gaps.
- Builds a 4-double wall from your copy-pastes. Pair A sits wide (±100%) and Pair B inner (±50%), and every double is distinct. They're tucked low so verses stay clear, and they play the whole song.

**You'll use:** FL Studio 2024 or newer (Producer Edition) · Auto-Tune Artist · FabFilter Pro-Q 4, Pro-C 3, Pro-DS, Saturn 2, Pro-R 2, Timeless 3, and Pro-L 2 (as a meter only). Only if your booth is noisy: Edison and FabFilter Pro-G.

**Written for:** a mid-range voice on a Lewitt LCT 440 PURE in a makeshift booth, raw takes peaking around −12 to −6 dBFS, and a 2-track beat. "Your mic" in this file means the LCT 440 PURE.

**Contents:** 1. Session setup and routing · 2. Lead chain · 3. Doubles · 4. FX returns · 5. Delay and pre-delay times · 6. Final balance · 7. Optional: carve the beat · 8. Troubleshooting

---

## 1. Session setup and routing

### 1.1 How to enter exact values

| Where | How |
|---|---|
| FabFilter knobs | Double-click the knob, type the number, press Enter. A plain number sets the value in the knob's own unit: "35" on a % knob is 35%, "-22" on a dB knob is −22 dB. "1k" = 1000 Hz. Ctrl-click resets a knob. |
| FabFilter knobs with no published unit | Type a percentage with the % sign, like "65%". That puts the knob exactly 65% of the way through its travel. This file only does this where it says "typed travel". |
| FabFilter EQ bands and filters | To add a band, double-click the display background where you want it (a single click only deselects while a band is selected). Double-click at the far left or far right for a Low Cut or High Cut; drag the curve at either end for a shelf. Double-click the band's dot, then type Frequency, press Tab, type Gain, press Tab, type Q. Cut bands have no Gain: type Frequency, then Tab to Q. Ctrl+Alt-click a dot to change its shape. Alt+Shift-click a dot to change its slope. |
| Auto-Tune Artist | Drag each control until its readout shows the value. |
| FL mixer (fader, pan, send level) | Right-click → "Type in value". In the entry box, pick the context-aware unit (dB for faders and send knobs, % for pan), not the normalized one, then type the value. |
| On a Mac | Use Cmd where this file says Ctrl, and Option where it says Alt. |

### 1.2 Mixer map

| Insert | Name | What's on it | Pan | Track delay | Routes to |
|---|---|---|---|---|---|
| 1 | BEAT | Optional carve (section 7) | 0% | — | Master |
| 2 | LEAD | L1–L8 (section 2) | 0% | — | Master + sends to 8 and 9 (the sends also key the duckers) (+ a sidechain link to 1 if you do section 7) |
| 3 | DBL A-L | D1, D2 | −100% | 17 ms | 7 only |
| 4 | DBL A-R | D1, D2 | +100% | 23 ms | 7 only |
| 5 | DBL B-L | D1, D2 | −50% | 11 ms | 7 only |
| 6 | DBL B-R | D1, D2 | +50% | 29 ms | 7 only |
| 7 | DBL BUS | B1–B6 | 0% | — | Master + send to 8 |
| 8 | FX HALL | R8.1–R8.2 | 0% | — | Master |
| 9 | FX DELAY | R9.1–R9.2 | 0% | — | Master |

Every insert's stereo separation knob stays at centre (off). Faders: BEAT is set in 1.3, the doubles in 3.2, everything else in section 6.

### 1.3 Build the session

1. Open the Mixer menu → "Plugin delay compensation" → make sure **"Automatic"** is ticked. It keeps every insert in time, including sends and sidechains.
2. Put the beat on its own playlist track. In its channel settings, set **TRACK** to **1**. Put your lead take on another playlist track, with TRACK set to **2**. Then set FL's project tempo to the beat's BPM: every synced delay and pre-delay in this file follows it.
3. Name inserts 1–9 as in the map. Right-click each insert → "Rename, color & icon..." (F2).
4. **Beat headroom.** Load Pro-L 2 in BEAT's first slot with the meter settings from 1.5 (TP metering on), and play the beat's loudest part. Read the maximum true peak shown above its output meter. Set the BEAT fader to **−6.0 dB minus that reading** (a peak of −0.4 dB gives −5.6 dB), so the beat peaks at about −6.0 dBFS. Then remove the meter.
5. Run the L2a **Test** now. If you hear room tone, do L2a Part 1 (Edison) now, **before** you make the doubles, so the copies start from the cleaned take (3.1 step 6 checks this). Part 2 (Pro-G) goes in later with the lead chain.
6. Make the doubles (section 3.1).
7. Do the routing in 1.4, then calibrate in 1.5.

### 1.4 Routing walkthrough

1. **Doubles go to DBL BUS only.** Select insert 3 (DBL A-L). Left-click the send switch (the arrow at the bottom) of insert 7 (DBL BUS). Then left-click the **Master** track's send switch to turn that route off. Repeat for inserts 4, 5, and 6.
2. **LEAD sends.** Select insert 2 (LEAD) and left-click the send switches of inserts 8 and 9. With LEAD still selected, right-click each new send knob (it sits on the destination's send switch) → "Type in value": insert 8 = **−10.0 dB**, insert 9 = **−11.0 dB**. LEAD keeps its Master route. FL sends are post-fader, so the effects follow your LEAD fader.
3. **DBL BUS send to the hall.** Select insert 7 (DBL BUS) and left-click insert 8's send switch. Right-click the send knob → "Type in value" → **−14.0 dB**. DBL BUS keeps its Master route. This puts the wall inside the arena too.
4. **The ducking needs no extra link.** In FL, every send also carries a sidechain feed, so the LEAD sends from step 2 already let the duckers on inserts 8 and 9 hear your voice. Don't use "Sidechain to this track" on these sends: that option turns a send into a sidechain-only link (its level drops to 0): the duckers could still hear your voice, but no audio would reach the effects.
5. **Pans and Track delays.** Right-click each pan knob → "Type in value": insert 3 = −100%, insert 4 = +100%, insert 5 = −50%, insert 6 = +50%. On each double's insert, click the clock icon (**Track delay**) → "Set in ms (milliseconds)": insert 3 = **17**, insert 4 = **23**, insert 5 = **11**, insert 6 = **29**.
6. **Feed the duckers.** When you load Pro-C 3 on inserts 8 and 9 (R8.2, R9.2), open each one's gear icon → **"Plugin Wrapper Settings"** → **"Processing"** → **"Connections"**. Right-click the plugin's sidechain input number and choose insert 2 (LEAD), or click **"Auto map inputs"**. Then, in Pro-C 3, set **Side Chain Input** to **External**. On insert 8, pick LEAD by hand: DBL BUS feeds that return too, and only your lead should trigger the ducking.
7. Both returns stay routed to Master (the default).

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
2. Read the **Integrated** loudness, for example −24.0 LUFS.
3. Work out **T = −20.0 − reading**. For example, −20.0 − (−24.0) = **+4.0 dB**. You'll type T into L1 and use it again on DBL BUS.
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
| 5 | L5 | Pro-C 3 | Level control that keeps the melody on top |
| 6 | L6 | Pro-Q 4 | Tone: bright and airy |
| 7 | L7 | Saturn 2 | Light warmth |
| 8 | L8 | Pro-DS | Second de-ess after the air boost and warmth |

### L1 · Pro-Q 4 · trim

| Parameter | Setting | Why |
|---|---|---|
| Bands | None | This instance only sets level |
| Output Gain | **T** (from 1.5), e.g. +4.0 dB | Puts every take at −20 LUFS so every threshold and drive below works as written |
| Processing Mode | Zero Latency | No bands to process, so no latency needed |
| Character | Clean | The warmth comes from L7, where you can control it |
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
| A (attack) | 50% (auto, panel closed) | 50% = automatic attack |
| R (release) | 50% (auto, panel closed) | 50% = automatic release |
| Triggering | Band | Reacts to the 4.2 kHz region itself |
| External side chain | Off | Triggered by the vocal itself |
| Spectral | Off | Spectral mode adds about 100 ms of latency; not needed |

| Globals | Setting | Why |
|---|---|---|
| Processing Mode | Zero Latency | No added latency |
| Character | Clean | Warmth is controlled in L7 |
| Output Gain | 0.0 dB | Level is already set by L1 |
| Output Pan | Centre (L/R mode) | Mono vocal stays centred |
| Auto Gain | Off | Keeps levels predictable |
| Gain Scale | 100% (type 100) | Bands at their stated gain |
| Phase Invert (Ø) | Off | Keeps polarity |

**Dial it in**
1. Double-click the far left of the display to create a Low Cut. Double-click its dot, type 85, Tab to Q and type 1, then set the slope to 18 dB/oct (Alt+Shift-click the dot to step through slopes).
2. Double-click the display background around 300 Hz to add a bell. Double-click its dot and type 320, Tab, −2.5, Tab, 1.2.
3. Double-click the display background around 4 kHz to add another bell. Double-click its dot and type 4.2k, Tab, 0, Tab, 2. Drag the dynamic range ring around its GAIN knob down to **−4.0 dB**. Leave the band's dynamics panel (**expand >>**) closed: closed, its threshold, attack, and release run in auto mode, which is exactly the table's A / 50% / 50%.
4. Play the loudest, brightest lines. Band 3 should dip **0–3 dB on harsh notes only** and stay still on soft lines.

### L2a · only if room tone is audible

**Test:** If you already ran this Test in 1.3, don't repeat it: if it was yes, Part 1 is done, so go straight to Part 2; if it was no, skip L2a. Otherwise, solo LEAD (right-click its mute switch), play a gap between phrases at your normal listening level, then Ctrl+right-click any mute switch to unsolo. If you hear booth hiss, hum, or room tone, do both parts below. If not, skip L2a. Four doubles add up any room tone in your take, so check carefully.

**Part 1: Edison (offline, before you copy the doubles).** Skip this part if you already did it in 1.3, unless 3.1 step 6 sent you here to clean the doubles: then do every step on each double's clip and channel instead of the lead's. If you made the doubles without doing this part first, delete them now and make them again in 3.1 afterwards. Open the lead clip's menu (top-left corner of the clip) → **"Edit sample"** (E). Edison opens with your take.
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
5. Solo the cleaned track and play a gap: the hiss should be gone. For LEAD, use a plain solo (right-click its mute switch); for a double, Alt+left-click its mute switch so DBL BUS still passes it. If the hiss is still there, select that clip's Audio Clip channel in the Channel rack and right-click Edison's **Send sample to Playlist** button (it replaces the selected Audio Clip with the cleaned take), then play the gap again. Then Ctrl+right-click any mute switch to unsolo.

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
| RETUNE SPEED | **8 ms** | Hard but smooth: the melody locks to pitch without snapping between notes |
| FLEX-TUNE | 0 | Every note gets corrected |
| HUMANIZE | **18** | Light: long anthem notes don't sound frozen |
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
2. Play a sustained melody. Notes should land clearly tuned, and long notes should sound smooth rather than frozen.
3. If a note jumps to the wrong pitch, your key or scale is off. Fix that first.

### L5 · Pro-C 3 · level control

| Parameter | Setting | Why |
|---|---|---|
| Style | **Versatile** | Tight and smooth at shorter attacks: keeps a melodic lead steady and on top |
| THRESHOLD | −22 dB | Loud lines get 4–6 dB of reduction at the calibrated level |
| AUTO (threshold) | Off | A fixed threshold makes the readings predictable |
| Audition Triggering | Off | Monitoring only |
| RATIO | **3.5:1** | Firm control so the melody holds its place over a busy beat |
| KNEE | 12 dB | Smooth onset |
| RANGE | 24 dB | High enough to never cap normal compression |
| Character | Off | Warmth comes from L7 |
| DRIVE / POST | Inactive (Character Off) / Post | Character is off |
| ATTACK | **8 ms** | Lets the front of each word through, so the melody keeps its articulation |
| RELEASE | **100 ms** | Smooth recovery across sustained notes |
| AUTO (release) | Off | Fixed, predictable release |
| LOOKAHEAD | 0 ms (bottom-bar Lookahead: Off) | Not needed at this attack |
| HOLD | 0 ms | No hold needed |
| GAIN | **+3.5 dB** | Makes up about 60% of the reduction, so bypassing keeps the level about the same |
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
1. Play the loudest section. The gain-reduction meter should show **4–6 dB** on loud lines.
2. Turn on **Show Input Level** in Pro-C 3's Help menu. On a loud section, compare the floating loudness indicators (Momentary loudness) on the input and output meters: they should stay within about **1 dB** of each other. If not, adjust GAIN in 0.5 dB steps.

### L6 · Pro-Q 4 · tone

| Band | Shape | Frequency | Gain | Q | Slope | Placement | Why |
|---|---|---|---|---|---|---|---|
| 1 | Bell | 250 Hz | −1.0 dB | 1.0 | 12 dB/oct | Stereo | Clears low-mid weight so the melody floats |
| 2 | Bell | 3.0 kHz | +1.5 dB | 1.0 | 12 dB/oct | Stereo | Presence that cuts through rage synths |
| 3 | High Shelf | 11 kHz | **+3.0 dB** | 1.0 | 12 dB/oct | Stereo | Arena shine and air. L8 controls the esses it brings up |

All three bands are static. Globals as in L2: Zero Latency · Clean · Output Gain 0.0 dB · Output Pan centre · Auto Gain off · Gain Scale 100% · Phase Invert off.

**Dial it in:** A/B with bypass. With the EQ on, the lead should sound brighter, airier, and more present, with no added harshness.

### L7 · Saturn 2 · light warmth

| Parameter | Setting | Why |
|---|---|---|
| Bands | 1 (no crossovers) | Even warmth across the whole voice |
| Style | **Warm Tape** (in the **Tape** section of the Style menu) | Gentle tape saturation: thickness, not grit |
| DRIVE | **15%** (typed travel) | Light: you feel more body, but don't hear distortion |
| DRIVE pan ring | Centre | Even on both channels |
| MIX (band) | 100% (typed travel) | Full effect at a low drive |
| FEEDBACK | 0% (typed travel) | No feedback colouring |
| FREQ | 1k (inactive at FEEDBACK 0%) | Feedback is off |
| DYNAMICS | Centre: Ctrl-click to reset, pointer at 12 o'clock | Neutral |
| TONE (four sliders: bass, mid, treble, presence) | Centre: Ctrl-click each to reset | Flat. Tone is shaped in L6 |
| LEVEL | **−1.0 dB** | Offsets the small loudness gain from the drive |
| LEVEL pan ring | Centre | Balanced |
| Band power | On | The band is active |
| Input / Output (global) | 0.0 dB / 0.0 dB | Unity |
| Mix (global) | 100% (type 100) | Full effect |
| High Quality | Good | Oversampled saturation: less harsh aliasing |
| Linear Phase | Off | One band, so no crossovers to correct |
| Channel Mode | Stereo | Normal |
| FB (unrestricted feedback) | Off | Safe |
| Modulation | None (no sources added) | Steady warmth |

**Dial it in**
1. Toggle bypass. With L7 on, the lead should feel slightly thicker and warmer, with **no audible grit**.
2. Check the level with the Pro-L 2 meter (settings from 1.5) right after L7: reset it and play 8 loud bars with L7 on, then reset and play the same 8 bars with L7 bypassed. The two Integrated readings should be within about **1 dB**. If not, adjust LEVEL in 0.5 dB steps. Remove the meter.

### L8 · Pro-DS · second de-ess

| Parameter | Setting | Why |
|---|---|---|
| MODE | Single Vocal | Solo vocal |
| WIDE BAND / SPLIT BAND | WIDE BAND | Gentle; no added latency |
| THRESHOLD | −30 dB | Catches the esses the air shelf and warmth brought up |
| RANGE | 4 dB | Lighter touch than L3 |
| HP / LP (trigger filters) | 6.5 kHz / 14.0 kHz | Covers the boosted air region |
| LOOKAHEAD | On, 10 ms | Catches ess onsets |
| STEREO LINK | 100% (scale mark) | Fully linked |
| SIDE CHAIN | In (not Ext) | Triggered by the vocal |
| Audition Triggering / Audition | Off / Off | Monitoring only |
| Oversampling | 2x | Cleaner gain changes |
| In: / Out: | 0.0 dB / 0.0 dB, pan centre | Unity |

**Dial it in:** On an ess-heavy line, expect **2–4 dB** of reduction on esses only.

---

## 3. Doubles (inserts 3–7)

### 3.1 Make the copies

If the copies already exist, skip to 3.2.

1. Hold Shift and drag the lead clip straight down onto an empty playlist track. Drop it at exactly the same start position. The playlist snaps to the grid, so drop it in the same grid spot. All timing offsets come from Track delay, never from clip position.
2. Open the copy's clip menu (top-left corner of the clip) → **"Make unique"**. Don't use "Make unique as sample".
3. In the new channel's settings, set **TRACK** to the double's insert (3, 4, 5, or 6).
4. Repeat until you have four copies: DBL A-L (3), DBL A-R (4), DBL B-L (5), and DBL B-R (6).
5. Zoom in on the starts: all five clips (lead + 4 doubles) must begin at the same point. If one doesn't, turn snapping off (the magnet icon in the playlist toolbar) and drag it into line.
6. If you did L2a Part 1, Alt+left-click one double's mute switch (this solos it together with what it's routed to) and play a gap: it should be as clean as the lead. Then Ctrl+right-click any mute switch to unsolo. If the hiss was back, go through L2a Part 1 again for each double, on that double's clip and channel.

### 3.2 Mixer settings

Pans and Track delays were set in 1.4. The faders are new here.

| Insert | Pan | Fader | Track delay | Route | Why |
|---|---|---|---|---|---|
| 3 DBL A-L | −100% | 0.0 dB | 17 ms | DBL BUS only | Pair A: the wide wall, left |
| 4 DBL A-R | +100% | 0.0 dB | 23 ms | DBL BUS only | Pair A: the wide wall, right |
| 5 DBL B-L | −50% | **−3.0 dB** | 11 ms | DBL BUS only | Pair B: the inner wall, left. Quieter, so the wall stays tucked |
| 6 DBL B-R | +50% | **−3.0 dB** | 29 ms | DBL BUS only | Pair B: the inner wall, right |

Every double has its own timing offset, so no two copies line up.

### 3.3 D1 · Auto-Tune Artist on each double

| Parameter | DBL A-L | DBL A-R | DBL B-L | DBL B-R | Why |
|---|---|---|---|---|---|
| INPUT TYPE | Alto/Tenor | Alto/Tenor | Alto/Tenor | Alto/Tenor | Mid-range voice |
| KEY / SCALE | Same as L4 | Same as L4 | Same as L4 | Same as L4 | Same target notes as the lead |
| CLASSIC | Off | Off | Off | Off | Classic would disable Formant and Throat |
| FORMANT | **On** | **On** | **On** | **On** | Needed for THROAT to work |
| THROAT | **104** | **96** | **107** | **94** | Four different throat lengths: four different "singers" |
| TRANSPOSE | 0 | 0 | 0 | 0 | Same pitch as the lead |
| DETUNE | **+8 c** | **−9 c** | **+5 c** | **−4 c** | Each copy sits slightly off pitch, so the wall sounds like real stacked takes |
| TRACKING | 50 | 50 | 50 | 50 | Standard |
| RETUNE SPEED | 10 ms | 12 ms | 14 ms | 16 ms | Each copy tunes a little differently from the lead (8 ms) |
| FLEX-TUNE | 0 | 0 | 0 | 0 | Full correction |
| HUMANIZE | 20 | 22 | 24 | 26 | Different holds per copy |
| NATURAL VIBRATO | 0.0 | 0.0 | 0.0 | 0.0 | Untouched |
| Vibrato (Advanced view) | As L4 (No Vibrato, amounts 0) | As L4 | As L4 | As L4 | No artificial vibrato |
| TARGETING IGNORES VIBRATO / keyboard / MIDI | As L4 | As L4 | As L4 | As L4 | Same as the lead |
| Settings | As L4 (Use Low Latency off, Detune Display Cents) | As L4 | As L4 | As L4 | Highest quality |

### 3.4 D2 · Pro-Q 4 on each double

**DBL A-L**

| Band | Shape | Frequency | Gain | Q | Slope | Placement | Why |
|---|---|---|---|---|---|---|---|
| 1 | Low Cut | 180 Hz | — | 1.0 | 18 dB/oct | Stereo | Keeps the wide pair out of the lead's low end |
| 2 | High Shelf | 10 kHz | −2.0 dB | 1.0 | 12 dB/oct | Stereo | Slightly darker than the lead, so the lead stays the brightest |

**DBL A-R**

| Band | Shape | Frequency | Gain | Q | Slope | Placement | Why |
|---|---|---|---|---|---|---|---|
| 1 | Low Cut | 190 Hz | — | 1.0 | 18 dB/oct | Stereo | A different low corner from A-L |
| 2 | High Shelf | 9 kHz | −2.0 dB | 1.0 | 12 dB/oct | Stereo | Darker from a different corner |
| 3 | Bell | 1.5 kHz | +0.5 dB | 1.0 | 12 dB/oct | Stereo | A slightly different colour from A-L |

**DBL B-L**

| Band | Shape | Frequency | Gain | Q | Slope | Placement | Why |
|---|---|---|---|---|---|---|---|
| 1 | Low Cut | 220 Hz | — | 1.0 | 18 dB/oct | Stereo | The inner pair stays lighter in the lows |
| 2 | Bell | 2.0 kHz | −1.5 dB | 1.0 | 12 dB/oct | Stereo | Makes room for the lead's 3 kHz presence |

**DBL B-R**

| Band | Shape | Frequency | Gain | Q | Slope | Placement | Why |
|---|---|---|---|---|---|---|---|
| 1 | Low Cut | 240 Hz | — | 1.0 | 18 dB/oct | Stereo | A different low corner from B-L |
| 2 | Bell | 2.6 kHz | −1.5 dB | 1.0 | 12 dB/oct | Stereo | Makes room for the lead, at a different spot from B-L |

Globals on all four D2s: Zero Latency · Clean · Output Gain 0.0 dB · Output Pan centre · Auto Gain off · Gain Scale 100% · Phase Invert off.

**Dial it in (D1 and D2)**
1. Alt-solo each double in turn (it plays through DBL BUS). It should follow your melody, tuned to the same notes as the lead.
2. Compare them. All four should sound like slightly different singers (THROAT), and Pair B a little lighter and quieter than Pair A. DETUNE's few cents are too small to judge here; step 3 checks them on the readout.
3. Check each D1's DETUNE readout against the table (+8 c, −9 c, +5 c, −4 c). When you're done, unsolo (Ctrl+right-click any mute switch).

### 3.5 DBL BUS (insert 7)

| Order | Slot | Plugin | Settings |
|---|---|---|---|
| 1 | B1 | Pro-Q 4 trim | As L1, but Output Gain = **T − 3.0 dB**. Cancels the extra level of four doubles summing, so B4 sees the same level as L5. It's a starting point: do Dial it in step 1 right after loading B1, before B2 |
| 2 | B2 | Pro-Q 4 cleanup | L2's bands 2 and 3 only (Bell 320 Hz −2.5 dB Q 1.2; dynamic Bell 4.2 kHz, Range −4.0 dB, Threshold A, A/R 50%), with L2's globals. No Low Cut: each D2 already cuts higher |
| (only if L2a used) | B2a | Pro-G | Identical to L2a's Pro-G |
| 3 | B3 | Pro-DS | Identical to L3 |
| 4 | B4 | Pro-C 3 | Table below |
| 5 | B5 | Saturn 2 | Table below |
| 6 | B6 | Pro-Q 4 | Table below |

**B4 · Pro-C 3** (same as L5 except where marked)

| Parameter | Setting | Why |
|---|---|---|
| Style | **Smooth** | Built to stay smooth and glue at low ratios: keeps the wall steady |
| THRESHOLD | **−24 dB** | Steady control of the summed wall |
| RATIO | **3.0:1** | Gentle glue |
| KNEE | **18 dB** | Softer than the lead |
| RANGE | 24 dB | Never caps normal compression |
| ATTACK / RELEASE | **10 ms / 150 ms** | Slower and smoother than the lead |
| GAIN | **+3.0 dB** | Level-matched makeup |
| All other parameters | As L5 (Character Off, Internal side chain, Lookahead Off, HOLD 0 ms, DRY off, Oversampling 2x, In/Out 0 dB, Mix 100%) | Same clean setup |

**B5 · Saturn 2** (same as L7 except where marked)

| Parameter | Setting | Why |
|---|---|---|
| Style | Warm Tape (in the **Tape** section of the Style menu) | The wall shares the lead's light warmth |
| DRIVE | **12%** (typed travel) | A touch lighter than the lead, so the wall stays smooth |
| LEVEL | −1.0 dB | Offsets the small loudness gain |
| All other parameters | As L7 (1 band, MIX 100%, FEEDBACK 0%, FREQ 1k, DYNAMICS centre, TONE flat, pans centre, High Quality Good, Linear Phase off, Stereo, FB off, no modulation) | Same setup |

**B6 · Pro-Q 4**

| Band | Shape | Frequency | Gain | Q | Slope | Placement | Why |
|---|---|---|---|---|---|---|---|
| 1 | High Shelf | 9 kHz | −1.5 dB | 1.0 | 12 dB/oct | Stereo | The lead stays the brightest thing; the wall sits behind it |

Globals: Zero Latency · Clean · Output Gain 0.0 dB · Output Pan centre · Auto Gain off · Gain Scale 100% · Phase Invert off.

**DBL BUS send:** → FX HALL **−14.0 dB** (set in 1.4).

**Dial it in (DBL BUS)**
1. **Check the bus level right after you load B1**, before B2 and the rest, with nothing soloed: put the Pro-L 2 meter (settings from 1.5) in the next slot, click its loudness reset button, and play the whole take. Integrated should read **−20.0 LUFS (±0.5)**, the same level LEAD has after L1. If it doesn't, add (−20.0 − reading) to B1's Output Gain: a reading of −21.5 means +1.5 dB. Then remove the meter.
2. Alt-solo DBL BUS. You should hear a wide, smooth wall of four voices, slightly darker than the lead.
3. B4's gain-reduction meter should show **5–7 dB** on loud lines: a little more than L5, because B4's threshold is 2 dB lower.
4. Unsolo (Ctrl+right-click any mute switch). The DBL BUS fader is set in section 6.

---

## 4. FX returns

### 4.1 FX HALL (insert 8)

**R8.1 · Pro-R 2**

| Parameter | Setting | Why |
|---|---|---|
| Style | Modern | FabFilter's style for natural, realistic spaces: a believable arena without vintage shimmer |
| SPACE | **3.4 s** (yellow readout) | Arena-sized tail |
| Decay Rate | 100 (SPACE then shows a single time) | Uses SPACE's decay as is |
| PREDELAY | Sync **16th Note**: click the small sync icon above PREDELAY and choose it. The knob then sets the Offset: type 100 | A clear gap before the hall: the words land first. It follows your tempo |
| CHARACTER | 40 | A little life in the tail, below the 50% point where modulation starts |
| THICKNESS | 0% (typed travel) | Minimum: no added density or saturation in the reverb |
| DISTANCE | 55 | Longer build-up and a more diffuse tail: big-room feel |
| BRIGHTNESS | **65%** (typed travel) | Bright arena |
| WIDTH | 100 | Fully stereo |
| DUCKING | 0% (typed travel) | Ducking is done by R8.2 instead |
| MIX | 100 | Wet only (this is a send return) |
| Lock Mix / Auto Gate / Freeze | Off / Off / Off | Normal reverb |
| Decay Rate EQ | One band: Low Shelf 250 Hz, decay rate 70%, Q 1.0 | Lows decay faster, so the arena stays clear, not muddy |
| Post EQ band 1 | Low Cut 220 Hz, Q 1.0, 24 dB/oct, Stereo | No low mud |
| Post EQ band 2 | High Shelf 9 kHz, −2.0 dB, Q 1.0, Stereo | Tames sizzle in a bright hall |
| Post EQ band 3 | High Cut 15 kHz, Q 1.0, 12 dB/oct, Stereo | Smooth top |
| Input / Output | 0.0 dB / 0.0 dB, centre | Unity |

To make the EQ bands: in the Decay Rate EQ (the blue curve), drag the curve at the far left to make the low shelf. In the Post EQ (the yellow curve), double-click the far left for the low cut, drag the curve at the far right for the shelf, and double-click the far right for the high cut. Then double-click each dot to type its values (Tab steps through the fields; cut bands have no Gain).

**R8.2 · Pro-C 3 · ducker**

| Parameter | Setting | Why |
|---|---|---|
| Style | Clean | Precise, transparent ducking |
| THRESHOLD | −30 dB | Every sung word triggers it |
| AUTO (threshold) / Audition Triggering | Off / Off | Predictable |
| RATIO | **6.0:1** | Reaches the full range quickly |
| KNEE | 6 dB | Smooth onset |
| RANGE | **10 dB** | Dry and clear while you sing; the hall blooms when you stop |
| Character / DRIVE / POST | Off / inactive / Post | No saturation on the ducker |
| ATTACK | 10 ms | Ducks smoothly as you start a phrase |
| RELEASE | **300 ms** | The hall swells up in the gaps instead of snapping back |
| AUTO (release) | Off | Predictable |
| LOOKAHEAD | 0 ms (bottom-bar Lookahead: Off) | Not needed |
| HOLD | 50 ms | No flutter between words of a phrase |
| GAIN / AUTO (gain) / pan ring | 0.0 dB / Off / centre | No makeup on a ducker |
| DRY | 0% (typed travel, fully off) | Ducked signal only |
| Side Chain Input | **External** (fed from LEAD: map it as in 1.4 step 6) | Ducks to your voice |
| LEVEL (side chain) / Audition | 0.0 dB / Off | Unity |
| STEREO LINK | 100% (scale mark) | Linked ducking |
| Side-chain EQ | No active bands | Full-range trigger |
| Oversampling | 2x | Clean gain changes |
| Input / Output | 0.0 dB / 0.0 dB, centre | Unity |
| Mix | 100 | Full effect |

**Dial it in (FX HALL)**
1. Alt-solo FX HALL and play. Along with your lead you should hear a big, bright, long arena tail.
2. Unsolo it. R8.2 should show about **10 dB** of reduction while you sing. When you stop, the hall should bloom up. If it shows no reduction at all, recheck the side-chain mapping (1.4 step 6).

### 4.2 FX DELAY (insert 9)

**R9.1 · Timeless 3**

| Parameter | Setting | Why |
|---|---|---|
| Delay Sync | On: click the sync icon at the top-right of DELAY and choose its **quarter-note** entry | Locks the echoes to your tempo |
| DELAY (Delay Offset while synced) | **100** (type the number) | Exactly a **¼ note** |
| Delay Time Pan | Centre (the L and R readouts under DELAY show the same time) | Equal times for the ping-pong |
| Delay Read Mode (tape-reel icon) | Stretch | Clean, steady echoes |
| Freeze (snowflake icon) | Off | Normal delay |
| Ping Pong (icon below Freeze) | On, starting from the **right** (hover over the icon to see its setting; if it offers no start-side choice, just switch it on) | Wide bouncing echoes. The earliest doubles sit left (11 and 17 ms), so the first echo lands right to balance them |
| FEEDBACK | 35 | About 2–3 repeats |
| Feedback Pan | Centre (Ctrl-click) | Even repeats |
| ± invert (both) | Off | Normal polarity |
| CROSS | 100 | Full cross-feedback (Ping Pong uses cross-feedback only) |
| WIDTH | 100 | Arena-wide |
| WET | Ctrl-click to reset, then hover: it should read **0.0 dB** (if it shows another dB value, type 0) | Unity; amount is set by the send instead |
| WET pan ring | Centre | Balanced |
| MIX | 100 | Wet only (this is a send return) |
| Lock Mix | Off | Not needed |
| Filter 1 | Low cut (high-pass), style **Clean**, 300 Hz, Q 0.7, 12 dB/oct, pan centre | Keeps the echoes out of the lows |
| Filter 2 | High cut (low-pass), style **Clean**, 7.0 kHz, Q 0.7, 12 dB/oct, pan centre | Bright but not brittle |
| Filter Routing | Serial | Both filters shape every repeat |
| DRIVE / LO-FI | Off / Off (amounts 0 / 0) | Clean echoes; the warmth is on the voice |
| DIFFUSE | **On**, 20 | Softens the repeats so they blend into the arena |
| DYNAMICS | Off (amount at centre: Ctrl-click to reset, pointer at 12 o'clock) | Neutral |
| PITCH | Off | No pitch shifting |
| Input / Output | 0.0 dB / 0.0 dB, centre | Unity |
| Channel Mode | Left/Right | Normal stereo |
| Auto Mute Self-Osc (bottom bar) | On | Silences any filter ringing once the input goes quiet. The Clean filters here shouldn't ring, so it's only a safety net |
| Modulation | None | Steady repeats |

To make the filters: double-click the far left of the filter display for the low cut and the far right for the high cut. Then double-click each dot to type Frequency and Q, and choose the **Clean** style in the filter's value display (the settings panel for the selected filter). The five effect knobs (DRIVE, LO-FI, DIFFUSE, DYNAMICS, PITCH) switch on or off when you click the power icon at the knob's centre; dragging sets the amount.

**R9.2 · Pro-C 3 · ducker:** same as R8.2 (map its side chain as in 1.4 step 6), except RANGE **12 dB** · ATTACK **5 ms** · RELEASE **250 ms** · HOLD **40 ms**. The echoes duck a little deeper than the hall and come back a little faster.

**Dial it in (FX DELAY)**
1. Alt-solo FX DELAY and play. Behind your lead you should hear wide, soft ¼-note ping-pong repeats.
2. Check the L and R readouts under DELAY against section 5 for your project tempo. If they don't match, turn Delay Sync off and type the ms value from section 5.
3. Unsolo it. R9.2 should show about **12 dB** of reduction while you sing, with the echoes blooming in the gaps. If it shows no reduction at all, recheck the side-chain mapping (1.4 step 6).

---

## 5. Delay and pre-delay times

The synced settings follow the project tempo you set in 1.3. Use this table to check the readouts, or to type ms values if you ever turn sync off.

| BPM | ¼, R9.1 delay (ms) | 1/16, R8.1 pre-delay (ms) |
|---|---|---|
| 130 | 461.5 | 115.4 |
| 135 | 444.4 | 111.1 |
| 140 | 428.6 | 107.1 |
| 145 | 413.8 | 103.4 |
| 150 | 400.0 | 100.0 |
| 155 | 387.1 | 96.8 |
| 160 | 375.0 | 93.8 |
| 165 | 363.6 | 90.9 |
| 170 | 352.9 | 88.2 |

For any other tempo: ¼ = 60000 ÷ BPM; 1/16 = 15000 ÷ BPM.

---

## 6. Final balance

### 6.1 Place the lead (target: 1.5 LU under the beat)

1. Load the **Pro-L 2 meter** (settings from 1.5) as the last slot on BEAT and as the last slot on LEAD. On each, set the max readout above the loudness meter to **Max S** (Max Short Term), then click the loudness reset button.
2. Play the loudest 8 bars where you sing all the way through (a hook, for example) once. Read **Max S** on each meter: that's **Beat ST** on BEAT and **Lead ST** on LEAD. These readings are pre-fader.
3. Set the **LEAD fader = (Beat ST + BEAT fader − 1.5) − Lead ST**. BEAT fader is the value you set in 1.3, not the −6.0 dBFS peak target.
   - Example: Beat ST −9.0, BEAT fader −4.5 dB, Lead ST −16.5 → (−9.0 − 4.5 − 1.5) − (−16.5) = **+1.5 dB**.
4. If the result is more than the LEAD fader can reach, pull the BEAT fader down by another 3.0 dB and redo the formula with the new BEAT fader value. Repeat if needed.
5. Remove both Pro-L 2 meters.
6. Re-check R8.2 and R9.2 against their section 4 readings: they hear LEAD after its fader. If the LEAD fader ended up below 0 dB and a ducker now shows less reduction than its target, lower that ducker's THRESHOLD by the same number of dB.

### 6.2 Doubles and returns

| Fader | Setting | Why |
|---|---|---|
| DBL A-L / DBL A-R / DBL B-L / DBL B-R | 0.0 / 0.0 / −3.0 / −3.0 dB | Set in 3.2 |
| DBL BUS | **LEAD fader − 10.0 dB** (e.g., +1.5 → −8.5 dB) | The wall is tucked low, so verses stay clear |
| FX HALL / FX DELAY | 0.0 dB / 0.0 dB | Amounts come from the sends (LEAD −10.0 / −11.0 dB; DBL BUS → HALL −14.0 dB) |

### 6.3 Final listen

- The melody rides clearly on top of the beat. While you sing it's dry and clear; in the gaps, the arena opens up.
- The wall makes the hooks sound huge but never covers the words in the verses.
- Mute DBL BUS. The vocal should shrink to a single voice. Unmute.
- Mute FX HALL and FX DELAY together. The arena should disappear and the lead should feel close. Unmute.

---

## 7. Optional: carve the beat

Skip this section if the lead already sits clearly. It dips the beat slightly in the vocal's presence range, only while you sing.

1. Load **Pro-Q 4** on BEAT (insert 1).
2. Select LEAD → right-click BEAT's send switch → **"Sidechain to this track"**.
3. In the BEAT Pro-Q 4: gear icon → "Plugin Wrapper Settings" → "Processing" → "Connections". Map its sidechain input to insert 2 (or click "Auto map inputs").

| Band | Shape | Frequency | Gain | Q | Slope | Dynamic range | Threshold / attack (A) / release (R) | Triggering | External side chain | Why |
|---|---|---|---|---|---|---|---|---|---|---|
| 1 | Bell | 2.5 kHz | 0.0 dB | 1.0 | 12 dB/oct | **−3.0 dB** | Auto (A) / 50% / 50% | Band | **On** (click "expand >>" to see the button) | Clears room for the melody's diction |
| 2 | Bell | 4.5 kHz | 0.0 dB | 1.4 | 12 dB/oct | **−2.0 dB** | Auto (A) / 50% / 50% | Band | **On** | Clears room for its presence |

Globals: Zero Latency · Clean · Output Gain 0.0 dB · Output Pan centre · Auto Gain off · Gain Scale 100% · Phase Invert off. Spectral off on both bands.

**Dial it in:** The beat's 2.5 and 4.5 kHz regions should dip up to 3 and 2 dB **only while you sing**, and stay flat in the gaps.

---

## 8. Troubleshooting

Each fix changes only the slots it names. "or" means pick one; ";" means do both.

| If it sounds… | Do this |
|---|---|
| The melody gets buried in the hall while you sing | R8.2 RANGE 10 → **13 dB**, or LEAD → FX HALL send −10 → **−12 dB** |
| The hall doesn't feel arena-sized | R8.1 SPACE 3.4 → **4.0 s**; DISTANCE 55 → **65** |
| The hall is muddy or boomy | R8.1 Post EQ Low Cut 220 → **300 Hz**; Decay Rate EQ low shelf 70% → **50%** |
| The echoes are too busy | R9.1 FEEDBACK 35 → **25** |
| The ping-pong is distracting | R9.1 WIDTH 100 → **70** |
| The wall is too loud in the verses | DBL BUS fader to **LEAD − 12 dB** |
| The wall sounds phasey or hollow | DBL B-L / B-R faders −3.0 → **−5.0 dB**. Still phasey: mute the doubles one at a time, and pull the one that clears it down another **2 dB** |
| The lead is harsh or brittle | L6 band 3 +3.0 → **+2.0 dB**; L2 band 3 Range −4 → **−6 dB** |
| Esses spit after the air shelf | L8 THRESHOLD −30 → **−34 dB** |
| The voice sounds too clean, not warm | L7 DRIVE 15% → **22%** (typed travel) |
| The warmth turns gritty | L7 DRIVE 15% → **10%** (typed travel) |
| Long notes sound robotic | L4 HUMANIZE 18 → **28** |
