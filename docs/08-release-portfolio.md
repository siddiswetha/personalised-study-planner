# 08 — Staged Release + Portfolio Write-up

## Personalised Study Planner

---

## Part A — Staged release plan

### Principle

Release to a few students first, learn from real use, fix what breaks, and only then release to more students.

Do not release to a full class on the strength of a good idea. Release on the strength of pilot data.

---

### Stage 0 — Internal test (before any student)

**Who:** The product manager (you) + 1–2 people who will check the work honestly.

**What to do:**

- Run all 12 eval scenarios in `evals/eval-set.csv` against the rubric in `docs/04-eval.md`.
- Fix every automatic fail (any plan that over-allocates hours).
- Check every guardrail in `docs/07-risks-guardrails.md` — especially the hours cap, mandatory breaks, "lighter day", and the planning-aid statement.

**Gate to Stage 1:** 12 / 12 eval scenarios pass, with 0 hours-rule violations.

**Status:** TBD

### Stage 1 — Pilot with 5 students for one full exam cycle

**Who:** The same 5 students from the research in `docs/02-research-notes.md`, if they agree — or 5 new students across different courses / years.

**How long:** One full exam cycle — from plan creation until the last exam.

**What happens:**

- Each student provides the five inputs (exam dates, topics + weightage, difficulty, hours, commitments).
- Each student receives a weekly plan (see the chosen approach in `docs/06-cost-latency.md`).
- Each student can override any day and tap "lighter day" at any time.

**Human review loop — weekly check-ins:**

Every week, a short check-in with each student. This is the human review loop. It is not optional.

Weekly check-in questions (template):

1. How many planned sessions did you complete this week? (done / partly done / missed)
2. How useful was the plan this week? (1–5)
3. Did the plan ask for too much this week? (Yes / No — and what was too much?)
4. What was most useful? What was least useful?
5. Did you reschedule? Why?
6. How prepared do you feel for your next exam? (1–5)
7. Is there anything the plan should do differently next week?

Keep it short — 10 minutes or less. Record answers in the pilot metrics tables in `docs/05-metrics.md`.

**What to measure in the pilot:**

- Plan adherence after 7 days
- Coverage % — overall and high-weight
- Reschedule rate and reason
- Time to generate / regenerate a plan
- Cost per plan
- Latency (< 5s for regeneration)
- Self-reported preparedness
- Harm signals — overload, demotivation, stress (see `docs/05-metrics.md` and `docs/07-risks-guardrails.md`)

**Gate to Stage 2:** All of the following must be true —

- [ ] Eval pass rate is 12 / 12.
- [ ] Adherence after 7 days is recorded for all 5 students, and the reasons for missed sessions are understood.
- [ ] High-weight coverage reaches 100% before the exam, or every miss is explained and fixed.
- [ ] No unresolved harm signal — no student left feeling overloaded or demotivated without a fix.
- [ ] Weekly check-ins were held every week, and the iteration after week 1 (see Part B) is recorded.

If any gate is not met, stay in Stage 1. Fix the product, and run another cycle.

**Status:** TBD

### Stage 2 — Release to a full class

**Who:** One full class, with the teacher's / institution's agreement.

**What changes at this scale:**

- More students, more subjects, more exam dates — the planner must handle variety, not just the 5 pilot students.
- Support must be ready: a clear way for students to ask for help, report a problem, or ask for a lighter plan.
- Metrics continue weekly. Adherence and coverage are reviewed every week, not at the end.
- The same guardrails apply. Scale does not remove the hours cap, the breaks, or the planning-aid statement.

**What to watch for in Stage 2:**

- Does adherence hold when the product manager is not checking in personally every week?
- Do new failure modes appear — subjects, schedules, or constraints the pilot did not cover?
- Does cost per plan stay acceptable as volume grows?

**Gate to wider release:** Stage 2 data reviewed, with adherence, coverage, cost, and harm all recorded and acceptable. Wider release beyond one class is out of scope for this academic project — record it as a future step, not a claim.

**Status:** TBD

---

### Rollback / pause rules

Pause or roll back if any of the following happens:

- A plan over-allocates hours and reaches a student.
- A student reports feeling overwhelmed and the plan is not fixed within a week.
- A student asks for wellbeing help and receives anything other than the planning-aid statement + a pointer to real support.
- Coverage of high-weight topics falls below target with no explanation.

