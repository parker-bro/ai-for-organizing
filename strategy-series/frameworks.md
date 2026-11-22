# Goal frameworks

The skill doesn't care which goal format you use. It cares that whichever one you pick is driven
the whole way: every session feeds it, every wrap writes to it, and the final pass tests it.

Each framework below fills the **same eight slots**. Every mode reads the slots, never the
framework's name, so a custom format works exactly like a built-in one.

| Slot | What it answers |
|---|---|
| `unit` | The thing you're writing (a key result, a Rock, a KPI target) and the thing it rolls up to |
| `shape` | The columns every unit carries |
| `limits` | How many is too many |
| `quality_test` | What makes one well written |
| `measure_gate` | How you know you can actually track it |
| `cut_to` | Where a unit goes when it doesn't make the cut (it never just disappears) |
| `not_doing` | Where "we decided not to do this" is written |
| `asks_feed` | Which agenda asks produce or change a unit |

---

## OKRs (`okr`)

- **unit:** a key result under an objective.
- **shape:** `# | Key result | Baseline (source, date) | Target | Owner | Where it's measured`.
- **limits:** 3 to 5 objectives; at most 4 key results per objective.
- **quality_test:** an outcome, not a task ("Repeat clients go from 20% to 35%", not "Launch a
  loyalty program"). One sentence. Has a number and a direction.
- **measure_gate:** for each KR, `Measurable today?` 🟢 yes / 🟡 partly / 🔴 no, plus the hole and
  its fix. A 🔴 KR gets one of: fix the tracking, change the measure, or change the KR.
- **cut_to:** a cut KR becomes a KPI you watch but don't commit to, in a `KPI | Why not a KR |
  Measurable?` table under its objective.
- **not_doing:** a list in the goals doc.
- **asks_feed:** any decision that sets or changes a target, baseline, owner or metric definition.

## Goals and KPIs (`goals_kpis`)

The plainest format, and the right default for a small team with no planning habit yet.

- **unit:** a goal, with one to three KPIs that show progress.
- **shape:** `Goal | Why it matters | KPI | Today | Target | By when | Owner`.
- **limits:** at most 5 goals; at most 3 KPIs per goal.
- **quality_test:** a reader can tell in five seconds whether the goal was hit.
- **measure_gate:** same 🟢 / 🟡 / 🔴 check as OKRs, per KPI.
- **cut_to:** "Nice to have" list, each line naming which goal it would have served.
- **not_doing:** a list in the goals doc.
- **asks_feed:** decisions that set a goal, a KPI or a target.

## Rocks (`rocks`)

Quarterly priorities with a single owner, in the style made popular by the Entrepreneurial
Operating System. Use it when the team plans in quarters, not years.

- **unit:** a Rock: one 90-day priority, owned by one person, under a one-year goal.
- **shape:** `Rock | Owner | Done means | Due (end of quarter) | One-year goal it serves`.
- **limits:** 3 to 7 company Rocks a quarter; no person owns more than 3.
- **quality_test:** "Done means" is binary. On the last day of the quarter it's either done or not.
- **measure_gate:** each "Done means" names the evidence (a launched page, a signed contract), not a
  feeling.
- **cut_to:** the "Issues list" or next quarter's candidates, never just deleted.
- **not_doing:** the issues list, marked "decided: not this year".
- **asks_feed:** decisions that pick, reshape or reassign a Rock.

## OGSM (`ogsm`)

Objective, Goals, Strategies, Measures. Common in larger organizations because it fits one page.

- **unit:** a strategy, with its measures, under a goal.
- **shape:** `Goal | Strategy | Measure | Today | Target | Owner`.
- **limits:** one objective; 3 to 5 goals; 2 to 4 strategies per goal.
- **quality_test:** each strategy is a choice that rules something out. If no one would argue
  against it, it isn't a strategy.
- **measure_gate:** 🟢 / 🟡 / 🔴 per measure.
- **cut_to:** a "Strategies we considered" list, each with why it lost.
- **not_doing:** the same list, marked "decided against".
- **asks_feed:** decisions that pick a strategy or set a measure.

## V2MOM (`v2mom`)

Vision, Values, Methods, Obstacles, Measures. Good when alignment on direction is the real problem.

- **unit:** a method, with its measures.
- **shape:** `Method (in priority order) | Measure | Target | Owner`, under one Vision and a short
  Values list. Obstacles are listed once, for the whole plan.
- **limits:** at most 5 methods, ranked. The ranking is the point.
- **quality_test:** methods are actions the team controls; obstacles are named honestly.
- **measure_gate:** 🟢 / 🟡 / 🔴 per measure.
- **cut_to:** methods below the line, kept in rank order.
- **not_doing:** the methods below the line, marked as such.
- **asks_feed:** decisions that rank, add or drop a method, or name an obstacle.

## Custom (`custom`)

When the person already has a format (a board template, a funder's logic model, a house plan
shape), setup builds this adapter with them. It fills the eight slots in `framework_rules` in the
profile, from their template plus at most five questions. See [`modes/setup.md`](modes/setup.md),
Step 3.

---

## Picking one (setup uses this)

| If the person says… | Recommend |
|---|---|
| "We've never really set goals" · fewer than ~15 people | `goals_kpis` |
| "We plan by quarter" · "we need accountability" | `rocks` |
| "We need stretch and focus" · they already know OKRs | `okr` |
| "It all has to fit on one page" · a board or parent company reads it | `ogsm` |
| "We don't agree on where we're going" | `v2mom` |
| They paste or link an existing template | `custom`, built from it |

Say why in one line, and make the person confirm. The framework can change later; only the goals
mode's final pass depends on it.
