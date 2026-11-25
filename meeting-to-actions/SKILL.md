---
name: meeting-to-actions
description: >-
  Turns a meeting transcript into clean records in the tracker your team already uses: tasks,
  decisions, open questions, bugs and deliverables (the forms, docs, templates and automations the
  work produces). Checks every item against existing work so nothing gets
  duplicated, catches decisions that make a written rule out of date, stages one numbered review,
  and writes nothing until a person approves. Use when
  someone says "triage this meeting", "process this transcript", "what came out of that meeting",
  or "run the weekly sweep".
license: MIT
---

# Meeting → Actions

Most AI notetakers stop at a summary. This skill keeps going: it turns what was said into the
right records in your tracker, without making a mess of it.

It is built on four beliefs, each learned the hard way:

1. **A duplicate is worse than a miss.** A missed item costs one re-add. A duplicate splits the
   history of a piece of work, and someone has to find it and merge it later. When in doubt,
   **flag and ask, don't create.**
2. **Saying something in a meeting doesn't make it a task.** Most of what gets said is context,
   logistics or "we should someday". Apply a high bar.
3. **Nothing gets written until a person says so.** The AI proposes. A human approves.
4. **A decision isn't done until the rules say it.** People and agents follow the written rules,
   not the decision log. A decision that only lands in the log is invisible to whoever reads the
   rules next, so the old rule keeps running.

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

# Where your rules live: whatever your agents read before they act, plus the SOPs people follow.
rule_homes:
  - "CLAUDE.md / AGENTS.md / project instructions"   # agent instructions
  - "Volunteer handbook (Google Doc)"                # human-facing SOPs and runbooks
# Columns the skill fills on every decision. Add them to your decision log once.
decision_metadata:
  changes_a_rule:  "Changes a rule?"   # yes / no
  superseded_by:   "Superseded by"     # link or ID of the newer decision
  last_reviewed:   "Last reviewed"     # date the rule question was asked
```

If your decision log is a doc rather than a table, the same three facts go on one line under each
entry: `Changes a rule: yes · Superseded by: — · Last reviewed: 2026-11-19`.

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
- **Note which older decisions a new one reverses.** If a decision covers the same subject as an
  earlier one in the log and settles it differently, it supersedes it. Step 5 links the two.

### 3b. Does a decision change a rule?
Run this over every decision from Step 2, plus any action item that changes how an existing
workflow runs. Skip it when there are none. It never blocks the triage and writes nothing before
approval.

1. **Ask of each decision: would someone following the rules now act differently?** A new or
   removed step, gate, owner, approver, deadline, threshold, channel, recipient, naming rule, or an
   "always" or "never" → **yes**. A priority call, a creative direction or a one-off choice that
   sets no standing rule → **no**, and say nothing.
2. **Find the sentence it breaks.** Search the `rule_homes` for the decision's key nouns (the
   system, the role, the form, the date). A hit means *may*: read it and quote the exact sentence
   that is now wrong, or say where a missing rule belongs. If you can't open a rule home from here,
   name the file or doc you'd expect and mark it **unverified**. Never stage a file just because
   it shares a topic with the meeting.
3. **Stage one line per file:** the decision, the file, the old sentence, and the new sentence in
   the decision's own words. If an open task already names that file, note it on that task instead
   of staging a second one.

No hit and no likely home: one line in the review, `Rules: none changed.`

### 4. Stage one review
Post everything grouped by lane **before writing anything**, with each item's destination, its
duplicate label and its project:

```
📋 Meeting → Actions: [Meeting name] ([date])

✅ Action items → Tasks (3)
  1. Send volunteer FAQ draft — owner: Sam — project: Volunteer Relaunch — ✅ New
  2. Book venue for Oct 22 — owner: Ana — ⚠️ Matches "Venue for Show & Tell" (In Progress) → skip?
⚡ Decisions (2)
  3. Going with the Thursday time slot — decided by: Ana, Sam — why: host availability
  3a. New volunteers get a buddy call before their first shift — decided by: Ana — supersedes "Self-serve onboarding" (Mar 4)
📏 Rules a decision changes (1)
  3b. Decision 3a → Volunteer handbook, "Onboarding": "New volunteers can sign up for any open shift."
      → "New volunteers book a buddy call before their first shift." → edit on "go", or a task if I can't
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

Every staged decision carries `Changes a rule?` as you judged it in Step 3b, so a person can
correct it in the reply (`3→no rule`). That is the only way they ever touch it.

### 5. Wait for approval, then write
Write nothing until a person replies. Accept partial instructions (`skip 3`, `keep 2`,
`link 4 to project X`), apply them, then write only what was approved.

**Write in this order, so every record can link to the ones before it:** decisions and questions,
then bugs, then deliverables, then rule edits, then tasks. Tasks come last because they link to
everything else: the decision behind them, the bug they fix, and the asset they produce.

**Decisions carry their own metadata.** On every decision you write, fill the `decision_metadata`
columns yourself:
- `Changes a rule?`: yes or no, from Step 3b and any correction in the reply.
- `Superseded by`: on each **older** decision this one reverses, link it to the new one.
- `Last reviewed`: today's date, on every decision, rule change or not. It is the stamp that says
  the rule question was asked.