Pausing is not failure. Shipping a harmful plan is failure.

---

## Part B — Portfolio write-up (Lesson 10.1 style)

This section is the portfolio proof for the project. Complete it with real evidence from the pilot. Do not invent results.

### 1. Research insights

*What we learned from 5 real students — and what it changed.*

**To be completed after the interviews in `docs/02-research-notes.md`.**

| Insight | Evidence (Student A–E) | What it changed in the product |
|---------|------------------------|--------------------------------|
| TBD | TBD | TBD |
| TBD | TBD | TBD |
| TBD | TBD | TBD |
| TBD | TBD | TBD |

### 2. Eval table — 12 scenarios

*The plan was tested before any student trusted it.*

- **Test set:** `evals/eval-set.csv` — 12 EXAMPLE scenarios
- **Rubric:** `docs/04-eval.md`
- **Result:** TBD / 12 passed
- **Automatic fails (hours-rule violations):** TBD
- **Most common failure:** TBD
- **Fix made after evals:** TBD

Copy the completed results table from `docs/04-eval.md` here once it is filled in.

### 3. Before / after plan for one real student (anonymised)

*One student, one real exam cycle — what changed?*

**Student:** Student A / B / C / D / E — anonymised (TBD)
**Course / exams:** TBD
**Exam cycle:** TBD

#### Before — the generic plan they used

Describe, in the student's own words where possible:

- How they planned before: TBD
- What the generic timetable looked like: TBD
- Where it broke: TBD
- Coverage before the exam (if known): TBD
- How prepared they felt (1–5, if known): TBD

#### After — the personalised plan

- What the personalised plan changed: TBD
- Example week (anonymised, with real topics and hours): TBD
- Coverage before the exam: TBD
- Adherence after 7 days: TBD
- How prepared they felt (1–5): TBD
- What the student said about the difference (with permission, in their own words): TBD

**Do not include the student's name, timetable, or syllabus in this section. Anonymise fully.**

### 4. Pilot metrics

*One full exam cycle, 5 students.*

Copy the completed tables from `docs/05-metrics.md` here once the pilot is done.

| Metric | Pilot result |
|--------|--------------|
| Plan adherence after 7 days | TBD |
| Coverage % (overall) | TBD |
| Coverage % (high-weight topics) | TBD |
| Reschedule rate | TBD |
| Top reschedule reasons | TBD |
| Time to generate a plan (median) | TBD |
| Time to regenerate a plan (median) | TBD |
| Cost per plan | TBD |
| Cost per successful plan | TBD |
| Latency (regeneration) | TBD — target < 5s |
| Self-reported preparedness (before exam) | TBD / 5 |
| Overload reports | TBD |
| Demotivation / drop-off | TBD |

### 5. Iteration after week 1 feedback

*What changed after the first week — and why.*

This is the most important part of the portfolio. It shows that the product was tested with real users, that feedback was heard, and that the product changed.

**Week 1 feedback — to be completed after the first weekly check-ins:**

| What students said / what the data showed | Source (check-in / metric) | What we changed | Why |
|-------------------------------------------|----------------------------|-----------------|-----|
| TBD | TBD | TBD | TBD |
| TBD | TBD | TBD | TBD |
| TBD | TBD | TBD | TBD |

**What we deliberately did NOT change — and why:**

| Feedback / request | Why we did not change it |
|--------------------|--------------------------|
| TBD | TBD |

**Result of the change (if known):**

- Adherence in week 2 vs. week 1: TBD
- Coverage trend: TBD
- Student reaction: TBD

---

## What this project proves

When this document is complete — with real interviews, real eval results, a real before / after, real pilot metrics, and a real week-1 iteration — it proves:

1. **You can find a real problem** and show evidence for it, not just an idea.
2. **You can listen to users** and turn what they say into product decisions.
3. **You can write a clear spec** with in-scope and out-of-scope, and rules a plan must follow.
4. **You can test before you ship** — 12 scenarios, a hard fail rule, and no fake results.
5. **You can measure what matters** — success, quality, cost, and harm.
6. **You can release in stages** and stop when the data says stop.
7. **You can learn from feedback** and change the product in week 1, not at the end.

That is the work of an AI Product Manager.
