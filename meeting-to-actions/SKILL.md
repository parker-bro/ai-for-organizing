---
name: meeting-to-actions
description: >-
  Turns a meeting transcript into clean records in the tracker your team already uses: tasks,
  decisions, open questions, bugs and deliverables (the forms, docs, templates and automations the
  work produces). Checks every item against existing work so nothing gets
  duplicated, stages one numbered review, and writes nothing until a person approves. Use when
  someone says "triage this meeting", "process this transcript", or "what came out of that meeting".
license: MIT
---

# Meeting → Actions

Most AI notetakers stop at a summary. This skill keeps going: it turns what was said into the
right records in your tracker, without making a mess of it.

It is built on three beliefs, each learned the hard way:

1. **A duplicate is worse than a miss.** A missed item costs one re-add. A duplicate splits the
   history of a piece of work, and someone has to find it and merge it later. When in doubt,
   **flag and ask, don't create.**
2. **Saying something in a meeting doesn't make it a task.** Most of what gets said is context,
   logistics or "we should someday". Apply a high bar.
3. **Nothing gets written until a person says so.** The AI proposes. A human approves.

---

## Configure once

Fill this in for your org. Everything below refers to these names, never to your tool directly.

```yaml
tracker: "Airtable | Asana | Notion | Linear | Google Sheet | ..."
destinations:
  action_item:   "Tasks"            # where a committed to-do lives
  decision:      "Decision Log"     # what was settled, by whom, and why
  open_question: "Decision Log"     # or a separate Questions list
  bug:           "Feedback"         # something live is broken or in the way
  deliverable:   "Deliverables"     # the catalog of assets: forms, docs, templates, dashboards, SOPs
  idea:          "Tasks (someday)"  # recommendation or research, only if it clears the bar
  new_project:   "propose only"     # never created automatically
assignable_people: ["Name A", "Name B"]   # only these people can own a record
review_channel: "chat | Slack thread"
sensitive_field: "Visibility"             # optional; see the privacy rule below
```

---

## Steps

