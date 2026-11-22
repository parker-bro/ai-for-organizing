# Mode: build

**What it does:** writes one session's agenda and its deck outline, from the profile, the intake
results and the last wrap. The agenda and deck are built together, because they must use the same
words for every topic.

Works in any tool: a Google Doc and Slides, Notion, Word and PowerPoint, or plain markdown. The
rules are about content and order, not formatting.

## Step 1 — Gather

Read, in this order:
1. The profile: the session's `covers`, `minutes`, `standing_goals`, `goal_framework`.
2. The last wrap, if there is one: anything ⏸ deferred to this session, ⬜ not reached, and asks
   carried two or more times.
3. The intake results for this session's themes: every item marked `gap` or `homed (thin)`.
4. The goals doc: the units this session is meant to set or change (the framework's `asks_feed`).
5. The existing agenda doc, if there is one. Edit it in place.

## Step 2 — Write the asks first

Before any agenda row exists, write each topic as one **ask**. An ask has:

```
DECISION NEEDED: <the question, open enough to make the decider think>
Who decides: <a name from decision_makers>
Options: <2 or 3, each one line>
Recommendation: <the drafter's pick, and why in one line>
Default if no answer: <what happens if the room doesn't get to it>
Decided by: <date>
```

Use `ACTION NEEDED:` instead when the room only has to assign or approve work, not choose.

**If you can't write the options, the topic isn't ready.** Call it a discussion, give it a minutes
cap, and say what it would take to become a decision next time.

Topics with nothing to decide are **passive**: four or five bullets and a `WHAT'S NEXT:` line. They
go in the pre-read, not on the agenda, unless the room has to react to them.

## Step 3 — Rank, then cut

1. Test every ask against the standing goals. One that moves none is tested once more: is it a
   **repeatable** thing the org does every period, or a **one-off**? A one-off that moves no goal
   goes to the not-doing list with that reason, not on the agenda.
2. Rank what's left by how much it moves a standing goal, and how much later work waits on it.
3. Budget the minutes, starting with a fixed opening row: **"Catch-up and hard-stop check · 10"**.
   Every session after the first also gets one **"Where we are"** item of at most 2 minutes.
4. Draw the **cut line** where the minutes run out. Everything below it moves to a linked section
   at the bottom, "Where the cut topics live", each with where it went (the next session, a solo
   stream, the pre-read, or not now) and the goal it would have moved.

## Step 4 — The agenda

One row per topic, in ranked order:

| # | Topic (the takeaway, as a sentence) | Minutes | Ask | Pre-read |
|---|---|---|---|---|

Rules:
- **Break a big topic into sub-topic rows,** each with its own ask. A topic with three decisions
  is three rows.
- **Open decisions go inline,** right under their row: a one-line TLDR, the decision, and the
  proposed call. Nobody should have to open another doc to know what's being asked.
- **Deep-link everything.** Every source, tracker item and earlier decision gets its own link, not
  a link to the folder.
- **Mark each topic REPEATABLE or ONE-OFF.**
- **The agenda can hold more than the deck.** Extra push-ons, backup numbers and the full option
  text live here; the deck carries only what the room needs to see.

## Step 5 — The deck outline

One outline, slide by slide. For each topic, in agenda order:

1. **Question slide first, then evidence.** The room should know what it's deciding before it sees
   a number.
2. **Every headline is the so-what, with its unit.** "Repeat clients fell from 31% to 22% this
   year", not "Client retention". Same words as the agenda row.
3. **Speaker notes carry three things,** each on its own line:
   - `ASK:` the decision, word for word from the agenda.
   - `IF THEY PUSH:` at most 3 short follow-ups the presenter can use.
   - `---` then the source of every number on the slide: the doc, the record, how many rows, and
     how old.
4. **One "Where we are" slide,** in sessions after the first, readable in under 2 minutes.
5. **Refer to slides by title, not number.** Numbers change; titles don't.
6. **No capture slide.** Notes and decisions are wrap mode's job, after the session.

## Step 6 — Stage it, then stop

Run the edit pass (`../SKILL.md`) on every row and every slide line. Then show, as one numbered
review:
1. The ranked asks, with the cut line drawn.
2. The agenda.
3. The deck outline.
4. Where each cut topic went.

On "go", write the agenda into its doc (copying anything you replace into "Earlier content" first)
and hand back the deck outline. Building the slides themselves is the person's call: some will
paste the outline, some will ask you to fill an existing deck in place.
