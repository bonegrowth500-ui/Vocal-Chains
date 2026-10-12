# Build Plan: The 4 Vocal Chain Files

> **Status:** Step 1 done: boundaries locked (Appendices A–D, judgement calls J23–J30). **Waiting for your cue to run Step 2.** Nothing in `chains/` has been written yet.
> **Governing document:** `SPEC.md` (frozen). This plan only decides *how* the spec gets delivered, never *what* the spec is.
> **Last updated:** 2026-10-12

---

## Ground rules

1. **The spec is law.** Every sound, scope item, tool, and per-style decision comes from `SPEC.md`. If this plan and the spec ever disagree, the spec wins.
2. **Judgement covers delivery only.** Allowed:
   - picking an exact value inside a range or description the spec already gives
   - picking which owned tool carries out an effect the spec asks for
   - order of presentation, wording, formatting, naming
   - how to measure and verify

   Not allowed: adding, removing, or changing any sound, effect, layer, plugin, section, or scope item the spec defines.
3. **No consulting during creation.** Between your "start" and delivery, I ask you nothing. Every open question gets the most spec-faithful answer and is written to the Judgement log at the bottom of this file.
4. **`SPEC.md` is never edited.** Progress and judgement calls are tracked here only.
5. **The deliverables are exactly the 4 files** named in spec §1. No extra shared or common files, no README.

**The "what vs how" test**, applied to every call:

| Question | If yes |
|---|---|
| Does it add, remove, or change a sound, effect, layer, plugin, section, or scope item the spec defines? | ❌ Not allowed |
| Does it choose an exact number inside a range or wording the spec already gives? | ✅ Allowed, logged |
| Does it choose which owned tool carries out an effect the spec asks for, where the spec doesn't name a tool? | ✅ Allowed, logged |
| Is it about order, wording, formatting, naming, or how to measure and verify? | ✅ Allowed |

---

## Step 1: Lock the boundaries and pre-resolve ambiguities

**Goal:** settle every known gray area before writing starts, so creation never stalls or drifts.

- **1.1 Freeze the inputs.** The pushed `SPEC.md` (commit `7b2edc9`) is the only input.
- **1.2 Build the boundary checklist from spec §3.** The In list becomes required content. The Out list becomes a "must not appear" list, checked in Step 5.
- **1.3 Build the toolkit allow-list and block-list from spec §5.** Only the owned plugins listed there may appear in the files. Everything in the "Not in your kit" table is blocked.
- **1.4 Apply the pre-resolved ambiguity rulebook** below to all four files.
- **1.5 Open the Judgement log** for any new call made during creation. Each entry records the file, the gap, the decision, and why it stays inside the spec.

### Pre-resolved ambiguities (delivery decisions)

