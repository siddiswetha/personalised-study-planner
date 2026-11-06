# 03 — One-Page Spec

## Personalised Study Planner

---

## Product

A personalised study planner that turns a student's exam dates, syllabus, difficulty, and real available time into a day-by-day plan they can actually follow.

**User:** A student preparing for exams.
**Problem:** Limited study time is spent on the wrong topics — comfortable, low-weight topics first; high-weight, weak topics last.
**Primary metric:** Syllabus coverage completed before the exam + self-reported preparedness.

---

## Inputs

The student provides these five things. The planner cannot make a good plan without them.

| # | Input | Example (EXAMPLE) | Required? |
|---|-------|-------------------|-----------|
| 1 | Exam dates | Subject A: 10 June; Subject B: 12 June | Yes |
| 2 | Syllabus topics + weightage | Topic 1: 40% of marks; Topic 2: 25% | Yes |
| 3 | Self-rated difficulty | Easy / Medium / Hard, per topic | Yes |
| 4 | Available hours per day | 3 hours on weekdays, 5 on weekends | Yes |
| 5 | Fixed commitments | Classes 9–12, part-time job Sat–Sun | Yes |

If weightage is not known, the student estimates it or marks it "unknown". The plan must say clearly when weightage was estimated, not present a guess as a fact.

---

## Output

A day-by-day plan, from today until the last exam. For each day, the plan shows:

| Field | What it means | Example (EXAMPLE) |
|-------|---------------|-------------------|
| Date | The day the plan covers | Monday 12 May |
| Topic | What to study | Subject A — Topic 1 |
| Goal | What "done" looks like for that session | "Explain Topic 1 in your own words and solve 5 practice questions" |
| Recall task | A short test from memory, not re-reading | "Write down the 4 key steps from memory, then check" |
| Break | When to stop and rest | "10-minute break after 50 minutes" |

The plan must also show, at the top:

- Total days left
- Coverage so far — what % of the syllabus is planned and completed
- The next exam date

---

## Rules the plan must follow

1. **Never over-allocate.** Total planned study time on any day must be less than or equal to the student's available hours that day. A plan that breaks this rule fails automatically.
2. **Cover 100% of high-weight topics** before the exam. "High-weight" means the topics that carry the most marks — defined in the eval rubric in `docs/04-eval.md`.
3. **Spaced repetition is present.** A topic is revisited after a gap, not studied once and never seen again.
4. **The day before an exam is revision-only.** No new topics on that day.
5. **Breaks are mandatory.** No study block runs without a break.
6. **The student can override any day.** The plan is a suggestion, not an order.

---

## In scope

- Planning a study schedule from the five inputs above.
- Rescheduling when life changes — a missed day, illness, a new commitment, or a "lighter day" request.
- Showing coverage and progress clearly.
- One-tap "lighter day" reschedule (see `docs/07-risks-guardrails.md`).

## Out of scope

- No teaching of subject content. The planner does not explain topics.
- No medical or mental-health advice.
- No counselling.
- No guarantee of marks or exam results.
- No automatic sharing of a student's plan, timetable, or results with anyone else.
- No exam predictions — the planner does not guess exam questions.

---

## User journey — simple version

1. **Student enters inputs** — exam dates, topics and weightage, difficulty, hours, commitments.
2. **Planner generates a plan** — day by day, with topic, goal, recall task, and break.
3. **Student reviews the plan** — checks it fits their real day, and overrides any day they want to change.
4. **Student follows the plan** — marks each day done, partly done, or missed.
5. **Life happens** — the student taps "lighter day" or reschedules. The planner moves topics, keeps high-weight coverage, and never over-allocates.
6. **Before the exam** — the last day is revision-only. The student can see coverage and how prepared they feel.

---

## Success criteria

The spec is met when:

- [ ] A plan can be generated from the five inputs, with no missing days.
- [ ] Every day fits inside the student's available hours.
- [ ] 100% of high-weight topics are covered before the exam.
- [ ] Spaced repetition appears in the plan.
- [ ] The day before each exam is revision-only.
- [ ] The student can override any day and request a lighter day.
- [ ] The plan states clearly that it is a planning aid, not a counsellor, and gives no medical advice.

---

## Non-goals for this version

- No mobile app build is required for this academic project. A chat tool + documents + test sets is enough to design, test, and prove the product.
- No integration with school systems or exam boards.
- No social features, leaderboards, or comparison with other students.
