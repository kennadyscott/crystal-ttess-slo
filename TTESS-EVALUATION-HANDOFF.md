# Crystal Instruction ↔ T-TESS — complete descriptor-level evaluation
### Handoff document · assembled 2026-07-29

**What this is.** A complete, indicator-by-indicator evaluation of how the Crystal Instruction platform (ClearK12) does and does not support a Texas teacher against the T-TESS rubric — all **4 domains, 16 dimensions, 5 performance designations, 274 individual indicator bullets**. Every verdict is grounded in a live crawl of the shipped product, not marketing copy.

**How to use it in a new session.** This file is self-contained. Sections 1–3 orient you; §4 is the governing structure; §5–8 are the evaluation itself; §9–11 are the conclusions, the open items, and the file map. If you only read one thing, read §4 (the ceiling rule) and §10 (what's unverified).

---

## 1. Sources

| | |
|---|---|
| **Rubric** | TEA, *T-TESS Rubric — Working Copy*, rev. **2/10/2022**, 17pp, retrieved from teachfortexas.org. Extracted verbatim to `ttess-rubric-verbatim.txt`. All indicator text quoted in this document is from that file. |
| **Platform** | Live authenticated crawl of `cs.cleark12.com` as teacher demo account **Dirk Nowitski** (Dallas Mavs Elementary), 2026-07-29. Modules crawled: Home dashboard, ClearLessons library + About panel + full lesson preview, Snap Lessons, ClearSheets library + sheet detail, Assignments, Clear Monitor / Live Monitor, Lesson Summaries + report, Crystal Analysis, Crystal Reports, Class Manager (students + small groups), ClassCade Showdown, Curriculum Connect, My Lessons, Paused Lessons. |
| **Dimension-level companion** | `crystal-ttess-alignment.md` — the earlier, coarser pass. Superseded by this document where they disagree (and they do; see §9). |

### Verdict key
| | Meaning |
|---|---|
| **PROVES** | CI output is *by itself* sufficient evidence for this indicator. Hand the artifact to the appraiser. |
| **SUPPORTS** | CI contributes real evidence but does not close the indicator. Teacher must supply the rest. |
| **NO HELP** | CI contributes nothing to this indicator. |
| **RISK** | CI use could actively *hurt* the rating if presented carelessly. |

---

## 2. Status

**Complete.** Verbatim rubric for all 16 dimensions. Descriptor-level evaluation for all 16 dimensions × 5 designations × 274 bullets. Consolidated cross-domain gap analysis with rubric citations.

**Not done.** T-TESS 2 has **not** been evaluated at all — see §3. Three verification items and one writing task remain open — see §10 and §11.

**Built into the product** (`slo-generator.html`) off the back of this: the rubric tab was extended from 8 dimensions to all 16; the TIA average was scoped so Domain 1 and 4 ratings can never leak into the Domains 2–3 / 3.75 calculation; help bullets are **gated** so five dimensions (3.1, 3.2, 4.1, 4.3, 4.4) carry no product claims at all; and a T-TESS 2 readiness band was added.

---

## 3. T-TESS 2 — known shape, zero evaluation

Confirmed at TEA, but **no T-TESS 2 descriptor has been read**. The pilot rubric PDF exists at `teachfortexas.org/Resource_Files/Evaluation_Process/T-TESS_2_Pilot_Rubric.pdf` and has never been fetched.

| | |
|---|---|
| **Structure** | **12 dimensions** (down from 16), same **4 domains**, same 5-point scale. Adds indicators that name each skill and look for evidence of student learning at higher levels. |
| **2026–27** | Pilot, **15 school systems**. Everyone else stays on the 16-dimension rubric this document evaluates. Appraiser recertification training runs spring/summer. |
| **2027–28** | TEA's **recommended adoption year**. |
| **2028–29** | Fallback for districts that can't move in 2027–28. |

Implication for this work: 2026–27 and most of 2027–28 run on the current rubric, so nothing here is wasted. But the 16→12 consolidation mapping is unknown, which means **the product's claim that "your evidence maps forward" is reasonable but unproven bullet-by-bullet.** That's the first thing to test when T-TESS 2 work starts.

---

## 4. The governing structure — read this first

**1. The rubric's own left/right split is the ceiling on CI.**
Every page of the T-TESS rubric is footed with the same two labels: **STUDENT-CENTERED ACTIONS** under Distinguished and Accomplished, **TEACHER-CENTERED ACTIONS** under Proficient, Developing and Improvement Needed. That is not decoration — it's the promotion rule. Moving from Proficient to Accomplished requires evidence that *students* are doing something: setting their own goals, self-monitoring, generating questions, holding each other accountable, taking leadership of routines.

Crystal Instruction is a teacher-facing instrument. Nearly everything it emits is evidence of *teacher* action. **Consequence: CI can carry a teacher to Proficient on most of Domains 2 and 3, and can support but never supply Accomplished or Distinguished.** The product should say this out loud rather than imply otherwise — it's also a roadmap, because a student-facing surface is what would break the ceiling.

**2. CI data is admissible in all eight dimensions by the rubric's own terms.**
Each of the eight dimensions lists **"analysis of student data"** among its *Potential Sources of Evidence*, and five of the eight also list **"classroom artifacts."** So an appraiser cannot wave off CI reports as off-rubric. This is worth telling teachers explicitly — it's the permission slip for the whole Evidence Locker.

**3. The single best cell in the rubric for CI.** Dimension 2.1 Distinguished asks for evidence that **"all students demonstrate mastery"** where Accomplished and Proficient both settle for **"most students."** Per-student exit-ticket data is *exactly* that evidence, and it is the one place in Domains 2–3 where CI can push a teacher a full level above Proficient on a bullet's own merits. Flag it in the product.

### Why Domains 1 and 4 behave differently

**Neither domain is scored from the classroom observation.** Both are evidenced through *artifacts and conferences* — and the rubric says so explicitly in its own Potential Sources of Evidence:

- **1.1–1.4:** "Conferences and conversations with the teacher; formal observations and walkthroughs; **classroom artifacts**; student growth processes; **analysis of student data**"
- **4.2:** "**Goal-setting and professional development plan (GSPD)**; conferences and conversations with the teacher, **including the end-of-year conference**; **analysis of student data**"

This inverts the usual assumption about where an instructional platform helps. In Domains 2 and 3 the appraiser is in the room generating their own evidence, and CI is supplementary. In Domains 1 and 4 **the teacher must arrive at a conference with artifacts, and CI is one of very few sources of them.** A dated, standard-tagged, per-student record is exactly the currency these two domains trade in.

The student-centred ceiling described above still applies — Distinguished and Accomplished require student agency — but it bites less here, because much of Domain 1 is about *design* rather than student action.


---

# 5. DOMAIN 1 — PLANNING

## 1.1 Standards and Alignment
> *The teacher designs clear, well-organized, sequential lessons that reflect best practice, align with standards and are appropriate for diverse learners.*
> Standards basis 1A, 1B, 3A, 3B, 3C · Sources: conferences; observations/walkthroughs; **classroom artifacts**; student growth processes

The rubric's biggest dimension, and CI's best. Structure at each level: a goals bullet, an "activities, materials and assessments that…" bullet with sub-indicators, an objectives bullet, and a technology bullet.

### DISTINGUISHED
| Indicator (verbatim) | Verdict | Proof / reasoning |
|---|---|---|
| "All **rigorous and measurable** goals aligned to state content standards" | **SUPPORTS** | Aligned: PROVES — every asset carries a TEKS ID and ClearSheets carry the full standard text. Measurable: the "I can" learning target plus an exit ticket is a measurable goal. **Rigorous** is the unmet word — no DOK or rigor tag exists anywhere in CI, so rigour is your assertion, not the platform's. |
| *Activities/materials/assessments:* "are **logically** sequenced" | **SUPPORTS** | Within a lesson, PROVES — the 18-slide architecture is explicitly gradual-release, and "Read More" documents it: *"starts using the support of a place value chart… gradually releases students to compare two numbers without the immediate support."* Across lessons, NO HELP — there is no unit planner. |
| "are relevant to students' prior understanding **and real-world applications**" | **SUPPORTS** | Prior understanding: PROVES twice — the APK slide and the "Builds On" prior-grade TEKS. Real-world: thematic only (money, budgets, payroll tax), not a documented field. |
| "**integrate and reinforce concepts from other disciplines**" | **NO HELP** | No cross-discipline linkage exists in CI. Recurs at Accomplished here and at all three upper levels of 2.2 — see the cross-domain table. |
| "provide appropriate time for student work, **student reflection**, lesson and lesson closure" | **SUPPORTS** | Time for student work is structurally built in (checkpoints, exit ticket, device tasks) and the filmstrip + progress % is a pacing instrument. Student reflection and explicit lesson closure are absent — there is no closure or reflection slide in the 18-slide anatomy. |
| "**deepen understanding of broader unit and course objectives**" | **NO HELP** | CI has no unit or course object at all. Lessons are standard-tagged but not unit-tagged. |
| "are **vertically aligned** to state standards" | **PROVES** | The strongest single cell in Domain 1. "Builds On" names the prior-grade TEKS (3.2D ← 2.2D) and "Next Level" the next-grade TEKS (→ 4.2C), in the product, per lesson, screenshot-able. Very few teachers can evidence vertical alignment this cleanly. |
| "are appropriate for **diverse learners**" | **SUPPORTS** | Level-filtered ClearSheets, Remediation Breakouts, Snap Lessons, Spanish learning-target toggle. Weakened by the student record holding no ELL/ELPS, IEP/504 or reading-level data — you can differentiate by performance but cannot show you planned for a *designated* population. |
| "Objectives aligned and logically sequenced to the lesson's goal, providing relevant and **enriching extensions** of the lesson" | **SUPPORTS** | "Focuses On" decomposes the standard into sequenced sub-objectives. Extensions: Crystal Analysis frames the Proficient tier for "more advanced concepts" but offers no actual extension resource — the extension library is thin. |
| "**Integration of technology to enhance mastery** of goal(s)" | **PROVES** | CI *is* the technology integration, and "to enhance mastery" is the operative clause — checkpoints and exit tickets exist to establish mastery. This bullet is easier for a CI teacher than for almost anyone else. |

### ACCOMPLISHED
Identical structure, one notch down in qualifiers. Deltas that matter:

| Indicator | Verdict | Proof / reasoning |
|---|---|---|
| "All **measurable** goals aligned to state content standards" | **PROVES** | "Rigorous" drops out, and measurable + aligned is exactly what a TEKS ID plus an exit ticket delivers. CI closes this bullet outright at Accomplished where it only supported at Distinguished. |
| "are **sequenced**" (not "logically") | **PROVES** | Within-lesson sequencing, documented. |
| "are relevant to students' prior understanding" (real-world clause drops) | **PROVES** | APK + Builds On. |
| "**integrate other disciplines**" | **NO HELP** | Still required. |
| "provide appropriate time for student work, lesson and lesson closure" (reflection drops) | **SUPPORTS** | Closure still absent. |
| "**reinforce** broader unit and course objectives" | **NO HELP** | No unit object. |
| "are vertically aligned to state standards" | **PROVES** | Builds On / Next Level. |
| "are appropriate for diverse learners" | **SUPPORTS** | As above. |
| "All objectives aligned and logically sequenced to the lesson's goal" | **PROVES** | "Focuses On." |
| "Integration of technology to enhance mastery of goal(s)" | **PROVES** | As above. |

### PROFICIENT
| Indicator | Verdict | Proof / reasoning |
|---|---|---|
| "**All goals** aligned to state content standards" | **PROVES** | TEKS ID on every asset. |
| "are sequenced" | **PROVES** | — |
| "are relevant to **students**" | **PROVES** | APK. |
| "provide appropriate time for lesson and lesson closure" | **SUPPORTS** | Closure is the gap — and it's required at the *expected* level. |
| "**fit into the broader unit and course objectives**" | **NO HELP** | Required at Proficient, and CI has no unit construct. A real Proficient-level hole, not a stretch-goal gap. |
| "are appropriate for diverse learners" | **SUPPORTS** | — |
| "All objectives aligned to the lesson's goal" | **PROVES** | — |
| "Integration of technology **when applicable**" | **PROVES** | — |

### DEVELOPING / IMPROVEMENT NEEDED
Deficit ladders ("**Most** goals aligned" → "**Few** goals aligned"; "sometimes provide appropriate time" → "rarely provide time"). CI is close to dispositive against these: a library where *every* asset is TEKS-tagged makes "few goals aligned to state content standards" very hard to sustain.

**CI ceiling on 1.1: strong Accomplished on the alignment bullets, capped by three consistent holes — unit/course context, lesson closure, and cross-discipline integration.** Note that two of those three bite at Proficient.

---

## 1.2 Data and Assessment
> *The teacher uses formal and informal methods to measure student progress, then manages and analyzes student data to inform instruction.*
> Standards basis 1B, 1F, 2B, 2C, 5A, 5B, 5C, 5D · Sources: conferences; observations/walkthroughs; **classroom artifacts**; student growth processes; **analysis of student data**

Three bullets per level: assessment, feedback, analysis. CI is excellent on two of three and absent on the third at *every* level.

### DISTINGUISHED
| Indicator | Verdict | Proof / reasoning |
|---|---|---|
| "Formal and informal assessments to monitor progress of all students, **shares appropriate diagnostic, formative and summative assessment data with students to engage them in self-assessment, build awareness of their own strengths and weaknesses and track their own progress**" | **SUPPORTS** | First limb PROVES emphatically — exit ticket (summative), checkpoints (formative), APK (diagnostic), all three named assessment types, per student, dated. Second limb NO HELP — there is no student-facing data view, so nothing is *shared with students*. The bullet fails on its longer half. This is the student-facing gap again, and here it costs a Distinguished on CI's best data dimension. |
| "**Substantive, specific and timely feedback** to students, families and school personnel… and **engages with colleagues to adapt school-wide instructional strategies**… maintaining confidentiality" | **NO HELP** | No feedback field, no family-facing report, no colleague/PLC surface. Crystal Analysis has a "Parent" field that was unpopulated in the demo — worth investigating whether it's a real channel. |
| "Analysis of student data **connected to specific instructional strategies** and use of results **to reflect on his or her teaching** and to monitor teaching strategies and behaviors in relation to student success" | **SUPPORTS** | Analysis connected to strategies: PROVES — Crystal Analysis literally pairs a data diagnosis with named strategies. Reflecting on *your own teaching* is the missing half: CI analyses students, never the teacher. Nothing correlates a teaching choice to a result. |

### ACCOMPLISHED
| Indicator | Verdict | Proof / reasoning |
|---|---|---|
| "Formal and informal assessments to monitor progress of all students **and incorporate appropriate diagnostic, formative and summative assessments data into lesson plans**" | **SUPPORTS** | Better fit than Distinguished — "into lesson plans" rather than "with students." Crystal Analysis feeds results into a next-step grouping, and Snap Lessons are indexed to the flagged Instructional Block. The missing link is the same one as 2.4: no record of the resource you actually chose. |
| "Substantive, specific and timely feedback to students, families and other school personnel…" | **NO HELP** | — |
| "Analysis of student data connected to specific instructional strategies and use of results to reflect on his or her teaching…" | **SUPPORTS** | As above. |

### PROFICIENT
| Indicator | Verdict | Proof / reasoning |
|---|---|---|
| "**Formal and informal assessments to monitor progress of all students**" | **PROVES** | Cleanest PROVES in Domain 1. Checkpoints + exit tickets across 42 lesson summaries and 54 assignments, every student, every lesson. |
| "**Consistent feedback** to students, families and other school personnel while maintaining confidentiality" | **NO HELP** | Required at the expected level, zero coverage. Combined with 2.5, student feedback is now the gap that appears at Proficient in two separate dimensions. |
| "Analysis of student data **connected to specific instructional strategies**" | **PROVES** | Crystal Analysis: data → diagnosis → named strategies → named students. Exactly the bullet. |

### DEVELOPING / IMPROVEMENT NEEDED
"Utilization of **multiple** sources of student data" (Developing) / "**few** sources" (IN) — CI alone supplies checkpoints, exit tickets, ClearSheet assignments, APK, SEL, ClassCade and Crystal Reports. Multiple sources is trivially exceeded.

**CI ceiling on 1.2: Proficient with two of three bullets PROVES — and the third (feedback) blocked at every level including Proficient.** Build a feedback field and 1.2 becomes a credible Accomplished.

---

## 1.3 Knowledge of Students
> *Through knowledge of students and proven practices, the teacher ensures high levels of learning, social-emotional development and achievement for all students.*
> Standards basis 1A, 1B, 1C, 2A, 2B, 2C · Sources: conferences; observations/walkthroughs; **classroom artifacts**; student growth processes; **analysis of student data**

### DISTINGUISHED
| Indicator | Verdict | Proof / reasoning |
|---|---|---|
| "**All lessons** that connect to students' prior knowledge, experiences, **interests** and future learning expectations **across content areas**" | **SUPPORTS** | Prior knowledge: PROVES (APK slide, every lesson). Future learning expectations: PROVES ("Next Level"). Interests: NO HELP — no interest inventory; the student record is name/ID/grade. Across content areas: NO HELP. Two of four limbs. |
| "Guidance for students to apply their strengths, background knowledge, life experiences and skills to enhance **each other's** learning" | **NO HELP** | Peer-to-peer knowledge sharing. Turn-and-Talk prompts gesture at it but nothing captures or guides it. |
| "Opportunities for students to utilize their **individual learning patterns, habits and needs** to achieve high levels of academic **and social-emotional** success" | **SUPPORTS** (weak) | The SEL check is a genuine social-emotional instrument and it is per student and dated. Learning patterns and habits are not modelled in CI at all. |

### ACCOMPLISHED
| Indicator | Verdict | Proof / reasoning |
|---|---|---|
| "All lessons that connect to students' prior knowledge, experiences and future learning expectations" (interests + cross-content drop) | **PROVES** | With "interests" and "across content areas" removed, CI closes this outright: APK covers prior knowledge and experiences, "Next Level" covers future learning expectations. Every lesson, dated. A clean Accomplished bullet. |
| "Guidance for students to apply their strengths… to enhance **their own** learning" | **NO HELP** | — |
| "Opportunities for students to utilize their individual learning patterns, habits and needs" | **SUPPORTS** (weak) | — |

### PROFICIENT
| Indicator | Verdict | Proof / reasoning |
|---|---|---|
| "**All lessons that connect to students' prior knowledge and experiences**" | **PROVES** | The APK slide is in every ClearLesson and its responses are preserved in every Lesson Summary. Verified live: *"Activate Prior Knowledge: How do you know if one number is bigger than another?"* with a captured response field and a teacher tip. Dated, per student, 42 summaries deep. |
| "Adjustments to address strengths and gaps in **background knowledge, life experiences and skills** of all students" | **SUPPORTS** | "Skills" gaps: PROVES — Crystal Analysis tiering and per-standard mastery are exactly skills-gap adjustment. **Background knowledge and life experiences: NO HELP** — CI holds none of it. This is the 1.3 gap in one line, and it's why my dimension-level pass rated 1.3 only Moderate. |

### DEVELOPING / IMPROVEMENT NEEDED
"**Most** lessons that connect…" → "**Few** lessons…" — since the APK slide is built into every ClearLesson, a CI teacher is structurally above these descriptors.

**CI ceiling on 1.3: Proficient, and a genuine Accomplished on the first bullet.** Better than I rated it at dimension level, because the APK slide maps almost word-for-word onto the Accomplished indicator. The blocker for Distinguished is student *interests* and peer knowledge-sharing — both absent.

---

## 1.4 Activities
> *The teacher plans engaging, flexible lessons that encourage higher-order thinking, persistence and achievement.*
> Standards basis 1B, 1C, 1D, 1E · Sources: conferences; observations/walkthroughs; **classroom artifacts**; student growth processes; **analysis of student data**

Four bullets per level: questioning, grouping, student roles, materials. Note how heavily student-centred the top two levels are.

### DISTINGUISHED
| Indicator | Verdict | Proof / reasoning |
|---|---|---|
| "Opportunities for **students to generate questions** that lead to further inquiry and promote complex, higher-order thinking, problem solving and real-world application" | **NO HELP** | Students generating questions. CI is entirely teacher-question-driven; no student question capture exists. |
| "Instructional groups based on the needs of all students, and allows for **students to take ownership of group and individual accountability**" | **SUPPORTS** | First limb PROVES (Crystal Analysis tiers + persisted Small Groups). Student ownership of accountability: NO HELP. |
| "The ability for **all students to set goals, reflect on, evaluate and hold each other accountable** within instructional groups" | **NO HELP** | Four student-agency verbs in one bullet. The purest expression of the ceiling. |
| "Activities, resources, technology and instructional materials that are all aligned to instructional purposes, are varied and appropriate to ability levels **and actively engage them in ownership of their learning**" | **SUPPORTS** | Aligned + varied + ability-appropriate: PROVES (TEKS-tagged, three resource tiers, Level filter). Ownership: NO HELP. |

### ACCOMPLISHED
| Indicator | Verdict | Proof / reasoning |
|---|---|---|
| "Questions that encourage all students to engage in complex, higher-order thinking **and problem solving**" | **SUPPORTS** | The multi-clue "select ALL that apply" reasoning item and word-problem lessons are genuine problem solving. No DOK tag to prove the mix. |
| "Instructional groups based on the needs of all students and **maintains both group and individual accountability**" | **SUPPORTS** | Grouping PROVES; ClassCade gives a group-accountability record (team ranks) and per-student coins give an individual one. Reasonable claim. |
| "All students understanding their individual roles within instructional groups **and facilitates opportunities for student input on goals and outcomes**" | **NO HELP** | Student input on goals. |
| "Activities… all aligned to instructional purposes, are varied and appropriate to ability levels of students" | **PROVES** | Drop the ownership clause and CI closes it: TEKS-aligned, three tiers, Level-filtered. |

### PROFICIENT
| Indicator | Verdict | Proof / reasoning |
|---|---|---|
| "Questions that encourage all students to engage in complex, higher-order thinking" | **SUPPORTS** | Item variety yes, provable rigour no. |
| "**Instructional groups based on the needs of all students**" | **PROVES** | Crystal Analysis produces the needs-based grouping automatically and Small Groups persists it — verified live with named students on 3.6A. Same artifact that carries 2.4. |
| "All students understanding their individual roles within instructional groups" | **NO HELP** | Required at Proficient. CI creates the group but assigns no roles and communicates nothing to students. |
| "**Activities, resources, technology and instructional materials that are all aligned to instructional purposes**" | **PROVES** | Every asset TEKS-tagged with the standard description attached. |

### DEVELOPING / IMPROVEMENT NEEDED
"Questions that promote limited, predictable or **rote** responses" / "materials **misaligned** to instructional purposes" — a TEKS-tagged library is a strong defence on the alignment limb; the questioning limb is genuinely at risk given the absence of rigour tagging.

**CI ceiling on 1.4: Proficient on two of four bullets, with student roles unaddressed even at Proficient.** The higher levels are almost entirely student-agency and out of reach.

---

---

# 6. DOMAIN 2 — INSTRUCTION

## 2.1 Achieving Expectations
> *The teacher supports all learners in their pursuit of high levels of academic and social-emotional success.*
> Standards basis 1B, 1D, 1E, 2A, 2C, 3B, 4A, 4D, 5B · Sources: conferences; observations/walkthroughs; student growth processes; **analysis of student data**

### DISTINGUISHED
| Indicator (verbatim) | Verdict | Proof / reasoning |
|---|---|---|
| "Provides opportunities for students to establish high academic and social-emotional expectations **for themselves**" | **NO HELP** | CI has no student goal-setting surface. The SEL slide *asks* students how they feel; it does not let them set an expectation. Teacher must supply student goal-setting sheets or conference records. |
| "Persists with the lesson until there is evidence that **all** students demonstrate mastery of the objective" | **PROVES** | This is CI's best cell in the entire rubric. The Exit Ticket returns per-student mastery, and Crystal Analysis names every student below in Intensive Support / Targeted Reteach. That *is* "evidence that all students demonstrate mastery" — or precisely who didn't. Note Accomplished/Proficient only require "most," so this one bullet is a genuine level-jump. Caveat: you must show the *return trip* — CI shows current mastery, not a retest trail, so log the post-reteach result. |
| "Provides opportunities for students to self-monitor and self-correct mistakes" | **NO HELP** | No student-facing progress view exists. Students answer items; they don't see their own trend or correct their own errors in CI. |
| "**Systematically** enables students to set goals for themselves and monitor their progress over time" | **NO HELP** | Same gap, and "systematically" raises the bar further. This is the clearest single argument for building a student view. |

### ACCOMPLISHED
| Indicator | Verdict | Proof / reasoning |
|---|---|---|
| "Provides opportunities for students to establish high academic and social-emotional expectations for themselves" | **NO HELP** | As above. |
| "Persists... evidence that **most** students demonstrate mastery" | **PROVES** | Trivially satisfied by the same exit-ticket data that reaches the Distinguished bar. |
| "**Anticipates** student mistakes and encourages students to avoid common learning pitfalls" | **SUPPORTS** (weakly) | Teacher Tips occasionally pre-empt an error, but there is **no misconception library in the shipped product** — the predictor is a prototype. Anticipation is currently the teacher's own knowledge. This is the highest-value 2.x product gap. |
| "Establishes systems where students take initiative of their own learning and self-monitor" | **NO HELP** | No student-facing system. |

### PROFICIENT
| Indicator | Verdict | Proof / reasoning |
|---|---|---|
| "Sets academic expectations that challenge **all** students" | **SUPPORTS** | Crystal Reports lets the teacher set proficiency bands (100–85 / 85–70 / 70–50 / <50), and Crystal Analysis frames the Proficient tier for extension. But CI has **no per-objective mastery target** — the bands are report thresholds, not lesson expectations. Pair with your SLO growth targets, which *are* per-student expectations. |
| "Persists with the lesson until there is evidence that most students demonstrate mastery" | **PROVES** | Exit ticket + checkpoint averages. |
| "**Addresses** student mistakes and follows through to ensure student mastery" | **SUPPORTS** | CI identifies the mistake precisely (Live Monitor names who missed which item; Crystal Analysis names the failing Instructional Block). "Follows through" is unevidenced — nothing logs the follow-through. Log it in the Evidence Locker. |
| "Provides students opportunities to take initiative of their own learning" | **NO HELP** | — |

### DEVELOPING / IMPROVEMENT NEEDED
These are deficit descriptions ("challenge *most*/*few* students," "concludes the lesson even though... few students demonstrate mastery," "allows student mistakes to go unaddressed"). **CI's function here is exculpatory:** exit-ticket and Crystal Analysis records are direct evidence *against* "concluded the lesson despite few students mastering it," because they document that the teacher knew the mastery split and acted. That's a real use — a teacher contesting a Developing rating on 2.1 should bring the Lesson Summary.

**CI ceiling on 2.1: Proficient, with a defensible Distinguished claim on the mastery-evidence bullet alone.** Everything blocking a full Accomplished is student-agency language.

---

## 2.2 Content Knowledge and Expertise
> *The teacher uses content and pedagogical expertise to design and execute lessons aligned with state standards, related content and student needs.*
> Standards basis 1A, 1C, 1E, 1F, 2C, 3A, 3B, 3C · Sources: conferences; observations/walkthroughs; student growth processes; **analysis of student data**

### DISTINGUISHED
| Indicator | Verdict | Proof / reasoning |
|---|---|---|
| "Displays **extensive** content knowledge of all the subjects she or he teaches **and closely related subjects**" | **RISK** | This rates the *teacher*, not the resource. Leaning on CI here can read as scripted delivery. Frame CI as the vehicle and your own commentary as the expertise. |
| "Integrates learning objectives with other disciplines, content areas **and real-world experience**" | **SUPPORTS** | ClearLessons carry thematic real-world framing (money, budgets, income and payroll tax in the G5 Snap Lessons) and the "Read More" rationale names real-world application. Cross-*discipline* integration is not a CI feature — no lesson field links to another content area. |
| "**Consistently** anticipates possible student misunderstandings and proactively develops teaching techniques to mitigate concerns" | **NO HELP** | No misconception library ships. Verified: the closest thing, Crystal Analysis's "View Reteach Suggestions," is *reactive* (post-data) and returns generic strategies. |
| "**Consistently** provides opportunities for students to use different types of thinking (analytical, practical, creative, research-based)" | **SUPPORTS** | Item formats do reach analytical and practical (the multi-clue "select ALL that apply" riddle is genuine analytical reasoning). Creative and research-based are absent from CI item types, and there is **no DOK tag** to prove any of it — you must characterise the thinking yourself. |
| "Sequences instruction that allows students to understand how the lesson fits within the structure of the discipline, the state standards, related content **and within real-world scenarios**" | **PROVES** (partially) | This is CI's strongest 2.2 asset. Slide 2 projects the standard; "Builds On" names the prior-grade TEKS and "Next Level" the next-grade TEKS; "Read More" states the lesson's place in the K–5 progression. That is the discipline structure and the standards, documented. "Related content and real-world scenarios" is the part you add. |

### ACCOMPLISHED
| Indicator | Verdict | Proof / reasoning |
|---|---|---|
| "Conveys a depth of content knowledge that allows for **differentiated explanations**" | **SUPPORTS** | Snap Lessons give a second, narrower explanation of a single Instructional Block; ClearSheets exist at multiple Levels. The prototype "Explain 5 ways" would nail this bullet — it isn't shipped. |
| "Integrates learning objectives with other disciplines and real-world experiences" | **SUPPORTS** | As above, real-world yes, cross-discipline no. |
| "Anticipates possible student misunderstandings and proactively develops teaching techniques" | **NO HELP** | As above. |
| "**Regularly** provides opportunities for students to use different types of thinking" | **SUPPORTS** | As above. |
| "Sequences instruction that allows students to understand how the lesson fits within the structure of the discipline and the state standards" | **PROVES** | Builds On / Next Level / Read More, verbatim to the bullet. Drop the "real-world" clause and CI closes this one outright. |

### PROFICIENT
| Indicator | Verdict | Proof / reasoning |
|---|---|---|
| "Conveys **accurate** content knowledge in multiple contexts" | **SUPPORTS** | 470 TEKS-tagged ClearLessons with worked examples are a reasonable accuracy warrant; "multiple contexts" is served by the lesson/Snap/sheet tiering. |
| "Integrates learning objectives with other disciplines" | **NO HELP** | No cross-discipline linkage anywhere in CI. Note this is required as low as Proficient — a real gap, not just a stretch goal. |
| "Anticipates possible student misunderstandings" | **NO HELP** | Required at Proficient. CI does not help you meet the *expected* level on this bullet. This is the strongest business case in Domain 2 for shipping the misconception predictor. |
| "Provides opportunities for students to use different types of thinking" | **SUPPORTS** | Item variety. |
| "Accurately reflects how the lesson fits within the structure of the discipline and the state standards" | **PROVES** | Builds On / Next Level. |

### DEVELOPING / IMPROVEMENT NEEDED
Deficit language ("sometimes integrates," "conveys inaccurate content knowledge that leads to student confusion"). CI's TEKS-aligned, reviewed content is a strong defence against the *inaccuracy* descriptors.

**CI ceiling on 2.2: Proficient at best, and CI leaves two Proficient bullets uncovered** (cross-discipline integration; anticipating misunderstandings). This is the weakest of CI's Domain 2 dimensions relative to its reputation.

---

## 2.3 Communication
> *The teacher clearly and accurately communicates to support persistence, deeper learning and effective effort.*
> Standards basis 1D, 1E, 2A, 3A, 4D · Sources: conferences; observations/walkthroughs; student growth processes; **analysis of student data**

### DISTINGUISHED
| Indicator | Verdict | Proof / reasoning |
|---|---|---|
| "Establishes classroom practices that encourage **all** students to communicate safely and effectively using a **variety of tools and methods** with the teacher **and their peers**" | **SUPPORTS** | Real: the Student Device View gives every student a private response channel, and Turn-and-Talk prompts direct peer talk. "Variety of tools" is served by device + whiteboard + verbal. Peer-to-peer communication is prompted but never *captured* — no artifact. |
| "**Uses** possible student misunderstandings at strategic points in lessons to highlight misconceptions and inspire exploration and discovery" | **SUPPORTS** | Structurally CI is well-shaped for this — checkpoints land at planned points and Live Monitor surfaces the wrong-answer cluster in real time, which is exactly a "strategic point." But CI never suggests *teaching into* the misconception; it suggests remediating it. Prototype territory. |
| "Provides explanations that are clear and coherent and uses verbal and written communication that is clear and correct" | **SUPPORTS** | Written communication in CI is professionally produced — learning targets in "I can" form, numbered worked-example steps. Your verbal delivery is unevidenced by CI. |
| "Asks questions at the **creative, evaluative and/or analysis** levels that require deeper learning and broader understanding" | **SUPPORTS** (weakly) | Embedded slide questions verified — *"Which digit should we start with? Which number is greater? How do you know?"* The "how do you know" is genuine analysis; the first two are recall/apply. Without a DOK tag you cannot show the mix. |
| "**Skillfully balances wait time, questioning techniques and integration of student responses** to support student-directed learning" | **SUPPORTS** | Notable: Teacher Tips explicitly script wait time — *"Give students a minute to respond to the prompt. Share a few responses out, then move on."* That is wait time *and* integration of student responses, in writing, in the product. Strong artifact. "Student-directed" is the ceiling clause. |
| "Skillfully provokes and guides discussion to pique curiosity and inspire **student-led** learning" | **NO HELP** | Student-led. Ceiling. |

### ACCOMPLISHED
| Indicator | Verdict | Proof / reasoning |
|---|---|---|
| "Establishes classroom practices that encourage all students to communicate effectively, **including the use of visual tools and technology**, with the teacher and their peers" | **PROVES** | CI is visual tools and technology used by all students, every lesson, with a per-student response record. This bullet is easier for a CI teacher than a non-CI teacher. |
| "Anticipates possible student misunderstandings and proactively develops techniques to address obstacles" | **NO HELP** | Recurring gap — appears in 2.1, 2.2 and 2.3. One product gap, three dimensions. |
| "Provides explanations that are clear and coherent..." | **SUPPORTS** | As above. |
| "Asks questions at the creative, evaluative and/or analysis levels that focus on the objective and provoke thought and discussion" | **SUPPORTS** | As above. |
| "**Skillfully uses probing questions** to clarify, elaborate and extend learning" | **SUPPORTS** | Slide-embedded probes give you the questions; skill in using them is observed, not logged. |
| "Provides wait time when questioning students" | **PROVES** | The Teacher Tips wait-time script is a citable artifact. |

### PROFICIENT
| Indicator | Verdict | Proof / reasoning |
|---|---|---|
| "Establishes classroom practices that provide opportunities for **most** students to communicate effectively with the teacher and their peers" | **PROVES** | Device view + Turn-and-Talk. |
| "**Recognizes** student misunderstandings and responds with an **array of teaching techniques** to clarify concepts" | **SUPPORTS** | Recognition: strong (Live Monitor, checkpoint clusters). Array of techniques: the reteach suggestions do list several strategies — manipulatives, visual aids, one-on-one, simplified language — so at Proficient the generic list actually *is* an "array." This is the one level where the vague suggestions are adequate. |
| "Provides explanations that are clear and uses verbal and written communication that is clear and correct" | **SUPPORTS** | — |
| "Asks **remember, understand and apply** level questions that focus on the objective and provoke discussion" | **PROVES** | This is exactly the level CI's slide questions sit at. Ironically CI matches Proficient on this bullet better than it matches the higher levels. |
| "Uses probing questions to clarify and elaborate learning" | **PROVES** | Slide questions plus Teacher Tips. |

### DEVELOPING / IMPROVEMENT NEEDED
Deficit language including *"uses verbal and written communication characterized by inaccurate grammar; written communication that has inaccurate spelling, grammar..."* — professionally produced CI materials are a straightforward defence on the written half.

**A gap the rubric exposes that my dimension-level pass missed:** nothing in 2.3 at any level rewards translation or language scaffolding, so CI's Spanish toggle earns nothing here directly — its value is in 2.4 and 1.3. Don't spend the ELD story on 2.3.

**CI ceiling on 2.3: solid Proficient, four of five bullets PROVES.** This is CI's most fully-covered Proficient row in Domain 2.

---

## 2.4 Differentiation
> *The teacher differentiates instruction, aligning methods and techniques to diverse student needs.*
> Standards basis 1C, 1F, 2A, 2B, 2C, 3C, 4A, 5A, 5C, 5D · Sources: conferences; observations/walkthroughs; **classroom artifacts**; student growth processes; **analysis of student data**

### DISTINGUISHED
| Indicator | Verdict | Proof / reasoning |
|---|---|---|
| "Adapts lessons with a **wide variety of instructional strategies** to address individual needs of **all** students" | **SUPPORTS** | Real variety exists across modalities — full ClearLesson, Snap Lesson on one Instructional Block, Skill Builder sheet, ClassCade game. That is four genuinely different strategies against one skill. What's missing is any record of *you choosing among them*, because reteach suggestions don't link to resources. |
| "**Consistently** monitors the quality of student participation **and performance**" | **PROVES** | Live Monitor covers performance at item level per student, continuously; the Participation tab covers participation per lesson. Both halves of the bullet, and "consistently" is provable from the 42-summary, 54-assignment record. |
| "**Always** provides differentiated instructional methods **and content** to ensure students have the opportunity to master what is being taught" | **SUPPORTS** | Content differentiation is real (Levels, Breakouts, **Remediation Breakouts**, Skill Builder vs Full Topic). "Always" needs your log, not CI's. |
| "**Consistently prevents** student confusion or disengagement by addressing learning **and/or social/emotional** needs of all students" | **SUPPORTS** | Note "prevents" — pre-emptive. CI is reactive by design: checkpoint fires, then you respond. The SEL slide is the one genuinely *preventive* instrument, and it covers the social/emotional limb explicitly. Lean on SEL for this bullet. |

### ACCOMPLISHED
| Indicator | Verdict | Proof / reasoning |
|---|---|---|
| "Adapts lessons to address individual needs of all students" | **SUPPORTS** | Identical to the Proficient bullet — the levels are distinguished here only by the surrounding indicators. |
| "**Regularly** monitors the quality of student participation and performance" | **PROVES** | As above. |
| "**Regularly** provides differentiated instructional methods and content" | **SUPPORTS** | As above. |
| "**Proactively minimizes** student confusion or disengagement..." | **SUPPORTS** | SEL again; "proactively" still fights CI's reactive design. |

### PROFICIENT
| Indicator | Verdict | Proof / reasoning |
|---|---|---|
| "Adapts lessons to address individual needs of all students" | **PROVES** | Crystal Analysis produces three named tiers — Intensive Support / Targeted Reteach / Proficient — with the actual students listed, and Small Groups persists them. Verified live: Avery Nicole and Jace Dennis sitting in Intensive Support on 3.6A with a four-item focus list. That is adaptation to individual needs, documented, dated and standard-tagged. Best single artifact in Domain 2. |
| "Regularly monitors the quality of student participation and performance" | **PROVES** | Live Monitor + Participation tab. |
| "Provides differentiated instructional methods and content to ensure students have the opportunity to master what is being taught" | **PROVES** | Snap Lessons are indexed to the exact Instructional Block Crystal Analysis flagged (IB1/IB2/IB3), so method *and* content are targeted at the diagnosed gap. **Caveat that matters:** the click-through doesn't exist — you must name which Snap Lesson or Skill Builder you actually used, or the evidence stops at the diagnosis. |
| "**Recognizes** when students become confused or disengaged **and responds** to student learning or social/emotional needs" | **SUPPORTS** | Recognition is airtight (Live Monitor "Not Started," per-item incorrect lists, SEL). The *response* is the unevidenced half — the same missing action log that caps 2.5. |

### DEVELOPING / IMPROVEMENT NEEDED
*"Provides one-size-fits-all lessons without meaningful differentiation"* — a Crystal Analysis tiering record plus a Small Group roster is close to dispositive against this. Genuinely useful for a teacher contesting a low 2.4.

**CI ceiling on 2.4: strong Proficient — three of four bullets PROVES — and the most credible reach toward Accomplished in the whole product**, gated on you logging which resource you used and what changed.

---

## 2.5 Monitor and Adjust
> *The teacher formally and informally collects, analyzes and uses student progress data and makes needed lesson adjustments.*
> Standards basis 1D, 1F, 2B, 2C, 3B, 4D, 5C, 5D · Sources: conferences; observations/walkthroughs; **classroom artifacts**; student growth processes; **analysis of student data**

This is the dimension the platform was built for. It is also where the rubric's wording is most awkward for CI, and that's worth seeing precisely.

### DISTINGUISHED
| Indicator | Verdict | Proof / reasoning |
|---|---|---|
| "**Systematically gathers input from students** in order to monitor and adjust instruction, activities or pacing to respond to differences in student needs" | **SUPPORTS — and read this carefully** | "Input from students" appears at *every* level of 2.5, including Proficient. CI gathers student *responses* (checkpoints, exit tickets, APK prompts, SEL) systematically and at scale — a reasonable reading of "input." But the rubric's intent leans toward students telling you what they need, not answering your items. Best defence: the APK prompt and the SEL check are student *voice*, not just assessment. Pair them with the checkpoint data and the claim is solid. |
| "Adjusts instruction and activities to maintain student engagement" | **SUPPORTS** | Identical text at Distinguished, Accomplished and Proficient — so the *adjustment* itself is required at all three levels, and CI does not record it. This is the single most consequential gap in the platform: **CI proves you had the data; nothing proves you adjusted.** Log the adjustment. |
| "Uses **discreet and explicit** checks for understanding through questioning **and academic feedback**" | **SUPPORTS** | Explicit checks: PROVES outright — Checkpoints ×3 plus Add CFU for an unplanned check. Discreet checks: Live Monitor is genuinely discreet, since you read item-level correctness without interrupting. "Academic feedback" is the failure — CI has **no student-feedback field at all**. |

### ACCOMPLISHED
| Indicator | Verdict | Proof / reasoning |
|---|---|---|
| "**Utilizes** input from students in order to monitor and adjust instruction, activities **and** pacing..." | **SUPPORTS** | As above. Pacing is real — the filmstrip and progress % plus Pause for Instruction are pacing controls. |
| "Adjusts instruction and activities to maintain student engagement" | **SUPPORTS** | Same missing action log. |
| "**Continually** checks for understanding through **purposeful** questioning and academic feedback" | **SUPPORTS** | "Continually" and "purposeful" are both well served — checkpoints are placed at designed points, not sprinkled. Academic feedback still missing. |

### PROFICIENT
| Indicator | Verdict | Proof / reasoning |
|---|---|---|
| "**Consistently invites input from students** in order to monitor and adjust instruction and activities" | **PROVES** | APK prompt every lesson, SEL check every lesson, checkpoints, exit tickets — invited, captured, dated, per student, across 42 lesson summaries. "Consistently" is exactly what a platform record is good for. |
| "Adjusts instruction and activities to maintain student engagement" | **SUPPORTS** | Required even at Proficient, and still unevidenced by CI. Pause for Instruction and Paused Lessons are the closest thing — a paused lesson is a persisted record that you stopped. Use it. |
| "**Monitors student behavior and responses for engagement and understanding**" | **PROVES** | Live Monitor covers responses (item-level, per student, live) and gives a soft behaviour signal via Not Started / progress. Understanding is the checkpoint and exit-ticket data. Both limbs met. |

### DEVELOPING / IMPROVEMENT NEEDED
*"Sees student behavior but misses some signs of disengagement," "is aware of most student responses but misses some clues of misunderstanding," "generally does not link student behavior and responses with student engagement and understanding."* CI is a strong defence on all three — it is very hard to argue a teacher "missed clues of misunderstanding" when Live Monitor named every student who missed every item and Crystal Analysis grouped them.

**CI ceiling on 2.5: Proficient, provable twice over, with Accomplished blocked by one missing feature.** Build the action log and 2.5 becomes the first dimension where CI credibly reaches Accomplished.

---

---

# 7. DOMAIN 3 — LEARNING ENVIRONMENT

Domain 3 is where the honest answer is mostly "not us." Presenting it that way is the right product decision — the rubric asks about physical space, bodies, supplies and behaviour, and software sees none of it.

## 3.1 Classroom Environment, Routines and Procedures
> *The teacher organizes a safe, accessible and efficient classroom.*
> Standards basis 1D, 4A, 4B, 4C, 4D · Sources: conferences; observations/walkthroughs; **classroom artifacts**; **analysis of student data**

| Designation | Indicator | Verdict | Proof / reasoning |
|---|---|---|---|
| **DIST.** | "Establishes and uses effective routines, transitions and procedures that **primarily rely on student leadership and responsibility**" | **NO HELP** | Student leadership. Nothing in CI. |
| **DIST.** | "**Students take primary leadership** for managing student groups, supplies and/or equipment" | **NO HELP** | — |
| **DIST.** | "The classroom is safe and thoughtfully designed to engage, challenge and inspire students to participate in high-level learning **beyond the learning objectives**" | **NO HELP** | Physical design. |
| **ACC.** | "Establishes and uses effective routines, transitions and procedures that she or he implements **effortlessly**" | **SUPPORTS** (thin) | The one honest hook in 3.1: a consistent 18-slide lesson architecture and a device workflow students run every day *is* a routine, and the persisted Small Groups are named for real routines — "Centers Rotation," "Centers," "Enrichment Block," "Writing Block." That's a classroom artifact showing the routine structure exists. It says nothing about effortlessness. |
| **ACC.** | "**Students take some responsibility** for managing student groups, supplies and/or equipment" | **NO HELP** | — |
| **ACC.** | "The classroom is safe, inviting and organized... accessible to all students" | **NO HELP** | Physical. |
| **PROF.** | "**All** procedures, routines and transitions are clear and efficient" | **SUPPORTS** (thin) | As above — structure only. |
| **PROF.** | "Students actively participate in groups, manage supplies and equipment with very limited teacher direction" | **NO HELP** | — |
| **PROF.** | "The classroom is safe and organized to support learning objectives and is accessible to most students" | **NO HELP** | Physical. |
| **DEV. / IN** | Deficit descriptions (unclear transitions, students depending on the teacher, disorganized/cluttered/unsafe room, students unable to access materials) | **NO HELP** | Nothing in CI speaks to any of it. |

**CI ceiling on 3.1: effectively none.** One thin artifact (Small Group names as routine documentation). **Product decision: keep the help bullets suppressed and say why** — a teacher who tries to argue 3.1 from a software record will lose credibility with the appraiser on the dimensions where they actually have a case.

## 3.2 Managing Student Behavior
> *The teacher establishes, communicates and maintains clear expectations for student behavior.*
> Standards basis 4A, 4B, 4C, 4D · Sources: conferences; observations/walkthroughs; **classroom artifacts**; **analysis of student data**

| Designation | Indicator | Verdict | Proof / reasoning |
|---|---|---|---|
| **DIST.** | "**Consistently monitors behavior subtly**, reinforces positive behaviors appropriately and intercepts misbehavior fluidly" | **SUPPORTS** (very thin) | Only the middle limb. ClassCade Quick Rewards is a per-student positive-reinforcement ledger, and "reinforces positive behaviours appropriately" is arguably evidenced by a coin-gifting record. Subtle monitoring and fluid interception are physical acts. |
| **DIST.** | "**Students and the teacher create, adopt and maintain** classroom behavior standards" | **NO HELP** | Co-created standards. Nothing. |
| **ACC.** | "Consistently encourages and monitors student behavior subtly and responds to misbehavior swiftly" | **SUPPORTS** (very thin) | Encouragement only, via coins. |
| **ACC.** | "**Most students know, understand and respect** classroom behavior standards" | **NO HELP** | — |
| **PROF.** | "**Consistently implements the campus and/or classroom behavior system** proficiently" | **NO HELP** | Decisive: CI *is not* a behaviour system. There is no behaviour standard, incident, or redirection record anywhere in the product. Presenting a coin ledger as a behaviour system to an appraiser is the clearest overclaim risk in the whole platform. |
| **PROF.** | "Most students meet expected classroom behavior standards" | **NO HELP** | — |
| **DEV. / IN** | Deficit descriptions (inconsistent or unfair enforcement, behaviour impeding learning) | **NO HELP** | — |

**CI ceiling on 3.2: none.** Coins reinforce; they do not manage. Keep suppressed.

## 3.3 Classroom Culture
> *The teacher leads a mutually respectful and collaborative class of actively engaged learners.*
> Standards basis 1E, 1F, 3B, 4C, 4D, 5A, 5B, 5D · Sources: conferences; observations/walkthroughs; **classroom artifacts**; **analysis of student data**

This is the one Domain 3 dimension worth arguing, and the SEL record is why.

| Designation | Indicator | Verdict | Proof / reasoning |
|---|---|---|---|
| **DIST.** | "**Consistently engages all students** with relevant, meaningful learning **based on their interests and abilities** to create a positive rapport amongst students" | **SUPPORTS** | "Abilities" is well covered — Crystal Analysis tiering plus Level-differentiated sheets. "Interests" is not: CI holds no interest inventory (the student record has name, ID, grade only). Engagement volume is evidenced by Instructional Minutes and Questions Answered. |
| **DIST.** | "**Students collaborate positively and encourage each other's** efforts and achievements" | **SUPPORTS** | Genuinely arguable, which is unusual for Domain 3. ClassCade Showdown is team play with recorded team outcomes (Blue Team / Red Team / Tie Game across 13 sessions), and **students gift recognition coins to each other** — that is a literal record of students encouraging each other's achievements. Turn-and-Talk prompts structure peer collaboration. This is the best Domain 3 artifact in the product. |
| **ACC.** | "Engages all students with relevant, meaningful learning, **sometimes adjusting lessons based on student interests and abilities**" | **SUPPORTS** | Abilities yes, interests no. |
| **ACC.** | "Students collaborate positively **with each other and the teacher**" | **SUPPORTS** | ClassCade + Turn-and-Talk + the per-student SEL exchange. |
| **PROF.** | "**Engages all students in relevant, meaningful learning**" | **PROVES** | Per-student participation and response records across 42 lesson summaries establish that all students were engaged in the learning, lesson by lesson. The Participation tab is the direct artifact. |
| **PROF.** | "Students work respectfully individually and in groups" | **SUPPORTS** | Small Groups + ClassCade team records show the grouping happened; "respectfully" is observed. |
| **DEV. / IN** | *"Students are sometimes disrespectful of each other"* / *"disrespectful of each other and of the teacher"*; few students engaged | **SUPPORTS** | The dated per-student SEL record (Happy / Normal / Sad) is real evidence about classroom climate over time — the closest thing in CI to a culture measure, and a reasonable defence against a low 3.3. |

**CI ceiling on 3.3: Proficient, with a genuine reach at the Distinguished peer-encouragement bullet via ClassCade coin-gifting.** Of the three Domain 3 dimensions, this is the only one to make claims about.

---

# 8. DOMAIN 4 — PROFESSIONAL PRACTICES AND RESPONSIBILITIES

## 4.1 Professional Demeanor and Ethics
> *The teacher meets district expectations for attendance, professional appearance, decorum, procedural, ethical, legal and statutory responsibilities.*
> Standards basis 6B, 6C, 6D · Sources: conferences; observations/walkthroughs; classroom artifacts; analysis of student data; **daily interaction with others**

| Designation | Indicator | Verdict | Proof / reasoning |
|---|---|---|---|
| **DIST.** | "Behaves in accordance with the **Code of Ethics and Standard Practices for Texas Educators**" | **NO HELP** | Identical text at Distinguished, Accomplished, Proficient and Developing. Not a software matter. |
| **DIST.** | "**Models all professional standards** (attendance, professional appearance and behaviors) **across the campus and district**" | **NO HELP** | — |
| **DIST.** | "**Advocates for the needs of all students** in the classroom **and campus**" | **SUPPORTS** (thin) | The one defensible thread in 4.1: bringing per-student mastery data to a campus conversation about an underserved group *is* advocacy, and Crystal Reports produces exactly that evidence. Weak but not nothing. |
| **ACC.** | Code of Ethics / "Models all professional standards **within the classroom**" / "Advocates for the needs of all students in the classroom" | **NO HELP** / **NO HELP** / **SUPPORTS** (thin) | As above. |
| **PROF.** | Code of Ethics / "**Meets** all professional standards" / "Advocates for the needs of students in the classroom" | **NO HELP** / **SUPPORTS** (very thin) | "Meets professional standards (e.g. attendance…)" — a continuous instructional record (203 lessons completed, 42 summaries, 54 assignments, dated) is circumstantial evidence of reliable practice. Do not lead with it. |
| **DEV.** | Code of Ethics / "Meets **most** professional standards" | **NO HELP** | — |
| **IN** | "**Fails to meet** the Code of Ethics…" / "Meets few professional standards or **violates legal requirements**" | **NO HELP** | — |

**CI ceiling on 4.1: none worth claiming.** Keep the help bullets suppressed. One legitimate use: student-advocacy evidence drawn from Crystal Reports.

---

## 4.2 Goal Setting
> *The teacher reflects on his/her practice.*
> Standards basis 5D, 6A, 6B · Sources: **Goal-setting and professional development plan (GSPD)**; conferences and conversations with the teacher, **including the end-of-year conference**; **analysis of student data**

**Read the Sources line first.** All three admissible evidence sources for 4.2 are things this tool either *is* or *produces*. This is the only dimension in the whole rubric where the SLO Generator is not supporting evidence — it is the artifact.

### DISTINGUISHED
| Indicator | Verdict | Proof / reasoning |
|---|---|---|
| "**Consistently sets, modifies and meets** short- and long-term professional goals based on self-assessment, reflection, **peer and supervisor feedback, contemporary research** and analysis of student learning" | **SUPPORTS** | Covered: sets (BOY goal + growth targets), modifies (MOY revision, unlock/relock), meets (EOY met-target count), self-assessment (the 16-dimension self-rating), supervisor feedback (the appraiser-approval checkbox gating Accept & Lock), analysis of student learning (Crystal Reports + the SLO's own BOY/MOY/EOY arc). **Not covered: peer feedback and contemporary research** — no peer or research surface exists. Six of eight limbs, which is a strong Distinguished claim with two named holes. |
| "Implements **substantial changes in practice** resulting in **significant improvement in student performance**" | **SUPPORTS** | Second limb PROVES — the EOY Analysis Report gives students-met-target and average full-year growth, which is exactly documented improvement in student performance. First limb is the recurring hole: nothing in CI records a *change in practice*. Same missing action log that caps 2.5. |

### ACCOMPLISHED
| Indicator | Verdict | Proof / reasoning |
|---|---|---|
| "Sets **some** short- and long-term professional goals based on self-assessment, reflection, peer and supervisor feedback, contemporary research and analysis of student learning" | **SUPPORTS** | Same six-of-eight. |
| "**Meets all professional goals resulting in improvement in practice and student performance**" | **SUPPORTS** | Student performance PROVES (EOY report). "Improvement in practice" needs your own reflection note. |

### PROFICIENT
| Indicator | Verdict | Proof / reasoning |
|---|---|---|
| "**Sets short- and long-term professional goals based on self-assessment, reflection and supervisor feedback**" | **PROVES** | Every element is a built feature and nothing extra is required: short-term = MOY checkpoints, long-term = the year-long SLO, self-assessment = the rubric self-rating across 16 dimensions, reflection = per-dimension evidence and notes, supervisor feedback = the appraiser-approval gate on Accept & Lock. Peer feedback and contemporary research drop out at this level, so **CI closes this bullet completely.** The single cleanest PROVES in the entire 274-bullet rubric. |
| "Meets all professional goals resulting in improvement in practice and student performance" | **SUPPORTS** | EOY report covers student performance; practice improvement is your note. |

### DEVELOPING / IMPROVEMENT NEEDED
"Sets **short-term** goals based on self-assessment" (Dev) → "Sets **low or ambiguous** goals **unrelated to student needs or self-assessment**" (IN). A locked SLO with per-student growth targets derived from BOY data is close to dispositive against "ambiguous goals unrelated to student needs." Worth saying to teachers plainly: completing the BOY wizard is, on its own, evidence against an Improvement Needed on 4.2.

**CI ceiling on 4.2: Proficient outright, with a strong Distinguished claim on the first bullet.** Best dimension in Domain 4 by an enormous margin, and the strategic justification for including Domain 4 in the tool at all. Two additions would take it to a defensible Distinguished: a **peer-feedback field** and a **"changes I made to my practice" log** — and the latter is the same build that unblocks 2.5, 2.4, 2.1 and 1.2.

---

## 4.3 Professional Development
> *The teacher enhances the professional community.*
> Standards basis 3A, 6A, 6B, 6C · Sources: **GSPD**; conferences including the end-of-year conference; analysis of student data; **daily interaction with others**

| Designation | Indicator | Verdict | Proof / reasoning |
|---|---|---|---|
| **DIST.** | "**Leads colleagues** collaboratively in and **beyond the school** to identify professional development needs through **detailed data analysis** and self-reflection" | **SUPPORTS** (thin) | Only the "detailed data analysis" instrument. Crystal Reports domain- and standard-level breakdowns are a legitimate basis for identifying a PD need. The leading, the colleagues and the beyond-school reach are all absent. |
| **DIST.** | "Seeks resources and collaboratively fosters faculty knowledge and skills" | **NO HELP** | — |
| **DIST.** | "Develops and fulfills the school and district improvement plans through **professional learning communities**, grade- or subject-level team leadership, committee leadership…" | **NO HELP** | CI has no PLC or collaboration surface. |
| **ACC.** | "Leads colleagues collaboratively **on campus** to identify professional development needs through self-reflection" | **SUPPORTS** (thin) | As above. |
| **ACC.** | "Fosters faculty knowledge and skills in support of the school improvement plan through PLCs, team leadership, committee membership…" | **NO HELP** | — |
| **PROF.** | "**Collaboratively practices in all scheduled professional development activities**, campus PLCs, grade- or subject-level team membership, committee membership or other opportunities" | **NO HELP** | Decisive. CI has no PD library, no completion record and no PLC surface. It cannot help a teacher meet the *expected* level. |
| **DEV. / IN** | "Engages in **most**/**few** scheduled professional development activities…" | **NO HELP** | — |

**CI ceiling on 4.3: none.** The Getting Started video and Quick Start Guide are product onboarding, not professional development, and presenting them as PD would be an overclaim. Keep suppressed. *Product note:* a PD-completion record tied to Crystal Reports-identified needs would be a real 4.3 feature, and the dashboard prototype's "ClearK12 PD site" link is the seed of it.

---

## 4.4 School Community Involvement
> *The teacher demonstrates leadership with students, colleagues, and community members in the school, district and community through effective communication and outreach.*
> Standards basis 2A, 2B, 4A, 4D, 5B, 6B, 6C, 6D · Sources: conferences including the end-of-year conference; **classroom artifacts**; **student data**; **daily interaction with others**

| Designation | Indicator | Verdict | Proof / reasoning |
|---|---|---|---|
| **DIST.** | "**Systematically contacts parents/guardians** regarding students' academic **and social/emotional** growth **through various methods**" | **NO HELP** — *but note* | CI has no family communication channel. However it produces the two things such a contact would be *about*: per-student academic growth (Crystal Reports, EOY report) and social/emotional signal (the SEL record). Crystal Analysis also carries an unpopulated **"Parent"** field — worth checking whether that's a dormant channel or vestigial. If real, this dimension changes. |
| **DIST.** | "**Initiates** collaborative efforts that enhance student learning and growth" | **NO HELP** | — |
| **DIST.** | "**Leads** students, colleagues, families and community members toward reaching the mission, vision and goals of the school" | **NO HELP** | — |
| **ACC.** | "Systematically contacts parents/guardians…" | **NO HELP** | — |
| **ACC.** | "**Joins** colleagues in collaborative efforts that enhance student learning and welfare" | **SUPPORTS** (thin) | The Assignment List's **District** and **School** tabs mean campus- or district-pushed assignments leave a record that you participated in a shared initiative. Thin, but it is a genuine classroom artifact of joining a collective effort. |
| **ACC.** | "**Clearly communicates** the mission, vision and goals of the school…" | **NO HELP** | — |
| **PROF.** | "**Contacts parents/guardians regularly** regarding students' academic and social/emotional growth" | **NO HELP** | Required at the expected level, zero coverage. |
| **PROF.** | "**Actively participates in all school outreach activities**" | **NO HELP** | — |
| **PROF.** | "Communicates the mission, vision and goals of the school to students, colleagues, parents and families" | **NO HELP** | — |
| **DEV.** | "Contacts parents/guardians in accordance with campus policy" / "Attends most required school outreach activities" / "Communicates school goals…" | **NO HELP** | — |
| **IN** | "Contacts parents **generally about disciplinary matters**" / "Attends few required school outreach activities" | **NO HELP** | — |

**CI ceiling on 4.4: effectively none.** One thin artifact (District/School assignment participation). *Highest-leverage finding here:* a **parent-facing growth summary** would move 4.4 from zero to a Proficient claim in a single feature, because it would satisfy "contacts parents/guardians regularly regarding students' academic and social/emotional growth" — and CI already holds both the academic and the social/emotional data. Chase down whether the Crystal Analysis "Parent" field is live.

---

# 9. All 16 dimensions — consolidated

## Coverage at the expected (Proficient) level

| Dimension | Proficient bullets | PROVES | SUPPORTS | NO HELP |
|---|---|---|---|---|
| 1.1 Standards & Alignment | 8 | 5 | 2 | 1 |
| 1.2 Data & Assessment | 3 | 2 | 0 | 1 |
| 1.3 Knowledge of Students | 2 | 1 | 1 | 0 |
| 1.4 Activities | 4 | 2 | 1 | 1 |
| 2.1 Achieving Expectations | 4 | 1 | 2 | 1 |
| 2.2 Content Knowledge | 5 | 2 | 1 | 2 |
| 2.3 Communication | 5 | 3 | 2 | 0 |
| 2.4 Differentiation | 4 | 3 | 1 | 0 |
| 2.5 Monitor & Adjust | 3 | 2 | 1 | 0 |
| 3.1 Environment & Routines | 3 | 0 | 1 | 2 |
| 3.2 Managing Behavior | 2 | 0 | 0 | 2 |
| 3.3 Classroom Culture | 2 | 1 | 1 | 0 |
| 4.1 Demeanor & Ethics | 3 | 0 | 1 | 2 |
| **4.2 Goal Setting** | **2** | **1** | **1** | **0** |
| 4.3 Professional Development | 1 | 0 | 0 | 1 |
| 4.4 School Community | 3 | 0 | 0 | 3 |

**Strongest Proficient rows:** 1.1 (5 PROVES), 2.3 and 2.4 (3 each). **Dead rows:** 3.2, 4.3, 4.4 — zero PROVES, zero SUPPORTS between them on 6 of 7 bullets.

## The six gaps, now with full rubric citations

| Rank | Gap | Dimensions hit | Proficient-level bullets blocked | Note |
|---|---|---|---|---|
| **1** | **Action / change-in-practice log** | 2.5, 2.4, 2.1, 1.2, 4.2 | 3 | Now spans five dimensions across three domains, including the "improvement in practice" limb of 4.2. Still the cheapest high-value build in the product. |
| **2** | **Student-facing view** (self-monitor, goal-setting, own progress, data shared with students) | 2.1, 1.2, 1.4, 3.1 | 1 | The structural ceiling-breaker. Blocks ~14 Distinguished/Accomplished bullets. |
| **3** | **Feedback to students / families** | 1.2, 2.5, 4.4 | 3 | Required at Proficient in all three. The single most-cited absent capability in the rubric. A parent-facing growth summary would close the 4.4 limb and part of 1.2 at once. |
| **4** | **Unit / course construct** | 1.1 | 1 | "Fit into the broader unit and course objectives" is required at Proficient; CI has no unit object. Also blocks "lesson closure." |
| **5** | **Misconception library** | 2.2, 2.1, 2.3 | 1 | Required at Proficient in 2.2. Prototype exists. |
| **6** | **Cross-discipline linkage** | 1.1, 2.2 | 1 | Required at Proficient in 2.2 and Accomplished in 1.1. Cheap to add as a metadata field. |

## What this means for the product

**1. Lead with 4.2 Goal Setting, not 2.5 Monitor & Adjust.** The instinct is to lead with Monitor & Adjust because that is the product's identity. But **4.2 Proficient is the only bullet in all 274 that CI closes completely and unaided**, and all three of 4.2's admissible evidence sources — the GSPD, the end-of-year conference, and analysis of student data — are things this tool itself produces. That is the strongest honest claim available anywhere in the rubric.

**2. Rewrite the ceiling language.** The rubric tab currently says "Accomplished and Distinguished require students to drive their own learning." Correct, but under-sold. It should say: *these levels require student-centred evidence, which CI does not currently produce — here is specifically what you need to add.* Per dimension, that list is now known (§5–§8).

**3. The per-dimension content can now be written from evidence rather than intuition.** Every "How Crystal Instruction helps" bullet can cite the designation and indicator it serves; every "Watch for" caveat can name the exact bullet CI fails. Not yet done — see §10.4.

**4. Five dimensions should carry no product claims at all** — 3.1, 3.2, 4.1, 4.3, 4.4. All five are now gated in `slo-generator.html`. 4.4 was gated *as a result of this analysis*: every one of its Proficient indicators scored NO HELP, and its former "Curriculum Connect" bullet mapped to no 4.4 indicator at any level. **Do not re-add help bullets to these five without a descriptor citation.**

**5. Two claims to retire, one to add.**
- *Retire:* any implication that CI supports cross-discipline integration (required at Proficient in 2.2, Accomplished in 1.1 — zero coverage) or feedback to students (required at Proficient in 1.2, 2.5 and 4.4 — zero coverage). Neither is acknowledged anywhere in the product today.
- *Add:* **2.1 Distinguished's "evidence that all students demonstrate mastery."** Accomplished and Proficient both settle for "most." Per-student exit-ticket data is exactly that evidence, making this the one place in Domains 2–3 where CI can carry a teacher a full level above Proficient on a bullet's own merits. No marketing material mentions it.

**6. Highest-value single unknown:** the **"Parent" field on the Crystal Analysis header**, unpopulated in the demo tenant. If it is a live family-communication channel, 4.4 goes from zero to a Proficient claim and the feedback gap (#3 above) gets materially cheaper. See §10.2.

---

## 10. Open items — read before relying on this document

Three of the verdicts above rest on things I inferred rather than observed. They are flagged here rather than buried.

### 10.1 The ceiling finding rests on an unverified negative — highest priority
The governing conclusion in §4 — that CI structurally caps a teacher at Proficient — depends on there being **no student-facing progress or goal-setting view**. That was inferred from the teacher side. **No student login was ever performed.** If a student view exists with progress, goals or self-assessment, verdicts flip on roughly **14 Distinguished/Accomplished bullets**, specifically:

- 2.1 Distinguished: "opportunities for students to self-monitor and self-correct", "systematically enables students to set goals for themselves and monitor their progress over time"
- 2.1 Accomplished: "establishes systems where students take initiative of their own learning and self-monitor"; 2.1 Proficient: "provides students opportunities to take initiative of their own learning"
- 1.2 Distinguished: "shares… data **with students** to engage them in self-assessment… and track their own progress"
- 1.4 Distinguished/Accomplished: student goal-setting, ownership and accountability bullets
- 3.1: the student-leadership limbs

**Action:** log in as a student and check for any progress, history or goal surface. This single check either confirms the document's central claim or overturns a meaningful chunk of it.

### 10.2 Evidence cited from screens never opened
The **Participation** tab of the Lesson Summary was used as proof for **2.4 Proficient** ("regularly monitors the quality of student participation and performance") and **3.3 Proficient**. Only the tab *name* was ever observed — the tab was never opened. The same applies to the **APK**, **Checkpoints** and **Exit Ticket** sub-tabs of the Lesson Summary report, which are referenced throughout. Treat those specific verdicts as inference pending a look.

Also unopened or unresolved:
- **The "Parent" field on the Crystal Analysis header** — present but unpopulated in the demo tenant. If it is a live family-communication channel, **4.4 moves from zero to a Proficient claim** and gap #3 in §9 gets materially cheaper. Highest-value single unknown after §10.1.
- **Spanish translation depth** — the EN/ES toggle was verified on the *learning target* only. Whether full-lesson translation exists affects 1.1 "appropriate for diverse learners" and 2.3.
- **ClearSheets `Level` filter values** — the accordion would not expand without a subject selected, so the actual levels are unknown. Affects 1.1 and 2.4 "appropriate for diverse learners".
- **Crystal Reports `Preferences`** — band values are visible on the page (100–85 / 85–70 / 70–50 / <50) but the editor was never opened, so teacher-editability is assumed. Affects 2.1 "sets academic expectations".
- **Curriculum Connect population** — verified **empty** for Eureka Grade 3. Other providers unchecked. Affects the 1.1 claim about district-program alignment.

### 10.3 Rubric currency and local variants
- The rubric used is rev **2/10/2022**; it has not been confirmed as the current revision.
- teachfortexas.org lists an **"Alt Domain 1 Rubric"** for districts using alternative lesson-internalization assessment. If Crystal's districts use it, **the entire Domain 1 analysis — CI's strongest domain — does not apply to them.** Worth confirming early.
- Districts may locally modify T-TESS. Everything here is against the state rubric.

### 10.4 Product writing task not yet done
The 11 dimensions that still carry "How Crystal Instruction helps" bullets in `slo-generator.html` were written from the **earlier dimension-level pass**, before the verbatim rubric was read. They are not wrong, but they are not yet citation-grounded, and they don't reflect this document's findings — notably that 1.1's standout is vertical alignment, that 4.2 is the cleanest claim in the product, and that cross-discipline integration, feedback-to-students and the missing unit construct are all **Proficient-level** failures. Porting §9 into the tab's per-dimension content is a writing pass, not research.

---

## 11. File map

All paths relative to `~/Documents/Claude/ttess-slo/`.

| File | What it is |
|---|---|
| `ttess-rubric-verbatim.txt` | TEA rubric, verbatim, all 16 dimensions / 274 bullets. Extracted with PyMuPDF (`import fitz`) — note there is no `pdftotext`/poppler on this machine, and WebFetch cannot read the PDF directly (returns binary) though it does save it to disk. |
| `ttess-descriptor-level-domains-2-3.md` | Source document for §4 (part), §6, §7, §9 (part) — the TIA 35%. |
| `ttess-descriptor-level-domains-1-4.md` | Source document for §4 (part), §5, §8, §9 — Domains 1 & 4 plus the consolidated tables. |
| `slo-generator.html` | The T-TESS / SLO Generator prototype. Rubric tab now carries all 16 dimensions, a scoped TIA average, gated help bullets, and the T-TESS 2 band. |
| `crystal-ttess-alignment.md` | The earlier dimension-level crawl report. Superseded where it disagrees with this document. |

**Related, outside this folder:** the platform itself is at `cs.cleark12.com` and now **requires login** — the demo account is no longer open-access. A live teacher session exists in the user's real Chrome, so use the Claude-in-Chrome tools rather than a fresh browser. Direct URL navigation bounces to the dashboard; navigate by clicking the sidebar.

---

## 12. Recommended next steps, in order

1. **Verification crawl (~15 min).** Student login (§10.1) + the four Lesson Summary sub-tabs (§10.2) + the Crystal Analysis Parent field. Confirms or overturns the central finding and retires the citations that can't currently be stood behind.
2. **Confirm rubric currency and whether the Alt Domain 1 Rubric is in play** (§10.3). Cheap, and it gates whether the strongest domain's analysis applies.
3. **Port §9 into the product's per-dimension content** (§10.4). Writing pass.
4. **T-TESS 2** (§3). Fetch the pilot rubric, map the 16→12 consolidation, re-run the evaluation against the new indicators, and test whether "your evidence maps forward" survives contact with the actual bullets.
