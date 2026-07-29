# T-TESS / SLO Growth Tracker — developer handoff

**Product:** Crystal Instruction (ClearK12) · new teacher-facing module
**Status:** design prototype, functionally complete for the 2026–27 flow. Not production code.
**Live prototype:** https://kennadyscott.github.io/crystal-ttess-slo/
**Owner:** Kennady Scott · kennady@cleark12.com
**Last updated:** 2026-07-29

---

## 1. What this is

A single self-contained HTML file that implements the entire teacher journey for building a
Student Learning Objective, collecting a Body of Evidence against the T-TESS rubric, and
producing an end-of-year analysis. Every screen is real and interactive — nothing is a
picture of a screen. Click through it before reading the rest of this document.

**It is a specification, not a starting codebase.** All state lives in one `localStorage`
key and all data is mocked. Treat the HTML as the source of truth for *behaviour, copy and
layout*, and rebuild it in the platform's own stack.

### The one non-negotiable

Teachers earn TIA designations through their district's system, not through our software.
**No screen may promise, imply or predict a designation.** The prototype's copy has been
written carefully around this and the disclaimer on the Skill Statement step is deliberate:

> Crystal Instruction assessments are for progress-monitoring only. They support your Body of
> Evidence but do not replace your district-approved assessments for TIA, and using this tool
> does not guarantee a TIA designation.

Keep that guarantee-free framing in any copy you add. Related: §9 explains why five rubric
dimensions deliberately show *no* "how Crystal Instruction helps" content. Do not fill those in.

---

## 2. Files in this package

| File | What it is | Who needs it |
|---|---|---|
| `slo-generator.html` | The prototype. Open in any browser, no build step. | Everyone |
| `HANDOFF.md` | This document. | Everyone |
| `crystal-ttess-alignment.md` | Verified crawl of the live platform mapped to all 16 T-TESS dimensions: what artifacts exist, per-dimension coverage, ranked gaps. | Whoever builds the Rubric tab |
| `ttess-descriptor-level-domains-2-3.md` | Indicator-by-indicator analysis of Domains 2 & 3 (the TIA 35%). | Rubric tab; content team |
| `ttess-descriptor-level-domains-1-4.md` | Same for Domains 1 & 4, plus the cross-domain gap table. | Rubric tab; product |
| `ttess-rubric-verbatim.txt` | TEA *T-TESS Rubric Working Copy* rev 2/10/2022, all 16 dimensions, 274 indicator bullets. Source of the indicator text in the app. | Content/data seeding |
| `TTESS2-EVALUATION.md` + `ttess2-pilot-rubric-verbatim.txt` | The 2026–27 pilot rubric (11 dimensions) and our analysis of it. | Roadmap; see §12 |
| `TTESS-EVALUATION-HANDOFF.md` | Long-form alignment reference the rubric verdicts were derived from. | Reference |
| `fonts.html` | Type comparison: the same UI in 8 faces. Records why Outfit was chosen. | Design |

---

## 3. The year, in three phases

The whole module is organised around a teacher's actual calendar. The top tab row runs in
phase order; each panel names its phase in an eyebrow.

```
PHASE 1 — Set up  (Aug–Sep)
  BOY Setup wizard, 5 steps:
    1 Skill Statement → 2 Skill Profile → 3 Personal Plan → 4 BOY Data → 5 Growth Targets
  Ends with "Accept & Lock SLO" — the commitment point.

PHASE 2 — Monitor progress  (Oct–Mar)
  Overview · Evidence Lockers · T-TESS Rubric · Progress · MOY
  MOY data entry unlocks 1 December.

PHASE 3 — Body of evidence  (Apr–Jun)
  EOY post-assessment → generated analysis report.
  EOY data entry unlocks 1 April.
```

Once the SLO is locked, returning teachers land on **Evidence Lockers**, because during Phase 2
that is where the daily work happens.

---

## 4. Screen-by-screen

### Step 1 · Skill Statement
Grade selector **before** subject (deliberate — see §5.1). Three research-based strands per
subject for Math, ELAR and Science, each running Grades 2–5, plus "write my own".

### Step 2 · Skill Profile
Five editable performance-level descriptors and the scoring scale. The scale is set in a modal
and is **the only scale in the SLO** (§5.2).

