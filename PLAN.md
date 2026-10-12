# Build Plan: The 4 Vocal Chain Files

> **Status:** ✅ Delivered. All six steps are done: boundaries locked (Appendices A–D), toolkit verified (Appendix E), all four chains designed (Appendix F), all four chain files written in `chains/`, every QA gate passed (Appendix G), and the files pushed and handed off (Step 6), with judgement calls J23–J70. **No changes after delivery unless you ask.**
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
- **2.2 Build a parameter reference sheet per plugin** (in the session scratchpad, not a deliverable). Each sheet lists exact control names as printed in the UI, units, ranges, defaults, modes, and styles. Only names on these sheets may appear in the files. A condensed digest of the sheets is kept in Appendix E (J31).
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
**Result:** ✅ Met on 2026-10-12. 8 reference sheets (2,700+ lines) built from official manuals, help pages, screenshots, and changelogs; digest in Appendix E; gaps handled in E9 with calls J31–J42.

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
**Result:** ✅ Met on 2026-10-12. Appendix F: shared conventions (F1), four blueprints (F2–F5), traceability matrix (F6), every gray-area item settled (F7), and the distinctness check (F8); calls J43–J56.

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

**Result:** ✅ Met on 2026-10-12. Four files in `chains/`, written in order 04 → 05 → 06 → 09, each committed and pushed as a checkpoint. Every file passes the automated per-file checks (the automated parts of 5.1–5.7): the identity line, all eight sections, no blocked tools or out-of-scope terms, no saturation in #4 and #9, complete tables with a Why on every setting, a Dial it in for every slot and return, a recomputed delay table, value ranges, every Appendix F value present, the right number of doubles, and 8–12 troubleshooting entries. Calls J57–J58. Step 5 runs the full QA, including the manual audits, the cross-file audit, and the cold read.

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

**Result:** ✅ Met on 2026-10-12. All ten gates pass on all four files (Appendix G). The audits and cold reads found three blockers (an effect send that could go silent, an Edison cleanup that missed the take, and no step setting the project tempo) plus a set of majors. All were fixed in ten batches, with the gates re-run after each. Cold reads: round 1 found 3 blockers and 14 majors, round 2 found 4 majors, and the final full round found 3 majors (06 and 09 passed clean). All were fixed, and focused re-checks of the room-tone, Edison, and solo flow then passed on every path. Calls J59–J70; Appendix B is ticked.

---

## Step 6: Deliver

**Goal:** ship exactly the spec's deliverables, saved and pushed.

- **6.1 Final file set:** `chains/04-alien-transmission.md`, `chains/05-rage-blowout.md`, `chains/06-melodic-rage-anthem.md`, `chains/09-plugg-cloud.md`, named exactly as in spec §1.
- **6.2 Update this plan.** Tick the progress tracker and finalize the Judgement log. `SPEC.md` stays untouched.
- **6.3 Final commit and push** to `origin/master`.
- **6.4 Hand-off.** Send you the 4 files with a one-paragraph summary of each and the judgement calls worth knowing.
- **6.5 Stop.** No changes after delivery unless you ask.

**Exit gate:** the files are on GitHub and delivered in chat.

**Result:** ✅ Met on 2026-10-12. The final file set is exactly the four files in spec §1, unchanged since every gate passed in Step 5 (the per-file checks were re-run and still pass), and `SPEC.md` still matches its freeze hash (Appendix A). The files are on `origin/master`, last changed in `5d180bf`, and were handed off in chat with a summary of each and the judgement calls worth knowing. The Judgement log is closed at J70.

| File | Style | Lines | SHA-256 |
|---|---|---|---|
| `chains/04-alien-transmission.md` | #4 Alien Transmission | 651 | `8df2e59e09bf3975b90fb9ba5c1a25cb3f3e633c9401d157ace03e0f1b3a8255` |
| `chains/05-rage-blowout.md` | #5 Rage Blowout | 656 | `4bbb5fbf4769294c8b70a9822d0ef7b61239eb448c751c56bb98afd964501e14` |
| `chains/06-melodic-rage-anthem.md` | #6 Melodic Rage Anthem | 668 | `451995a2adefd49d4897b5341ec59108dacd213c646cc2d8590f06fd60d21c6f` |
| `chains/09-plugg-cloud.md` | #9 Plugg Cloud | 620 | `6368ff757d56c70d5a8fd016321efa2032a5bbd154d6b2f484c3411ac6056265` |

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
| 2. Verify the toolkit | ✅ Done: Appendix E, J31–J42 |
| 3. Design blueprints | ✅ Done: Appendix F, J43–J56 |
| 4. Write the files | ✅ Done: `chains/` (4 files), J57–J58 |
| 5. QA gates | ✅ Done: Appendix G, J59–J70 |
| 6. Deliver | ✅ Done: 4 files on `origin/master`, handed off in chat |

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

Each item was ticked per file in Step 5.1 (2026-10-12, after the Step 5 fixes). ✅ = checked and passing. — = doesn't apply to that file.

### B1. Required in every file

| ID | Requirement | Spec | 04 | 05 | 06 | 09 |
|---|---|---|---|---|---|---|
| R01 | Saved at its exact §1 path, titled with the style name and its §1 identity line | §1 | ✅ | ✅ | ✅ | ✅ |
| R02 | A full lead vocal chain | §1, §3 In | ✅ | ✅ | ✅ | ✅ |
| R03 | Doubles processing, with the doubles playing the whole song | §3 In, §7 | ✅ | ✅ | ✅ | ✅ |
| R04 | Exactly the FX returns this style's §7 rows call for (listed in B2) | §3 In, §7 | ✅ | ✅ | ✅ | ✅ |
| R05 | An FL routing walkthrough | §3 In, §4 | ✅ | ✅ | ✅ | ✅ |
| R06 | A troubleshooting section ("if it sounds X → do Y") | §3 In, §4 | ✅ | ✅ | ✅ | ✅ |
| R07 | An optional beat carve, labeled optional: Pro-Q 4 on the 2-track, dynamic dips in the vocal's presence range, sidechained from the Lead | §3 In, §6.7 | ✅ | ✅ | ✅ | ✅ |
| R08 | Every plugin slot has a settings table with an exact value and a one-line why for every parameter, then a "Dial it in" step list | §4 | ✅ | ✅ | ✅ | ✅ |
| R09 | Intermediate level: no basic definitions, but FL-specific clicks spelled out | §4 | ✅ | ✅ | ✅ | ✅ |
| R10 | Delay times as tempo-synced note values + an ms table for 130–170 BPM | §4, §6.6 | ✅ | ✅ | ✅ | ✅ |
| R11 | Mixer layout: Lead on its own insert; each double on its own insert → Doubles bus; each reverb, delay, or parallel effect on its own FX return insert, fed by sends (never on the Lead insert) | §6.1, §9 | ✅ | ✅ | ✅ | ✅ |
| R12 | All ducking is done by Pro-C 3 on the FX return, sidechained from the Lead insert | §6.1 | ✅ | ✅ | ✅ | ✅ |
| R13 | Cleanup comes first, in this order: trim gain → high-pass → boxiness dip → Pro-Q 4 dynamic harshness band → Pro-DS | §6.2, §2 | ✅ | ✅ | ✅ | ✅ |
| R14 | Edison denoise and Pro-G expansion are offered only as "if room tone is audible" steps | §6.2 | ✅ | ✅ | ✅ | ✅ |
| R15 | Chain skeleton: cleanup → Auto-Tune Artist → compression → tone shaping → style processing → sends, with every deviation explained | §6.3 | ✅ | ✅ | ✅ | ✅ |
| R16 | Every double has its own time offset, its own Auto-Tune Artist Detune, a throat/formant variation, and its own EQ and pan | §6.4, §2 | ✅ | ✅ | ✅ | ✅ |
| R17 | Delays are always on and ducked by the dry lead, with no automation needed | §6.5 | ✅ | ✅ | ✅ | ✅ |
| R18 | EQ and de-ess frequencies are set for a mid-range voice | §2 | ✅ | ✅ | ✅ | ✅ |
| R19 | Oversampling is on where it helps | §2, J27 | ✅ | ✅ | ✅ | ✅ |
| R20 | Only a light trim at the input (raw peaks are −12 to −6 dBFS) | §2 | ✅ | ✅ | ✅ | ✅ |
| R21 | The vocal wins its space through its own EQ and level | §2 | ✅ | ✅ | ✅ | ✅ |
| R22 | Auto-Tune Artist runs in Auto mode, with Key/Scale set per song and Chromatic as the fallback | §9 | ✅ | ✅ | ✅ | ✅ |
| R23 | Written for FL Studio 2024+ and Pro-C 3 | §9 | ✅ | ✅ | ✅ | ✅ |
| R24 | Any octave or pitch trick uses Auto-Tune Artist Transpose | §5, §9 | ✅ | ✅ | ✅ | ✅ |

### B2. Required per file (spec §7)

**#4 Alien Transmission** (`chains/04-alien-transmission.md`)

| ID | Requirement | Check |
|---|---|---|
| AT00 | Returns: exactly two. Delay (Timeless 3 → Fruity Phaser) and Shimmer (Auto-Tune Artist → Pro-R 2). Doubles: 3 inserts (Dbl L, Dbl R, Alien layer) | ✅ |
| AT01 | FX constant but tasteful: always present, words always clear | ✅ |
| AT02 | Lead on top and clear; the FX surround it rather than cover it | ✅ |
| AT03 | Tone bright and crisp, glossy top, harshness controlled | ✅ |
| AT04 | Tuning hard but smooth: fast retune, light Humanize | ✅ |
| AT05 | Chorus/detune on the doubles for constant width | ✅ |
| AT06 | Slow phaser on the delay return | ✅ |
| AT07 | Main space: dotted-⅛ ping-pong on Timeless 3, always on, ducked by the lead | ✅ |
| AT08 | Secondary space: quiet octave-up shimmer, Auto-Tune Artist Transpose +12 on a send → Pro-R 2 | ✅ |
| AT09 | Alien layer: formant-shifted double via Auto-Tune Artist throat modeling, band-passed, blended low | ✅ |
| AT10 | Doubles: chorused wide L/R pair + the alien layer, whole song | ✅ |

**#5 Rage Blowout** (`chains/05-rage-blowout.md`)

