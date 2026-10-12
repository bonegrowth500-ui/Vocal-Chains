# Build Plan: The 4 Vocal Chain Files

> **Status:** Plan saved. **Waiting for your cue.** Nothing in `chains/` has been written yet.
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

---

## Step 2: Verify the toolkit down to the knob

**Goal:** check every plugin name, control name, unit, range, and FL menu path in the files against official docs. Nothing is written from memory.

- **2.1 Gather official documentation** for every plugin that will appear:
  - **FabFilter:** Pro-Q 4, Pro-C 3, Pro-DS, Pro-G, Pro-MB, Saturn 2, Timeless 3, Pro-R 2, Volcano 3, and Pro-L 2 (as a meter only, if chosen in 2.6)
  - **Antares:** the Auto-Tune Artist manual
  - **Image-Line:** the FL manual page for every native plugin used (e.g., Fruity Chorus, Fruity Phaser, Fruity Delay 3, Fruity Stereo Shaper, a utility gain such as Fruity Balance, Edison), plus the mixer and plugin wrapper pages
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
- **2.6 Choose the meters** for calibration (J2) and placement (J6) from owned plugins, and confirm they read what's needed.
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
| 1. Lock boundaries and pre-resolve ambiguities | ⏸ Waiting for cue |
| 2. Verify the toolkit | ⏸ |
| 3. Design blueprints | ⏸ |
| 4. Write the files | ⏸ |
| 5. QA gates | ⏸ |
| 6. Deliver | ⏸ |

---

## Judgement log

New delivery calls made during creation are added here, starting at J23.

| ID | File | Gap | Decision | Why it stays inside the spec |
|---|---|---|---|---|
| — | — | — | — | — |
