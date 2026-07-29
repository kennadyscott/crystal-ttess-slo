# Crystal Instruction ↔ T-TESS Rubric Alignment

**Method:** live crawl of `cs.cleark12.com` logged in as teacher **Dirk Nowitski** (Dallas Mavs Elementary), 2026-07-29. Every claim below is from a screen I opened, not from marketing copy. Where a feature exists only in our prototypes and not in the shipped product, it is called out as such.

**Rubric scope:** all 4 T-TESS domains / 16 dimensions. Note that TIA weights student growth 65% and **T-TESS Domains 2 & 3 only** at 35% — that split matters a lot here (see [TIA implication](#tia-implication)).

---

## 1. Artifact inventory (what the platform actually produces)

| Artifact | Count in tenant | Standards-tagged? | Structure verified |
|---|---|---|---|
| **ClearLesson** | 470 | Yes — Grade, Subject, TEKS ID | 18 slides: title → standard + "I can" target → **Prior Knowledge (APK)** → **Social Emotional** → instruction blocks (IB1–IB3) → **Checkpoint 1** → … **Checkpoint 2** → … **Checkpoint 3** → **Exit Ticket**. Dual surface: *Presentation Screen* vs *Student Device View*. Per-slide **Teacher Tips**. |
| **Snap Lesson** | 928 | Yes — Grade, Subject, TEKS, **+ Targeted Skill = IB1/IB2/IB3** | Single-instructional-block mini-lesson. Product copy: "designed for targeted reteaching or reinforcement — not as a replacement for a comprehensive lesson." Contains Turn-and-Talk prompts. |
| **ClearSheet** | 1,177 | Yes — Standard ID **+ full standard description** | Three flavors: *Skill Builder* (4–9 items, one skill), *Full Topic* (10 items), plain topic sheet (8–14 items). Metadata includes **Topic Name, Breakouts, Remediation Breakouts**. Printed sheet carries the "I can" target + worked example with numbered steps. Actions: *Print Only* / *Assign Online*. Library filters: Grade, Subject, **Level**, Topics, Breakouts. |
| **Assignment** | 54 past | Inherited from sheet | Tabs: Active / **District** / **School** / Past. Columns: Date Assigned, Date Due, Class, Title, # Completed, # Not Completed, Avg Score, Game Rankings, View Results. |
| **Live Monitor** | live | Inherited | Per-student progress + **per-item Correct / Incorrect / Not Completed listed by student name**, class average, sort by Greatest/Least Progress and Highest/Lowest Score, and an explicit **"Pause for Instruction"** control. |
| **Lesson Summary** | 42 | Yes — Standard in header | Header: Title, Grade, Subject, **Standard**, Class, **Date Given**. Tabs: **SEL / APK / Checkpoints / Exit Ticket / Participation / Crystal Analysis / View Game Ranks**. SEL records a per-student emotion (Happy / Normal / Sad). |
| **Crystal Analysis** | per lesson | Yes | Performance Snapshot (Checkpoint Avg, Exit Ticket Avg, Overall Avg) · **Instructional Blocks** list · **Lesson Analysis Overview** narrative · **Recommended Small Groups = Intensive Support / Targeted Reteach / Proficient**, each with a diagnosis paragraph, a **"What They Need to Focus On"** list, *View Reteach Suggestions*, and **named student chips**. Targeted Reteach adds *Common Challenge Blocks*. |
| **Crystal Reports** | tenant-wide | Yes — by TEKS code | Filters Class / Grade / Subject. **Teacher-set performance bands** (Preferences: 100–85 / 85–70 / 70–50 / <50). Questions Answered, Lessons Completed, Score. **Domain Performance** by TEKS reporting category. **Per-standard mastery list with TEKS codes**. **Lesson Performance = Checkpoint Average vs Exit Ticket, sortable**. |
| **Small Groups** | 10 | No | Named, persistent groups per class with N teams — e.g. "Centers Rotation" (2), "Enrichment Block" (3), "Writing Block" (2). |
| **ClassCade Showdown** | 13 | By topic | Team review game — Blue Team / Red Team / Tie Game, per topic and class, Attended / Not Attended, Game Rank, View Results. Dashboard has per-student **Quick Rewards** coin gifting. |
| **Curriculum Connect** | 8 providers | Provider → Grade → **Module** → CI resources | Eureka Math, Number Corner, Amplify, FL Education, Bluebonnet Learning Math, Bluebonnet Learning ELAR, MAP Growth Reading, MAP Growth Math. **Verified empty for Eureka G3 in this tenant** — the structure exists, population varies. |
| **My Lessons** | 0 | — | Teacher uploads their own lesson and adds CI instrumentation: "checkpoints, pathways, APKs, polls." |
| **Student record** | 493 | — | First name, last name, Student ID, Grade, username/password method, class assignment. **Nothing else** — see 1.3. |

---

## 2. Dimension-by-dimension alignment

Rating key: **Strong** = platform produces first-class evidence an appraiser would accept · **Moderate** = real but partial or indirect evidence · **Weak** = incidental · **Out of scope** = not a software problem.

### Domain 1 — Planning

#### 1.1 Standards and Alignment — **Strong**
- Every ClearLesson, Snap Lesson and ClearSheet carries a **TEKS Standard ID**; ClearSheets also carry the **full standard description** verbatim.
- Slide 2 of every lesson projects the standard *and* a student-facing **"I can…"** learning target (with an English/Spanish toggle).
- **"Focuses On"** decomposes the standard into sub-objectives (e.g. 3.2D → "comparing with a place value chart" / "without the support of a place value chart").
- **"Builds On" / "Next Level"** name the prior-grade and next-grade TEKS explicitly (3.2D ← 2.2D, → 4.2C). This is textbook vertical alignment evidence.
- **"Read More"** states where the lesson sits in the K–5 progression and describes the gradual-release sequence ("starts using the support of a place value chart … gradually releases students to compare two numbers without the immediate support").
- **Curriculum Connect** ties CI resources to the district's adopted program and module.
- *Gaps:* no unit/weekly planner or scope-and-sequence view — sequencing **across** lessons remains entirely the teacher's work, and "logically sequenced" is half of this dimension's language. Curriculum Connect mapping is unpopulated for at least Eureka G3.

#### 1.2 Data and Assessment — **Strong**
- Formal: Exit Ticket per lesson; ClearSheet assignments with Avg Score; 54-record assignment history.
- Informal: 1–3 Checkpoints per lesson; APK responses.
- Analysis: **Crystal Reports** per-standard and per-domain mastery, **teacher-set proficiency bands**, and **Checkpoint Average vs Exit Ticket** side by side per lesson.
- Every Lesson Summary is a dated, standard-tagged record — a ready-made body-of-evidence item.
- *Gaps:* **"provides substantive, specific and timely feedback to students"** has no home in the product — I found no comment or feedback field on student work anywhere. No student-facing progress/self-tracking surface was reachable from the teacher side. And exit tickets read **0%** across the demo data, confirming the exit-ticket step is skippable — the strongest part of the data trail is optional.

#### 1.3 Knowledge of Students — **Moderate**
- What exists: APK captures prior knowledge per lesson; the **SEL slide** captures each student's emotional state per lesson; per-standard performance history per student; "Builds On" states the prior-grade expectation; EN/ES toggle on the learning target.
- *Gap (verified in the Student Detail modal):* the student record holds **only** name, ID, grade, credentials and class assignment. There is **no emergent-bilingual/ELL designation, no ELPS proficiency level, no IEP / 504 / dyslexia flag, no reading level, no interest or background field.**
- Consequence: CI's "knowledge of students" is *performance history plus an in-lesson mood pulse* — not a student profile. An appraiser looking for evidence that the teacher knows and plans for individual differences won't find it here.
- Timing note: **ELPS proficiency levels move from 4 to 5 levels starting 2026–27** and there is nowhere in CI to record a level at all.

#### 1.4 Activities — **Moderate**
- Three deliberate resource tiers — ClearLesson (full) → Snap Lesson (single block) → ClearSheet (practice), with *Skill Builder* vs *Full Topic* as a second axis.
- Genuinely varied item formats, verified on one exit ticket: multiple choice with comparison symbols, **drag-and-drop true/false**, and a **multi-clue "select ALL that apply" reasoning riddle**.
- Worked examples with numbered steps; **Turn-and-Talk** prompts; ClassCade Showdown as an alternate modality; **My Lessons** lets a teacher bring their own lesson and add checkpoints/pathways/APKs/polls.
- *Gaps:* student choice and ownership of activity is essentially absent — the teacher pushes everything. And there is **no DOK or cognitive-rigor tag** on items, so "develops higher-order thinking" has to be argued from the item text rather than shown from metadata.

### Domain 2 — Instruction

#### 2.1 Achieving Expectations — **Moderate**
- Exit-ticket mastery per student makes "did *every* student reach the objective" visible, which is the heart of this dimension.
- Crystal Analysis names the students who didn't and routes them into **Intensive Support** / **Targeted Reteach**; Snap Lessons make the re-teach loop cheap.
- The **SEL slide** is a literal social-emotional measure, and 2.1's descriptor language is "academic **and social-emotional** success" — unusually on-target for an instructional platform.
- *Gaps:* no per-objective mastery threshold the teacher can set as an expectation (the 85/70/50 bands live in Crystal Reports Preferences, not against a lesson objective). No student self-monitoring surface. Critically, **no re-assessment trail** — Crystal Reports shows current % per standard, not "this student was 40% then 85% after reteach," so "persists until all students reach the objective" can't be demonstrated over time.

#### 2.2 Content Knowledge and Expertise — **Moderate**
- **Builds On / Next Level** connect prior and future learning explicitly — this is nearly a direct quote of the 2.2 descriptor.
- **Read More** explains the conceptual rationale and the gradual-release design.
- Per-slide **Teacher Tips** deliver pedagogical moves at the moment of use.
- **Instructional Blocks (IB1/IB2/IB3)** decompose a standard into its conceptual pieces.
- *Two caveats worth being honest about:*
  1. This dimension rates **the teacher's** expertise, not the resource's. An appraiser could read heavy scripted reliance either way, so CI should frame these as teacher-capacity supports, not substitutes.
  2. **"Anticipates possible student misunderstandings"** is in the descriptor, and the shipped product has **no misconception or anticipated-error library**. Our misconception predictor is a Brief 2 prototype only. This is the highest-value 2.2 gap.

#### 2.3 Communication — **Moderate**
- Learning target written in student-facing "I can" language and projected; **EN/ES toggle**.
- Dual-surface design (Presentation Screen vs Student Device View) separates what's projected from what's on the desk.
- Probing questions are embedded in instructional slides — verified: *"Which digit should we start with? Which number is greater? How do you know?"*
- Teacher Tips script wait time — verified: *"Give students a minute to respond to the prompt. Share a few responses out, then move on."*
- Turn-and-Talk prompts; Popup Whiteboard.
- *Gaps:* no sentence stems, language scaffolds or academic-vocabulary supports for emergent bilinguals in the shipped product (that's the ELD prototype). The Spanish toggle appears on the learning target — I did **not** verify full-lesson Spanish translation.

#### 2.4 Differentiation — **Strong structurally, one real hole**
- **Crystal Analysis auto-produces three tiers** — Intensive Support / Targeted Reteach / Proficient — each with a diagnosis, a focus list, and **named students**. This is the single best 2.4 artifact in the product.
- **Manage Small Groups** persists those groups (named, multi-team) so grouping is an object, not a one-off.
- **Snap Lessons are indexed by exactly the Instructional Block** (IB1/IB2/IB3) that Crystal Analysis flags — the data model for precision reteach already lines up.
- ClearSheets carry **Breakouts and Remediation Breakouts**; Skill Builder sheets are narrow-skill by design; the library filters by **Level**.
- Proficient tier is framed for extension ("readiness for more advanced concepts"); ClassCade offers a modality switch.
- ***The hole:*** **"View Reteach Suggestions" returns strategy prose, not matched resources.** Verified output: *"Use manipulatives to physically sort shapes · Provide visual aids to illustrate sorting criteria · Incorporate one-on-one support for personalized learning · Utilize simple, clear language when explaining concepts."* No link to the Snap Lesson for IB2, no link to the Skill Builder for 3.6A. The teacher diagnoses in one click and then has to go shopping. **The index exists; the click-through doesn't.**
- Second gap: with no ELL/SpEd/504 fields (see 1.3), there is nothing to differentiate *for* beyond performance.

#### 2.5 Monitor and Adjust — **Strong — the platform's best alignment**
Monitoring side, all verified:
- 1–3 **Checkpoints** launched to student devices mid-lesson, plus **Add CFU** to insert an unplanned check.
- **Live Monitor** shows item-level correctness by student name *while students work*, with sort-by-least-progress and an explicit **"Pause for Instruction"** button. The product copy says it outright: *"Monitor class ClearSheet work live to see progress, item results as they happen, and to allow for instructional pauses."*
- **Paused Lessons** is a first-class module — a paused lesson is a resumable object, which means "I stopped and adjusted" is a system state, not a memory.
- **Crystal Reports Lesson Performance puts Checkpoint Average next to Exit Ticket** per lesson — that delta is a retention-vs-struggled-from-the-start read an appraiser can actually use.
- Crystal Analysis turns results into named groups immediately after the lesson; Lesson Summary preserves it all, dated and standard-tagged.
- *Gap that matters for scoring:* the **adjust** half is advisory only, and **nothing logs what the teacher actually did** in response. There is no "action taken" record. Accomplished and Distinguished on 2.5 require evidence of *adjustment*, not just monitoring — so today the platform proves the teacher had the data, not that they acted on it.

### Domain 3 — Learning Environment

#### 3.1 Classroom Environment, Routines and Procedures — **Weak / indirect**
- What genuinely helps: Small Groups are named for real routines — *"Centers Rotation," "Centers," "Enrichment Block," "Writing Block"* — so the platform holds the routine structure. The consistent 18-slide architecture builds a predictable instructional routine students learn. Device-based checkpoints and exit tickets run technology through one managed flow. Filmstrip + progress % supports pacing.
- *Reality:* physical environment, transitions and supplies are outside a software product's reach. Most of this dimension is unaddressable by CI — better to say so than to stretch.

#### 3.2 Managing Student Behavior — **Weak**
- ClassCade Showdown structures participation into teams with ranks and Attended / Not Attended. **Quick Rewards** coin gifting is a positive-reinforcement mechanism the teacher operates per student. Live Monitor's "Not Started" / per-student progress is a soft on-task signal.
- *Reality:* there is no behavior-standards, incident, or redirection tracking. Coins are a reward ledger, not a behavior system. Don't oversell this one to appraisers.

#### 3.3 Classroom Culture — **Moderate**
- The **SEL slide plus a per-student emotion record in every Lesson Summary** is a genuine, dated culture artifact — very few instructional products capture this at all.
- **Participation** tab per lesson; Turn-and-Talk prompts; ClassCade team play and peer coin gifting; Instructional Minutes / Questions Answered as engagement volume; themed lesson art doing real work on relevance and engagement.
- *Gaps:* SEL is a 3-point mood check, not a culture measure. No student-voice capture and no way to evidence "students collaborate positively and encourage each other."

### Domain 4 — Professional Practices and Responsibilities

#### 4.1 Professional Demeanor and Ethics — **Out of scope**
The Educators' Code of Ethics isn't a software surface. CI contributes only marginal reliability evidence — a dated record of 203 lessons completed, 42 lesson summaries, 54 assignments. Don't claim this dimension.

#### 4.2 Goal Setting — **Moderate today, and this is exactly where the SLO Generator lands**
- In the shipped product: Crystal Reports supplies the per-standard baseline and trend a goal needs; teacher-set performance bands are a mild threshold mechanism; Lesson Summaries are the dated body of evidence.
- *Gap:* **there is no goal object in the shipped platform.** No place to write a goal or an SLO, set a growth target, or attach evidence to a rubric dimension.
- That is precisely the hole the **T-TESS / SLO Generator** fills — BOY→MOY→EOY, per-student growth targets with appraiser approval, Evidence Locker with T-TESS tagging, and a per-dimension rating + evidence collector for Domains 2 & 3. **Stated plainly: 4.2 alignment is aspirational today; shipping the SLO Generator converts it into the strongest Domain 4 story available to Texas elementary teachers.**

#### 4.3 Professional Development — **Weak**
Getting Started video + Quick Start Guide + the in-app assistant + a vendor feedback channel. No PD library, no learning path, and no record of PD completed that a teacher could show an appraiser. (The "ClearK12 PD site" link is prototype-only.)

#### 4.4 School Community Involvement — **Weak / indirect**
- Real hook: the Assignment List has **District** and **School** tabs, so assignments pushed from campus or district level leave a record a teacher can point to when evidencing participation in campus-wide initiatives. Crystal Analysis has a **Parent** field (unpopulated in demo). Curriculum Connect ties the teacher to the district's adopted program.
- *Gaps:* no family communication, no parent-facing report, no PLC or peer-collaboration surface.

---

## 3. Coverage summary

| Rating | Dimensions | Count |
|---|---|---|
| **Strong** | 1.1, 1.2, 2.4, 2.5 | 4 |
| **Moderate** | 1.3, 1.4, 2.1, 2.2, 2.3, 3.3, 4.2 | 7 |
| **Weak** | 3.1, 3.2, 4.3, 4.4 | 4 |
| **Out of scope** | 4.1 | 1 |

Read as a shape: **Crystal Instruction is a Domain 1 + Domain 2 product.** Planning and Instruction are where it produces evidence an appraiser would accept without argument. Domain 3 is thin by nature, Domain 4 is thin by omission.

### TIA implication

TIA weights **student growth 65% / T-TESS Domains 2 & 3 at 35%**. Within that 35%:

- **Domain 2 (5 dimensions):** 2 Strong, 3 Moderate — CI's home turf.
- **Domain 3 (3 dimensions):** 1 Moderate, 2 Weak — almost no product surface.

This is a direct content problem for the SLO Generator's **T-TESS Rubric tab**, which covers exactly those 8 dimensions (2.1–2.5, 3.1–3.3) and offers a "How Crystal Instruction helps" list per dimension. For **3.1 and 3.2 there is currently nothing credible to put in those bullets.** Options: (a) scope those two to what's honest (Small Groups hold your routine structure; ClassCade structures participation), (b) suppress the help bullets for 3.1/3.2 and let them be pure self-rating + evidence upload, or (c) build something real for Domain 3. Option (b) is the honest short-term answer and costs nothing.

---

## 4. Gaps ranked by leverage

| # | Gap | Dimensions unlocked | Notes |
|---|---|---|---|
| 1 | **No record of the action a teacher took after a data alert** | 2.5, 2.1 | Blocks Accomplished/Distinguished on the platform's own best dimension. An "action taken" log on Crystal Analysis is a small build with outsized rubric value. |
| 2 | **Reteach suggestions don't deep-link to the matched Snap Lesson / Skill Builder** | 2.4, 2.5 | The IB1/IB2/IB3 index already exists on both sides. This is plumbing, not new content. |
| 3 | **No student profile fields** — ELL/emergent bilingual, ELPS level, IEP/504/dyslexia, reading level | 1.3, 2.4 | Also a 2026–27 timing issue: ELPS goes 4→5 levels and CI can't record a level at all. |
| 4 | **No goal / evidence object** | 4.2 | The SLO Generator is the fix; this is the argument for shipping it. |
| 5 | **No misconception / anticipated-error library in the shipped product** | 2.2, 2.3 | Brief 2 prototype exists; it maps to a live descriptor phrase. |
| 6 | **No student-facing feedback or self-tracking** | 1.2, 2.1 | "Substantive, specific, timely feedback" is explicit rubric language with no home in the product. |
| 7 | **Exit tickets are skippable** (0% across demo data) | 1.2, 2.5 | The strongest evidence artifact is optional. |
| 8 | **No DOK / cognitive-rigor tag on items** | 1.4, 2.2 | Rigor has to be argued from item text instead of shown. |
| 9 | **Domain 3 has almost no surface** | 3.1, 3.2 | Decide whether to claim it at all — see TIA implication. |

---

## 5. Where the "attach to T-TESS" flow should hook in

The dashboard prototype's **"Attach today's response to T-TESS"** button is the right idea and the crawl confirms what it should attach. The **Lesson Summary report is already a complete evidence item** — it carries Title, Grade, Subject, **Standard**, Class, **Date Given**, plus SEL / APK / Checkpoints / Exit Ticket / Participation / Crystal Analysis. Add a dimension tag and it drops straight into the SLO Generator's Evidence Locker.

Suggested default dimension tags per artifact, for the Evidence Locker's *Tag T-TESS* toggle:

| Artifact | Default tags |
|---|---|
| Lesson Summary (whole) | 1.2, 2.5 |
| Lesson Summary → Crystal Analysis | 2.4, 2.5 |
| Lesson Summary → SEL / Participation | 3.3, 2.1 |
| Lesson Summary → APK | 1.3, 2.2 |
| Live Monitor session (with a pause) | 2.5 |
| Small Group created from Crystal Analysis | 2.4 |
| Snap Lesson taught after a flagged IB | 2.4, 2.1 |
| ClearSheet assignment + Avg Score | 1.2 |
| Crystal Reports per-standard mastery export | 1.2, 4.2 |
| ClearLesson About panel (Builds On / Next Level) | 1.1, 2.2 |
| ClassCade Showdown result | 3.3 |
| Curriculum Connect mapping | 1.1, 4.4 |

---

## 6. Not verified / open

- **Participation, APK, Checkpoints and Exit Ticket tabs** of the Lesson Summary — tab names confirmed, contents not opened.
- **Full-lesson Spanish translation** — only the learning-target toggle was verified.
- **Student-facing experience** — needs a student login; matters for 1.2 (feedback), 2.1 (self-monitoring) and 3.3 (student voice).
- **Crystal Reports Preferences modal** — band values are visible on the page (100–85 / 85–70 / 70–50 / <50) but I didn't open the editor to confirm they're teacher-editable.
- **Level / Topics / Breakouts filter values** in the ClearSheets library — the accordions didn't expand without a subject selected.
- **Curriculum Connect population** — verified empty for Eureka G3; other providers unchecked.