| ID | Requirement | Check |
|---|---|---|
| RB00 | Returns: exactly three. Parallel crunch bus, Room, Delay. Doubles: 2 inserts (Dbl L, Dbl R) | ✅ |
| RB01 | Crunchy: obvious distortion, still controlled | ✅ |
| RB02 | Built for a mix of melodic and yelled delivery | ✅ |
| RB03 | Light crunch on the lead itself | ✅ |
| RB04 | A heavier parallel crunch bus that only distorts the mids (lows stay tight, highs don't fizz) | ✅ |
| RB05 | Fast compression before the distortion | ✅ |
| RB06 | On top and cutting: the most forward of the 4 | ✅ |
| RB07 | Mid-forward and aggressive, top end controlled (no airy shine) | ✅ |
| RB08 | Tuning hard (fast retune), with Flex-Tune nudged so yells and unpitched shouts don't warble | ✅ |
| RB09 | A short dark room | ✅ |
| RB10 | A ducked delay that blooms on line endings | ✅ |
| RB11 | Doubles: a tight L/R pair at one exact pan inside ±40–50%, dirtier and more band-limited than the lead ("dirty halo"), whole song | ✅ |

**#6 Melodic Rage Anthem** (`chains/06-melodic-rage-anthem.md`)

| ID | Requirement | Check |
|---|---|---|
| MA00 | Returns: exactly two. Hall (Pro-R 2) and Delay (Timeless 3), both ducked. Doubles: 4 inserts (Pair A L/R, Pair B L/R) | ✅ |
| MA01 | Light warmth: subtle saturation for thickness | ✅ |
| MA02 | On top and clear: the melody rides over the chaos | ✅ |
| MA03 | Bright and airy (arena shine), harshness controlled | ✅ |
| MA04 | Tuning hard but smooth | ✅ |
| MA05 | An arena-sized hall on Pro-R 2 | ✅ |
| MA06 | A ¼-note ping-pong delay on Timeless 3 | ✅ |
| MA07 | Ducked wet behavior: dry and clear while singing, with the space blooming in the gaps | ✅ |
| MA08 | 4-double wall: Pair A at ±100% + Pair B at one exact pan near ±50% | ✅ |
| MA09 | Every double distinct (detune, offset, throat, EQ), all tucked low so verses stay clear, whole song | ✅ |

**#9 Plugg Cloud** (`chains/09-plugg-cloud.md`)

| ID | Requirement | Check |
|---|---|---|
| PC00 | Returns: exactly two. Delay (Timeless 3) and Plate (Pro-R 2). Doubles: 2 inserts (Dbl L, Dbl R) | ✅ |
| PC01 | Melted in: even with the beat, not on top | ✅ |
| PC02 | Soft and airy: warm, buttery body with a breathy, de-essed shimmer on top | ✅ |
| PC03 | Smooth hard tune: fast retune with Humanize | ✅ |
| PC04 | Gentle, smooth, opto-style compression | ✅ |
| PC05 | Delay: long ¼-note echoes, highs rolled off, a slight tape-style wobble (Timeless 3), sitting behind the beat | ✅ |
| PC06 | Reverb: a medium soft plate, darkened, about 2 s, supporting the delays | ✅ |
| PC07 | Width: mostly centered lead, chorused L/R doubles | ✅ |
| PC08 | Doubles: a chorused L/R pair, tucked low, whole song | ✅ |

### B3. Must not appear in any file

| ID | Must not appear | Source | 04 | 05 | 06 | 09 |
|---|---|---|---|---|---|---|
| N01 | Ad-lib processing or advice | §3 Out | ✅ | ✅ | ✅ | ✅ |
| N02 | Harmonies or background vocals | §3 Out | ✅ | ✅ | ✅ | ✅ |
| N03 | An overall vocal bus (the Lead routed through a shared vocal group) | §3 Out, J24 | ✅ | ✅ | ✅ | ✅ |
| N04 | Tracking or monitoring chains, or low-latency recording setups | §3 Out | ✅ | ✅ | ✅ | ✅ |
| N05 | A master chain or mastering: any processing on the Master, or on the beat beyond the optional carve | §3 Out, J7 | ✅ | ✅ | ✅ | ✅ |
| N06 | A section automation map, or any step that needs automation | §3 Out, §6.5, J25 | ✅ | ✅ | ✅ | ✅ |
| N07 | A signal-flow diagram | §3 Out, J17 | ✅ | ✅ | ✅ | ✅ |
| N08 | Any plugin outside the allow-list (C1), including everything on the block-list (C2) | §2, §5, J23 | ✅ | ✅ | ✅ | ✅ |
| N09 | Saturation of any kind: Saturn 2, FL distortion plugins, Pro-C 3 Character, Pro-Q 4 character modes | J9 | ✅ | — | — | ✅ |
| N10 | Pro-C 2 instructions or fallbacks, or pre-2024 FL menu paths | §9, J13 | ✅ | ✅ | ✅ | ✅ |
| N11 | Ducking done any way other than Pro-C 3 on the return keyed from the Lead | §6.1, J19 | ✅ | ✅ | ✅ | ✅ |
| N12 | Doubles detuned any way other than Auto-Tune Artist's Detune (e.g., clip pitch) | §6.4 | ✅ | ✅ | ✅ | ✅ |
| N13 | Processors beyond their stage's job (limiters, clippers, exciters, wideners, transient shapers, multiband, extra parallel buses) unless a §6/§7 item calls for that effect | J26 | ✅ | ✅ | ✅ | ✅ |
| N14 | Troubleshooting outside this chain (mastering, ad-libs, re-recording advice) | J15 | ✅ | ✅ | ✅ | ✅ |
| N15 | Relying on another file (another chain, SPEC, or PLAN) for a required step | J20 | ✅ | ✅ | ✅ | ✅ |

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
| FL Studio built-ins (not plugins) | Mixer faders, pan, stereo separation, sends, sidechain routing, mixer Track delay (added in Step 2, J34), mixer meters, playlist clip editing, channel settings |

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

## Appendix E: Verified toolkit digest (Step 2)

This is condensed from 8 reference sheets (2,700+ lines, kept in the session scratchpad). They were built from official manuals, help pages, UI screenshots, release notes, and changelogs. The **Source** column says where each fact comes from: **Text** = official manual/help text; **Shot** = official UI screenshot; **Notes** = official release notes; **Staff** = FabFilter staff forum post; **2nd** = corroborated non-official source, used only for option labels, never for ranges. "Unpublished" = no official value exists; J33 governs those.

### E1. Versions documented

| Tool | Current version | Documentation used |
|---|---|---|
| FL Studio (Producer Edition) | The online manual now covers FL Studio 2026 (26.1.7, 2026-09-28). The changelog shows no parameter changes to the natives used here since FL 2024, except Parametric EQ 2's HQ+ | Image-Line online manual + changelog |
| Auto-Tune Artist | 9.6.0 (discontinued, still downloadable for owners) | Antares User Guide (documents the 9.0 UI; the 9.5/9.6 notes list no control changes) |
| Pro-Q 4 / Pro-C 3 / Pro-DS / Pro-G / Pro-L 2 | 4.13 / 3.02 / 1.32 / 1.42 / 2.26 | FabFilter online help + PDF manuals (Apr 2026) |
| Pro-R 2 / Timeless 3 / Saturn 2 / Volcano 3 / Simplon | 2.06 / 3.10 / 2.13 / 3.09 / 1.42 | FabFilter online help + PDF manuals (Apr 2026) |
| Lewitt LCT 440 PURE | — | Official product page + manual Figure 9.1 |

### E2. Auto-Tune Artist

| Control (UI label) | Range / options | Source |
|---|---|---|
| INPUT TYPE | Soprano, Alto/Tenor, Low Male, Instrument, Bass Instrument | Text p.9 |
| KEY / SCALE | 28 scales, including CHROMATIC | Text p.10, p.31–33 |
| CLASSIC | On/off. "Auto-Tune 5 sound"; disables Formant, Throat, Transpose, and Flex-Tune | Text p.10 |
| FORMANT | On/off. Corrects formants after pitch shifts (prevents the "chipmunk" effect) | Text p.10–11 |
| THROAT | 100 = neutral; only active with FORMANT on; full range unpublished | Text p.11; Shot p.13 |
| TRANSPOSE | −12 to +12 semitones | Text p.11 |
| DETUNE | −100 to +100 cents (shown in cents or Hz); 0 c = A440. Shifts the target pitches themselves | Text p.11, p.28 |
| TRACKING | Default 50 | Text p.12 |
| RETUNE SPEED | ms. 0 = the hard "Auto-Tune Effect"; 10–50 is typical for natural correction | Text p.13–14 |
| FLEX-TUNE | 0 = always pulls to the note; higher values let more expression through; 0–100 scale | Text p.14; Shot |
| HUMANIZE | Slows retuning on sustained notes only; 0–100 scale (50 sits at 12 o'clock) | Text p.14; Shot p.14 |
| NATURAL VIBRATO | 0.0 at 12 o'clock (bipolar) | Shot p.13 |
| Advanced view | Vibrato SHAPE (No Vibrato / Sine Wave / Square / Sawtooth), RATE (Hz), ONSET DELAY (ms), ONSET RATE (ms), VARIATION, PITCH.AMT. (cents), AMPLITUDE AMT., FORMANT AMT.; TARGETING IGNORES VIBRATO. Ranges unpublished | Text p.20–22 |
| Settings | "Use Low Latency" (off = highest-quality processing) | Text p.29 |
| Not present | No Mix knob documented; no plug-in bypass (use FL's) | Text |

### E3. FabFilter

**Pro-Q 4**

| Control | Range / options | Source |
|---|---|---|
| Band shape | Bell, Low Shelf, Low Cut, High Shelf, High Cut, Notch, Band Pass, Tilt Shelf, Flat Tilt, All Pass | Text |
| Slope | 0–96 dB/oct in fractional steps, plus Brickwall on cuts. Minimums: Bell/Notch 12; cuts/Band Pass 0; others 6 | Text |
| FREQ / GAIN / Q | 10 Hz–30 kHz / −30 to +30 dB / Q default 1 (range unpublished) | Text |
| Stereo placement | Left, Right, Stereo, Mid, Side | Text |
| Dynamics | Range ring −30 to +30 dB (0 = static); Threshold slider with A (auto); "expand >>"; External side chain button per band; A / R knobs (50% = auto); Triggering Band / Free | Text |
| Spectral | Per band; always linear phase, about 100 ms latency | Text; Staff |
| Processing Mode | Zero Latency / Natural Phase / Linear Phase (default unpublished) | Text |
| Character | Clean (default) / Subtle (transformer) / Warm (tube). Subtle and Warm add saturation | Text |
| Global | Output Gain −∞ to +36 dB; Auto Gain; Gain Scale (%); Phase Invert (Ø); Output Pan in L/R or M/S mode | Text |
| Meter | Output level meter with peak readout | Product page |

**Pro-DS**

| Control | Range / options | Source |
|---|---|---|
| MODE | SINGLE VOCAL / ALLROUND | Shot |
| WIDE BAND / SPLIT BAND | Split Band is linear-phase and adds latency | Shot; Text |
| THRESHOLD / RANGE | −∞ to 0 dB / 0–24 dB | Shot |
| HP / LP trigger filters | 2–20 kHz | Text |
| LOOKAHEAD | 0–15 ms + on/off; help suggests about 10 ms for vocals | Shot; Text |
| STEREO LINK | 0–100%, then Mid- or Side-only | Text |
| Also | SIDE CHAIN In / Ext; Audition Triggering; Audition; Oversampling: Off / 2x / 4x; In: / Out: level and pan (ranges unpublished) | Shot; Text |
| Meters | Output and gain-reduction meters with max-level dB readouts (click to reset) | Text |

**Pro-G**

| Control | Range / options | Source |
|---|---|---|
| Style | Classic, Clean, Vocal, Guitar, Upward, Ducking | Text |
| Core | THRESHOLD −60 to 0 dB; RATIO 1:1 to ∞:1 (help: 2:1–5:1 for natural expansion); RANGE 0–100 dB; ATTACK 0 ms–1 s; RELEASE 0 ms–5 s; HOLD 0–250 ms; KNEE 0–30 dB; LOOKAHEAD 0–10 ms + on/off | Shot; Text |
| Expert | WET / DRY (OFF to +36 dB, with pan); SIDE CHAIN In / Ext; side-chain HP/LP 48 dB/oct; Audition; side-chain gain ±36 dB | Text |
| Also | Oversampling: Off / 2x / 4x; In: / Out: (ranges unpublished) | Shot |

**Pro-C 3**

| Control | Range / options | Source |
|---|---|---|
| Style (14) | Modern: Clean, Versatile, Smooth, Punch, Upward, TTM. Classic: Op-El, Vari-Mu, Classic, Opto. Utility: Vocal, Mastering, Bus, Pumping. Opto-type = Opto, Op-El. Vocal sets knee and ratio automatically | Text |
| THRESHOLD (AUTO, lock) / RANGE | dB; ranges unpublished | Shot |
| RATIO / KNEE | 1:1 to ∞ / 0–72 dB | Text |
| ATTACK / RELEASE (AUTO) | 0.005–250 ms / range unpublished | Text |
| LOOKAHEAD / HOLD | Up to 20 ms (global maximum Off–20 ms) / up to 500 ms | Text |
| GAIN (AUTO) / DRY | dB; ranges unpublished | Shot |
| Bottom bar | Input / Output / Mix (Mix 0–200%); Oversampling: Off, 2x, 4x, 8x, 16x, 32x | Text |
| Character | Off / Tube / Diode / Bright, plus Drive (range unpublished) and Pre/Post (Post default) | Text |
| SIDE CHAIN | Side Chain Input: Internal (default) / External / Host Sync / MIDI; LEVEL; STEREO LINK (0–100%, then Mid / Side / M>S / S>M); side-chain EQ up to 6 bands; Audition | Text |
| Meters | Gain reduction + output (+ input via Help > Show Input Level); numeric highest-peak readouts; EBU Momentary loudness on top | Text |

**Pro-L 2** (meter only, per J35)

| Item | Detail | Source |
|---|---|---|
| Loudness meter | Meter Scale → Loudness: Momentary, Short Term, Integrated (LUFS, BS.1770-4, gated); LRA; TP metering | Text |
| Transparent setup | True Peak Limiting off, Oversampling off, Gain 0 dB, Output Level 0 dB; Dither, DC, Unity Gain, Audition Limiting off. With these, no limiting happens while the input stays below 0 dB | Text; Staff |

**Saturn 2**

| Control | Range / options | Source |
|---|---|---|
| Per band | Style button; DRIVE (with pan ring; unit unpublished); MIX; FEEDBACK; FREQ; DYNAMICS; TONE (4 sliders: bass / mid / treble / presence); LEVEL −∞ to +36 dB (with pan ring); band power button (bypass); solo/mute with 2+ bands | Text |
| Bands | Up to 6; add with "+"; drag a crossover or double-click it to type Hz; slopes 6/12/24/48 dB/oct; Linear Phase button | Text |
| Global | Input / Output −36 to +36 dB; Mix %; High Quality: Good (8×) / Superb (32×); Channel Mode Stereo / Mid-Side; FB (unrestricted feedback) off by default | Text |
| Style names | Official: Warm Tape, Smudge, Breakdown, Foldback, Rectify, Destroy. Release notes: Subtle Tube / Tape / Saturation; British Rock / Pop; American Tweed / Plexi; Subtle / Gentle / Warm Transformer. Corroborated: Clean Tube, Warm Tube, Broken Tube, Clean Tape, Old Tape, Smooth Amp, Crunchy Amp, Lead Amp, Screaming Amp, Power Amp, Gentle Saturation, Heavy Saturation. Menu sections: Tube, Tape, Amp, Saturation, Transformer, FX | Text; Shot; Notes; 2nd |
| Behavior | Some input color remains even with a band's MIX fully dry; an always-on output soft clipper (higher ceiling for Subtle / Transformer styles) | Staff |

**Timeless 3**

| Control | Range / options | Source |
|---|---|---|
| DELAY | 5 ms–5 s; L / R time readouts under the knob; Delay Time Pan (up to 400%) | Text; Shot |
| Delay Sync (icon) | Mode list unpublished. When on, DELAY becomes Delay Offset, 50–200% (typing "d" / "t" gives dotted / triplet) | Text |
| Delay Read Mode | Tape / Stretch | Text |
| FEEDBACK / CROSS | 0–200% (above 100% drives the internal saturation) / 0–100%; Feedback Pan; ± invert | Text |
| Ping Pong (icon) | Starts from L or R; feeds one channel, cross-feedback only | Text |
| Output side | WIDTH (MONO…STEREO); WET (pan ring); MIX 0–100% (100% = wet only); Lock Mix | Text; Shot |
| Filters | Up to 6, in the feedback loop. LP / HP / BP are analog-style with styles, including Clean ("no saturation"). Bell / Shelf / Notch are clean. Freq / Gain / Q / Pan per filter; routing Serial / Parallel / Per-channel | Text |
| Color stages | DRIVE, LO-FI, DIFFUSE 0–100%; DYNAMICS gate↔compression; PITCH −12 to +12 (minimum delay becomes 45 ms when on) | Text; Shot |
| Modulation | "+" → New XLFO (0.02–500 Hz, or synced 16 to 1/64 bars) → drag onto the target → slot Level = depth | Text |
| Also | Input / Output gain −36 to +36 dB; Channel Mode Left/Right (default) or Mid/Side; zero latency; no built-in ducking control | Text; Staff |

**Pro-R 2**

| Control | Range / options | Source |
|---|---|---|
| Style | Modern / Vintage / Plate | Text |
| SPACE + Decay Rate | Decay readout in seconds, 0.2–10 s; Decay Rate (% knob) 25–400% (final decay = Space × rate) | Text; Shot |
| PREDELAY | 0–500 ms; sync Off (default) / Quarter Note / 8th Note / 16th Note / 32th Note [sic]; Predelay Offset 50–200% | Text |
| CHARACTER | 0–100% (0% transparent; modulation rises from 50%) | Text |
| THICKNESS / BRIGHTNESS / DUCKING | Density + saturation / high-frequency absorption / built-in ducking range. All three ranges unpublished | Text |
| DISTANCE / WIDTH | From 0% / 0% mono, 100% independent channels, above 100% boosts the side signal | Text |
| Also | MIX % (100% on sends); Lock Mix; Auto Gate; Freeze | Text |
| EQs | Decay Rate EQ: 6 bands (Bell, Low Shelf, High Shelf, Notch). Post EQ: 6 bands (Bell, Low Shelf, High Shelf, Low Cut, High Cut; cuts up to 96 dB/oct) | Text |

**Volcano 3 and Simplon** (band-pass candidates)

| Plugin | Facts | Source |
|---|---|---|
| Volcano 3 | 4 filters; shapes low/high pass, band pass, bell, low/high shelf, notch, all pass; slopes 6/12/24/48 dB/oct; 11 styles, including Clean ("linear behavior with no drive or clipping at all"); DRIVE, FREQUENCY, PEAK, SLOPE, DELAY (≤ 50 ms), LEVEL | Text |
| Simplon | Low / High / Band Pass; characteristics FabFilter One / Gentle / Raw. **Every characteristic includes overdrive** (none is linear), so it can't be a clean band-pass | Text |

### E4. FL Studio native plugins

| Plugin | Controls (panel labels) and what's documented | Source |
|---|---|---|
| Fruity Chorus | DELAY 0–30 ms; DEPTH (ms; screenshot 2.25); STEREO 0–360°; LFO 1/2/3 FREQ. (Hz; screenshot 0.45 / 1.25 / 2.45); LFO 1/2/3 WAVE ("sin" shown, "Multi-sine" named); CROSS TYPE ("Process HF" on the panel; the text says Process HP / LP); CROSS CUTOFF (Hz; screenshot 320); WET ONLY (no/yes). No mix or output knob | Text; Shot |
| Fruity Phaser | SWEEP FREQ. (0–2 Hz in small range, 0–10 Hz in large); MIN DEPTH / MAX DEPTH (screenshot 0.10 / 0.80); FREQ. RANGE (small / large); STEREO (0–360°; readout says "phase"); NR. STAGES (up to 23; "stompboxes usually have 4 or 6"); FEEDBACK (screenshot 0.40); DRY-WET (% wet); OUT GAIN (dB) | Text; Shot |
| Not usable / not preferred | Fruity Delay 3: its feedback-distortion stage has no Off, so a clean copy can't be guaranteed. Fruity Stereo Shaper: delays only one channel. Parametric EQ 2 main level: range unpublished. Blood Overdrive / Fast Dist / Soft Clipper / WaveShaper: no ranges or defaults published (still allowed, J33) | Text |
| Typing values | Right-click → "Type in value". Context-aware units are confirmed for Parametric EQ 2, Blood Overdrive, Fast Dist, WaveShaper, Soft Clipper, and Stereo Shaper, but **not** for Chorus, Phaser, or Delay 3: set those by dragging while reading the hint bar. Ctrl-drag = fine adjust; Alt-click = reset | Text |

### E5. FL Studio procedures (FL 2026 wording; all present since FL 2024)

| Task | Exact steps | Source |
|---|---|---|
| Send, keeping Master | Select the source → left-click the destination's send switch. The level knob sits on the destination; right-click → "Type in value" (the hint shows dB) | Text |
| Route only to a bus | Select the source → left-click the bus's send switch → left-click Master's send switch off. Or Track routing → "Route selected to this track only" | Text |
| Sidechain feed | Select the source → right-click the target's send switch → "Sidechain to this track". This is a send at 0, so it's silent; the source keeps its Master route | Text |
| Feed a VST3 sidechain | Plugin window gear → "Plugin Wrapper Settings" → "Processing" → "Connections": right-click the sidechain input number and pick the source (or "Auto map inputs"). Then enable the plugin's own external side chain | Text |
| Delay compensation | Mixer menu → "Plugin delay compensation" → "Automatic" (the default). Covers sends and sidechains | Text |
| Send position | Post-fader, after the insert effects | Text |
| Track delay | Clock icon on the mixer track → "Set in ms (milliseconds)". Not cancelled by PDC; sign convention unpublished | Text |
| Doubles on own inserts | Shift-drag a copy to a new playlist track → clip menu "Make unique" (not "Make unique as sample") → channel settings TRACK = the double's insert | Text |
| Rename / color | Right-click the track → "Rename, color & icon..." (F2) | Text |
| Pan / separation | Pan in %; Circular pan law (−3 dB center) by default. Stereo separation: center = off, right = narrower toward mono, left = wider | Text |
| Mixer meters | Peak only, no numeric readout (hover → hint bar) | Text |
| Edison denoise | Select a noise-only part → Tools > Spectral > "Aquire noise profile" [sic] (Alt+U) → "Clean up (denoise)" (Ctrl+U) → Preview, set Threshold first, then Amount ("Output noise only" to check) → Accept | Text |

### E6. Meters chosen (sub-step 2.6, J35)

| Job | Meter | How it's used |
|---|---|---|
| Calibration (J2) | Pro-L 2, transparent setup, **Integrated** loudness | Temporarily first on the Lead insert; play the whole raw take; trim = target − reading; then remove it |
| Placement (J6) | Pro-L 2, **Short Term** loudness | Temporarily on the beat insert and last on the Lead insert; read both on the loudest section; set the Lead fader to the target gap; then remove it |
| Gain-reduction readings (J18) | Each dynamics plugin's own meter | Pro-C 3 and Pro-DS have numeric max readouts |
| Beat headroom (J7) | FL Master peak meter (hint bar) | Read while the beat plays alone |

### E7. Mic facts (sub-step 2.7)

From Lewitt's official Figure 9.1 (read to about ±0.5 dB):
- **Lows and mids:** flat. −1.5 dB at 20 Hz, 0 dB from 150 Hz to 1 kHz.
- **Gentle rise:** +1 dB at 2 kHz, **+3.5 dB presence bump near 4 kHz**, +2.5 dB at 6–7 kHz.
- **Air:** **+5 dB peak near 12–13 kHz**, back to 0 dB at 20 kHz.

So the spec's "leans bright" is confirmed. Harshness control centers on 3.5–5 kHz, de-essing on the band above it, and air boosts can be smaller than usual. The boxiness comes from the booth, not the mic. Lewitt calls the mic "neutral", "never straining or harsh".

### E8. Delay and pre-delay master table (sub-step 2.8)

Computed by script with exact rational math, rounded half-up to 0.1 ms, and self-checked (e.g., 150 BPM dotted ⅛ = 300.0 ms). Each file copies only the columns it uses.

| BPM | 1/2 | 1/4. | 1/4 | 1/8. | 1/8 | 1/8T | 1/16 | 1/32 | 1/64 |
|---|---|---|---|---|---|---|---|---|---|
| 130 | 923.1 | 692.3 | 461.5 | 346.2 | 230.8 | 153.8 | 115.4 | 57.7 | 28.8 |
| 135 | 888.9 | 666.7 | 444.4 | 333.3 | 222.2 | 148.1 | 111.1 | 55.6 | 27.8 |
| 140 | 857.1 | 642.9 | 428.6 | 321.4 | 214.3 | 142.9 | 107.1 | 53.6 | 26.8 |
| 145 | 827.6 | 620.7 | 413.8 | 310.3 | 206.9 | 137.9 | 103.4 | 51.7 | 25.9 |
| 150 | 800.0 | 600.0 | 400.0 | 300.0 | 200.0 | 133.3 | 100.0 | 50.0 | 25.0 |
| 155 | 774.2 | 580.6 | 387.1 | 290.3 | 193.5 | 129.0 | 96.8 | 48.4 | 24.2 |
| 160 | 750.0 | 562.5 | 375.0 | 281.3 | 187.5 | 125.0 | 93.8 | 46.9 | 23.4 |
| 165 | 727.3 | 545.5 | 363.6 | 272.7 | 181.8 | 121.2 | 90.9 | 45.5 | 22.7 |
| 170 | 705.9 | 529.4 | 352.9 | 264.7 | 176.5 | 117.6 | 88.2 | 44.1 | 22.1 |

### E9. Gaps found and how they're handled (sub-step 2.9)

| Gap | Handling | Call |
|---|---|---|
| Vendors publish almost no defaults | Every row states the value to set; no row relies on "default" | J32 |
| Some ranges are unpublished (Pro-C 3 Threshold / Range / Release / Gain / Dry; Pro-R 2 Thickness / Brightness / Ducking; Timeless 3 filter ranges; Fruity Chorus / Phaser) | Value-selection rule, plus typed entry or readback | J33, J40 |
| Auto-Tune Artist maximums and Throat range unpublished | Read from the official screenshots | J39 |
| No clean FL plugin for double time offsets | Mixer Track delay | J34 |
| FL meters show no numbers | Pro-L 2 as a meter only | J35 |
| The trim must sit before the dynamic band | Trim-only Pro-Q 4 | J36 |
| Timeless 3 sync labels unpublished | Quarter-note entry + Delay Offset | J37 |
| The FL manual now documents FL 2026 | 2026 wording, FL 2024 feature floor | J38 |
| Pro-Q 4 spectral mode adds about 100 ms latency | Standard dynamic bands, Zero Latency mode | J41 |
| Built-in ducking and saturation in other plugins | Neutralized where the spec doesn't call for them | J42 |
| Some Saturn 2 style names are unofficial | J33's option-label clause (name + menu section) | J33 |
| Simplon always overdrives | Out for the Alien layer's clean band-pass (J9) | — |

### E10. Effect on Step 1's lists

C1 now lists the mixer Track delay among FL built-ins. The C3 "open for Step 3" list after Step 2:

| Job | Status |
|---|---|
| Input trim / calibration | **Resolved:** trim-only Pro-Q 4 (J36) |
| Double time offsets | **Resolved:** FL mixer Track delay (J34) |
| Placement and calibration meters | **Resolved:** Pro-L 2 as a meter (J35) |
| Alien layer band-pass | Pro-Q 4 Band Pass, or Volcano 3 in Clean style. Simplon is out (always overdrives) |
| #5 in-line crunch | Saturn 2 (fully mapped structure) or Pro-C 3 Character. FL distortion natives allowed but unpublished ranges |
| #5 parallel crunch, mids only | Saturn 2 multiband (band power / mute), or a Pro-Q 4 band-limit around Saturn 2 |
| #5 doubles' extra dirt + band-limit | Saturn 2 + Pro-Q 4 |
| #6 light warmth | Saturn 2 (e.g., Warm Tape, an official name), Pro-C 3 Character, or Pro-Q 4 Character |
| Where the chorus sits (#4, #9) | Unchanged: Fruity Chorus on each double or on the Doubles bus |

---

## Appendix F: Chain blueprints (Step 3)

Every value is decided here; Step 4 turns these into full per-parameter tables and prose.

**Slot IDs:**
- **L** = a slot on the LEAD insert
- **D** = a slot on a double's insert
- **B** = a slot on DBL BUS
- **R7.1** etc. = insert 7, slot 1 (a return)

**T** = your calibration trim (F1). "Typed %" means FabFilter's documented text entry, where a typed percentage sets the knob's position in its travel (J43).

### F1. Shared conventions (all four files)

**Session and routing**
- Insert 1 is always **BEAT** (fader trim + the optional carve only). Insert 2 is always **LEAD**. The doubles come next, then **DBL BUS**, then the FX returns.
- LEAD → Master, plus post-fader sends to its returns. Every ducked return also gets "Sidechain to this track" from LEAD; the key is the Lead insert's output (J29).
- Each double routes **only** to DBL BUS. DBL BUS → Master. Returns → Master, faders at 0.0 dB.
- Return feeds (J46): in #4 and #5 the returns are fed by LEAD only. In #6 the hall, and in #9 the plate, are also fed by DBL BUS.
- If you need Edison denoise (L2a), do it **before** copying the doubles, so every copy is clean.

**Gain structure (J49, J50)**

| Item | Value |
|---|---|
| Calibration | Pro-L 2 used as a meter (J35), Integrated, played over the whole raw take, placed on LEAD before L1. **T = −20.0 − reading** (e.g., −24.3 LUFS → T = +4.3 dB). The same T goes in every TRIM slot |
| DBL BUS trim | T + offset: #4 −0.5 dB, #5 −1.5 dB, #6 −3.0 dB, #9 −1.0 dB. This cancels the extra level of several doubles summing on the bus, so its compressor sees the same level as the lead's |
| Beat headroom | Pull the BEAT fader down until the beat alone peaks at **−6.0 dBFS** on the Master meter (hint bar) |
| Level matching | Each compressor's GAIN ≈ 60% of its loud-line gain reduction; each Saturn 2 LEVEL offsets its drive. Bypass check: loudness within about 1 dB |
| Placement | Pro-L 2 Short Term, last slot on BEAT and on LEAD, over the loudest 8 bars. Inserts are pre-fader, so: **LEAD fader = (Beat ST + BEAT fader + Δ) − Lead ST**. Δ: #5 **0.0 LU**, #4 **−1.5 LU**, #6 **−1.5 LU**, #9 **−3.5 LU**. Then remove both meters |
| Doubles level | Each double's fader as listed per style; **DBL BUS fader = LEAD fader − D**: #4 9 dB, #5 7 dB, #6 10 dB, #9 11 dB |

**Lead front end, identical in all four (GX03)**

| Slot | Plugin | Settings | Expect |
|---|---|---|---|
| L1 TRIM | Pro-Q 4 | No bands · Processing Mode Zero Latency · Character Clean · Output Gain **T** · Output Pan centre (L/R mode) · Auto Gain off · Gain Scale 100% · Phase Invert off | Raw take sits at −20 LUFS Integrated |
| L2 CLEANUP | Pro-Q 4 | Band 1: Low Cut 85 Hz, 18 dB/oct, Q 1.0, Stereo. Band 2: Bell 320 Hz, −2.5 dB, Q 1.2, Stereo. Band 3: Bell 4.2 kHz, 0.0 dB, Q 2.0, Stereo, dynamic with Range −4.0 dB, Threshold A (auto), A 50% / R 50% (auto), Triggering Band, external side chain off, Spectral off. Globals as L1, with Output Gain 0.0 dB | Band 3 dips 0–3 dB on bright/harsh notes only |
| L2a (only if room tone is audible) | Edison, then Pro-G | **Edison** (on the raw clip, before copying the doubles): noise profile from a gap → Clean up (denoise), Threshold 0 dB, Amount 60% (hint bar), check with "Output noise only", Accept. **Pro-G:** Style Vocal · THRESHOLD −50 dB · RATIO 2.0:1 · RANGE 10 dB · ATTACK 1 ms · HOLD 60 ms · RELEASE 180 ms · KNEE 6 dB · LOOKAHEAD on, 2 ms · Expert off · Oversampling 2x · In/Out 0.0 dB, centre | Test: solo LEAD; if booth hiss or hum is audible in the gaps at normal volume, use it (and add the same Pro-G as B2a) |
| L3 DE-ESS | Pro-DS | MODE Single Vocal · WIDE BAND · THRESHOLD −26.0 dB · RANGE 6.0 dB · HP 5.5 kHz / LP 11.0 kHz · LOOKAHEAD on, 10 ms · STEREO LINK 100% (the "100%" scale mark) · SIDE CHAIN In · Audition Triggering off · Audition off · Oversampling 2x · In/Out 0.0 dB, centre | 3–6 dB GR on s / sh / t; about 0 elsewhere |

**Auto-Tune Artist settings shared by every instance:**
- INPUT TYPE Alto/Tenor
- KEY / SCALE = the song's key (Chromatic if unknown)
- CLASSIC off · TRACKING 50 · NATURAL VIBRATO 0.0
- Vibrato: SHAPE No Vibrato (RATE 5.0 Hz, ONSET DELAY 0 ms, ONSET RATE 0 ms, VARIATION 0, PITCH.AMT. 0, AMPLITUDE AMT. 0, FORMANT AMT. 0) · TARGETING IGNORES VIBRATO off
- No notes removed or bypassed · Use Low Latency off

The per-instance values are listed with each style: RETUNE SPEED, HUMANIZE, FLEX-TUNE, FORMANT, THROAT, TRANSPOSE, DETUNE.

**Doubles recipe (J45).**
- Each double's insert: D1 Auto-Tune Artist (FORMANT on; its own RETUNE, HUMANIZE, THROAT, DETUNE) → D2 Pro-Q 4 (its own EQ; Zero Latency, Clean). On the mixer: its own pan, fader, and Track delay ("Set in ms").
- DBL BUS: B1 TRIM (Pro-Q 4, Output Gain = T + offset) → B2 CLEANUP (Pro-Q 4 = L2 bands 2 and 3, no Low Cut) → B2a (same Pro-G as L2a, only if used) → B3 Pro-DS (= L3) → B4 Pro-C 3 → B5 and on: style processing.

**Return building blocks**

| Block | Settings |
|---|---|
| Ducking Pro-C 3 (last slot of every ducked return) | Style Clean · AUTO threshold off · KNEE 6 dB · AUTO release off · bottom-bar Lookahead: Off, LOOKAHEAD slider 0 ms · GAIN 0.0 dB, AUTO gain off, gain pan centre · DRY fully off (−∞) · Character Off · Side Chain Input **External** (fed from LEAD through the wrapper's Connections) · LEVEL 0.0 dB · Audition off · STEREO LINK 100% · no side-chain EQ bands · Oversampling 2x · Input / Output 0.0 dB, centre · Mix 100%. THRESHOLD, RATIO, RANGE, ATTACK, RELEASE, and HOLD are set per return |
| Timeless 3 base | Delay Sync on, quarter-note entry (J37) · Delay Time Pan centre · Freeze off · Feedback Pan centre · both ± invert off · WET 50% typed (the 12 o'clock unity position) · MIX 100% · Lock Mix off · Filter Routing Serial · Auto Mute Self-Osc on · DRIVE 0% · LO-FI 0% · DYNAMICS 50% typed (centre = off) · PITCH off · Input / Output 0.0 dB, centre · Channel Mode Left/Right · no modulation unless listed · every filter in Clean style, Q 0.7 |
| Pro-R 2 base | Decay Rate 100% (Ctrl-click; SPACE then shows one time only) · THICKNESS 0% typed · DUCKING 0% typed · MIX 100% · Lock Mix off · Auto Gate off · Freeze off · Input / Output 0.0 dB, centre |
| Oversampling (J27) | Pro-C 3 / Pro-DS / Pro-G: 2x. Saturn 2: High Quality Good |

### F2. #4 Alien Transmission

**Mixer:** 1 BEAT · 2 LEAD · 3 DBL L · 4 DBL R · 5 DBL ALIEN · 6 DBL BUS · 7 FX DELAY · 8 FX SHIMMER

| Slot | Plugin | Settings | Expect |
|---|---|---|---|
| L4 | Auto-Tune Artist | RETUNE SPEED 10 ms · HUMANIZE 15 · FLEX-TUNE 0 · FORMANT off (THROAT 100, inactive) · TRANSPOSE 0 · DETUNE 0 c | Clearly tuned; held notes stay natural |
| L5 | Pro-C 3 | Clean · THRESHOLD −22 dB · RATIO 3.0:1 · KNEE 12 dB · RANGE 24 dB · ATTACK 5 ms · RELEASE 80 ms · HOLD 0 ms · GAIN +3.0 dB · DRY off · Character Off · Side Chain Internal (LEVEL 0 dB, link 100%, no EQ) · Lookahead Off · Oversampling 2x · In/Out 0 dB · Mix 100% | 4–6 dB GR on loud lines, 1–2 dB on soft |
| L6 | Pro-Q 4 TONE | Bell 200 Hz −1.5 dB Q 0.8 · Bell 2.8 kHz +1.5 dB Q 1.0 · High Shelf 10 kHz +2.0 dB, 12 dB/oct, Q 1.0 · Zero Latency, Clean | Crisp, glossy top |
| L7 | (none) | The style lives in the returns and doubles; no saturation (J9) | — |
| L8 | Pro-DS #2 | As L3, except THRESHOLD −30 dB · RANGE 4 dB · HP 6.0 kHz / LP 14.0 kHz | 2–4 dB GR on the esses the shelf brought up |
| Sends | LEAD | → FX DELAY −8.0 dB · → FX SHIMMER −16.0 dB · sidechain → FX DELAY and FX SHIMMER | — |

**Doubles**

| | DBL L (3) | DBL R (4) | DBL ALIEN (5) |
|---|---|---|---|
| Pan / fader / Track delay | −85% / 0.0 dB / 15 ms | +85% / 0.0 dB / 23 ms | 0% / −7.0 dB / 31 ms |
| D1 Auto-Tune | RETUNE 14 ms · HUMANIZE 20 · FLEX 0 · THROAT 104 · DETUNE +7 c | RETUNE 18 ms · HUMANIZE 25 · FLEX 0 · THROAT 96 · DETUNE −8 c | RETUNE 12 ms · HUMANIZE 10 · FLEX 0 · THROAT 111 · DETUNE −4 c |
| D2 Pro-Q 4 | Low Cut 140 Hz, 18 dB/oct · Bell 1.2 kHz +1.0 dB Q 1.0 · High Shelf 8 kHz −1.5 dB | Low Cut 160 Hz, 18 dB/oct · Bell 2.4 kHz −1.0 dB Q 1.0 · High Shelf 8 kHz −0.5 dB | Band-pass: Low Cut 500 Hz, 24 dB/oct + High Cut 5.0 kHz, 24 dB/oct · Bell 1.6 kHz +2.0 dB Q 1.4 |

**DBL BUS (6):**
- B1 trim T − 0.5 dB · B2 / B3 shared
- B4 Pro-C 3 Smooth: THRESHOLD −24 dB, RATIO 3.0:1, KNEE 18 dB, RANGE 24 dB, ATTACK 10 ms, RELEASE 150 ms, GAIN +3.0 dB (everything else as L5)
- B5 Fruity Chorus: DELAY 8.0 ms, DEPTH 2.0 ms, STEREO 90°, LFO 1/2/3 FREQ. 0.35 / 0.80 / 1.70 Hz, LFO WAVE sin ×3, CROSS TYPE Process HF, CROSS CUTOFF 250 Hz, WET ONLY no
- Fader: LEAD − 9 dB · no sends

**Returns**

| Slot | Plugin | Settings | Expect |
|---|---|---|---|
| R7.1 | Timeless 3 | Base + Delay Offset **75%** (dotted ⅛) · Delay Read Mode Stretch · Ping Pong on, start Left · FEEDBACK 38% · CROSS 100% · WIDTH 100% · Filter 1 High Pass 350 Hz, 12 dB/oct · Filter 2 Low Pass 6.5 kHz, 12 dB/oct · DIFFUSE 12% | 2–3 bouncing repeats; the readouts under DELAY match the 1/8. column |
| R7.2 | Fruity Phaser | SWEEP FREQ. 0.10 Hz · FREQ. RANGE small · MIN DEPTH 0.20 · MAX DEPTH 0.75 · STEREO 90° · NR. STAGES 6 · FEEDBACK 0.30 · DRY-WET 40% wet · OUT GAIN 0.0 dB | A slow swirl on the echoes (one sweep every 10 s) |
| R7.3 | Pro-C 3 duck | THRESHOLD −30 dB · RATIO 4.0:1 · RANGE 8 dB · ATTACK 5 ms · RELEASE 250 ms · HOLD 40 ms | 6–8 dB GR while you sing, 0 in the gaps |
| R8.1 | Auto-Tune Artist | RETUNE 20 ms · HUMANIZE 0 · FLEX 0 · FORMANT on · THROAT 100 · TRANSPOSE **+12** · DETUNE 0 c | The send comes out an octave up |
| R8.2 | Pro-R 2 | Base + Style Modern · SPACE 3.5 s · PREDELAY sync 32th Note, Offset 100% · CHARACTER 55% · DISTANCE 40% · BRIGHTNESS 60% typed · WIDTH 100% · Decay Rate EQ: Low Shelf 300 Hz, 50%, Q 1.0 · Post EQ: Low Cut 400 Hz, 24 dB/oct; High Cut 12 kHz, 12 dB/oct | A quiet, airy octave-up glow behind the words |
| R8.3 | Pro-C 3 duck | THRESHOLD −30 dB · RATIO 3.0:1 · RANGE 4 dB · ATTACK 10 ms · RELEASE 400 ms · HOLD 40 ms | About 4 dB GR while you sing |

**Placement:** Δ −1.5 LU. **Optional carve:** Bell 2.5 kHz, Q 1.0, Range −3.0 dB + Bell 4.5 kHz, Q 1.4, Range −2.0 dB.

### F3. #5 Rage Blowout

**Mixer:** 1 BEAT · 2 LEAD · 3 DBL L · 4 DBL R · 5 DBL BUS · 6 FX CRUNCH · 7 FX ROOM · 8 FX DELAY

| Slot | Plugin | Settings | Expect |
|---|---|---|---|
| L4 | Auto-Tune Artist | RETUNE SPEED **2 ms** · HUMANIZE 0 · FLEX-TUNE **15** · FORMANT off (THROAT 100, inactive) · TRANSPOSE 0 · DETUNE 0 c | Hard tune on sung notes; yells pass without warbling |
| L5 | Pro-C 3 | Punch · THRESHOLD −24 dB · RATIO 6.0:1 · KNEE 6 dB · RANGE 30 dB · ATTACK 1.0 ms · RELEASE 60 ms · HOLD 0 ms · GAIN +5.0 dB · DRY off · Character Off · Side Chain Internal · Lookahead Off (J52) · Oversampling 2x · In/Out 0 dB · Mix 100% | Sung lines 3–6 dB GR, yelled lines 8–14 dB |
| L6 | Saturn 2 (in-line crunch) | 1 band · Style **British Rock** (Amp) · DRIVE 22% · DRIVE pan centre · MIX 100% · FEEDBACK 0% · FREQ 1.0 kHz (inactive at 0 feedback) · DYNAMICS 50% typed (centre) · TONE: all four sliders 50% typed (centre) · LEVEL −3.0 dB, pan centre · band on. Global: Input / Output 0.0 dB · Mix 100% · High Quality Good · Linear Phase off · Channel Mode Stereo · FB off · no modulation | Obvious but controlled grit; bypass level within 1 dB |
| L7 | Pro-Q 4 TONE (after the dirt, J48) | Bell 180 Hz −1.5 dB Q 0.9 · Bell 1.3 kHz +2.5 dB Q 0.8 · High Shelf 9.0 kHz −2.5 dB, 12 dB/oct · High Cut 16 kHz, 12 dB/oct · Zero Latency, Clean | Mid-forward bite; no airy shine; no fizz |
| Sends | LEAD | → FX CRUNCH 0.0 dB · → FX ROOM −13.0 dB · → FX DELAY −12.0 dB · sidechain → FX DELAY | — |

**Doubles**

| | DBL L (3) | DBL R (4) |
|---|---|---|
| Pan / fader / Track delay | −45% / 0.0 dB / 12 ms | +45% / 0.0 dB / 19 ms |
| D1 Auto-Tune | RETUNE 4 ms · HUMANIZE 0 · FLEX 15 · THROAT 103 · DETUNE +6 c | RETUNE 6 ms · HUMANIZE 5 · FLEX 15 · THROAT 97 · DETUNE −7 c |
| D2 Pro-Q 4 | Low Cut 220 Hz, 24 dB/oct · High Cut 6.0 kHz, 24 dB/oct · Bell 1.1 kHz +1.5 dB Q 1.0 | Low Cut 250 Hz, 24 dB/oct · High Cut 5.5 kHz, 24 dB/oct · Bell 1.6 kHz +1.5 dB Q 1.0 |

**DBL BUS (5):**
- B1 trim T − 1.5 dB · B2 / B3 shared
- B4 Pro-C 3 = L5 (Punch, −24 dB, 6:1, 1 ms / 60 ms, +5 dB)
- B5 Saturn 2: Style **Crunchy Amp** (Amp), DRIVE 45%, LEVEL −5.0 dB (everything else as L6)
- B6 Pro-Q 4: Low Cut 250 Hz, 12 dB/oct · High Cut 5.0 kHz, 24 dB/oct
- Fader: LEAD − 7 dB · no sends

**Returns**

| Slot | Plugin | Settings | Expect |
|---|---|---|---|
| R6.1 | Pro-Q 4 (pre) | Low Cut 300 Hz, 24 dB/oct · High Cut 4.0 kHz, 24 dB/oct · Zero Latency, Clean | Only the mids reach the dirt |
| R6.2 | Saturn 2 | Style **Crunchy Amp** (Amp) · DRIVE 60% · LEVEL −6.0 dB (everything else as L6) | Heavy crunch |
| R6.3 | Pro-Q 4 (post) | Low Cut 250 Hz, 12 dB/oct · High Cut 5.0 kHz, 24 dB/oct | Lows stay tight; highs don't fizz |
| R6 fader | — | −3.0 dB · **never ducked** (it's part of the lead's sound) | Soloed it sounds like a distorted telephone; blended, the lead is clearly dirtier |
| R7.1 | Pro-R 2 | Base + Style Modern · SPACE 0.6 s · PREDELAY 8 ms (sync Off) · CHARACTER 0% · DISTANCE 15% · BRIGHTNESS 25% typed · WIDTH 80% · Post EQ: Low Cut 250 Hz, 24 dB/oct; High Cut 5.0 kHz, 12 dB/oct · not ducked | Short, dark, gritty space |
| R8.1 | Timeless 3 | Base + Delay Offset **100%** (¼) · Delay Read Mode Stretch · Ping Pong off · FEEDBACK 30% · CROSS 0% · WIDTH 50% · Filter 1 High Pass 400 Hz, 12 dB/oct · Filter 2 Low Pass 3.5 kHz, 12 dB/oct · DIFFUSE 0% | Dark ¼ repeats |
| R8.2 | Pro-C 3 duck | THRESHOLD −32 dB · RATIO 8.0:1 · RANGE 18 dB · ATTACK 2 ms · RELEASE 180 ms · HOLD 30 ms | 15–18 dB GR while you rap or yell, so echoes appear only on line endings |

**Placement:** Δ 0.0 LU (the most forward of the four). **Optional carve:** Bell 2.5 kHz, Q 1.0, Range −4.0 dB + Bell 4.5 kHz, Q 1.4, Range −3.0 dB.

### F4. #6 Melodic Rage Anthem

**Mixer:** 1 BEAT · 2 LEAD · 3 DBL A-L · 4 DBL A-R · 5 DBL B-L · 6 DBL B-R · 7 DBL BUS · 8 FX HALL · 9 FX DELAY

| Slot | Plugin | Settings | Expect |
|---|---|---|---|
| L4 | Auto-Tune Artist | RETUNE SPEED 8 ms · HUMANIZE 18 · FLEX-TUNE 0 · FORMANT off (THROAT 100, inactive) · TRANSPOSE 0 · DETUNE 0 c | Hard but smooth; long notes don't sound frozen |
| L5 | Pro-C 3 | Versatile · THRESHOLD −22 dB · RATIO 3.5:1 · KNEE 12 dB · RANGE 24 dB · ATTACK 8 ms · RELEASE 100 ms · HOLD 0 ms · GAIN +3.5 dB · DRY off · Character Off · Side Chain Internal · Lookahead Off · Oversampling 2x · In/Out 0 dB · Mix 100% | 4–6 dB GR on loud lines |
| L6 | Pro-Q 4 TONE | Bell 250 Hz −1.0 dB Q 1.0 · Bell 3.0 kHz +1.5 dB Q 1.0 · High Shelf 11 kHz +3.0 dB, 12 dB/oct, Q 1.0 · Zero Latency, Clean | Bright, airy arena shine |
| L7 | Saturn 2 (light warmth) | 1 band · Style **Warm Tape** (Tape) · DRIVE 15% · LEVEL −1.0 dB (everything else as #5 L6) | Thicker, but no audible grit |
| L8 | Pro-DS #2 | As L3, except THRESHOLD −30 dB · RANGE 4 dB · HP 6.5 kHz / LP 14.0 kHz | 2–4 dB GR on esses |
| Sends | LEAD | → FX HALL −10.0 dB · → FX DELAY −11.0 dB · sidechain → FX HALL and FX DELAY | — |

**Doubles (4-double wall)**

| | DBL A-L (3) | DBL A-R (4) | DBL B-L (5) | DBL B-R (6) |
|---|---|---|---|---|
| Pan / fader / Track delay | −100% / 0.0 dB / 17 ms | +100% / 0.0 dB / 23 ms | −50% / −3.0 dB / 11 ms | +50% / −3.0 dB / 29 ms |
| D1 Auto-Tune | RETUNE 10 · HUM 20 · THROAT 104 · DETUNE +8 c | RETUNE 12 · HUM 22 · THROAT 96 · DETUNE −9 c | RETUNE 14 · HUM 24 · THROAT 107 · DETUNE +5 c | RETUNE 16 · HUM 26 · THROAT 94 · DETUNE −4 c |
| D2 Pro-Q 4 | Low Cut 180 Hz, 18 dB/oct · High Shelf 10 kHz −2.0 dB | Low Cut 190 Hz, 18 dB/oct · High Shelf 9 kHz −2.0 dB · Bell 1.5 kHz +0.5 dB Q 1.0 | Low Cut 220 Hz, 18 dB/oct · Bell 2.0 kHz −1.5 dB Q 1.0 | Low Cut 240 Hz, 18 dB/oct · Bell 2.6 kHz −1.5 dB Q 1.0 |

FLEX-TUNE is 0 on every double.

**DBL BUS (7):**
- B1 trim T − 3.0 dB · B2 / B3 shared
- B4 Pro-C 3 Smooth: THRESHOLD −24 dB, RATIO 3.0:1, KNEE 18 dB, RANGE 24 dB, ATTACK 10 ms, RELEASE 150 ms, GAIN +3.0 dB
- B5 Saturn 2 Warm Tape: DRIVE 12%, LEVEL −1.0 dB (the wall shares the light warmth)
- B6 Pro-Q 4: High Shelf 9 kHz −1.5 dB (the lead stays the brightest thing)
- Fader: LEAD − 10 dB · send → FX HALL −14.0 dB

**Returns**

| Slot | Plugin | Settings | Expect |
|---|---|---|---|
| R8.1 | Pro-R 2 | Base + Style Modern · SPACE 3.4 s · PREDELAY sync 16th Note, Offset 100% · CHARACTER 40% · DISTANCE 55% · BRIGHTNESS 65% typed · WIDTH 100% · Decay Rate EQ: Low Shelf 250 Hz, 70%, Q 1.0 · Post EQ: Low Cut 220 Hz, 24 dB/oct; High Shelf 9 kHz −2.0 dB; High Cut 15 kHz, 12 dB/oct | Arena-sized tail |
| R8.2 | Pro-C 3 duck | THRESHOLD −30 dB · RATIO 6.0:1 · RANGE 10 dB · ATTACK 10 ms · RELEASE 300 ms · HOLD 50 ms | About 10 dB GR while you sing; the hall blooms in the gaps |
| R9.1 | Timeless 3 | Base + Delay Offset **100%** (¼) · Delay Read Mode Stretch · Ping Pong on, start Right · FEEDBACK 35% · CROSS 100% · WIDTH 100% · Filter 1 High Pass 300 Hz, 12 dB/oct · Filter 2 Low Pass 7.0 kHz, 12 dB/oct · DIFFUSE 20% | Wide ¼ ping-pong |
| R9.2 | Pro-C 3 duck | THRESHOLD −30 dB · RATIO 6.0:1 · RANGE 12 dB · ATTACK 5 ms · RELEASE 250 ms · HOLD 40 ms | About 12 dB GR while you sing |

**Placement:** Δ −1.5 LU. **Optional carve:** Bell 2.5 kHz, Q 1.0, Range −3.0 dB + Bell 4.5 kHz, Q 1.4, Range −2.0 dB.

### F5. #9 Plugg Cloud

**Mixer:** 1 BEAT · 2 LEAD · 3 DBL L · 4 DBL R · 5 DBL BUS · 6 FX DELAY · 7 FX PLATE

| Slot | Plugin | Settings | Expect |
|---|---|---|---|
| L4 | Auto-Tune Artist | RETUNE SPEED 6 ms · HUMANIZE **35** · FLEX-TUNE 0 · FORMANT off (THROAT 100, inactive) · TRANSPOSE 0 · DETUNE 0 c | Smooth hard tune with soft, natural holds |
| L5 | Pro-C 3 | **Opto** · THRESHOLD −20 dB · RATIO 2.5:1 · KNEE 18 dB · RANGE 18 dB · ATTACK 15 ms · RELEASE 200 ms · HOLD 0 ms · GAIN +2.5 dB · DRY off · Character Off · Side Chain Internal · Lookahead Off · Oversampling 2x · In/Out 0 dB · Mix 100% | 3–4 dB GR on loud lines, gentle |
| L6 | Pro-Q 4 TONE | Low Shelf 180 Hz +1.5 dB, 12 dB/oct, Q 1.0 · Bell 3.8 kHz −1.5 dB Q 1.5 · High Shelf 12 kHz +2.5 dB, 12 dB/oct, Q 1.0 · Zero Latency, Clean | Warm, buttery body; breathy top |
| L7 | (none) | No saturation (J9) | — |
| L8 | Pro-DS #2 | As L3, except THRESHOLD −32 dB · RANGE 6 dB · HP 5.5 kHz / LP 12.0 kHz | De-essed shimmer: 3–6 dB GR on esses |
| Sends | LEAD | → FX DELAY −9.0 dB · → FX PLATE −12.0 dB · sidechain → FX DELAY | — |

**Doubles**

| | DBL L (3) | DBL R (4) |
|---|---|---|
| Pan / fader / Track delay | −60% / 0.0 dB / 14 ms | +60% / 0.0 dB / 21 ms |
| D1 Auto-Tune | RETUNE 8 ms · HUMANIZE 40 · FLEX 0 · THROAT 102 · DETUNE +6 c | RETUNE 10 ms · HUMANIZE 45 · FLEX 0 · THROAT 98 · DETUNE −5 c |
| D2 Pro-Q 4 | Low Cut 160 Hz, 18 dB/oct · High Shelf 9 kHz −1.0 dB | Low Cut 180 Hz, 18 dB/oct · Bell 2.2 kHz −1.0 dB Q 1.0 |

**DBL BUS (5):**
- B1 trim T − 1.0 dB · B2 / B3 shared
- B4 Pro-C 3 Opto: THRESHOLD −22 dB, RATIO 2.5:1, KNEE 18 dB, RANGE 18 dB, ATTACK 15 ms, RELEASE 220 ms, GAIN +2.5 dB
- B5 Fruity Chorus: DELAY 10.0 ms, DEPTH 2.5 ms, STEREO 120°, LFO 1/2/3 FREQ. 0.30 / 0.70 / 1.30 Hz, LFO WAVE sin ×3, CROSS TYPE Process HF, CROSS CUTOFF 250 Hz, WET ONLY no
- Fader: LEAD − 11 dB · send → FX PLATE −16.0 dB

**Returns**

| Slot | Plugin | Settings | Expect |
|---|---|---|---|
| R6.1 | Timeless 3 | Base + Delay Offset **100%** (¼) · Delay Read Mode **Tape** · Ping Pong off · FEEDBACK 45% · CROSS 0% · WIDTH 70% · Filter 1 High Pass 250 Hz, 12 dB/oct · Filter 2 Low Pass 3.2 kHz, 12 dB/oct · DIFFUSE 15% · Modulation: + → New XLFO (2-step sine, Free, 0.50 Hz) → drag onto DELAY → slot Level **+3%** to start (J44) | Long, dark repeats with a cassette-style pitch drift, never vibrato |
| R6.2 | Pro-C 3 duck | THRESHOLD −30 dB · RATIO 3.0:1 · RANGE 5 dB · ATTACK 10 ms · RELEASE 350 ms · HOLD 40 ms | About 5 dB GR while you sing; the echoes stay present |
| R7.1 | Pro-R 2 | Base + Style **Plate** · SPACE 2.0 s · PREDELAY sync 32th Note, Offset 100% · CHARACTER 35% · DISTANCE 30% · BRIGHTNESS 30% typed · WIDTH 100% · Post EQ: Low Cut 200 Hz, 24 dB/oct; High Cut 6.0 kHz, 12 dB/oct · not ducked | A soft, dark plate the delays melt into |

**Placement:** Δ −3.5 LU (melted in). **Optional carve:** Bell 2.5 kHz, Q 1.0, Range −1.5 dB + Bell 4.5 kHz, Q 1.4, Range −1.0 dB.

### F6. Traceability matrix (sub-step 3.1)

Every Appendix B requirement maps to the slots that carry it out; no row is empty.

| Req | #4 | #5 | #6 | #9 |
|---|---|---|---|---|
| R11 / §6.1 layout | LEAD 2; DBL 3–5 → 6; returns 7, 8 | LEAD 2; DBL 3–4 → 5; returns 6, 7, 8 | LEAD 2; DBL 3–6 → 7; returns 8, 9 | LEAD 2; DBL 3–4 → 5; returns 6, 7 |
| R12 / §6.1 ducking | R7.3, R8.3 | R8.2 | R8.2, R9.2 | R6.2 |
| R13–R14 / §6.2 cleanup | L1–L3 (+L2a) | same | same | same |
| R15 / §6.3 skeleton | L1–L8 | L1–L7 (L6 dirt before L7 EQ, J48) | L1–L8 | L1–L8 |
| R16 / §6.4 doubles | D1, D2, pan, Track delay ×3 | ×2 | ×4 | ×2 |
| R17 / §6.5 delays ducked | R7.3 | R8.2 | R9.2 | R6.2 |
| R10 / §6.6 timing | R7.1 + E8 | R8.1 + E8 | R9.1 + E8 | R6.1 + E8 |
| R07 / §6.7 carve | BEAT Pro-Q 4 | same | same | same |
| R18–R21 | L2, L3, L8; oversampling; L1; placement | same | same | same |
| R22–R24 | L4 + shared Auto-Tune values; FL 2024+; R8.1 Transpose | L4 | L4 | L4 |

| Style rows | Slots |
|---|---|
| AT00–AT10 | AT00 map · AT01 R7.1 / R7.3 / sends · AT02 Δ −1.5 + ducks · AT03 L6, L2 band 3, L8 · AT04 L4 · AT05 D1 DETUNE + B5 · AT06 R7.2 · AT07 R7.1 / R7.3 · AT08 R8.1 / R8.2 · AT09 DBL ALIEN D1 / D2 / −7 dB · AT10 ±85% + B5 |
| RB00–RB11 | RB00 map · RB01 L6 + R6 · RB02 L5 readings + L4 FLEX-TUNE · RB03 L6 · RB04 R6.1–R6.3 · RB05 L5 before L6 · RB06 Δ 0.0 · RB07 L7 · RB08 L4 · RB09 R7.1 · RB10 R8.1 / R8.2 · RB11 ±45% + D2 + B5 / B6 |
| MA00–MA09 | MA00 map · MA01 L7 + B5 · MA02 Δ −1.5 + ducks · MA03 L6 / L8 / L2 band 3 · MA04 L4 · MA05 R8.1 · MA06 R9.1 · MA07 R8.2 / R9.2 · MA08 pans · MA09 D1 / D2 / Track delay + bus −10 dB, Pair B −3 dB |
| PC00–PC08 | PC00 map · PC01 Δ −3.5 · PC02 L6 / L8, no saturation · PC03 L4 · PC04 L5 Opto · PC05 R6.1 · PC06 R7.1 · PC07 LEAD centred + ±60% + B5 · PC08 bus −11 dB |

### F7. Gray-area register: settled

| IDs | Settled as |
|---|---|
| GU01 | J1 / J21 / J22 / J32 / J43 table rules (applied in Step 4) |
| GU02, GU06 | −20 LUFS Integrated calibration; trim-only Pro-Q 4 (F1); thresholds and readings per slot |
| GU03, GU16 | Wording only (Step 4) |
| GU04, GU05 | Pro-L 2 Short Term + the F1 formula; beat peaks at −6.0 dBFS |
| GU07, GU08 | Track delay and per-double values in F2–F5 |
| GU09 | J46 feeds; send levels in F2–F5 |
| GU10 | L2a: Edison first, then Pro-G between L2 and L3 (and B2a) |
| GU11 | J51: a second Pro-DS in #4, #6, #9; none in #5 |
| GU12 | Alto/Tenor (J39) |
| GU13 | 2x on Pro-C 3 / Pro-DS / Pro-G; Saturn 2 Good; Pro-L 2 off (meter) |
| GU14 | E8 |
| GU15 | Carve values per style (F2–F5) |
| GU17, GU18 | Settled in Step 1 |
| GA01–GA10 | F2 (shimmer ducked lightly, J47; chorus on the bus, J54; band-pass with Pro-Q 4, J55; Throat 111, J56; pans ±85%) |
| GR01–GR12 | F3 (British Rock in-line, Crunchy Amp on the bus and doubles, J53; room not ducked, J47; delay ¼; pans ±45%) |
| GM01–GM10 | F4 (Warm Tape on lead and wall; hall 3.4 s Modern; ducks 10 / 12 dB; Pair B ±50%; Pair B −3 dB) |
| GP01–GP08 | F5 (Opto; Plate 2.0 s, not ducked; XLFO wobble, J44; pans ±60%; bus −11 dB) |
| GX01 | Δ: #5 0.0 > #4 / #6 −1.5 > #9 −3.5 LU |
| GX02 | RETUNE / HUMANIZE: #5 2 ms / 0 (+FLEX 15) · #6 8 ms / 18 · #4 10 ms / 15 · #9 6 ms / 35 |
| GX03 | L1–L3 identical in all four |

### F8. Distinctness check (sub-step 3.8)

| | #4 Alien | #5 Rage | #6 Anthem | #9 Plugg |
|---|---|---|---|---|
| Placement Δ | −1.5 LU | **0.0 LU** | −1.5 LU | **−3.5 LU** |
| Compressor | Clean 3:1 | Punch 6:1, 1 ms | Versatile 3.5:1 | Opto 2.5:1 |
| Tone move | +2.8 kHz, +10 kHz shelf | +1.3 kHz, −9 kHz shelf, cut at 16 kHz | +3 kHz, +11 kHz shelf | warm low shelf, −3.8 kHz, +12 kHz shelf |
| Grit | none | British Rock + Crunchy Amp | Warm Tape (light) | none |
| Space | dotted-⅛ ping-pong + octave shimmer | 0.6 s dark room + heavily ducked ¼ | 3.4 s hall + ¼ ping-pong, both ducked | ¼ tape-wobble delay + 2.0 s plate |
| Doubles | 2 wide (±85%) + alien layer, chorused | 2 tight (±45%), dirty and band-limited | 4-double wall (±100 / ±50) | 2 (±60%), chorused, tucked |
| Shared parts | L1–L3, Auto-Tune base, return bases, carve method | same | same | same |

Every §7 difference shows up as a different value; every §6 convention is identical across the four.

---

## Appendix G: QA results (Step 5)

Run on 2026-10-12 against the four files in `chains/`. The automated checks are `check_chain.py` (per file, extended during this step so every fix stays fixed) and `check_plan.py` (this plan). The manual audits were done by reading every file in full. The cold read used independent reviewers who had only the one file and the persona from 5.9.

### G1. Gate results

| Gate | Result | Found and fixed | Calls |
|---|---|---|---|
| 5.1 Spec compliance | ✅ Pass | Every B1–B3 row holds in all four files (Appendix B is ticked). Gap fixed: the doubles' D1 and D2 slots had no Dial it in | J65 |
| 5.2 Toolkit | ✅ Pass | Allow and block lists are clean. Every control name in a settings table appears on the Step 2 reference sheets, and every value is in range. Fixed: Edison's Amount unit (dB, not %); explicit on/off states for Timeless 3's effects | J62, J63 |
| 5.3 Routing | ✅ Pass | The map, walkthrough, sends, and sidechain references agree. There are no loops, and every sidechain source exists. Fixed (blocker): "Sidechain to this track" on LEAD sends that already fed the returns | J59 |
| 5.4 Gain staging | ✅ Pass | Lead slots match the −20 LUFS calibration. Fixed: the DBL BUS level is now measured; B4's expected readings follow from its threshold; Rage R8.2's reading wording | J61 |
| 5.5 Doubles | ✅ Pass | Every double has its own pan, Track delay, Detune, Throat, and EQ. Counts are 3 / 2 / 4 / 2, and all play the whole song | — |
| 5.6 Math | ✅ Pass | All 63 delay-table cells match `delay_table.py`, whose self-checks pass. Every worked example (T, placement, DBL BUS fader) adds up; these are now checked automatically | — |
| 5.7 Format | ✅ Pass | Every plugin slot has a table with a Why on every row, plus a Dial it in. Each file has 12 troubleshooting rows and a routing walkthrough, and every table renders | J65 |
| 5.8 Cross-file | ✅ Pass | Shared blocks have identical settings. Files differ only in insert counts, worked examples, style-specific Why text, and the values §7 sets per style | — |
| 5.9 Cold read | ✅ Pass (after round 3 and the focused re-checks) | Cold reads: round 1 found 3 blockers and 14 majors, round 2 found 4 majors, and the final full round found 3 majors (06 and 09 passed clean). All were fixed, and focused re-checks of the room-tone, Edison, and solo flow then passed on every path. | J59–J70 |
| 5.10 Fix and re-run | ✅ Done | Ten fix batches, each followed by a full re-run of the automated gates. `check_chain.py` now also guards every fix | — |

### G2. Cold-read findings (round 1) and what happened to them

| Finding | Raised by | Outcome |
|---|---|---|
| "Sidechain to this track" on an existing send could leave the effects silent (blocker) | 04, 05 (06, 09 on first pass) | Fixed (J59). This matched the 5.3 finding |
| Edison cleaned only the selected gap (blocker when L2a is needed) | 04, 05, 06, 09 | Fixed: deselect first, open with "Edit sample", check the take came back, with the documented Send sample to Playlist remedy (J63) |
| The project tempo was never set (blocker for every synced time) | 04, 05, 09 | Fixed (J66) |
| A plain solo can silence a bus's inputs; a return heard with the dry lead | 05, 09 | Fixed: Alt-solo (J60). Rage FX CRUNCH is checked with LEAD's Master route off |
| Placement read a moving value; the loudest bars may have no vocal; the fader may not reach | 04, 05, 06, 09 | Fixed (J64, J68) |
| "Toggle bypass, within 1 dB" named no meter | 04, 05, 06, 09 | Fixed (J67) |
| Beat headroom read from the meter's hover hint; unit of "Type in value" | 05 (others as doubts) | Fixed (J70) |
| The room-tone decision came too late, or was made twice | 04, 05, 06, 09 | Fixed: 1.3 runs the Test; L2a keeps that answer; doubles made too early get rebuilt |
| Ducker mapping step easy to miss; no recovery; no re-check after the LEAD fader | 04, 05, 09 | Fixed: pointers in every ducker row and check, a recovery line, and 6.1 step 6 with a target and an action |
| The DBL BUS check came after B2–B5, and the correction had no sign | 09 | Fixed: check right after B1, and add (−20.0 − reading) |
| Ping-pong start side names no control | 04, 06 | Handled (J69): the setting is undocumented, so the file says how to confirm it and gives a fallback |
| Wording and clarity | various | Fixed: fader notes; section 7's link in the map; "Written for" line; Mac shortcuts; L2 steps (double-click, "A" meaning, expand >>, cut-band Q); Pro-DS "In (not Ext)"; meter resets; Pro-R 2 curve colours, typing, and sync wording; Timeless sync and filter-style wording; "typed travel" in troubleshooting; troubleshooting convention; chorus pattern wording; off-grid copies; standalone wording in #5; the 6.1 example's BEAT value; "For any other tempo" |
| FL's fader maximum (+5.6 dB?) isn't stated | 06, 09 | Not changed: Image-Line's manual doesn't give it, and the J68 rule works without the number |
| Pro-Q 4 uses "click" for bells but "double-click" for cuts | 04, 09 | Not changed: both are correct per FabFilter |
| Whether DELAY's readouts show ms while synced; Chorus STEREO units; the PDC menu path | 04, 06 (doubts) | Not changed: the official Timeless screenshot shows ms readouts; Fruity Chorus STEREO is documented in degrees; the PDC path was verified in Step 2 (E5) |

### G2b. Cold-read round 2 (on the fixed files) and what happened

| Finding | Raised by | Outcome |
|---|---|---|
| The DBL BUS level check came after B2–B6 were loaded, and a solo left on from the doubles check would make it read about 3 dB low | 05 | Fixed: the B1 row says to check right after loading B1; the check runs with nothing soloed; every Alt-solo check now ends with an unsolo (guarded in `check_chain.py`) |
| A reader who already did Edison in 1.3 was sent back into Part 1, which would re-denoise the take and delete the doubles | 04, 05 | Fixed: Part 1 is skipped if done in 1.3, the Test says so, and 3.1 skips only if the copies still exist |
| In Pro-Q 4, a single click only deselects while a band is selected, so "click the display" wouldn't add the bells | 04, 06 | Fixed (FabFilter help): L2 double-clicks the background, and 1.1 explains how to add bands |
| Pro-Q 4's auto threshold is the slider's top value, not a button | 06 | Fixed (FabFilter help): the dynamics panel stays closed, which is auto mode and matches the table |
| The doubles might not carry the Edison cleanup, because FL's "Make unique" re-uses the original audio file | 06 | Fixed: 3.1 checks a gap on one double and reruns Part 1 on the doubles if the hiss is back (J63) |
| Template leftovers: "a ducker" in single-ducker files, a "synced pre-delay" in Rage (whose room pre-delay is a fixed 8 ms), and "the same 8 bars" with no bars named | 09, 05, 06 | Fixed |

### G2c. Cold-read round 3 (final) and the focused re-check

| Finding | Raised by | Outcome |
|---|---|---|
| After the room-tone test, LEAD stayed soloed, so the 3.1 check of a double's gap would run with the doubles muted | 04 | Fixed: the test ends with an unsolo, and the double check spells out Alt+left-click and its unsolo (guarded in `check_chain.py`) |
| Edison's own hiss check then ran unsoloed, with the beat masking the hiss; and 3.1's "run Part 1 on each double" clashed with Part 1's "skip if done in 1.3" | 05 | Fixed: every hiss check solos the cleaned track, every unsolo is Ctrl+right-click, and Part 1 says how to run it on a double's clip and channel |
| 1.3's "so every copy is clean" overpromised (Make unique may reload the original file) | 09 (aside) | Fixed: it now points to the 3.1 check |
| Files 06 and 09 | 06, 09 | PASS: no blockers, majors, or regressions |

**Focused re-checks of the room-tone, Edison, doubles and solo flow** (05, walked along three paths: noisy booth found in 1.3, quiet booth, noise found late):

| Finding | Outcome |
|---|---|
| The Send sample to Playlist fallback was re-checked after the unsolo, so the beat masked the hiss | Fixed: the re-check happens before the unsolo |
| When the noise is found late (after routing), Alt-soloing LEAD also played its still-empty returns, raising the hiss | Fixed: a plain solo for LEAD, Alt-solo only for a double (which needs DBL BUS) |
| The Test's "keep your 1.3 answer" came after the instruction to re-test, and read wrongly on the first run | Fixed: the Test opens with the 1.3 rule |
| 3.1's "copies from 1.3" let a reader make the doubles twice | Fixed: skip whenever the copies already exist |
| The D1/D2 check compared DETUNE against a muted lead | Fixed: DETUNE is checked on the readout |

The second focused re-check passed the noisy-booth path (found in 1.3) and the quiet-booth path. On the late-discovery path, "delete the doubles and remake them" left orphan Audio Clip channels and didn't help, because Make unique re-uses the noisy file. Fixed: keep the doubles and run Part 1 on the lead, then on each double. A third check of that path then passed: every clip and channel is cleaned, there are no orphans or duplicates, and nothing is left soloed.

### G3. Facts verified during Step 5

- **Image-Line (FL Studio manual):**
  - Alt+left-click solos a track with everything routed to and from it; Ctrl+right-click unmutes all.
  - "Sidechain to this track" is a macro that makes a send at level 0, and any send above 0 carries both audio and a sidechain path.
  - "Type in value" offers context-aware and normalized units.
  - Hovering a mixer meter shows the scale value.
  - Edison: Select > Deselect is the Up arrow; with no selection, Clean up processes the whole sample; Amount is in dB; Threshold is Windows-only, with Smoothing on macOS; right-clicking Send sample to Playlist replaces the selected Audio Clip.
- **FabFilter:**
  - Timeless 3's effect knobs have centre power icons and Auto Mute Self-Osc sits in the bottom bar (official screenshot). The ping-pong start side can be left or right, but how to choose it is undocumented.
  - Pro-C 3: Show Input Level is in the Help menu, and its meters show Momentary loudness indicators.
  - Pro-L 2 shows Max S with the Integrated time scale, and the max true peak with TP on.
  - Pro-R 2: the Decay Rate EQ is the blue curve and the Post EQ the yellow one; double-click a dot to type values; double-click at the edges for cuts, drag at the edges for shelves.
  - Pro-Q 4: double-clicking the background creates a band, while a single click only deselects when a band is selected; the dynamics panel opens with "expand >>", and closing it reverts the band to auto mode (threshold at its top value "A", attack and release at 50%).
  - FL: "Make unique" re-uses the original audio file in the new Audio Clip channel.
- **Not documented, so the files work around them:** FL's fader maximum (J68); whether Edison's "Edit sample" updates the clip automatically (J63 adds a check and a remedy); the ping-pong start-side control (J69); Timeless 3's WET unit (the fallback applies only to a dB readout).

---

## Judgement log

Every delivery call made during creation, J23–J70. J1–J22 are the pre-resolved calls in Step 1. The log closed at delivery; the note after the table lists the later calls that refine earlier ones.

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
| J31 | All | The plan keeps the reference sheets in the scratchpad, which is lost if the session goes idle | The full sheets stay in the scratchpad; Appendix E holds a condensed digest of every verified fact later steps need, so the build can continue from PLAN.md alone | Process record only; no spec content changes |
| J32 | All | Vendors publish almost no defaults, so J1's "write the actual default value" can't be met | Every table row states the exact value to set, including neutral ones (e.g., DRIVE 0%, Character Off). No row relies on "default" | Strengthens §4 "exact value for every parameter" |
| J33 | All | Some ranges and a few option labels are unpublished | Values only within (1) published ranges, (2) ranges shown in official screenshots, or (3) where neither exists, the conventional working range for that control type. Every value is entered by typing (FabFilter double-click, FL "Type in value") or set while reading FL's hint bar, and "Dial it in" confirms it on the plugin's readout. Option labels come from official text or screenshots; where only corroborated secondary names exist (some Saturn 2 styles), the file also names the menu section | Keeps every value exact and checkable (§4) |
| J34 | All | §6.4 needs a time offset per double. Fruity Delay 3 can't guarantee a clean copy, Stereo Shaper delays one channel only, and clips have no ms field | Offsets use each double's mixer Track delay ("Set in ms"), an FL built-in that PDC doesn't cancel. Its sign convention is unpublished; that doesn't matter for doubling, because only the gap from the lead counts. C1 built-ins now include Track delay | Carries out §6.4 with the cleanest owned tool |
| J35 | All | FL's mixer meters show no numbers, but J2 and J6 need measurable targets | Pro-L 2, in FabFilter's documented transparent setup, is used only as a meter and then removed: Integrated loudness of the raw take for calibration, Short Term loudness of lead vs beat for placement. Gain-reduction readings come from each dynamics plugin's own meter; beat headroom from FL's peak meter hint | Measurement only; nothing is processed (§3 Out, J26) |
| J36 | All | The trim must come before the dynamic harshness band so that band's threshold is exact. FL clip gain needs FL 2025.1+, and EQ 2's main level range is unpublished | Slot 1 is a trim-only Pro-Q 4 (no bands; Output Gain −∞ to +36 dB) | §6.2 order + J2 |
| J37 | All | Timeless 3's sync menu entry labels are unpublished | Use the quarter-note sync entry and the documented Delay Offset: ¼ = 100%, dotted ⅛ = 75%, ⅛ = 50%. Confirm against the ms table using the time readouts under DELAY | Keeps §6.6's tempo-synced note values |
| J38 | All | Image-Line's manual now documents FL Studio 2026, while §9 says FL 2024+ | FL 2026 wording is used, but only features present since FL 2024 (no Clip Properties, Deverb, or other 2025+ features) | §9 assumption |
| J39 | All | Auto-Tune Artist's maximums and Throat range are unpublished, and Input Type isn't mapped to voice ranges | From the official screenshots: Humanize and Flex-Tune on a 0–100 scale; Throat 100 = neutral. Input Type = Alto/Tenor for your mid-range voice. CLASSIC stays off wherever Formant, Throat, Transpose, or Flex-Tune is needed, because Classic disables them | §2 voice row, §6.4, §7 |
| J40 | 04, 09 | Fruity Chorus and Fruity Phaser (named by the spec) have mostly unpublished ranges, and typed units aren't confirmed for them | Values are anchored to the documented ranges and the manual's own screenshot readouts, set by dragging while reading FL's hint bar. Labels are as printed on the current panel (e.g., NR. STAGES, CROSS TYPE "Process HF") | §5 names these plugins; §4 exact values |
| J41 | All | Pro-Q 4's spectral dynamics add about 100 ms of linear-phase latency, and its processing-mode default is unpublished | Harshness bands use standard (non-spectral) dynamics, and every Pro-Q 4 is set to Zero Latency explicitly | Delivers §6.2's dynamic band without extra latency |
| J42 | All | Several plugins have built-in ducking or saturation the spec doesn't call for (Pro-R 2 DUCKING and THICKNESS; Timeless 3 DRIVE, FEEDBACK above 100%, non-Clean filter styles; Saturn 2's inherent input color) | Built-in ducking is set to zero everywhere (Pro-C 3 does the ducking, J19). Where no saturation is allowed (#4, #9): Timeless 3 DRIVE 0%, FEEDBACK ≤ 100%, filters in Clean style; Pro-R 2 THICKNESS at minimum; Saturn 2 not used | §6.1, J9, J19 |
| J43 | All | Several FabFilter knobs have unpublished units (Pro-R 2 BRIGHTNESS, THICKNESS, DUCKING; Timeless 3 WET, DYNAMICS; Saturn 2 TONE, DYNAMICS) | They're set by typed percentage of knob travel ("50%" = the exact middle), FabFilter's documented text-entry shortcut. For knobs whose own unit is %, only values where position and value agree are typed; Pro-R 2 Decay Rate 100% is confirmed by SPACE showing a single time, and STEREO LINK 100% by its scale mark | Keeps every value exact (§4) without guessing units |
| J44 | 09 | Timeless 3's modulation-slot Level has no published units or typed entry | Start at +3% (Shift-drag for fine moves), with an audible target: a hair of cassette-style pitch drift, never vibrato | Delivers §7 #9's "slight tape-style wobble" inside Timeless 3 |
| J45 | All | §6.4 gives each double its own detune, offset, throat, EQ, and pan, but doesn't say where the rest of the doubles' processing lives | Each double's insert carries only what must differ (Auto-Tune, its own EQ, pan, Track delay). Cleanup, compression, and style processing live once on the Doubles bus, whose trim gets a per-style offset for the summed doubles | §6.1 Doubles bus; §6.4 recipe |
| J46 | All | J10: which tracks feed the returns | #4 and #5: LEAD only, so the FX surround a dry, forward lead. #6's hall and #9's plate are also fed by DBL BUS: the wall lives in the arena, and the doubles melt into the plate | Follows each style's §7 space and placement rows |
| J47 | 04, 05, 09 | J19: whether the non-delay reverbs duck | #4's shimmer ducks lightly (4 dB) so the words stay clear. #5's room and #9's plate don't duck: the room is part of the grit, and the plate is the cloud | §7 #4 "words always clear"; §7 #5 and #9 space rows |
| J48 | 05 | §6.3 puts tone shaping before style processing, but Rage's "top end controlled" must also tame the fizz the crunch creates | The Saturn 2 crunch (L6) comes before the tone EQ (L7) | J11 allows spec-required order changes |
| J49 | All | FL inserts are pre-fader, so a meter on an insert can't read the post-fader balance | Placement is computed: LEAD fader = (Beat ST + BEAT fader + Δ) − Lead ST | Delivers J6 exactly |
| J50 | All | J2 and J7 needed concrete targets | Calibration −20.0 LUFS Integrated (a light trim for takes peaking at −12 to −6 dBFS); DBL BUS trim offsets per style; the beat peaks at −6.0 dBFS | §2 "light trim"; J2; J7 |
| J51 | 04, 06, 09 | J11: whether a second Pro-DS follows the tone EQ | Yes where the tone EQ boosts the top (#4, #6, #9); no in #5, whose top is cut | §2 de-esser; §7 tone rows |
| J52 | All | Pro-C 3's lookahead option values between Off and 20 ms are unpublished | Lookahead stays Off; fast attack settings handle transients | J33 |
| J53 | 05, 06 | Most Saturn 2 style names are unofficial | Rage in-line: British Rock (named in FabFilter's release notes). Rage crunch bus and doubles: Crunchy Amp (a corroborated name that matches the manual's "crunchy" amps). Anthem warmth: Warm Tape (official screenshot). Each file also names the menu section | J33 option-label clause |
| J54 | 04, 09 | Where the chorus sits (C3) | On the Doubles bus. FL's pan collapses a per-double chorus's stereo spread on panned doubles, while a bus chorus keeps L and R moving differently | Delivers the §7 width / chorus rows |
| J55 | 04 | The Alien layer's band-pass tool (C3) | Pro-Q 4 cuts (500 Hz–5 kHz) in the double's own EQ slot; Volcano 3 isn't needed | J8; fewer plugins, all clean |
| J56 | All | Auto-Tune Artist's Throat range is unpublished | Values stay between 94 and 111 (Antares' screenshots show 100 and 111): small variations around 100 for the doubles, 111 for the alien layer's bigger shift | J33; §6.4; §7 #4 |
| J57 | All | J43's typed-percentage entry is ambiguous on knobs whose own unit is %: typing "38%" could mean the value 38% or 38% of the knob's travel | Knobs with a % unit get a bare number, which sets the value in the knob's own unit (FEEDBACK 38, Delay Offset 75, CHARACTER 40). "NN%" typed travel is kept only for knobs with unpublished units (Pro-R 2 BRIGHTNESS, THICKNESS, DUCKING; Pro-C 3 DRY; Saturn 2 DRIVE, MIX, FEEDBACK). Bipolar knobs with unpublished units (Timeless 3 and Saturn 2 DYNAMICS, Saturn 2 TONE) are reset with Ctrl-click and checked at 12 o'clock, and Timeless 3 WET is reset with Ctrl-click and read back as 0.0 dB. This refines J43 and Appendix F's "50% typed" base rows | Same values as Appendix F, entered in a way that can't land on the wrong one (§4) |
| J58 | All | The final listen needs a check that the doubles and returns do their job, but hearing the whole mix in mono needs a control or plugin on the Master | Section 6.3 uses mute checks instead: mute DBL BUS, then the returns, and listen for the described change. No file touches the Master | N05; §3 Out (no master chain) |
| J59 | All | The walkthrough added "Sidechain to this track" on top of LEAD sends that already feed the returns. FL's manual calls that option "a macro to create a send link with the send volume set to 0", and states that any send above 0% carries "BOTH an audio and sidechain send" | The extra step is gone. Each ducked return keys from the LEAD send that already feeds it, and the files warn against the macro there. The beat carve keeps it, because LEAD has no other link to BEAT | §6.1 ducking (Pro-C 3 on the return, keyed from the Lead) is delivered as before, without risking a silent send |
| J60 | All | Checks said "Solo" a bus, a return, or a double. FL documents only Alt+left-click as soloing "track AND all tracks routed TO and FROM it", so a plain solo may cut off what feeds the track | Those checks use **Alt-solo**, defined once in 1.4, together with the undo (Ctrl+right-click = unmute all). The L2a test keeps a plain right-click solo on LEAD, which has no inputs. Every solo is undone the same way, and every hiss check solos the track it checks | How to verify (§4 FL clicks spelled out) |
| J61 | All | Gain staging (5.4): the DBL BUS trim offsets were estimates, and B4's expected readings (3–5 dB) did not follow from its threshold, which is 2 dB below L5's. Rage's delay-ducker reading assumed rapping, while §7 says melodic + yelled | Dial it in (DBL BUS) now starts by measuring B1's output with the Pro-L 2 meter: −20.0 LUFS Integrated, the same as LEAD after L1. B1's offset becomes the starting point. B4's expected readings now follow from the threshold: 5–7 dB (#4, #6), 4–5 dB (#9), same as L5 (#5). Rage R8.2 reads about 13–18 dB "while you sing or yell" | Same settings and sound; the checks now match the level that actually arrives (J2, J18) |
| J62 | All | Timeless 3's five effects (DRIVE, LO-FI, DIFFUSE, DYNAMICS, PITCH) switch on and off by clicking the knob's centre, and their default state is unpublished | Every effect gets an explicit state: DIFFUSE **On** where it has an amount (#4, #6, #9), Off in #5 (amount 0); DRIVE, LO-FI, DYNAMICS, and PITCH Off. The file explains the click | J1 (every audio-affecting control gets a value); J42 (no Timeless drive in #4, #9) |
| J63 | All | Edison: Image-Line gives Amount's unit as decibels (Appendix F said "60%"); a noise selection left active means only that selection is processed; Threshold exists on Windows only (macOS has Smoothing) | Amount 10 dB, following Image-Line's "only as much suppression as needed… less in a mix", with Pro-G handling the gaps. Step 2 deselects (Up arrow) so the whole take is processed. Threshold 0 dB is marked Windows; Smoothing (macOS) stays as it opens. The clip opens with the clip menu's "Edit sample". The return to the playlist is checked, with the documented Send sample to Playlist remedy. FL's "Make unique" re-uses the original audio file, so 3.1 checks that the doubles carry the cleanup and reruns Part 1 on them if not. If the noise is found only after the doubles exist, Part 1 runs on the lead and then on each existing double (no delete-and-remake, which would leave orphan channels) | §6.2 "Edison denoise only if room tone is audible", delivered with the documented unit and workflow |
| J64 | All | Placement read a live Short Term number, which keeps moving | Pro-L 2 shows Max S (the highest Short Term reading) when the time scale is Integrated: reset, play the loudest 8 bars once, read Max S on BEAT and LEAD | Same quantity as J49/F1 (Short Term), read as a stable value (J6) |
| J65 | All | D1 and D2 had settings tables but no "Dial it in" (R08) | One combined Dial it in after 3.4: Alt-solo each double, compare, and check each DETUNE readout | §4 layout rule (table, then Dial it in) for every plugin slot |
| J66 | All | Every tempo-synced value (delays, pre-delays, section 5's check) assumed FL's project tempo matched the beat, but no step set it | 1.3 step 2 now sets FL's project tempo to the beat's BPM, and the readout checks say "for your project tempo" | Delivers §6.6 tempo-synced values correctly |
| J67 | All | Two kinds of level checks ("toggle bypass, within about 1 dB") named no meter | Pro-C 3 checks use its own input/output loudness marks (Help menu → Show Input Level). Saturn 2 checks use the Pro-L 2 meter: an Integrated A/B over the same 8 bars | J18: every dynamics or drive slot is confirmed on a readout |
| J68 | All | The placement formula can ask for more than the LEAD fader can reach, and the loudest 8 bars may have no vocal | Read bars where you sing all the way through (a hook, for example). If LEAD can't reach the result, lower BEAT another 3.0 dB and redo the formula | Same targets (J6, J49); just measurable in every case |
| J69 | 04, 06 | Timeless 3 documents a left or right start for ping-pong but not how to choose it | Each file states the start side, says to confirm it from the icon's hover hint, and says to just switch ping-pong on if no start choice is offered | J33: unpublished UI is confirmed on the plugin's own readout |
| J70 | All | FL's own readouts: Image-Line's manual says hovering a mixer meter shows the scale value, not the signal; "Type in value" offers context-aware or normalized units, and the default isn't documented | Beat headroom is read from Pro-L 2's max true peak (BEAT fader = −6.0 dB minus the reading). Every typed FL value uses the context-aware unit (dB for faders and sends, % for pan), stated in 1.1 | J7 (beat headroom) and §4 (exact values), with readouts that actually exist |

**Later calls that refine earlier ones.** The log only grows, so where a later call changed how an earlier one is delivered, the later call governs:

| Earlier call | Refined by | What the files do now |
|---|---|---|
| J35 → | J64, J70 | Placement reads Pro-L 2's Max S, a stable value, instead of a live Short Term number. Beat headroom comes from Pro-L 2's max true peak instead of FL's meter hint |
| J43 → | J57 | Knobs whose own unit is % take a bare number. Typed travel ("NN%") is only for knobs with unpublished units |
| J45, J50 → | J61, J70 | The per-style DBL BUS trim offset is only the starting point: Dial it in measures B1's output to −20.0 LUFS Integrated. The beat's −6.0 dB peak target is read as Pro-L 2's max true peak |
| J49 → | J64, J68 | The placement formula uses Max S over bars where you sing all the way through. If LEAD can't reach the result, BEAT drops another 3.0 dB and the formula is redone |

**Closed at delivery (2026-10-12).** 70 calls in total: J1–J22 pre-resolved in Step 1, J23–J70 made during creation. Step 6 made no new calls.
