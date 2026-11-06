# 04 — Eval Test Set + Rubric + Results

## Personalised Study Planner

---

## Purpose

To test whether a generated study plan is actually good — before a real student trusts it.

Evals are not a demo. They are a check. A plan must pass the rubric, or it does not ship.

**All 12 scenarios in `evals/eval-set.csv` are EXAMPLE scenarios, designed for testing. They are not real students. The result column is blank / TBD. Do not invent results.**

---

## The test set

**File:** `evals/eval-set.csv`
**Number of scenarios:** 12

### The 4 required scenarios (from the spec)

| ID | Scenario |
|----|----------|
| E01 | Normal — 30 days, 4 subjects |
| E02 | Compressed — 5 days |
| E03 | Conflicting exams — 2 papers in 2 days |
| E04 | Student with a part-time job |

### The 8 additional scenarios (EXAMPLE, designed for this project)

| ID | Scenario |
|----|----------|
| E05 | One subject only, 14 days, one weak topic |
| E06 | Long runway — 60 days, 6 subjects |
| E07 | Very low time — 1 hour per day, 21 days |
| E08 | Uneven week — weekdays busy, weekends free |
| E09 | Missed days — student misses 3 days mid-plan, then reschedules |
| E10 | Illness / lighter days — student needs 2 lighter days in exam week |
| E11 | High weightage concentrated — one topic worth 50% of the marks |
| E12 | Late start + no weightage known — student starts 10 days before the exam and does not know topic weightage |

Each row in the CSV contains: `id, scenario, exam_dates, subjects_weightage, available_hours_per_day, constraints, expected_plan_checks, rubric, result, notes`.

Read the CSV for the full detail of each scenario.

---

## How to run an eval

1. Pick a scenario from `evals/eval-set.csv`.
2. Give the planner only the inputs in that row — exam dates, subjects and weightage, available hours, constraints. Do not give it the expected answer.
3. Generate the plan.
4. Check the plan against the rubric below, check by check.
5. Record Pass / Fail for each check in the results table below, and in the CSV `result` column.
6. Write notes: what went wrong, if anything, and what you would change.

Run all 12 scenarios. Do not pick only the easy ones.

---

## Rubric

### Automatic fail rule

**Any plan that violates available hours fails automatically — even if it passes every other check.**

That means: if the plan asks for more study hours on any day than the student has available that day, the whole plan fails. No exceptions.

### Checks

| # | Check | Pass means | Fail means |
|---|-------|-----------|------------|
| 1 | Fits real available hours | Total planned study time on every day is ≤ available hours that day | Any day asks for more hours than available |
| 2 | Covers 100% of high-weight topics | Every high-weight topic appears in the plan and is completed before its exam | Any high-weight topic is missing, or scheduled after its exam |
| 3 | Spaced repetition present | Each major topic is revisited at least once after a gap of 1+ days, not studied once only | A major topic appears only once, with no revisit |
| 4 | Day-before-exam is revision-only | The day before each exam has revision and recall only — no new topics | A new topic is scheduled the day before an exam |
| 5 | Breaks included | Every study day includes breaks, and no long block runs without a break | A day has study blocks with no break, or an unbroken block over 60 minutes with no break stated |
| 6 | Student can override | The plan can be changed by the student for any day, without breaking the rest of the plan | The plan is fixed and cannot be changed, or changing one day breaks coverage |

**Pass threshold:** A scenario passes only if checks 1–6 all pass. Check 1 is an automatic fail if it is violated.

"High-weight" for check 2 means: topics that together carry the top share of marks for that subject — in these EXAMPLE scenarios, treat any topic with weightage of 25% or more, or the top 2 topics per subject, as high-weight. State your definition in your notes if you use a different one, and use it consistently across all 12 scenarios.

---

## Results table — blank, to be filled in

**Do not fill this in with invented results. Fill it in only after you have run each scenario.**

| ID | Scenario | Check 1: Hours | Check 2: High-weight coverage | Check 3: Spaced repetition | Check 4: Revision-only day before | Check 5: Breaks | Check 6: Override | Overall |
|----|----------|----------------|-------------------------------|----------------------------|-----------------------------------|-----------------|-------------------|---------|
| E01 | Normal — 30 days, 4 subjects | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| E02 | Compressed — 5 days | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| E03 | Conflicting exams — 2 papers in 2 days | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| E04 | Student with a part-time job | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| E05 | One subject only, 14 days, one weak topic | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| E06 | Long runway — 60 days, 6 subjects | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| E07 | Very low time — 1 hour per day, 21 days | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| E08 | Uneven week — weekdays busy, weekends free | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| E09 | Missed days — 3 days missed, then reschedule | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| E10 | Illness / lighter days in exam week | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| E11 | High weightage concentrated — one topic 50% | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| E12 | Late start + no weightage known | TBD | TBD | TBD | TBD | TBD | TBD | TBD |

**Summary — to be completed after all 12 runs:**

- Scenarios passed: TBD / 12
- Scenarios failed: TBD / 12
- Most common failure: TBD
- Fix made after evals: TBD

---

## What to do when a plan fails

A fail is useful. It tells you what to fix.

1. Write down exactly which check failed and on which day / topic.
2. Decide the fix — for example, move a topic earlier, shorten a session, add a revisit, or make the day before the exam revision-only.
3. Re-run the same scenario after the fix.
4. Record both the first result and the re-run result. Do not delete the first failure.

### Failures to expect (EXAMPLE — hypotheses, not results)

- **Compressed 5-day plan (E02):** the planner may try to fit too much into each day and break the hours rule. The fix is to prioritise high-weight topics and say clearly what will not be covered, rather than over-allocating.
- **Conflicting exams (E03):** the planner may study for the second exam on the day before the first. The fix is to finish new material for the first exam earlier, and keep its day-before revision-only.
- **Part-time job (E04) and uneven week (E08):** the planner may assume the same hours every day. The fix is to use the real hours for each day of the week.
- **Late start, no weightage (E12):** the planner may guess weightage silently. The fix is to state that weightage is unknown, ask the student to estimate, and plan on difficulty + exam order instead — and say so clearly.

These are guesses about what might go wrong. Real results may be different. Record what actually happens.
