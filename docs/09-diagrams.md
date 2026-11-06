# Diagrams — Personalised Study Planner

These are simple diagrams to help a beginner see how the product works. They match the spec in `docs/03-spec.md`. No image files are used — the diagrams below are written in Mermaid text, which GitHub renders as a picture.

## 1. How it works

```mermaid
flowchart TD
    A["Student enters exam dates and hours"] --> B["Add topics, weightage, and difficulty"]
    B --> C["Rank high-weight weak topics first"]
    C --> D["Build a day-by-day plan within real hours"]
    D --> E{"Does the plan fit the real hours?"}
    E -- No --> F["Trim the day and reschedule"]
    F --> D
    E -- Yes --> G["Plan with a goal, a recall task, and a break"]
```

What this shows: the plan is built around what matters most and how much time the student really has. A plan that asks for more hours than the student has fails automatically.

## 2. User journey

```mermaid
flowchart TD
    A["Student feels behind before exams"] --> B["Student enters exams, topics, and hours"]
    B --> C["Student gets a day-by-day plan"]
    C --> D["Student follows the plan and ticks off topics"]
    D --> E["Life changes, so the student asks for a lighter day"]
    E --> F["Plan is rescheduled without losing coverage"]
    F --> G["Student covers the syllabus before the exam"]
```

What this shows: before the product, the student studied easy topics first and ran out of time. After it, the student studies the right topics first and can change the plan when life changes.

## 3. Eval and release flow

```mermaid
flowchart TD
    A["Create the 12 planner scenarios"] --> B["Test each plan against real hours"]
    B --> C{"Does it cover high-weight topics and fit the hours?"}
    C -- No --> D["Fix the planning rules"]
    D --> B
    C -- Yes --> E["Pilot with 5 students for one exam cycle"]
    E --> F["Weekly check-ins with the pilot students"]
    F --> G["Release to a full class only if adherence and coverage hold"]
```

What this shows: the planner is tested on hard cases first — short time, clashing exams, a part-time job — and only released to a class after a real pilot works.
