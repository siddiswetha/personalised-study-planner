# 07 — Risk & Guardrails List

## Personalised Study Planner

---

## Purpose

To name, in advance, what could go wrong for a student — and what the product will do to prevent it, or to limit the harm if it happens.

A plan that is efficient but overloading, demotivating, or blind to real life is not a good product, even if it covers the syllabus.

---

## Risks

### Risk 1 — Overloading plans

**What it is:** The planner asks for more hours, or more topics, than the student can handle in a day — even if the total is technically inside the available hours. For example, 3 hours of hard topics with no real break, back to back.

**Why it matters:** The student burns out, misses the next day, and then falls behind the whole plan. Overload on day one can end the plan by day three.

**Signs:** Low adherence in week 1, overload reports in weekly check-ins, students saying the plan "asked for too much".

### Risk 2 — Demotivating plans

**What it is:** The plan makes the student feel behind, guilty, or hopeless — for example, by showing a large backlog after one missed day, or by using punishing language ("You failed today", "You are 3 days behind").

**Why it matters:** A student who feels guilty stops opening the plan. Demotivation is a product failure, not a student failure.

**Signs:** Adherence falls sharply, the student stops marking days done, or says in a check-in that the plan made them feel worse.

### Risk 3 — Plans that ignore illness / life events

**What it is:** The plan assumes every day is a normal day. It has no way to handle illness, a family emergency, a work shift change, or a day when the student simply cannot study.

**Why it matters:** Life events are normal, not exceptions. A plan that cannot absorb them becomes useless the first time one happens — and the student has no plan at all when they need one most.

**Signs:** High reschedule rate with "illness" or "family" as the reason, or students abandoning the plan after a missed stretch.

### Risk 4 — False confidence

**What it is:** The student follows the plan, but the plan covered the wrong topics — for example, because weightage was guessed, or difficulty was misjudged — and the student feels prepared for the wrong exam.

**Why it matters:** The student arrives at the exam confident and unprepared, which is worse than arriving worried and prepared.

**Signs:** Low preparedness scores before the exam, or a mismatch between planned coverage and the real syllabus.

### Risk 5 — The planner is treated as a counsellor

**What it is:** A stressed student asks the planner for help with stress, anxiety, sleep, or personal problems — and the planner gives advice it is not qualified to give.

**Why it matters:** Bad advice about health can cause real harm. The planner is a planning aid, not a counsellor, and must never pretend to be one.

**Signs:** Students asking the planner health or wellbeing questions, or the plan containing advice beyond study planning.

### Risk 6 — Privacy

**What it is:** A student's exam timetable, syllabus, hours, and progress are personal. If they are shared, stored carelessly, or shown to others without permission, trust is lost.

**Why it matters:** Students will not use a planner they do not trust with their information.

**Signs:** Any sharing without explicit permission, or any storage the student did not agree to.

---

## Guardrails

These are non-negotiable. A plan that breaks a guardrail does not ship.

| # | Guardrail | What it means in practice | Linked risk |
|---|-----------|---------------------------|-------------|
| G1 | Max study hours cap | No day may plan more hours than the student's available hours that day. A plan that breaks this fails automatically (see `docs/04-eval.md`). In addition, set a sensible daily cap — for example, no day plans more than 6 hours of focused study, even if the student says they have 8 hours free — and say the cap clearly. | Risk 1 |
| G2 | Mandatory breaks | Every study day includes breaks. No study block runs longer than 50–60 minutes without a break. Breaks are part of the plan, not optional extras. | Risk 1 |
| G3 | One-tap "lighter day" reschedule | The student can tap once to make a day lighter. The planner moves topics, keeps high-weight coverage, and never over-allocates the days that follow. No guilt, no warning, no backlog shown as a failure. | Risks 1, 2, 3 |
| G4 | Kind language, always | The plan never uses punishing language. A missed day is "a day to reschedule", not "a failure". Progress is shown as coverage gained, not days lost. | Risk 2 |
| G5 | Clear statement: planning aid, not a counsellor | The plan and the product state clearly, in plain language: "This is a planning aid. It does not give medical or mental-health advice, and it is not a counsellor." If a student asks for wellbeing help, the product points them to real support — a trusted person, their school / university support service, or a doctor — and does not try to advise. | Risk 5 |
| G6 | No guarantee of marks | The product never promises marks, grades, or exam results. It says what it does: it helps the student use time well. | Risk 4 |
| G7 | Weightage must be honest | If weightage is unknown or estimated, the plan says so clearly. It never presents a guess as a fact. | Risk 4 |
| G8 | Student can override any day | The student can change, skip, or swap any day. The planner adjusts, and does not punish the change. | Risks 1, 2, 3 |
| G9 | Day before the exam is revision-only | No new topics the day before an exam. That day is for revision and recall only. | Risk 1 |
| G10 | Privacy by default | A student's timetable, syllabus, and progress are not shared with anyone else without their explicit permission. | Risk 6 |

---

## What to do when a guardrail is triggered

| Situation | Action |
|-----------|--------|
| Plan asks for more hours than available | Fail the plan automatically. Do not show it to the student. Fix it and re-run the eval. |
| Student taps "lighter day" | Regenerate that day (or week) lighter, keep high-weight coverage, and show the new plan without a guilt message. |
| Student misses 3+ days in a row | Offer a fresh plan from today, with coverage re-checked. Ask, in the weekly check-in, what happened — and listen. Do not assume laziness. |
| Student asks for health / wellbeing advice | Do not advise. Show the planning-aid statement (G5) and point to real support. Record that it happened, so the product team can see how often it occurs. |
| Student reports feeling overwhelmed | Reduce the plan, offer a lighter week, and check in sooner. Record it as an overload report (see `docs/05-metrics.md`). |

---

## Harm review — blank, to be filled in after the pilot

| Risk | Did it happen in the pilot? | How often? | What we did |
|------|-----------------------------|------------|-------------|
| Overloading plans | TBD | TBD | TBD |
| Demotivating plans | TBD | TBD | TBD |
| Plans ignoring illness / life events | TBD | TBD | TBD |
| False confidence | TBD | TBD | TBD |
| Planner treated as a counsellor | TBD | TBD | TBD |
| Privacy issue | TBD | TBD | TBD |

If a harm occurred, write down what happened and what changed. Hiding a harm does not fix it.