### 1. Read the transcript
Note the meeting name, date (use today if it's missing, and say so) and participants. If any
participant is external, say in the review that relationship or CRM logging isn't covered here.

### 2. Extract and classify
Pull out only things that would become a real new record. Skip resolved logistics, vague "more to
come", background discussion and small talk.

| Lane | What it looks like | Tell |
|---|---|---|
| ✅ **Action item** | A concrete task with an owner and a verb | "I'll follow up", "Sam will send" |
| 🐞 **Bug / friction** | Something live is behaving wrong or getting in someone's way | "that shouldn't have happened", "it keeps doing X", a workaround someone quietly built |
| ❓ **Open question** | An unknown that needs investigation or a later decision | No owner and no next action, so write it as a question |
| ⚡ **Decision** | Explicitly and conclusively agreed | "we decided", "going with", "final call". Record who and why |
| 📦 **Deliverable** | A specific asset is named (a form, doc, template, dashboard, automation, SOP), or the meeting talks about creating or changing one | "the signup form", "update the host guide", "we need a one-pager for donors" |
| 💡 **Idea** | A recommendation or research topic, not decided | Only keep it if it would change a workflow or a metric |

Rules:
- One item per record. Quote the transcript in the notes when wording is ambiguous.
- **Question or action? → Question.** If it has no owner and no next step, it isn't a task.
- **High bar for decisions.** Most "we should…" agreements are directional, not decisions. When
  in doubt, attach it as context to the work it feeds instead of logging a decision.
- A bug goes to the bug/feedback list first, then gets a linked fix task. It never goes straight
  to tasks, or you lose the link between "what broke" and "what we did about it".
- If you can't tell which project something belongs to, **flag it in the review. Don't guess.**

**Deliverables get special handling, because they're what the work actually produces:**
- **An existing asset is mentioned:** confirm it's in the deliverables catalog. If it's missing,
  add it with whatever is known and flag it as previously undocumented. Meetings are where you
  find out about the doc nobody catalogued.
- **A task will produce a new asset, or change one:** create a **placeholder** deliverable
  (status "Not created yet", no link) and connect it to the task. That way the asset shows up in
  the catalog the moment it's promised, and the task and its output can be closed together.
- **Set the asset type on the deliverable, not on the task.** The task inherits it through the link.
- ⛔ **"Existing" isn't the same as "approved."** Finding an asset doesn't mean it's cleared to go
  into a live volunteer-, member- or public-facing workflow, even if it hasn't changed. Record it
  and flag it as *needs approval*. Never quietly wire it into something people will receive.

### 3. Check against existing work
Load the current state of every destination **once**, then match each candidate in context.

- Match on **meaning, not exact words.** "Build Google Groups routing" matches an existing
  "Set up group email infrastructure".
- Label every item with one of these:
  - ✅ **New**: no meaningful match. Safe to write.
  - ⚠️ **Likely duplicate**: clear match. **Skip by default**, and show
    `Matches "[existing]" (status) → skip / keep / merge?`
  - ⚠️ **Possible duplicate**: partial match. Surface it and let a person decide.
  - ⛔ **Contradicts a settled decision**: not a duplicate but a reversal. Write nothing and flag it.
- **A repeat is a signal, not noise.** When an item matches existing work, don't create a new
  record. Add a note to the existing one ("Raised again at [meeting], [date]") and link the
  transcript. That way you can see what keeps coming up.
- A time-sensitive duplicate (someone is leaving, a deadline is close) still gets mentioned in the
  recap as a reminder, even though nothing new is written.

### 4. Stage one review
Post everything grouped by lane **before writing anything**, with each item's destination, its
duplicate label and its project:

```
📋 Meeting → Actions: [Meeting name] ([date])

✅ Action items → Tasks (3)
  1. Send volunteer FAQ draft — owner: Sam — project: Volunteer Relaunch — ✅ New
  2. Book venue for Oct 22 — owner: Ana — ⚠️ Matches "Venue for Show & Tell" (In Progress) → skip?
⚡ Decisions (1)
  3. Going with the Thursday time slot — decided by: Ana, Sam — why: host availability
❓ Open questions (1)
  4. Do returning volunteers need to re-sign the agreement?
🐞 Bugs (1)
  5. Confirmation email shows the wrong time zone → Feedback + fix task
📦 Deliverables (2)
  6. Volunteer FAQ (Doc) — new → placeholder, linked to item 1
  7. Host guide (Doc) — exists in catalog, being changed → linked to a task · ⚠️ needs approval before it goes to hosts
🏗️ Possible new projects (not created; need your OK)
  8. "Election-night volunteer roster" looks like multi-week work

Reply `go` to write all · `skip 2,5` · `2→keep` · `4→decision` · `make project 8`
```

### 5. Wait for approval, then write
Write nothing until a person replies. Accept partial instructions (`skip 3`, `keep 2`,
`link 4 to project X`), apply them, then write only what was approved.

**Write in this order, so every record can link to the ones before it:** decisions and questions,
then bugs, then deliverables, then tasks. Tasks come last because they link to everything else: the
decision behind them, the bug they fix, and the asset they produce.

**If the review runs in Slack:** one run can't sit and wait for a reply, so split it in two.
Run 1 posts the review and stops. Run 2 is started when someone says "process my reply": it reads
the thread, parses the reply, writes, and posts the confirmation in the same thread. **Don't
schedule a poll to watch the thread.** Polling burns runs on a thread that usually hasn't changed.

### 6. Confirm with links, not counts
Close with one line per record written, each with a direct link, grouped by lane, plus what was
skipped. "Wrote 7 records" isn't a confirmation. A person can only fix a wrong priority or a bad
routing call if they can click through to the record.

---

## Guardrails

- **Only real people own records.** Only the names in `assignable_people` can be assigned.
  Anyone else, such as a volunteer, a partner or a candidate, goes in the notes.
- **Never create a project automatically.** Propose it, and a person decides.
- **🔒 Set visibility explicitly. Never guess "public".** If your tracker has automations that
  broadcast certain records, such as posting feedback to a channel, then candid material from an
  internal meeting (a 1:1, a strategy reset, a retro) must be marked internal or confidential on
  every row you write. Guessing "open" can send someone's private words to a whole channel
  verbatim. This rule exists because that happened.
- **Recurring meetings:** when an item fits better in an existing recurring forum ("raise at the
  monthly budget review"), flag it for that forum instead of minting a standalone task.

## Edge cases

- **Transcript is empty or missing:** ask the person to paste it.
- **Long meeting (over 45 minutes):** extract everything, but apply the bar more strictly.
- **Links shared in the meeting chat:** many transcript exports drop the chat. Ask for any links
  that matter.
- **Owner isn't in the tracker:** put their name in the notes and leave the owner blank.

---

_Built by Alex Parks. Field-tested on 44 consecutive meetings at a volunteer-run political organization (Jun–Oct 2026).
Shared for the AI for Organizing Prize under the MIT License._