**Then land each approved rule change:**
- **If you can edit the rule home** (a repo, a doc you have write access to): make the edit, old
  sentence → new sentence, and cite the decision (its ID or link) next to the new sentence so the
  next reader can see why it says that. If the home works through review (a pull request, suggested
  edits), open it that way rather than editing directly.
- **If you can't:** create one task per file: `Update [file] for [decision in plain words]`, linked
  to the decision, with the old and new sentence quoted word for word in its notes. Done means the
  file says what the decision says.

**If the review runs in Slack:** one run can't sit and wait for a reply, so split it in two.
Run 1 posts the review and stops. Run 2 is started when someone says "process my reply": it reads
the thread, parses the reply, writes, and posts the confirmation in the same thread. **Don't
schedule a poll to watch the thread.** Polling burns runs on a thread that usually hasn't changed.

### 6. Confirm with links, not counts
Close with one line per record written, each with a direct link, grouped by lane, plus what was
skipped. "Wrote 7 records" isn't a confirmation. A person can only fix a wrong priority or a bad
routing call if they can click through to the record.

Give rule changes their own group, `📏 Rules flagged`: one line per file with the link to the edit
(or the pull request), or to the task created in its place. If none, say `Rules: none changed.`

---

## Guardrails

- **Only real people own records.** Only the names in `assignable_people` can be assigned.
  Anyone else, such as a volunteer, a partner or a candidate, goes in the notes.
- **Never create a project automatically.** Propose it, and a person decides.
- **The skill owns decision metadata. People don't.** In the decision log, people type the answer
  and change the status. Nothing else. Every other field (`Changes a rule?`, `Superseded by`,
  `Last reviewed`, links, dates) is the skill's job. Never leave a field for someone to "fill in
  later", and never ask anyone to tick a box. If you load a decision someone marked decided outside
  a triage and its metadata is blank, stage the values in the review under `📝 Backfill` and
  write them with everything else on "go".
- **🔒 Set visibility explicitly. Never guess "public".** If your tracker has automations that
  broadcast certain records, such as posting feedback to a channel, then candid material from an
  internal meeting (a 1:1, a strategy reset, a retro) must be marked internal or confidential on
  every row you write. Guessing "open" can send someone's private words to a whole channel
  verbatim. This rule exists because that happened.
- **Recurring meetings:** when an item fits better in an existing recurring forum ("raise at the
  monthly budget review"), flag it for that forum instead of minting a standalone task.

## Optional: weekly sweep

If you'd rather not paste each transcript, run one sweep a week instead. Point the skill at the
folder where your notetaker saves transcripts and schedule the sweep (a scheduled task, a cron job,
or a weekly reminder to say "run the weekly sweep"):

```yaml
transcript_source: "Google Drive › Meeting transcripts"   # wherever your notetaker saves them
sweep_window_days: 7
```

1. **Find this week's meetings.** List the transcripts saved in the window. Skip any that were
   already triaged (a decision or task already cites that meeting by name and date).
2. **Run Steps 1–3b on each one.**
3. **Stage one review for the whole week**, grouped by meeting and then by lane, numbered
   straight through, so a single reply covers everything (`skip 4,9` · `go`). Check duplicates
   across meetings too: the same task raised on Monday and Thursday is one record.
4. **Then Steps 5 and 6, unchanged.** A sweep writes nothing until a person replies, the same as a
   single triage. If no one replies, the sweep writes nothing at all.

Run it on its own or with the rule check below. They fit together: the sweep catches the
decisions made in meetings, and the rule check catches the ones made everywhere else.

## Optional: weekly rule check

Step 3b only catches decisions made in a triaged meeting. Decisions also get made in chat, in a
doc comment, or by someone flipping a status. If you can schedule a recurring run (a scheduled
task, a cron job, a weekly reminder to paste this in), add one that reads the decision log and the
rule homes and reports, writing nothing:

1. **Never reviewed.** A decision marked decided in the last 14 days with `Last reviewed` blank:
   nobody asked whether it changes a rule.
2. **Never landed.** A decision with `Changes a rule?` = yes that no rule home cites (by ID or
   link): the log says the rule changed, and the rules don't.
3. **Citing a dead decision.** A rule home that cites a decision with `Superseded by` filled in:
   the rule points at an answer that was overturned.

Checks 2 and 3 work only if rule edits cite their decision, which is why Step 5 asks for it.
Post the findings wherever the team reviews work. Each one gets fixed the same way as in a triage:
stage, approve, then write.

## Edge cases

- **Transcript is empty or missing:** ask the person to paste it.
- **Long meeting (over 45 minutes):** extract everything, but apply the bar more strictly.
- **Links shared in the meeting chat:** many transcript exports drop the chat. Ask for any links
  that matter.
- **Owner isn't in the tracker:** put their name in the notes and leave the owner blank.

---

_Built by Alex Parks. Field-tested on 44 consecutive meetings at a volunteer-run political organization (Jun–Oct 2026).
Shared for the AI for Organizing Prize under the MIT License._
