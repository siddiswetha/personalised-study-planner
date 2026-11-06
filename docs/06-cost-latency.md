# 06 — Cost & Latency Estimate

## Personalised Study Planner

---

## Purpose

To compare two ways of generating a plan, and to choose one with reasons — not by habit, but by cost, latency, and quality.

**All numbers in this document are EXAMPLE estimates for planning and discussion, unless they are marked as measured. Do not present estimates as real costs. Measure real cost, latency, and quality in the pilot, and record them in the tables at the end.**

---

## The two approaches

### Approach A — One call: generate a full 30-day plan in one go

The planner produces the entire 30-day plan in a single generation.

**How it works:** One request, with all inputs (exam dates, topics, weightage, difficulty, hours, commitments). One output: 30 days of topic, goal, recall task, and break.

### Approach B — Weekly generation: generate one week at a time

The planner produces the plan week by week — 7 days at a time — and regenerates the next week based on what actually happened.

**How it works:** First request generates Week 1. At the end of Week 1, the student reports what was done, missed, or rescheduled. The next request generates Week 2, using that real progress.

---

## Comparison

### Cost

| Factor | Approach A — One call, 30 days | Approach B — Weekly |
|--------|--------------------------------|---------------------|
| Number of generations for a 30-day plan | 1 | About 4–5 (one per week) |
| Size of each generation | Large — 30 days of detail in one output | Small — 7 days per output |
| Total output over 30 days | 30 days, once | 30 days, in weekly parts |
| Expected total cost | Lower in total, if the plan is followed without change | Higher in total, because there are more generations — but each one is smaller |
| Wasted cost when life changes | High — if the student misses days in Week 1, much of the 30-day plan is out of date and must be regenerated | Low — only the current week is affected; the next week is planned with real progress |
| Cost of a reschedule | A full or large regeneration | A small regeneration for the affected days / week |

**EXAMPLE illustration only — not a real price:**

If one full 30-day generation costs, say, 10 units and one weekly generation costs 3 units, then:

- Approach A: 10 units for the plan. If it needs a full regeneration after Week 1, that is another 10 units. Total: 20 units.
- Approach B: 3 units × 4 weeks = 12 units, with rescheduling built in each week. No wasted full plan.

The exact numbers depend on the model, the length of the plan, and the tool used. Measure them in the pilot. The pattern matters more than the numbers: Approach A is cheaper if nothing changes; Approach B is cheaper when life changes — and life usually changes.

### Latency

| Factor | Approach A — One call, 30 days | Approach B — Weekly |
|--------|--------------------------------|---------------------|
| Time to first plan | Longer — a large output takes longer to generate | Shorter — a 7-day plan is generated faster |
| Time to regenerate after a change | Longer — a large plan must be reworked | Shorter — only a week, or a single day, is reworked |
| Target | Full plan: as fast as reasonable; no fixed target set yet — measure it | Regeneration: **latency < 5 seconds** (target from the spec) |
| Student experience | Student waits longer once, then has the whole plan | Student gets a plan quickly, and each week's plan reflects real progress |

**Latency target from the spec: < 5 seconds** for a regeneration. That target is realistic for a small regeneration (a day, or a week). It is much harder for a full 30-day regeneration in one call. That is one reason to prefer smaller generations for rescheduling.

### Quality

| Factor | Approach A — One call, 30 days | Approach B — Weekly |
|--------|--------------------------------|---------------------|
| Accuracy on day 1 | Good — the whole plan is visible at once | Good — Week 1 is planned in detail |
| Accuracy in Week 3–4 | Weaker — the plan was made before the student missed days, fell behind, or changed pace | Stronger — Week 3 is planned using real Week 1–2 progress |
| Spaced repetition | Must be planned 30 days ahead, and may drift if days are missed | Can be adjusted each week, so revisits happen on time |
| Coverage of high-weight topics | Visible from day one, but at risk if early days are missed | Checked each week; if coverage slips, the next week corrects it |
| Student trust | Student sees the whole journey, which can be reassuring | Student sees a plan that adapts to them, which builds trust over time |
| Risk of overload | Higher — a 30-day plan can look overwhelming on day one | Lower — the student sees one week at a time |

---

## Chosen approach — and why

**Chosen approach: Weekly generation (Approach B), with a full-plan outline on day one.**

This is a hybrid, and it is chosen deliberately:

1. **On day one, generate a light outline for the whole period** — which topics go in which week, and when high-weight topics will be covered. This gives the student the reassurance of seeing that the whole syllabus fits, without the cost and fragility of a full 30-day detailed plan.
2. **Then generate each week in detail, one week at a time** — with topic, goal, recall task, and break for each day. Each week's plan uses real progress from the week before.
3. **Regenerate small, not large** — when a student misses a day or taps "lighter day", regenerate only the affected days or the current week. This keeps latency under 5 seconds and keeps cost low.

### Why this is the right trade-off

- **Cost:** More generations, but each is small, and almost nothing is wasted when life changes. The total cost over a 30-day cycle is expected to be similar to, or lower than, Approach A once rescheduling is counted.
- **Latency:** Weekly and daily regenerations are small enough to meet the < 5s target. A full 30-day regeneration is not.
- **Quality:** The plan stays true to real life. Coverage is checked weekly, spaced repetition is adjusted weekly, and a missed week does not break the whole plan.

### When Approach A would be better

If a student has a very stable schedule, never misses a day, and wants the full detail in advance, a one-call 30-day plan is simpler and cheaper. That is a real case — but it is not the common case for students with jobs, family, and changing commitments. The weekly approach is the default; the one-call plan remains an option for stable schedules.

---

## Cost & latency — measurement table (blank, to be filled in after testing)

Measure these with the actual tool and model used in the pilot. Record the tool / model name, so the numbers can be compared fairly.

| Measure | Approach A — One call, 30 days | Approach B — Weekly | Notes |
|---------|--------------------------------|---------------------|-------|
| Tool / model used | TBD | TBD | TBD |
| Cost per generation | TBD | TBD | TBD |
| Total cost for a 30-day cycle | TBD | TBD | TBD |
| Cost per successful plan (see `docs/05-metrics.md`) | TBD | TBD | TBD |
| Time to generate (median) | TBD | TBD | TBD |
| Time to regenerate (median) | TBD | TBD | TBD |
| Latency — regeneration | TBD | TBD — target < 5s | TBD |
| Eval pass rate (12 scenarios) | TBD / 12 | TBD / 12 | TBD |
| Adherence after 7 days | TBD | TBD | TBD |

**Decision after measurement:** TBD — confirm or change the chosen approach, with reasons, after the pilot data is in.

---

## Cost controls

Simple rules to keep cost low, whatever approach is used:

1. Generate detail only for the week ahead. Outline the rest.
2. Regenerate only what changed — a day, or a week — never the whole plan if a small fix will do.
3. Reuse the student's inputs. Do not re-send the full syllabus on every regeneration if only one day changed.
4. Log cost per plan, so a rising cost is noticed early (see `docs/05-metrics.md`).
