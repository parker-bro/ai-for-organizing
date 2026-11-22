# Mode: setup

**What it does:** writes the series profile (see `../SKILL.md`) so every other mode has its facts.
**Rule of thumb: detect first, then ask only about the gaps.** Most people have more of this written
down than they think: last year's goals, a board deck, a calendar of planning meetings. Read those
before asking anything.

## Step 1 — Read what already exists

Ask once for anything the person can link or paste: last year's goals, a strategy memo, the planning
calendar, the tracker, an agenda they liked. Then read all of it before asking a question.

From what you read, fill as much of the profile as you can, and mark each value **found** (with
where you found it) or **guessed**.

## Step 2 — Interview for the gaps

Ask only what Step 1 didn't answer, in **one message, at most seven questions**, each with your
best guess filled in so the person can just say "yes":

1. **What period do these goals cover, and when must they be agreed?** *(Guess: next calendar year,
   agreed by mid-January.)*
2. **Who drafts, and who signs off?** *(Guess: you draft, the director signs off.)*
3. **Which goals already stand, that every topic should be tested against?** Two or three, in plain
   words. If there are none, say so; the first session then sets them.
4. **What format do you want the goals in?** Offer the "Picking one" table in `../frameworks.md`
   with your recommendation and one line on why.
5. **Where does the work live?** The tracker, the decisions list, the goals doc.
6. **How many sessions, how long, and roughly when?** *(Or: "want me to propose a plan?" If so, run plan mode.)*
7. **What's off the table?** Topics leadership has already ruled out, so nobody re-opens them.

Accept partial answers. Anything still missing gets a sensible default, written into the profile
and marked `default — change me`.

## Step 3 — Build a custom framework (only if they have their own format)

When the person has a template that isn't one of the built-ins:
1. Read the template and propose all eight slots (`unit`, `shape`, `limits`, `quality_test`,
   `measure_gate`, `cut_to`, `not_doing`, `asks_feed`) from it.
2. Ask only about slots the template doesn't answer, at most five questions. The three that are
   almost never written down: *How many is too many?* *How do you know one is well written?* *Where
   does an idea go when it doesn't make the cut?*
3. Write the answers into `framework_rules` in the profile.

The same path works to **override a built-in**: "OKRs, but 3 KRs max and no stretch targets" goes
in `framework_rules` on top of `goal_framework: okr`.

## Step 4 — Set up the goals doc

If the goals doc doesn't exist, propose its skeleton in the framework's `shape`: one empty section
per objective or goal area, the measurability table, the cut-to table and the not-doing list.
Creating it is a new doc, so it needs the person's yes. If it exists, map its headings to the
framework's slots and show the mapping.

## Step 5 — Show the profile and stop

Show the whole profile with found / guessed / default marked on each value. Write it on "go", to
wherever the person keeps it: a file next to the skill, a project knowledge file, or pasted at the
top of the series doc. Without file access, give it back as a block to save and paste in next time.