| ID | Gray area in the spec | How it gets delivered | Why it stays inside the spec |
|---|---|---|---|
| J1 | "Exact value for every parameter": which controls count | Every audio-affecting control on the plugin's main and expert panels gets a row, including ones left at default (written as the actual default value). A feature group that stays off (e.g., an unused side-chain EQ) gets one "Off (default)" row. Display-only controls (analyzer, UI size) are skipped | Fulfills §4 "every parameter" without adding sound |
| J2 | Compressor, de-esser, and gate thresholds depend on the input level | Slot 1 of every lead chain sets the vocal to one fixed level, so every threshold after it is exact. The file states the target and the meter reading that confirms it | Carries out §6.2 "trim gain" and §4 "exact value" |
| J3 | Key/Scale changes per song | Give the exact procedure: set Key/Scale to the beat's key, with Chromatic as the fallback | §9 assumption |
| J4 | Approximate values ("about ±40–50%", "about ±50%", "about 2 s") | One exact value inside the stated range, used consistently | The value is chosen inside the spec's own range |
| J5 | Descriptive targets ("constant but tasteful", "blooms in the gaps", "behind the beat", "tucked low", "melted in", "most forward") | Turned into numbers: send levels, ducking depth (dB of gain reduction), filter cutoffs, relative levels | Converts spec wording into settings without changing what it means |
| J6 | Placement needs a measuring stick | Each file gives a lead-vs-beat level target and names the owned meter used to read it (chosen in Step 2) | Delivers the §7 "Placement" rows in a measurable way |
| J7 | 2-track beats are often mastered close to 0 dBFS, leaving no headroom for vocals | Session setup includes trimming the beat's fader for headroom. That's gain staging only: the beat gets no processing except the optional carve | Keeps "vocals only" (§3); no master chain |
| J8 | The spec names an effect but not the tool (time offset, band-pass, mids-only distortion, tape wobble) | Pick the most precise tool from the §5 kit. Where the spec does name a tool (Pro-C 3 for ducking, Timeless 3 for the delays, Pro-R 2 for reverbs, Auto-Tune Artist for Detune/Throat/Transpose), that tool is used even if another could do the job | A tool choice inside the owned kit; spec-named tools always win |
| J9 | Saturation isn't specified for #4 Alien Transmission or #9 Plugg Cloud | No saturation in those two chains. That includes the built-in saturation in other plugins: Pro-C 3's Character panel and Pro-Q 4's character modes stay off/clean there. Grit only where the spec asks for it: Rage (crunchy) and Anthem (light warmth). Plugg's "warm, buttery body" comes from EQ and opto compression | Adding dirt would add a sound the spec didn't ask for |
| J10 | Which tracks feed which FX returns | Decided per style in Step 3 from that style's clarity and space decisions, and stated in the routing walkthrough | Serves the spec's space decisions; adds no new effect |
| J11 | Order changes vs the §6.3 skeleton | Only where a spec decision requires one (e.g., Rage: compression before distortion). A second Pro-DS after an air boost counts as part of "every chain gets a de-esser" (§2). Every deviation gets a one-line why in the file | §6.3 allows per-style order changes |
| J12 | "Edison denoise / Pro-G only if room tone is audible" | Included as clearly marked conditional steps, each with exact settings and a quick test for when to use it | Matches the §6.2 wording exactly |
| J13 | Version differences (FL UI, Pro-C 3 vs 2) | Written for FL Studio 2024+ and Pro-C 3 only | §9 assumptions |
| J14 | How detailed the delay table is | 130–170 BPM in 5-BPM steps, covering every note value the file uses plus the reverb pre-delay values. Computed by script, not by hand | §4 / §6.6 "ms table for 130–170 BPM" |
| J15 | What troubleshooting covers | Only problems this chain can cause or fix. Every fix names the slot and the exact value change. No mastering, ad-lib, or recording advice | §4 extras + §3 Out list |
| J16 | What "intermediate" means | No definitions of basic terms (threshold, ratio, high-pass). FL-specific clicks and hidden menus are spelled out step by step | §4 level rule |
| J17 | Extras you didn't select (automation map, signal-flow diagram) | Not included. Routing is explained with a mixer-map table plus numbered steps | §3 Out list; §4 extras |
| J18 | How hard your loud lines hit a compressor depends on the performance | Every dynamics slot states the exact setting *and* the expected meter reading, so you can confirm it's right | Supports §4 "exact value" |
| J19 | Which returns get ducked | Delays are always ducked (§6.5). The Anthem's hall is ducked (§7). Whether the other reverbs duck (Alien shimmer, Rage room, Plugg plate) is decided in Step 3 from each style's wording and logged. All ducking is Pro-C 3 on the return, keyed from the Lead, even where another plugin has built-in ducking | §6.1, §6.5, §7 |
| J20 | Whether the files stand alone | Each file restates the shared conventions it uses, so it works on its own | §1 lists 4 standalone files |
| J21 | The same plugin on several inserts (e.g., each double's Auto-Tune Artist) | One table with a column per insert (Parameter / Dbl L / Dbl R / Why), so every value is still given without repeating near-identical tables | Every parameter still gets an exact value (§4) |
| J22 | Band-based plugins (Pro-Q 4, Pro-MB, Saturn 2 bands) | One row per band, with that band's controls as columns, plus a small table for global settings. The Why cell explains each non-default value in that band | Every parameter still gets an exact value and a why (§4) |

**Exit gate:** boundary checklist, allow/block lists, and the rulebook are in place.
**Result:** ✅ Met on 2026-10-12. Outputs are in Appendices A–D; new calls J23–J30 are in the Judgement log.

---

## Step 2: Verify the toolkit down to the knob

**Goal:** check every plugin name, control name, unit, range, and FL menu path in the files against official docs. Nothing is written from memory.

- **2.1 Gather official documentation** for every plugin that will appear:
  - **FabFilter:** Pro-Q 4, Pro-C 3, Pro-DS, Pro-G, Pro-MB, Saturn 2, Timeless 3, Pro-R 2, Volcano 3, and Pro-L 2 (as a meter only, if chosen in 2.6)
  - **Antares:** the Auto-Tune Artist manual
  - **Image-Line:** the FL manual page for every native plugin used, all from the closed allow-list (J23), e.g., Fruity Chorus, Fruity Phaser, Fruity Delay 3, Fruity Stereo Shaper, Edison. Plus the mixer, playlist, and plugin wrapper pages
- **2.2 Build a parameter reference sheet per plugin** (in the session scratchpad, not a deliverable). Each sheet lists exact control names as printed in the UI, units, ranges, defaults, modes, and styles. Only names on these sheets may appear in the files.
- **2.3 Verify the Auto-Tune Artist behaviors the spec relies on:**
  - Detune: units and range
  - Throat: range, and whether it depends on Formant being on
  - Transpose: range and how it handles formants
  - Retune Speed, Humanize, Flex-Tune, Classic Mode, input types
  - plugin latency
- **2.4 Verify FL routing in FL 2024+:**
  - insert-to-insert sends and send levels
  - "Sidechain to this track" vs. a normal audio send
  - how a VST3 plugin's sidechain input is assigned in FL's plugin wrapper
  - pan and stereo separation
  - plugin delay compensation with Auto-Tune and lookahead plugins
- **2.5 Verify the mechanisms the spec names:**
  - Timeless 3: ping-pong setup, tempo sync, and the modulation used for the "tape-style wobble"
  - Pro-R 2: controls that produce the "plate", "short dark room", and "arena hall" characters, and pre-delay units
  - Saturn 2: style list and multiband setup, for the "mids only" crunch
  - Pro-C 3: styles, sidechain input, and the Character panel
  - Pro-Q 4: dynamic bands and external sidechain, for the optional beat carve
  - Pro-DS: modes
- **2.6 Choose the meters** for calibration (J2) and placement (J6) from the allow-list or FL's built-in mixer meters (J23), and confirm they read what's needed.
- **2.7 Source facts.** Look up the Lewitt LCT 440 PURE's published frequency response, so the cleanup EQ targets real data instead of guesses.
- **2.8 Compute the delay and pre-delay table** for 130–170 BPM with a script. Its output is the only source the files copy from.
- **2.9 Handle gaps.** If a needed control doesn't exist, use the spec §5 replacement or an equivalent owned tool, following the J8 rules, and log it.

**Exit gate:** every control and menu path planned for the files is on a verified reference sheet, and the delay table is computed.

---

## Step 3: Design the four blueprints before writing prose

**Goal:** decide every value and trace it to a spec row before a single paragraph is written.

- **3.1 Traceability matrix.** For each style, map every §6 convention and §7 row → the slot(s) that carry it out → plugin → key values. A spec row with no slot, or a slot with no spec reason, is a defect.
- **3.2 Mixer map per style.**
  - insert numbers and names: Lead, each double, Doubles bus, each FX return
  - what feeds each return (J10)
  - send levels and sidechain sources
  - Lead, Doubles bus, and every return routed straight to Master (no overall vocal bus, per §3)
- **3.3 Gain structure.** The calibration target at slot 1 (J2), the expected level after every slot, level-matched bypass, and the beat headroom trim (J7).
- **3.4 Lead chain per style.** Slot order (the §6.3 skeleton plus spec-required changes, J11), every parameter value, and the expected meter readings (J18).
- **3.5 Doubles per style.** The count comes from the spec. Each double then gets:
  - a pan: one exact value inside the spec's range (J4)
  - an Auto-Tune Artist Detune in cents
  - a Throat value
  - a time offset in ms
  - EQ differences and a level relative to the lead

  No two doubles share the same combination. Check the stack for phasing and mono compatibility.
- **3.6 FX returns per style.** Note values, decay times, filters, modulation, ducking depth (J19), and return levels that turn the spec's wording into numbers (J5).
- **3.7 Placement and tone targets.** A lead-vs-beat level target per style (J6), and EQ curves that match each style's Tone row.
- **3.8 Distinctness check.** The four blueprints must differ exactly where §7 makes them differ, and match where §6 makes them shared.

### Preliminary blueprint outlines (draft: Step 2 can change tools, Step 3 finalizes)

**Lead front end, all styles (values differ per style):** calibrate gain → Pro-Q 4 cleanup (high-pass, boxiness dip, dynamic harshness band) → Pro-DS → Auto-Tune Artist → Pro-C 3 → Pro-Q 4 tone → style stage → sends. The conditional Edison denoise and Pro-G expansion (J12) are placed in Step 3.

| Style | Lead style stage | Doubles (copy-pastes → Doubles bus) | FX returns (delays always ducked by Pro-C 3 keyed from the Lead) |
|---|---|---|---|
| #4 Alien Transmission | Bright, glossy tone EQ; no saturation (J9) | Dbl L + Dbl R, wide and chorused (Fruity Chorus) + Alien layer (Throat-shifted, band-passed, low) | **Delay:** Timeless 3 dotted-⅛ ping-pong → slow Fruity Phaser. **Shimmer:** Auto-Tune Artist Transpose +12 → Pro-R 2 |
| #5 Rage Blowout | Fast Pro-C 3 before the dirt → light in-line Saturn 2 crunch → mid-forward EQ with the top controlled | Dbl L + Dbl R at one exact pan inside ±40–50%, dirtier and more band-limited than the lead | **Parallel crunch bus:** heavier distortion, mids only. **Room:** Pro-R 2 short and dark. **Delay:** Timeless 3, ducked so it blooms on line endings |
| #6 Melodic Rage Anthem | Light-warmth saturation → bright, airy EQ | Pair A (±100%) + Pair B (one exact pan near ±50%), every double distinct, tucked low | **Hall:** Pro-R 2 arena-sized, ducked. **Delay:** Timeless 3 ¼-note ping-pong, ducked |
| #9 Plugg Cloud | Gentle opto Pro-C 3 → warm body + breathy air EQ; no saturation (J9) | Dbl L + Dbl R, chorused, tucked low | **Delay:** Timeless 3 ¼-note, highs rolled off, tape-style wobble. **Plate:** Pro-R 2 soft and dark, about 2 s |

**Exit gate:** four complete blueprints, and a traceability matrix with no empty rows.

---

## Step 4: Write the four chain files

**Goal:** turn the blueprints into four standalone, consistent, readable files.

- **4.1 Lock one template** for all four files:
  1. Title, style identity (from spec §1), and a short "what this chain does"
  2. Session setup + FL routing walkthrough: mixer-map table, numbered steps, sidechain setup
  3. Lead chain, slot by slot
  4. Doubles: making the copies, each double's insert, the Doubles bus
  5. FX returns, including ducking
  6. Delay and pre-delay time table (130–170 BPM)
  7. Final balance: the placement target and how to read it
  8. Optional add-on: beat carve
  9. Troubleshooting
- **4.2 Slot format (spec §4).** Each plugin gets:
  - a header with slot number, plugin, and job
  - a Parameter / Setting / Why table covering **every** parameter (J1, J21, J22)
  - a 3–6 step "Dial it in" list that ends with the meter reading that confirms it's right
- **4.3 Writing rules.**
  - Plugin and control names copied exactly from the Step 2 reference sheets
  - units on every value
  - note values paired with the ms table
  - intermediate tone (J16)
  - the same insert names used everywhere in a file
- **4.4 Write shared blocks once, then adapt them.** Calibration, cleanup, Auto-Tune basics, the fake-real-double recipe, and the routing basics are drafted once and then adapted per style. Shared parts stay consistent, and every difference is deliberate.
- **4.5 Write in spec order: 04 → 05 → 06 → 09.** Each file passes the per-file checks (5.1–5.7) and is committed and pushed as a checkpoint before the next one starts. That keeps template mistakes from multiplying and keeps work from being lost if the session goes idle.
- **4.6 Troubleshooting.** 8–12 style-specific "if it sounds X → do Y" entries per file, each pointing to a slot and an exact change (J15).
- **4.7 Optional beat carve.** Clearly labeled as optional and skippable: Pro-Q 4 on the 2-track beat, with dynamic dips in the vocal's presence range, sidechained from the Lead (§6.7).

**Exit gate:** four complete files in `chains/`, each passing the per-file checks.

---

## Step 5: Verify everything (QA gates)

**Goal:** prove each file is spec-exact, technically correct, internally consistent, and usable without asking anything.

- **5.1 Spec-compliance audit, per file.** Walk spec §2–§7 row by row and tick each one off against the file. Then check the Out list: no ad-libs, harmonies, background vocals, vocal bus, tracking chain, master chain, automation map, or signal-flow diagram.
- **5.2 Toolkit audit.**
  - only allow-listed plugins, nothing from the block-list
  - every control name exists on its reference sheet
  - every value is inside its range and in the right unit
  - no saturation in #4 or #9 (J9)
- **5.3 Routing audit.**
  - the mixer map, the walkthrough steps, and every send and sidechain reference agree
  - no routing FL can't actually do (e.g., feedback loops)
  - every sidechain source exists
- **5.4 Gain-staging audit.** Trace the calibrated level through every slot. Thresholds and expected gain-reduction readings must match the level actually arriving at that slot.
- **5.5 Doubles audit.** Every double is unique (pan, Detune, Throat, offset, EQ), the counts match the spec, and the doubles play the whole song.
- **5.6 Math audit.** Re-run the delay script and compare its output with the table in every file.
- **5.7 Format audit.**
  - every plugin has a full table (every parameter with a why) plus a "Dial it in" list
  - troubleshooting and the FL routing walkthrough are present
  - tables render correctly and headings are consistent
- **5.8 Cross-file audit.** Shared conventions are identical where §6 says they're shared, and the four styles differ exactly where §7 says they differ.
- **5.9 Cold read.** Read each file as an intermediate FL user starting from an empty project with only a 2-track beat and a vocal take. Every step must be doable in order, with nothing left to guess.
- **5.10 Fix and re-run** any failed gate until all of them pass. Log any judgement made while fixing.

**Exit gate:** all gates pass on all four files.

---

## Step 6: Deliver

**Goal:** ship exactly the spec's deliverables, saved and pushed.

- **6.1 Final file set:** `chains/04-alien-transmission.md`, `chains/05-rage-blowout.md`, `chains/06-melodic-rage-anthem.md`, `chains/09-plugg-cloud.md`, named exactly as in spec §1.
- **6.2 Update this plan.** Tick the progress tracker and finalize the Judgement log. `SPEC.md` stays untouched.
- **6.3 Final commit and push** to `origin/master`.
- **6.4 Hand-off.** Send you the 4 files with a one-paragraph summary of each and the judgement calls worth knowing.
- **6.5 Stop.** No changes after delivery unless you ask.

**Exit gate:** the files are on GitHub and delivered in chat.

---

## Risks and where they're handled

| Risk | Handled by |
|---|---|
| Wrong control names or impossible values written from memory | 2.1–2.2 reference sheets, 5.2 toolkit audit |
| Copy-pasted doubles phasing or sounding fake | 3.5 unique settings per double, 5.5 doubles audit |
| Thresholds that don't match your real input level | J2 calibration, 5.4 gain-staging audit |
| Scope creep (bonus ad-lib tips, mastering advice, extra effects) | 1.2 boundary checklist, J9, J15, 5.1 compliance audit |
| Routing FL can't actually do (sidechain assignment, feedback loops) | 2.4 routing verification, 5.3 routing audit |
| Files too long or repetitive to use | J21/J22 table rules, one template (4.1) |
| The four files drifting apart in naming or conventions | 4.4 shared blocks, 5.8 cross-file audit |
| Tempo-dependent numbers wrong at your BPM | 2.8 computed table, 5.6 math audit |
| Work lost if the session goes idle mid-build | 4.5 checkpoint commit + push after each file |

---

## Progress tracker

| Step | Status |
|---|---|
| 1. Lock boundaries and pre-resolve ambiguities | ✅ Done: Appendices A–D, J23–J30 |
| 2. Verify the toolkit | ⏸ Waiting for cue |
| 3. Design blueprints | ⏸ |
| 4. Write the files | ⏸ |
| 5. QA gates | ⏸ |
| 6. Deliver | ⏸ |

---

## Appendix A: Spec freeze record (Step 1.1)

| Item | Value |
|---|---|
| File | `SPEC.md` |
| Frozen at commit | `7b2edc9` |
| SHA-256 | `473ab04317182e4dc0d15338679785864e7700ff6c8cee3edd41e6070a621285` |
| Changed since `7b2edc9`? | No. There's no diff at `HEAD`, the working tree is clean, and `7b2edc9` is the only commit that touches it |

Step 5 recomputes the SHA-256, and any mismatch fails QA.

---

## Appendix B: Boundary checklist (Step 1.2)

Each item is ticked per file during Step 5.1. ☐ = not checked yet. — = doesn't apply to that file.

### B1. Required in every file

| ID | Requirement | Spec | 04 | 05 | 06 | 09 |
|---|---|---|---|---|---|---|
| R01 | Saved at its exact §1 path, titled with the style name and its §1 identity line | §1 | ☐ | ☐ | ☐ | ☐ |
| R02 | A full lead vocal chain | §1, §3 In | ☐ | ☐ | ☐ | ☐ |
| R03 | Doubles processing, with the doubles playing the whole song | §3 In, §7 | ☐ | ☐ | ☐ | ☐ |
| R04 | Exactly the FX returns this style's §7 rows call for (listed in B2) | §3 In, §7 | ☐ | ☐ | ☐ | ☐ |
| R05 | An FL routing walkthrough | §3 In, §4 | ☐ | ☐ | ☐ | ☐ |
| R06 | A troubleshooting section ("if it sounds X → do Y") | §3 In, §4 | ☐ | ☐ | ☐ | ☐ |
| R07 | An optional beat carve, labeled optional: Pro-Q 4 on the 2-track, dynamic dips in the vocal's presence range, sidechained from the Lead | §3 In, §6.7 | ☐ | ☐ | ☐ | ☐ |
| R08 | Every plugin slot has a settings table with an exact value and a one-line why for every parameter, then a "Dial it in" step list | §4 | ☐ | ☐ | ☐ | ☐ |
| R09 | Intermediate level: no basic definitions, but FL-specific clicks spelled out | §4 | ☐ | ☐ | ☐ | ☐ |
| R10 | Delay times as tempo-synced note values + an ms table for 130–170 BPM | §4, §6.6 | ☐ | ☐ | ☐ | ☐ |
| R11 | Mixer layout: Lead on its own insert; each double on its own insert → Doubles bus; each reverb, delay, or parallel effect on its own FX return insert, fed by sends (never on the Lead insert) | §6.1, §9 | ☐ | ☐ | ☐ | ☐ |
| R12 | All ducking is done by Pro-C 3 on the FX return, sidechained from the Lead insert | §6.1 | ☐ | ☐ | ☐ | ☐ |
| R13 | Cleanup comes first, in this order: trim gain → high-pass → boxiness dip → Pro-Q 4 dynamic harshness band → Pro-DS | §6.2, §2 | ☐ | ☐ | ☐ | ☐ |
| R14 | Edison denoise and Pro-G expansion are offered only as "if room tone is audible" steps | §6.2 | ☐ | ☐ | ☐ | ☐ |
| R15 | Chain skeleton: cleanup → Auto-Tune Artist → compression → tone shaping → style processing → sends, with every deviation explained | §6.3 | ☐ | ☐ | ☐ | ☐ |
| R16 | Every double has its own time offset, its own Auto-Tune Artist Detune, a throat/formant variation, and its own EQ and pan | §6.4, §2 | ☐ | ☐ | ☐ | ☐ |
| R17 | Delays are always on and ducked by the dry lead, with no automation needed | §6.5 | ☐ | ☐ | ☐ | ☐ |
| R18 | EQ and de-ess frequencies are set for a mid-range voice | §2 | ☐ | ☐ | ☐ | ☐ |
| R19 | Oversampling is on where it helps | §2, J27 | ☐ | ☐ | ☐ | ☐ |
| R20 | Only a light trim at the input (raw peaks are −12 to −6 dBFS) | §2 | ☐ | ☐ | ☐ | ☐ |
| R21 | The vocal wins its space through its own EQ and level | §2 | ☐ | ☐ | ☐ | ☐ |
| R22 | Auto-Tune Artist runs in Auto mode, with Key/Scale set per song and Chromatic as the fallback | §9 | ☐ | ☐ | ☐ | ☐ |
| R23 | Written for FL Studio 2024+ and Pro-C 3 | §9 | ☐ | ☐ | ☐ | ☐ |
| R24 | Any octave or pitch trick uses Auto-Tune Artist Transpose | §5, §9 | ☐ | ☐ | ☐ | ☐ |

### B2. Required per file (spec §7)

**#4 Alien Transmission** (`chains/04-alien-transmission.md`)

| ID | Requirement | Check |
|---|---|---|
| AT00 | Returns: exactly two. Delay (Timeless 3 → Fruity Phaser) and Shimmer (Auto-Tune Artist → Pro-R 2). Doubles: 3 inserts (Dbl L, Dbl R, Alien layer) | ☐ |
| AT01 | FX constant but tasteful: always present, words always clear | ☐ |
| AT02 | Lead on top and clear; the FX surround it rather than cover it | ☐ |
| AT03 | Tone bright and crisp, glossy top, harshness controlled | ☐ |
| AT04 | Tuning hard but smooth: fast retune, light Humanize | ☐ |
| AT05 | Chorus/detune on the doubles for constant width | ☐ |
| AT06 | Slow phaser on the delay return | ☐ |
| AT07 | Main space: dotted-⅛ ping-pong on Timeless 3, always on, ducked by the lead | ☐ |
| AT08 | Secondary space: quiet octave-up shimmer, Auto-Tune Artist Transpose +12 on a send → Pro-R 2 | ☐ |
| AT09 | Alien layer: formant-shifted double via Auto-Tune Artist throat modeling, band-passed, blended low | ☐ |
| AT10 | Doubles: chorused wide L/R pair + the alien layer, whole song | ☐ |

**#5 Rage Blowout** (`chains/05-rage-blowout.md`)

| ID | Requirement | Check |
|---|---|---|
| RB00 | Returns: exactly three. Parallel crunch bus, Room, Delay. Doubles: 2 inserts (Dbl L, Dbl R) | ☐ |
| RB01 | Crunchy: obvious distortion, still controlled | ☐ |
| RB02 | Built for a mix of melodic and yelled delivery | ☐ |
| RB03 | Light crunch on the lead itself | ☐ |
| RB04 | A heavier parallel crunch bus that only distorts the mids (lows stay tight, highs don't fizz) | ☐ |
| RB05 | Fast compression before the distortion | ☐ |
| RB06 | On top and cutting: the most forward of the 4 | ☐ |
| RB07 | Mid-forward and aggressive, top end controlled (no airy shine) | ☐ |
| RB08 | Tuning hard (fast retune), with Flex-Tune nudged so yells and unpitched shouts don't warble | ☐ |
| RB09 | A short dark room | ☐ |
| RB10 | A ducked delay that blooms on line endings | ☐ |
| RB11 | Doubles: a tight L/R pair at one exact pan inside ±40–50%, dirtier and more band-limited than the lead ("dirty halo"), whole song | ☐ |

**#6 Melodic Rage Anthem** (`chains/06-melodic-rage-anthem.md`)

| ID | Requirement | Check |
|---|---|---|
| MA00 | Returns: exactly two. Hall (Pro-R 2) and Delay (Timeless 3), both ducked. Doubles: 4 inserts (Pair A L/R, Pair B L/R) | ☐ |
| MA01 | Light warmth: subtle saturation for thickness | ☐ |
| MA02 | On top and clear: the melody rides over the chaos | ☐ |
| MA03 | Bright and airy (arena shine), harshness controlled | ☐ |
| MA04 | Tuning hard but smooth | ☐ |
| MA05 | An arena-sized hall on Pro-R 2 | ☐ |
| MA06 | A ¼-note ping-pong delay on Timeless 3 | ☐ |
| MA07 | Ducked wet behavior: dry and clear while singing, with the space blooming in the gaps | ☐ |
| MA08 | 4-double wall: Pair A at ±100% + Pair B at one exact pan near ±50% | ☐ |
| MA09 | Every double distinct (detune, offset, throat, EQ), all tucked low so verses stay clear, whole song | ☐ |

**#9 Plugg Cloud** (`chains/09-plugg-cloud.md`)

| ID | Requirement | Check |
|---|---|---|
| PC00 | Returns: exactly two. Delay (Timeless 3) and Plate (Pro-R 2). Doubles: 2 inserts (Dbl L, Dbl R) | ☐ |
| PC01 | Melted in: even with the beat, not on top | ☐ |
| PC02 | Soft and airy: warm, buttery body with a breathy, de-essed shimmer on top | ☐ |
| PC03 | Smooth hard tune: fast retune with Humanize | ☐ |
| PC04 | Gentle, smooth, opto-style compression | ☐ |
| PC05 | Delay: long ¼-note echoes, highs rolled off, a slight tape-style wobble (Timeless 3), sitting behind the beat | ☐ |
| PC06 | Reverb: a medium soft plate, darkened, about 2 s, supporting the delays | ☐ |
| PC07 | Width: mostly centered lead, chorused L/R doubles | ☐ |
| PC08 | Doubles: a chorused L/R pair, tucked low, whole song | ☐ |

### B3. Must not appear in any file

| ID | Must not appear | Source | 04 | 05 | 06 | 09 |
|---|---|---|---|---|---|---|
| N01 | Ad-lib processing or advice | §3 Out | ☐ | ☐ | ☐ | ☐ |
| N02 | Harmonies or background vocals | §3 Out | ☐ | ☐ | ☐ | ☐ |
| N03 | An overall vocal bus (the Lead routed through a shared vocal group) | §3 Out, J24 | ☐ | ☐ | ☐ | ☐ |
| N04 | Tracking or monitoring chains, or low-latency recording setups | §3 Out | ☐ | ☐ | ☐ | ☐ |
| N05 | A master chain or mastering: any processing on the Master, or on the beat beyond the optional carve | §3 Out, J7 | ☐ | ☐ | ☐ | ☐ |
| N06 | A section automation map, or any step that needs automation | §3 Out, §6.5, J25 | ☐ | ☐ | ☐ | ☐ |
| N07 | A signal-flow diagram | §3 Out, J17 | ☐ | ☐ | ☐ | ☐ |
| N08 | Any plugin outside the allow-list (C1), including everything on the block-list (C2) | §2, §5, J23 | ☐ | ☐ | ☐ | ☐ |
| N09 | Saturation of any kind: Saturn 2, FL distortion plugins, Pro-C 3 Character, Pro-Q 4 character modes | J9 | ☐ | — | — | ☐ |
| N10 | Pro-C 2 instructions or fallbacks, or pre-2024 FL menu paths | §9, J13 | ☐ | ☐ | ☐ | ☐ |
| N11 | Ducking done any way other than Pro-C 3 on the return keyed from the Lead | §6.1, J19 | ☐ | ☐ | ☐ | ☐ |
| N12 | Doubles detuned any way other than Auto-Tune Artist's Detune (e.g., clip pitch) | §6.4 | ☐ | ☐ | ☐ | ☐ |
| N13 | Processors beyond their stage's job (limiters, clippers, exciters, wideners, transient shapers, multiband, extra parallel buses) unless a §6/§7 item calls for that effect | J26 | ☐ | ☐ | ☐ | ☐ |
| N14 | Troubleshooting outside this chain (mastering, ad-libs, re-recording advice) | J15 | ☐ | ☐ | ☐ | ☐ |
| N15 | Relying on another file (another chain, SPEC, or PLAN) for a required step | J20 | ☐ | ☐ | ☐ | ☐ |

### B4. Process boundaries (how the build runs)

| ID | Rule | Source |
|---|---|---|
| P01 | `SPEC.md` is never edited, and its SHA-256 still matches Appendix A at delivery | Ground rule 4 |
| P02 | No questions to you between "start" and delivery | Ground rule 3 |
| P03 | The deliverables are exactly the 4 files in `chains/`: no README, no shared files | Ground rule 5, §1 |
| P04 | Every new judgement call is logged before it's used | Ground rule 3, 1.5 |

---

## Appendix C: Toolkit lists (Step 1.3)

### C1. Allow-list (closed: exactly spec §5, per J23)

| Group | Allowed |
|---|---|
| FabFilter (12) | Pro-Q 4, Pro-C 3, Pro-DS, Pro-G, Pro-MB, Pro-L 2, Pro-R 2, Saturn 2, Timeless 3, Volcano 3, Simplon, Micro |
| Antares (1) | Auto-Tune Artist: Key/Scale, Retune Speed, Humanize, Flex-Tune, vibrato controls, Classic Mode, Formant correction, Throat modeling, Transpose, Detune |
| FL Studio Producer Edition natives (25) | Fruity Parametric EQ 2, Fruity Limiter, Fruity Delay 3, Fruity Delay Bank, Multiband Delay, Fruity Reeverb 2, Fruity Convolver, Fruity Chorus, Fruity Flanger, Fruity Phaser, Fruity Stereo Shaper, Fruity Stereo Enhancer, Fruity Love Philter, Fruity Soft Clipper, Fruity Fast Dist, Fruity Blood Overdrive, Fruity WaveShaper, Fruity Squeeze, Frequency Splitter, Frequency Shifter, Maximus, Vocodex, Effector, Patcher, Edison |
| FL Studio built-ins (not plugins) | Mixer faders, pan, stereo separation, sends, sidechain routing, mixer meters, playlist clip editing, channel settings |

Being on the allow-list means a plugin *may* be used, not that it will be. J26 still decides whether a processor belongs in a chain.

### C2. Block-list

| Blocked | Reason | Use instead |
|---|---|---|
| Pitch Shifter | All Plugins Edition only | Auto-Tune Artist Transpose (spec §5) |
| LuxeVerb | All Plugins Edition only | Pro-R 2 (spec §5) |
| Transient Processor | All Plugins Edition only | Pro-C 3 / Pro-G (spec §5) |
| Gross Beat | Signature Bundle | Not needed (spec §5) |
| Vintage Chorus / Vintage Phaser | Signature Bundle | Fruity Chorus / Fruity Phaser (spec §5) |
| Pitcher / NewTone | Signature Bundle | Auto-Tune Artist (spec §5) |
| Hardcore | Signature Bundle | Not needed |
| Xfer OTT | Third-party | Pro-MB, Pro-C 3 Upward style, or Maximus (spec §5) |
| Valhalla Supermassive | Third-party | Pro-R 2 + Timeless 3 (spec §5) |
| Auto-Tune Pro-only features (Graph mode) and the separate Auto-Key plug-in | Not in Auto-Tune Artist / not owned | Auto mode with Key/Scale set by hand |
| FabFilter Twin 3 / One | Synths, not on the §5 list | Not needed |
| Any FL plugin missing from C1 (e.g., Fruity Balance, Wave Candy) | Outside the closed list (J23) | A C1 tool or FL built-in for the same job |
| Any other third-party plugin | §2: "nothing else" | — |

### C3. Tool bindings

**Named by the spec (fixed):**

| Job | Tool | Spec |
|---|---|---|
| Ducking on every ducked return | Pro-C 3, sidechained from the Lead insert | §6.1 |
| Dynamic harshness control | Pro-Q 4 dynamic band | §6.2 |
| De-essing | Pro-DS | §6.2 |
| Conditional room-tone cleanup | Edison denoise / Pro-G expansion | §6.2 |
| Tuning | Auto-Tune Artist in Auto mode | §2, §9 |
| Double detune | Auto-Tune Artist Detune on each double | §6.4 |
| Alien layer formant shift | Auto-Tune Artist Throat | §7 #4 |
| Shimmer glow | Auto-Tune Artist Transpose +12 → Pro-R 2, on one return | §7 #4, §9 |
| Delays in #4, #6, #9 | Timeless 3 | §7 |
| Hall in #6 | Pro-R 2 | §7 #6 |
| Chorus | Fruity Chorus | §5 |
| Phaser | Fruity Phaser | §5 |
| Beat carve | Pro-Q 4 with an external sidechain from the Lead | §6.7 |

**Bound now under J8 (one clear choice inside the kit):**

| Job | Tool | Why |
|---|---|---|
| Throat/formant variation on every double | Auto-Tune Artist Throat | The only owned formant tool (Pitch Shifter is blocked) |
| Cleanup and tone EQ | Pro-Q 4 | The spec's EQ in §6.2 and §6.7 |
| Compression stages | Pro-C 3 | The spec's compressor (§6.1, §9). Plugg's "opto-style" maps to Pro-C 3's Opto style (confirmed in Step 2) |
| #5 room, #9 plate | Pro-R 2 | The spec's reverb in every other style |
| #5 delay | Timeless 3 | The spec's delay in every other style |

**Open for Step 3 (chosen after Step 2 verifies each candidate):**

| Job | Candidates (all in C1) |
|---|---|
| Input trim / calibration gain | Pro-Q 4 output gain, Fruity Parametric EQ 2 main level, FL clip gain (built-in) |
| Double time offsets | Fruity Delay 3, Timeless 3, Fruity Stereo Shaper, playlist clip nudge (built-in) |
| Alien layer band-pass | Pro-Q 4, Volcano 3, Simplon |
| #5 in-line crunch | Saturn 2, Fruity Blood Overdrive, Fruity Fast Dist, Fruity Soft Clipper, Fruity WaveShaper |
| #5 parallel crunch, mids only | Saturn 2 multiband, or a Pro-Q 4 band-limit + any C1 distortion |
| #5 doubles' extra dirt and band-limit | Saturn 2, C1 distortion plugins, Pro-Q 4 |
| #6 light warmth | Saturn 2, Pro-C 3 Character panel, Pro-Q 4 character mode |
| Placement and calibration meters | Pro-L 2 (as a meter only), other FabFilter meters, FL mixer meters |
| Where the chorus sits (#4, #9) | Fruity Chorus on each double, or on the Doubles bus |

---

## Appendix D: Gray-area register (Step 1.4: the rulebook applied per file)

This lists every place the spec leaves a value or method open, the rule that settles it, and when. No values are set here. They come in Step 3, after Step 2 verifies the tools.

### D1. All four files

| ID | Gray area | Rule | Settled in |
|---|---|---|---|
| GU01 | Which controls each plugin table must list | J1, J21, J22 | Step 2 (control lists) → Step 4 |
| GU02 | The calibration target, and every threshold after it | J2, J18 | Step 2 (meter) → Step 3 |
| GU03 | Key/Scale per song | J3 | Step 4 (procedure text) |
| GU04 | How placement is measured | J6 | Step 2 (meter) → Step 3 (targets) |
| GU05 | How far the beat fader comes down for headroom | J7 | Step 3 |
| GU06 | Which tool does the input trim | J8, J23 | Step 3 (from the C3 "open" list) |
| GU07 | Which tool does the double time offsets, and the ms values | J4, J5, J8 | Step 2 → Step 3 |
| GU08 | Each double's pan, Detune, Throat, EQ, and level | J4, J5 | Step 3 |
| GU09 | Which tracks feed which returns, and the send levels | J10, J5 | Step 3 |
| GU10 | Where the conditional Edison/Pro-G steps sit, and their settings | J12 | Step 3 |
| GU11 | Whether a second Pro-DS follows the tone EQ | J11 | Step 3 |
| GU12 | Auto-Tune Artist input type for a mid-range voice | J5 | Step 2 (options) → Step 3 |
| GU13 | The oversampling setting in each nonlinear slot | J27 | Step 2 (options) → Step 3 |
| GU14 | Delay and pre-delay table values | J14 | Step 2 |
| GU15 | Beat-carve bands, depth, and sidechain setup | J5 | Step 3 |
| GU16 | Troubleshooting entries | J15 | Step 4 |
| GU17 | §3's "parallel buses": only where a §7 row calls for one (Rage's crunch bus), none elsewhere | J26 | Settled now |
| GU18 | The "dry lead" ducking key = the Lead insert's output | J29 | Settled now |

### D2. #4 Alien Transmission

| ID | Gray area | Rule | Settled in |
|---|---|---|---|
| GA01 | "Constant but tasteful" → return levels and ducking depth | J5, J19 | Step 3 |
| GA02 | "On top and clear; FX surround the lead" → placement target | J5, J6 | Step 3 |
| GA03 | "Bright and crisp, glossy top, harshness controlled" → tone EQ, with no saturation | J5, J9 | Step 3 |
| GA04 | "Fast retune, light Humanize" → exact values | J4, J5 | Step 3 |
| GA05 | "Chorus/detune on the doubles": Fruity Chorus placement and settings, on top of each double's §6.4 Detune | J8, J5 | Step 3 |
| GA06 | "Slow phaser" → Fruity Phaser rate, depth, mix | J5 | Step 3 |
| GA07 | Dotted-⅛ ping-pong: feedback, filtering, ducking depth | J5, J19 | Step 3 |
| GA08 | "Quiet" shimmer: level, decay, and whether it ducks | J5, J19 | Step 3 |
| GA09 | Alien layer: Throat amount, band-pass tool and range, level, pan. It also gets the full §6.4 recipe | J4, J5, J8, J30 | Step 3 |
| GA10 | "Wide" L/R pair → exact pans | J5 | Step 3 |

### D3. #5 Rage Blowout

| ID | Gray area | Rule | Settled in |
|---|---|---|---|
| GR01 | "Crunchy … still controlled" → drive amounts | J5 | Step 3 |
| GR02 | Lead in-line crunch: tool and drive | J8, J5 | Step 3 |
| GR03 | Parallel crunch bus: how "mids only" is done, crossover points, return level. It's never ducked, because it's part of the lead's sound, not a space effect | J8, J5, J19 | Step 3 |
| GR04 | "Fast compression before the distortion" → style, attack, release | J5, J11 | Step 3 |
| GR05 | Melodic + yelled delivery → expected gain-reduction readings for sung lines and for yelled lines | J18 | Step 3 |
| GR06 | "The most forward of the 4" → the highest placement target | J6, GX01 | Step 3 |
| GR07 | "Mid-forward … top end controlled" → tone EQ | J5 | Step 3 |
| GR08 | "Fast retune, Flex-Tune nudged" → exact values | J4, J5 | Step 3 |
| GR09 | Short dark room: decay, darkness, and whether it ducks | J5, J19 | Step 3 |
| GR10 | "Blooms on line endings" → note value, feedback, ducking depth and release | J5, J19 | Step 3 |
| GR11 | Doubles' exact pan inside ±40–50% | J4 | Step 3 |
| GR12 | Doubles "dirtier and more band-limited": tool, placement (each double or the Doubles bus), amounts | J8, J5 | Step 3 |

### D4. #6 Melodic Rage Anthem

| ID | Gray area | Rule | Settled in |
|---|---|---|---|
| GM01 | "Light warmth" → tool and drive | J8, J5 | Step 3 |
| GM02 | Whether the doubles share the light warmth | J5 | Step 3 |
| GM03 | "On top and clear" → placement target | J6 | Step 3 |
| GM04 | "Bright and airy … harshness controlled" → tone EQ + a second de-ess | J5, J11 | Step 3 |
| GM05 | "Hard but smooth" → Retune Speed, Humanize | J4, J5 | Step 3 |
| GM06 | "Arena-sized" hall → size, decay, pre-delay | J5 | Step 3 |
| GM07 | ¼-note ping-pong settings | J5 | Step 3 |
| GM08 | "Blooms in the gaps" → ducking depth and release on both returns | J5, J19 | Step 3 |
| GM09 | Pair B's exact pan near ±50% | J4 | Step 3 |
| GM10 | "Each pair has its own detune, offset, throat, and EQ" + §6.4 "each double" → all 4 doubles unique; "tucked low" → per-pair levels | J5 | Step 3 |

### D5. #9 Plugg Cloud

| ID | Gray area | Rule | Settled in |
|---|---|---|---|
| GP01 | "Melted in: even with the beat" → the lowest placement target | J6, GX01 | Step 3 |
| GP02 | "Warm, buttery body + breathy, de-essed shimmer" → tone EQ and de-ess, with no saturation | J5, J9, J11 | Step 3 |
| GP03 | "Fast retune with Humanize" → values, with more Humanize than the "light" amount in #4/#6 | J4, J5, GX02 | Step 3 |
| GP04 | "Opto-style" → Pro-C 3's Opto style and its settings | J5 | Step 3 |
| GP05 | Delay: the cutoff for "highs rolled off", wobble rate and depth, and the level for "behind the beat" (depth, not late timing) | J5, J28 | Step 3 |
| GP06 | Plate: exact decay near 2 s, darkness, and whether it ducks | J4, J5, J19 | Step 3 |
| GP07 | "Mostly centered lead" → the Lead panned center with no widening on its insert; width comes only from the chorused doubles and the returns | J5, J26 | Step 3 |
| GP08 | "Tucked low" → doubles level | J5 | Step 3 |

### D6. Across files

| ID | Gray area | Rule | Settled in |
|---|---|---|---|
| GX01 | Placement order: #5 most forward; #4 and #6 on top and clear; #9 even with the beat | J6 | Step 3 |
| GX02 | Tuning-feel order: #5 hard (with Flex-Tune nudged); #4 and #6 hard but smooth, with light Humanize; #9 smooth, with more Humanize | J5 | Step 3 |
| GX03 | The shared cleanup and calibration baseline stays identical unless a style row requires a difference | Plan 4.4 | Step 3 |

---

## Judgement log

New delivery calls made during creation are added here, starting at J23.

| ID | File | Gap | Decision | Why it stays inside the spec |
|---|---|---|---|---|
| J23 | All | §2 says "FL stock", but §5 lists the verified Producer Edition natives | §5's list is the closed allow-list, plus FL's built-in mixer, playlist, and channel features (they aren't plugins). FL plugins not on the list (e.g., Fruity Balance) are out, and Steps 2.1 and 2.6 were reworded to match | Narrower than the spec, never broader; every listed plugin is verified for Producer Edition |
| J24 | All | §6.1 has a Doubles bus and FX returns, but §3 rules out an overall vocal bus | Only doubles pass through the Doubles bus; the Lead goes straight to Master. Returns, including Rage's parallel crunch bus, are fed by sends from the Lead, so none of them is a vocal bus | Satisfies §6.1 and §3 Out together |
| J25 | All | §6.5 says throws need no automation, and §3 rules out a section automation map | Every setting is static. No file asks for automation clips or section-by-section changes | §3 Out, §6.5 |
| J26 | All | The skeleton names stages but not which kinds of processors each may use; §3 mentions "parallel buses" in general | Each stage only uses its own kind of processor. Limiters, clippers, exciters, wideners, transient shapers, multiband processors, and parallel buses appear only when a §6/§7 item calls for that effect. The only parallel bus is Rage's crunch bus | Stops sounds the spec didn't ask for from creeping in |
| J27 | All | §2 says "oversampling on where it helps" without saying where | Oversampling on in every nonlinear slot that offers it (saturation/distortion, compressor character stages). Linear slots (EQ, reverb, delay) keep the plugin's default | Delivers §2's computer row |
| J28 | 09 | Plugg's delay "sitting behind the beat" could mean depth in the mix or late timing | Depth: darker and lower than the beat. The ¼-note stays tempo-synced | §6.6 requires tempo-synced note values, and §7 #9 describes the delay's tone ("highs rolled off") |
| J29 | All | §6.5 "ducked by the dry lead" could be read as the raw, unprocessed take | The ducking key is the Lead insert's output (§6.1): the processed lead without its returns | §6.1 names the Lead insert as the sidechain source |
| J30 | 04 | §7 lists the alien layer in the Doubles row, but its own row only mentions throat shift, band-pass, and level | The alien layer is a double, so it gets the full §6.4 recipe (offset, Detune, throat, EQ, pan) on top of its bigger formant shift | §7 #4 places it in the Doubles row, and §6.4 applies to every double |
