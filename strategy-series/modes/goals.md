# Mode: goals

**What it does:** drafts and pressure-tests the goals in whatever format the profile names. It runs
two ways:

- **Small writes, after every wrap.** Each decision that touches a goal lands in the goals doc the
  same week, so the final draft is mostly assembled by the time the series ends.
- **The full pass, once, before the ratify session.** It tests the whole set and cuts it to size.

Every rule below reads the framework's **slots** (`../frameworks.md`), not its name. A custom
format works the same way as a built-in one.

## Small writes (after each wrap)

For each queued goals-doc write from wrap mode:
1. Find the unit it touches (`unit`). If it doesn't exist yet, draft it in the framework's
   `shape`, with every column filled or marked `none yet`.
2. Write the change. **Never invent a baseline.** No source means `baseline: none yet`, and the
   measure gate will catch it.
3. Note the source on the unit: which session, which ask number.
4. Anything a decision removed goes to `cut_to` or `not_doing`. It never just disappears.

Stage all of them as one numbered list. Write on "go". Copy any text you replace into "Earlier
content" first.

## The full pass (before ratify)

Run these in order. Each one can move units, so the order matters.

1. **Coverage.** Every standing goal has at least one unit under it, and every unit serves a
   standing goal. An orphan unit is cut or re-homed. A standing goal with nothing under it is
   flagged: the org either drops the goal or writes a unit for it.
2. **Quality test.** Run the framework's `quality_test` on every unit. Rewrite the ones that fail,
   and show the before and after side by side.
3. **Measure gate.** For every unit's measure: 🟢 measurable today, 🟡 partly, 🔴 not at all. Each 🟡
   and 🔴 names the hole and one fix: fix the tracking, change the measure, or change the unit.
   A 🔴 unit can't be ratified as it stands.
4. **Rank, then apply the limits.** Rank units by how much they move their goal. Apply `limits`.
   Everything over the limit moves to `cut_to`, each line naming the goal it would have served. The
   ranking is shown, so the room can argue with it.
5. **Owners.** Every unit has one owner from `decision_makers`. No person owns more than the
   framework allows.
6. **Not-doing list.** Collect every ⏭️ from every wrap, and everything cut in this pass. The list
   is part of what gets ratified. A goal set without a not-doing list isn't finished.
7. **Edit pass.** Run it on every line (`../SKILL.md`).

## What the ratify session gets

One doc, in this order:
1. The goals, in the framework's `shape`.
2. The measure gate table.
3. The `cut_to` table.
4. The not-doing list.
5. One line per unit naming the session and ask it came from.

Nothing new is raised in the ratify session. If the full pass turned up a real new question, it
goes to the drafter and approver before that session, not into it.
