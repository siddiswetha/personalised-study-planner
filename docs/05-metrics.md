# 05 — Metrics Plan

## Personalised Study Planner

---

## Purpose

To decide, in advance, what "working" means — so we do not judge the product by feelings after the pilot, but by numbers we agreed on before it.

Four kinds of metric are tracked: task success, quality, cost per success, and harm.

**Primary metric:** syllabus coverage completed before the exam + self-reported preparedness.

All targets below are proposed targets to test in the pilot, not results. Record real results in the tables provided, and only after the pilot.

---

## 1. Task success — did the plan get made, and was it followed?

| Metric | Definition | How to measure | Proposed target (to test) |
|--------|------------|----------------|---------------------------|
| Plan generation success rate | % of plan requests that produce a complete plan with no missing days | Count: complete plans / all plan requests | TBD — set after first test run |
| Plan adherence after 7 days | % of planned study sessions the student actually completed in the first 7 days | Student marks each day done / partly done / missed; adherence = done sessions / planned sessions | TBD — set after pilot week 1 |
| Coverage % | % of the syllabus completed before the exam; high-weight coverage tracked separately | Topics marked complete / all topics; high-weight topics marked complete / all high-weight topics | 100% of high-weight topics; overall coverage as high as the student's hours allow |
| Reschedule rate | % of planned days that were rescheduled | Rescheduled days / all planned days | TBD — track, do not punish; a high rate may mean the plan did not fit real life |
| Reschedule reason | Why days were rescheduled | Student picks a reason each time: illness, work, family, tired, other | Track the top 3 reasons; fix the most common one first |

### Adherence — a simple example (EXAMPLE)

If a student had 14 sessions planned in 7 days and completed 10, adherence is 10 / 14 = 71%. That is a number to record, not a judgement. The question is why the other 4 were missed — and whether the plan or the student's life needs to change.

### Results table — blank, to be filled in after the pilot

| Metric | Pilot result | Target met? | Notes |
|--------|--------------|-------------|-------|
| Plan generation success rate | TBD | TBD | TBD |
| Plan adherence after 7 days | TBD | TBD | TBD |
| Coverage % (overall) | TBD | TBD | TBD |
| Coverage % (high-weight topics) | TBD | TBD | TBD |
| Reschedule rate | TBD | TBD | TBD |
| Top reschedule reasons | TBD | TBD | TBD |

---

## 2. Quality — was the plan good?

| Metric | Definition | How to measure | Proposed target (to test) |
|--------|------------|----------------|---------------------------|
| Eval pass rate | % of the 12 eval scenarios that pass all rubric checks | See `docs/04-eval.md` | 12 / 12 before release to a full class |
| Hours-rule violations | Number of plans that ask for more hours than available on any day | Count from evals + pilot plans | 0 — any violation is an automatic fail |
| Self-reported preparedness | How prepared the student feels before the exam | Short survey before the exam: 1–5 scale ("I feel prepared for this exam") + one open question | TBD — compare before / after the plan |
| Plan usefulness rating | How useful the student found the daily plan | Weekly check-in: 1–5 scale + "What was most useful? What was least useful?" | TBD — track weekly, look for the trend |
| Recall task completion | % of recall tasks the student actually did (not just re-reading) | Student marks recall task done / skipped each day | TBD — low recall completion may mean recall tasks are too hard or too long |

### Results table — blank, to be filled in after the pilot

| Metric | Pilot result | Target met? | Notes |
|--------|--------------|-------------|-------|
| Eval pass rate | TBD / 12 | TBD | TBD |
| Hours-rule violations | TBD | TBD | TBD |
| Self-reported preparedness (before exam) | TBD / 5 | TBD | TBD |
| Plan usefulness rating (week 1 / week 2 / final) | TBD | TBD | TBD |
| Recall task completion | TBD | TBD | TBD |

---

## 3. Cost per success — what does a good plan cost?

| Metric | Definition | How to measure |
|--------|------------|----------------|
| Cost per plan | Cost to generate one plan (see `docs/06-cost-latency.md`) | Log cost per generation, by approach (one call vs. weekly) |
| Cost per successful plan | Cost per plan that passes the eval rubric and is followed for 7 days | Total generation cost / number of successful plans |
| Time to generate a plan | Time from request to a complete plan | Measure in seconds, per generation |
| Time to regenerate a plan | Time to produce a revised plan after a reschedule request | Measure in seconds, per regeneration |
| Latency | Time to first output / full plan delivered | Target: < 5 seconds for a regeneration; see `docs/06-cost-latency.md` for the full-plan trade-off |

A cheap plan that no one follows is not a success. Cost per success — not cost per plan — is the number that matters.

### Results table — blank, to be filled in after the pilot

| Metric | Pilot result | Notes |
|--------|--------------|-------|
| Cost per plan | TBD | TBD |
| Cost per successful plan | TBD | TBD |
| Time to generate a plan (median) | TBD | TBD |
| Time to regenerate a plan (median) | TBD | TBD |
| Latency | TBD | TBD |

---

## 4. Harm — what could go wrong for the student?

Harm metrics are tracked even when everything else looks good. A product can have high adherence and still harm a student if the plan is overloading or demotivating.

| Metric | Definition | How to measure | Guardrail |
|--------|------------|----------------|-----------|
| Overload reports | Student says the plan asked for too much, or they felt overwhelmed | Weekly check-in: "Did the plan ask for too much this week?" Yes / No + comment | Max study hours cap; mandatory breaks; one-tap "lighter day" — see `docs/07-risks-guardrails.md` |
| Demotivation / drop-off | Student stops using the plan, or adherence falls sharply | Adherence by week; student stops marking days done | Weekly check-in asks why; do not blame the student — fix the plan |
| Missed high-weight topics | High-weight topics not covered before the exam | Coverage % for high-weight topics | 100% target; if missed, record why |
| Stress / wellbeing flag | Student reports feeling worse, or mentions health / stress problems | Weekly check-in, open question; no medical questions asked | Planner states clearly it is a planning aid, not a counsellor; point the student to real support (see `docs/07-risks-guardrails.md`) |
| Plan-induced guilt | Student feels guilty for missing a day, rather than simply rescheduling | Weekly check-in: "How did you feel when you missed a day?" | Plan language must be kind, not punishing; a missed day triggers a reschedule offer, not a warning |

### Results table — blank, to be filled in after the pilot

| Harm metric | Pilot result | Action taken |
|-------------|--------------|--------------|
| Overload reports | TBD | TBD |
| Demotivation / drop-off | TBD | TBD |
| Missed high-weight topics | TBD | TBD |
| Stress / wellbeing flag | TBD | TBD |
| Plan-induced guilt | TBD | TBD |

---

## How metrics are collected

- **Daily:** student marks each day done / partly done / missed, and marks recall tasks done / skipped.
- **Weekly:** short check-in (see `docs/08-release-portfolio.md`) — adherence, usefulness, overload, preparedness, open feedback.
- **Before the exam:** preparedness survey (1–5) + coverage %.
- **After the exam cycle:** full pilot review — all tables above, completed with real numbers.

Keep the check-in short. If measuring the product becomes a burden, students will stop answering — and then there are no metrics at all.

---

## What we will NOT do

- We will not rank students against each other.
- We will not use marks or grades as the product's success metric — the planner does not control the exam.
- We will not collect health or medical data.
- We will not present a single student's result as proof the product works for everyone.