### Step 3 · Personal Plan
Differentiation for the highest and lowest groups, monitoring cadence, support staff, and the
anticipatory Body of Evidence (which Crystal Instruction sources the teacher expects to draw on),
plus a free-text field for anything not listed.

### Step 4 · BOY Data
Teacher names the data source, then types each student's score into a table that colour-codes live
against the scale. Paste-from-spreadsheet import matches on student name. Administering a
Crystal Instruction pre-assessment in-app is **deferred to v2** (§10).

### Step 5 · Growth Targets
Per-student slider from pre-test to end-of-year target. Slider minimum is the student's own
pre-test — a target can never be below the starting point. Appraiser-approval checkbox plus a
complete Personal Plan gate the lock (§5.3).

### Overview
Post-lock SLO at a glance: locked goal, class growth summary, target distribution, differentiation
plan, evidence sources and counts.

### Evidence Lockers
Scrolling student list on the left, class/group filters on top, locker on the right. Per student:
growth summary, "X of 5 minimum data points", T-TESS-aligned count, a flat evidence list (each item
taggable as T-TESS-aligned, with a one-line note), artifact upload, and a "connect what you've
taught" library built from the SLO's standards.

### T-TESS Rubric
Left nav of all dimensions with rating dots; a coverage map across the top. **One rubric level at a
time**, full width, opening on Proficient — the level stepper is the switcher. Each indicator row
carries a verdict chip (*CI proves this* / *CI helps* / *On you* / *Careful*) and expands in place
to show the proof and attach evidence to that single indicator. Running TIA average against 3.75.

### Progress
Per-student BOY → Current → Target with status, a per-standard mastery matrix pulled from Crystal
Instruction work, and suggested learning plans by band. Before any mid-year data exists it shows a
neutral baseline state (§5.5).

### MOY / EOY
Score capture against the same scale, gated on the benchmark windows. EOY generates the analysis
report and advances the phase.

---

## 5. Business rules that are easy to get wrong

These are the parts where a reasonable-looking implementation is subtly wrong. Each one is here
because it was got wrong at least once during design.

### 5.1 Vertical alignment
Strands are keyed and run across Grades 2–5. Changing grade **keeps the same strand** and swaps in
that grade's statement and TEKS codes — e.g. Place Value in G3 becomes Place Value in G5, not a
different goal. This is what lets a campus run one initiative across grade levels. Grade therefore
comes before subject in the UI, because grade changes the content of the choice.

### 5.2 One scoring scale
There is exactly one band scale per SLO — five bands with editable low/high cut points, on whatever
scale the teacher's data uses (percent, NWEA RIT, raw points). It drives the performance-level
descriptors, the BOY colour coding, MOY, EOY and the growth-target slider maximum.

> The prototype originally had a second, independently editable copy of this editor on the BOY Data
> step. The two could silently disagree. **Do not reintroduce a second editor.** BOY Data shows the
> scale read-only with an "Edit scale" affordance that opens the one canonical editor.

### 5.3 Completion and the lock gate
A step's checkmark means **its required fields have content** — not that the teacher walked past it.

| Step | Complete when |
|---|---|
| Skill Statement | a statement exists |
| Skill Profile | all five descriptors non-empty |
| Personal Plan | highest-group plan **and** lowest-group plan non-empty, **and** ≥1 evidence source |
| BOY Data | scores saved |
| Growth Targets | SLO locked |

"Who else supports this goal" is genuinely optional and is labelled as such.

**Accept & Lock requires:** BOY data saved **and** Personal Plan complete **and** appraiser-approval
checked. If the plan is incomplete the button stays disabled, names exactly what is missing, and
offers a jump to fix it. Locking then opens a confirmation summarising what is being fixed for the
year. Lock is reversible by design (teacher + appraiser may need to amend) but must be deliberate.

### 5.4 Rubric level logic
- A level is **cleared** when the teacher has checked **≥ ⌈n/2⌉** of that level's indicators.
- The **suggested rating** is the highest level cleared with no gap below it — walk 1→5 and stop at
  the first uncleared level. Null means Improvement Needed isn't cleared yet.
