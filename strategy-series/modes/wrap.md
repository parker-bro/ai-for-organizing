# Mode: wrap

**What it does:** checks the transcript or notes of one session against its agenda and gives every
ask exactly one verdict. It catches the two failures that kill a series: topics nobody reached that
look settled, and agreements nobody owns.

Needs: the session's agenda doc, and a transcript or notes. A transcript is better; notes miss what
was said and not written down.

## Step 1 — Build the ledger

Number every ask on the agenda, in order: A1, A2, … An. Sub-topic rows get their own number. This
is the ledger, and every one of them gets a verdict. No ask is skipped because the room "probably
agreed".

## Step 2 — Give each ask one verdict

| Verdict | Means | Needs |
|---|---|---|
| ✅ **Decided as proposed** | The room took the recommendation | Who said so, quoted |
| ✏️ **Decided, changed** | The room decided something else | The new call, in one line |
| ⏸ **Deferred** | The room chose to decide later | An owner **and** a forum or date. Without both, it's ⬜ |
| ⬜ **Not reached** | The room never got to it | Nothing. It is **not** decided, whatever the default said |
| ⏭️ **Dropped** | The room decided not to pursue it | The reason, and the goal it didn't move, added to the not-doing list |
| 🧊 **Iced** | Parked on purpose, to come back to | What would bring it back |
| ➕ **Off-agenda** | Raised in the room, wasn't on the agenda | Treated as a new ask; queued for the next session or a solo stream |

Rules:
- **Silence is not a decision.** If the transcript doesn't show the room deciding, it's ⬜, even
  if the agenda had a default.
- **Quote the moment.** Every ✅ and ✏️ points to the line in the transcript where it happened, and
  who said it.
- **Flag contradictions with ⛔.** If the room decided something that conflicts with a standing
  goal, an earlier decision or the not-doing list, say so and name both.
- **Count carries.** An ask that has been ⬜ or ⏸ in two sessions gets **×2** and a prompt: decide it
  next time, make it solo, or drop it.

## Step 3 — Separate agreeing from owning

For every ✅ and ✏️, write four fields:

| Call | Owner | Approver | By |
|---|---|---|---|

The owner must be one of the profile's `decision_makers`. Anyone else who volunteered goes in the
notes, not the owner column.

Anything the room agreed to with no owner goes in a list called **"Agreed, nobody owns it"**. That
list has to be empty before the wrap is approved. Fill each line with an owner, or move it to ⏸.

## Step 4 — Queue the changes, don't make them

From the verdicts, stage:
1. **Goals doc writes** — for every ask the framework's `asks_feed` says touches a unit. Goals mode
   writes these in the framework's shape.
2. **Tracker changes** — new work, re-scoped work, closed work. Queued in plain words. If you use
   the companion `meeting-to-actions` kit, hand this list to it; it already knows how to dedupe
   against a tracker.
3. **Not-doing list** — every ⏭️, with its reason.
4. **Next session** — every ⬜, ⏸ and ➕, for build mode to pick up.

## Step 5 — One review, then stop

Show everything as **one numbered review**: the ledger with verdicts, the ownership table, the
"Agreed, nobody owns it" list (it should say "none"), and the four queues. The person replies `go`
or edits by number.

On "go", write each queue to its home from the profile. Then read back what you wrote and say, in
one line each, what landed where. Anything that didn't land is listed, not glossed.

## Self-check before showing the review

- Every ask on the agenda has exactly one verdict.
- No ✅ or ✏️ lacks a quote.
- No ⏸ lacks an owner and a forum or date.
- "Agreed, nobody owns it" is empty, or the review says plainly that it isn't.
- Nothing from the transcript is posted anywhere shared. Strategy sessions name people and money.
