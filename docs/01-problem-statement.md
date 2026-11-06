# 01 — Problem Statement

## Personalised Study Planner

---

## The problem

Student failure rarely comes from lack of material. It comes from poor allocation of limited study time across subjects with different exam dates, weightage, and personal difficulty.

Generic timetables ignore all three. So students over-study comfortable topics and arrive unprepared in high-weight, weak areas.

### In plain language

A student has, say, 30 days and 4 subjects. One exam is in 10 days and carries 40% of the marks. Another is in 30 days and carries 10%. One topic is easy for this student. Another is very hard.

A generic timetable treats every day and every topic the same. It does not ask which exam is first, which topic matters most, or how hard each topic feels to this student.

The result is predictable: the student spends too much time on what is comfortable, and too little on what is important and difficult. By exam week, the high-weight, weak areas are still unprepared.

---

## Who has this problem?

Students preparing for exams — across different courses and years — who have:

- More than one subject or paper to prepare
- Different exam dates
- Limited hours per day, because of classes, work, family, or other commitments
- Topics they find harder than others

This is not a problem for a student with one exam, unlimited time, and equal confidence in every topic. That student is rare.

---

## Why it matters now

- **Time cannot be recovered.** An hour spent on a low-weight, comfortable topic is an hour that cannot be spent on a high-weight, weak topic.
- **Exams are close together.** Many students face two papers in two days, or several papers in one week. Order matters.
- **Life does not stop for exams.** Part-time jobs, family duties, illness, and travel reduce real study time. A plan that ignores them is a plan that fails on day one.
- **Stress grows when coverage is unclear.** When a student cannot see whether the whole syllabus will be covered in time, worry replaces study.

---

## Evidence

This section is a template for real evidence. Do not fill it with invented numbers or quotes.

### Evidence to collect

| # | Evidence | Source | Status |
|---|----------|--------|--------|
| 1 | Interview notes from 5 students (see `02-research-notes.md`) | Student interviews | TBD — to be collected |
| 2 | Real exam timetables and syllabi, collected with permission | Students in the pilot | TBD — to be collected |
| 3 | Before / after plan for one real student, anonymised | Pilot student | TBD — to be collected |
| 4 | Pilot metrics: adherence after 7 days, coverage %, reschedule rate | Pilot (see `05-metrics.md` and `08-release-portfolio.md`) | TBD — to be collected |
| 5 | Eval results from the 12-scenario test set | `evals/eval-set.csv` and `docs/04-eval.md` | TBD — to be run |

### What counts as evidence here

- What students actually say and do in interviews — recorded in their own words, with permission.
- Real timetables and syllabi — not made-up examples.
- Plans that were actually followed, or not followed — and why.
- Measured coverage and adherence — not a feeling that the plan "seemed good".

### What does NOT count as evidence

- A claim with no source.
- An example scenario labelled EXAMPLE, used for testing — useful, but not proof about real students.
- A quote written by the product manager and presented as if a student said it.

---

## Current alternatives — and why they fall short

| Alternative | What it does | Why it falls short |
|-------------|--------------|--------------------|
| Generic timetable / calendar template | Gives every subject equal time, every day | Ignores exam dates, weightage, and difficulty |
| Studying in syllabus order | Works through topics in the order they appear | The first topic is not always the most important or the most urgent |
| Studying what feels comfortable | Feels productive in the moment | Leaves weak, high-weight areas until it is too late |
| Cramming at the end | Tries to cover everything in the last few days | No time for spaced repetition or recall; high stress, low retention |
| A friend's plan | Copies someone else's schedule | That student's exams, hours, and difficulties are different |

None of these ask the three questions that matter: **When is the exam? How much does it count? How hard is it for this student?**

---

## The product idea

A planner that asks for five inputs and produces one clear output.

**Inputs:**

1. Exam dates
2. Syllabus topics + weightage
3. Self-rated difficulty
4. Available hours per day
5. Fixed commitments

**Output:**

A day-by-day plan with topic, goal, recall task, and break — for every day until the exams.

The plan must:

- Fit inside the student's real available hours — never over-allocate.
- Cover 100% of high-weight topics before the exam.
- Include spaced repetition — revisiting a topic after a gap, not just once.
- Make the day before an exam revision-only — no new topics.

If a plan breaks the available-hours rule, it fails automatically. See `docs/04-eval.md`.

---

## Success looks like

- A student can see, on day one, that the whole syllabus fits in the time they have.
- High-weight, weak topics get time early, with repetition.
- The student follows the plan for at least 7 days, and coverage grows steadily.
- When life changes, the student can reschedule in one tap — "lighter day" — without the whole plan falling apart.
- Before the exam, the student reports feeling prepared, not just busy.

**Primary metric:** syllabus coverage completed before the exam + self-reported preparedness.

---

## What this product is not

- It is not a tutor. It does not teach the subject.
- It is not a counsellor. It gives no medical or mental-health advice.
- It does not guarantee marks. A plan helps a student use time well; it cannot control the exam, the questions, or the result.
- It does not replace the student's judgement. The student can override any day.

---

## Open questions to answer in research

1. How do students currently plan revision, and where does the plan break?
2. What does "a good plan" mean to each student — in their own words?
3. How do students decide what to study when time is short?
4. What happens on a bad day — illness, a missed day, a sudden commitment?
5. How much detail do students want in a daily plan — and how much is too much?