- The **TIA average** includes **Domains 2 and 3 only**. Ratings on 1.x and 4.x must never enter it.
  Target is a cumulative **3.75**. The readout shows both counts ("N of 8 TIA dimensions · M of 16
  overall") so the number cannot be misread as covering the whole rubric.

### 5.5 Progress status
```
frac = (current − pre) / (target − pre)

no mid-year data anywhere  → "Baseline" (neutral)
current ≥ target           → Target met
frac ≥ 0.50                → On track
frac ≥ 0.25                → Approaching
otherwise                  → Needs support
```
The baseline case matters. Without it, the moment a teacher locks their SLO every student is
"Needs support" — because *current* defaults to the BOY score and nothing has happened yet.
That is arithmetically true and pedagogically useless. Before any MOY score exists, show
"Baseline recorded for N students", neutral chips and grey bars, and name when the window opens.

### 5.6 Benchmark windows
Computed from the school year, not hardcoded, so it keeps working year over year:
```
school year start = month ≥ July ? this year : last year
MOY opens  1 December  (year start)
EOY opens  1 April     (year start + 1)
```
A preview override exists for demos. Production should decide whether districts can shift these.

### 5.7 Ceiling effects
When a student starts within `max(5, 6% of scale)` of the top, the growth-target row warns that
growth is structurally limited and to note it for the appraiser. A near-ceiling student with a small
target is not low expectations, and that argument is better had when the target is set than at the
end-of-year conference.

---

## 6. Data model

The prototype persists one object to `localStorage` under `ci-slo-draft-v2`. **Production must move
this server-side, per teacher per school year.** The shape maps closely to what you'll want:

```js
{
  // Step 1
  subject, grade, goalKey, custom,

  // Step 2 — the canonical scale + descriptors
  bands: { wb:{lo,hi}, b:{lo,hi}, t:{lo,hi}, a:{lo,hi}, wa:{lo,hi} },
  descriptors: { wb, b, t, a, wa },          // HTML strings (contenteditable)

  // Step 3
  diff: { highest, lowest, cadence, support },
  sources: { "<source name>": bool }, otherSources,

  // Step 4
  hasData, boySource, boyMode, entrySource,
  enteredScores: { "<student>": "<score>" },

  // Step 5
  targets: { "<student>": "<target>" },
  approved, locked,

  // Phase 2 — evidence
  evidence: { "<student>": [ {type,title,standard,ttess,score,note} ] },
  notes:    { "<student>": "<free text>" },

  // Phase 2 — rubric
  rubricVer, rubricSetupDone,
  checkedDesc:   { "<dimId>": { "<level>": [indicatorIndex, …] } },
  ttessRatings:  { "<dimId>": level },
  ttessEvidence: { "<dimId>": [ {type,label} ] },
  levelEvidence: { "<dimId>": { "<level>": [ {type,label} ] } },
  itemEvidence:  { "<dimId>|<level>|<index>": [ {type,label} ] },

  // Phases 2–3 — scores
  moyScores: { "<student>": "<score>" },
  eoyScores: { "<student>": "<score>" },
  eoyDone
}
```

Notes for the real schema:
- Key students by **student ID, not name**. The prototype uses names because it has no roster.
- `itemEvidence` is keyed `dimId|level|index`. Indicator *index* is positional against the rubric
  text — if you version rubric content, key evidence to a stable indicator ID instead, or
  re-tagging will silently drift.
- `descriptors` are HTML from `contenteditable`. Sanitise on the way in.
- An SLO is a year-scoped object. Locking should snapshot the scale and descriptors so later edits
  cannot retroactively change how a locked SLO is measured.

---

## 7. What must come from Crystal Instruction

These are the real integration points. Everything listed here is mocked in the prototype.

| # | Needs | Consumed by | Notes |
|---|---|---|---|
| 1 | Roster: students, classes, groups | Evidence Lockers, all score tables | Prototype has 8 hardcoded students |
| 2 | Per-standard mastery per student | Progress matrix | Currently a deterministic hash of the BOY score. Should be real aggregates from ClearLessons / ClearSheets / Snap Lessons |
| 3 | Recent activity by standard | "Connect what you've taught" | Type · standard · date, filtered to the SLO's TEKS |
| 4 | Lesson Summary report link | Evidence items | This report is already the ready-made evidence artifact — deep-link to it |
| 5 | Artifact upload + storage | Evidence Lockers, rubric | Upload is a stub |
| 6 | Appraiser identity / approval | Lock gate | Currently a self-checked box. Real approval should involve the appraiser |
| 7 | Report export | EOY | Renders on screen and prints; a real PDF pipeline is not built (§10) |

### Two platform gaps worth escalating
Both are documented in `crystal-ttess-alignment.md` and both **cap what this module can claim**:

1. **The student record holds only name / ID / grade / credentials / class.** No EL status, no ELPS
   level, no IEP/504/dyslexia, no reading level. This blocks rubric dimension 1.3 outright and caps
   2.4. It also collides with the Texas ELPS change to five proficiency levels in 2026–27, and
   T-TESS 2 names ELPS directly in its rubric text.
2. **Nothing logs what a teacher *did* after a data alert.** "Monitor & Adjust" (2.5) is the
   platform's strongest dimension, and the missing action log is what prevents a teacher from
   evidencing the Accomplished and Distinguished levels on it. Small build, outsized rubric value.

---

## 8. What's mocked

So nobody mistakes sample data for a feature:

- **8 hardcoded students**, no roster integration.
- **Per-standard mastery** is a deterministic FNV-1a hash of student + standard, seeded from the BOY
  score. Deterministic on purpose so screenshots are stable — it is not data.
- **"Fill with sample progress" / "Fill with sample results"** on MOY and EOY are demo helpers.
  Remove them or gate them behind a demo flag.
- **Upload** opens a file picker and records a label. Nothing is stored.
- **Evidence library** is generated from the SLO's standards, not from real activity.
- **Appraiser approval** is a self-checked box.

---

## 9. Rubric content, and the five gated dimensions

Indicator text is verbatim TEA rubric content (`ttess-rubric-verbatim.txt`). The per-indicator
verdicts — *CI proves this* / *CI helps* / *On you* / *Careful* — come from the descriptor-level
analysis in the two `ttess-descriptor-level-*.md` files, which were derived from a live crawl of the
platform, not from marketing copy.

**Five dimensions deliberately carry no "how Crystal Instruction helps" content: 3.1, 3.2, 4.1, 4.3,
4.4.** The platform has no honest claim on them. They are self-rating plus evidence upload only.
Do not add help bullets to these without a descriptor-level citation — writing plausible filler here
is exactly how the module would start overclaiming to appraisers.

Two findings worth knowing because they should shape marketing as much as engineering:

- Every rubric page separates **student-centered actions** (Distinguished, Accomplished) from
  **teacher-centered actions** (Proficient and below). Crystal Instruction is a teacher-facing
  instrument, so it structurally **supports a teacher to Proficient** and cannot supply the top two
  levels. The module should help teachers *see* that, not paper over it.
- **Dimension 4.2 Goal Setting at Proficient is the single rubric cell the platform closes completely
  and unaided** — and all three of its admissible evidence sources are things this module produces.
  4.2 is the strongest honest claim in the product.

---

## 10. Not built / deliberately deferred

| Item | Status |
|---|---|
| **PDF export of the EOY report** | The report renders and prints; no PDF pipeline. This was requested and is the largest known gap. |
| **Administering a BOY assessment in-app** | v2. Depends on the Student Dashboard project. Only "Input my BOY scores" is built. |
| **T-TESS 2 rubric content** | The version picker and the explainer are built; the 11 dimensions have titles and guiding questions but **no indicator text or verdicts**. See §12. |
| **Student-facing view** | Not in scope here, but see §9 — it is the ceiling-breaker for the top two rubric levels. |
| **Coverage map placement** | Currently on the Rubric tab, where it duplicates the left nav's rating dots. Recommend moving to Overview. |
| **Rubric header density** | Eyebrow + title + version capsule + phase is four elements doing one job. |

---

## 11. Design tokens and accessibility

All colour, radius, shadow and type is driven from CSS custom properties at the top of the file —
start there rather than reading the rules.

```
--ci-magenta      #E313C4   brand fuchsia, from the logo
--ci-magenta-deep #B80FA0   magenta for TEXT (see below)
--ci-purple       #9A2FC9
--ci-grad         linear-gradient(135deg,#E313C4,#9A2FC9)
--ink             #383838   charcoal — NOT navy
--page            #E7F1F8   --line #E3E8F0   --pink-soft #FCE4F2
--font-display / --font-body   Outfit
--font-logo                    Baloo 2  (wordmark only)
```

**Font decision:** the prototype uses **Outfit**, chosen from the comparison in `fonts.html`.
Production `teacher.css` currently serves **Inter**. Adopting the prototype's type means changing
production too, or the two will diverge. This is a live decision, not an oversight.

**Button hierarchy is meaningful — preserve it:**

| Class | Means |
|---|---|
| `.btn-commit` | irreversible commitment. Used **only** for Accept & Lock and its confirmation |
| `.btn-primary` | strong action within a step |
| `.btn-secondary` | navigation |
| `.btn-ghost` | back / cancel |

**Accessibility done:** colour bands always carry text labels, never colour alone; `aria-label`s on
icon-only and destructive controls and on every score input (a table of unnamed number boxes
otherwise); 3px `focus-visible` rings on all interactive elements; autosave status with a hover
timestamp; grey helper text lifted to 5.04:1.

**One open accessibility decision.** Small text uses `--ci-magenta-deep` (#B80FA0, 5.81:1) rather
than brand fuchsia (#E313C4, **4.07:1 — fails WCAG AA for text at these sizes**). It's more legible
and less vivid. If brand vibrancy wins, the cleaner fix is to raise those labels to 14px+ rather
than reverting the colour. **Product decision, currently unresolved.**

---

## 12. Open questions

1. **T-TESS 2 dimension count.** TEA's announcement letter says 12 dimensions; the published pilot
   rubric contains 11. The app follows the rubric and flags the discrepancy. **Confirm with TEA
   before building T-TESS 2 content.**
2. **TEKS codes** on the authored skill statements need curriculum-team verification. They were
   authored for the prototype, not pulled from the standards database.
3. **Benchmark windows** — should districts be able to shift the December/April dates?
4. **Lock semantics** — who may unlock, and should an unlock be audited?
5. **HQIM positioning.** T-TESS 2's Lesson Design dimension applies *only* to teachers not using
   SBOE-approved HQIM. Bluebonnet is Texas HQIM and already a Curriculum Connect provider. That is a
   positioning fork for ClearK12 — complement or core — and it affects what this module should claim.

---

## 13. Suggested build order

1. **Data model + persistence** server-side, per teacher per year. Everything else depends on it.
2. **Phase 1 wizard** through Accept & Lock, including the completion and lock gating (§5.3) and the
   single canonical scale (§5.2). This is the module's spine.
3. **Roster integration** (§7 item 1) — unblocks every table.
4. **Evidence Lockers**, with real upload and the Lesson Summary deep-link.
5. **Rubric tab** with the verbatim indicator text and per-indicator verdicts, keyed to stable
   indicator IDs.
6. **Progress** on real per-standard aggregates, including the baseline-only state (§5.5).
7. **MOY / EOY** with the window logic (§5.6).
8. **Report + PDF export** (§10).

Items 1–2 are the demo-able core; 3–4 make it usable; 5–8 complete the year.

---

## 14. Verification status

What has and hasn't been checked, so you know what to trust:

- **HTML structure:** validated with a tag-balance parser — 0 errors, nothing unclosed.
- **JavaScript:** `node --check` clean.
- **Flows exercised end to end in-browser:** completion/lock gating including the blank-plan block;
  BOY entry, save and re-save; growth targets and ceiling warning; lock confirmation; Progress
  baseline state flipping to real statuses once MOY exists; rubric level switching, indicator expand,
  per-indicator evidence add/remove; canonical scale propagating from the modal to BOY Data.
- **Not verified:** print/PDF output; touch interaction on real tablets; screen-reader passes with
  an actual AT; any behaviour under real data volumes.

One caveat worth stating plainly: this prototype was built in a long session with a flaky preview
tool, and a structural bug (two stray `</div>`s that pushed every panel outside the layout
container) survived several revisions because I trusted DOM measurements over screenshots that were
in fact rendering the bug correctly. It is fixed and guarded by the tag-balance check above — but if
something looks wrong when you open it, believe your eyes.
