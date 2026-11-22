# Mode: intake

**What it does:** checks that nothing in scope has been forgotten. It reads the tracker and the
series, and answers one question for every live project or workstream: **where will this get
decided?** It's read-only. It never changes the tracker.

Run it at the start of the series, after any change to the series, and before each session's
prep (build mode reads its results).

## Step 1 — Read the scope

From `homes.tracker`, list every project, workstream or area that's live in the period. Skip what
is done or archived. If the tracker can't be read, ask for an export or a pasted list and say the
result is **partial**.

## Step 2 — Match each item to a home

For each item, look for it in, in this order:
1. A session's `covers` or agenda doc.
2. A `solo_streams` entry.
3. The goals doc.
4. The not-doing list.

**Match by link, URL or ID first.** That's a strong match. A match on the name alone is weaker:
report it as **"named, not linked"**, because two things with similar names are often different
work.

If a doc that should be checked can't be opened, mark it **UNREAD** and say the result is partial.
Never report "no gaps" from a partial read.

## Step 3 — Give each item one disposition

| Disposition | Means |
|---|---|
| **session** | A session covers it, with a real ask |
| **homed (thin)** | A session mentions it, but there's no ask, owner or goal attached |
| **solo** | One person decides it alone, and that's written down |
| **parked** | On the not-doing list, with a reason |
| **execution?** | It's work already decided, not a strategy question. Confirm and drop it from the series |
| **gap** | No home anywhere. This is what the mode exists to find |

## Step 4 — Report

One table, gaps first:

| Item | Disposition | Where it lives (link) | What to do |
|---|---|---|---|

Then one line each:
- How many items were read, and from where.
- How many matches were "named, not linked".
- What was UNREAD, if anything.

For every **gap** and **homed (thin)**, suggest one of: add it to a session (and which), make it a
solo stream (and whose), or park it (with the goal it doesn't move). Changes to the profile are
staged; nothing is written until a person says "go".
