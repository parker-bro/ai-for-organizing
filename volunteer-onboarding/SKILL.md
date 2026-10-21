---
name: volunteer-onboarding-planner
description: >-
  Sets up the Volunteer Onboarding playbook on the tools an organization already has. Interviews
  the organizer, maps the five stages and three human decisions onto their stack, writes every
  volunteer email, gives them a daily routine they can run by hand from day one, walks them through
  their first three automations, and leaves a plain build list for the rest. Use when someone says
  "set up volunteer onboarding", "plan our volunteer onboarding", or "help us onboard volunteers".
license: CC-BY-4.0
---

# Volunteer Onboarding: setup planner

This skill turns the playbook in [`README.md`](README.md) into a working process for one
organization. Read the README first: the stages, the detour table, the signature rules and the six
guardrails are the operating rules here, and nothing in this file overrides them.

**What the organizer has at the end:**
1. Their journey: the five stages and three decisions mapped to their tools and their people.
2. A tracker they can run it from, set up in a tool they already use.
3. Every volunteer email, written and ready to send.
4. A daily routine that runs the whole process by hand, with or without an AI assistant, from day one.
5. Their first three automations, live: confirmations, reminders and re-invites.
6. A build list for the rest, specific enough that a volunteer with some technical skill can pick it up.

Be honest about the split. Items 1–5 are a full, working process. Item 6 is what takes the process
from "runs with a daily half hour of attention" to "runs on its own", and it's weeks of build.
Don't oversell it, and don't present item 6 as required.

---

## How to run it

Work through the stages below **in order**, one at a time. Ask one question at a time and propose a
default with each. At the end of each stage, show what you produced and get a yes before moving on.
**Never send anything to a volunteer, and never change their tools, without a yes.**

### 1. Interview (about ten minutes)
Ask, in this order:
1. Roughly how many volunteer sign-ups a month, and how long they wait today before anyone replies.
2. Who approves new volunteers, and who could host a short group orientation. Names or roles.
3. Their tools, one by one: intake form, where people are tracked (spreadsheet, Airtable, a CRM),
   shared calendar, email sender, team chat, e-signature, and any automation tool (Zapier, Make,
   Airtable automations, Google Apps Script). "None" is a fine answer for any of them.
4. Do volunteers sign an agreement today? Is anyone already signed in an old system?
5. When is their next crunch (an election, a big event)? That sets the freeze date.

If they answer "under ten sign-ups a month", say so: the daily routine alone may be all they ever
need, and stage 6 can wait.

### 2. Map the journey
Produce the stage table from the README, filled in for them:

| Stage | What the volunteer gets | Tool | Who acts |
|---|---|---|---|
| 1. Apply | … | their form | machine (or the routine) |
| 2. Invite | … | their email | **named approver**, one click |
| 3. Book | … | their calendar / booking | machine (or the routine) |
| 4. Attend | … | their video tool | **named hosts** |
| 5. Access | … | their email + chat | **host clicks Send Welcome** |

Name the three human decisions and the person who owns each. If one person owns all three, flag it:
that's the bottleneck the playbook exists to remove, so suggest at least two hosts.

### 3. Set up the tracker
In the tool they already use, propose the minimum:
- **Volunteers:** Name · Email (the one used for matching) · Stage (Applied / Approved / Invited /
  Booked / Attended / Agreement pending / Active) · Agreement evidence (Form verified / Manual,
  ops-verified / Legacy / None) · Re-invite used (yes/no) · Welcome sent at · Joined chat (yes/no) · Notes.
- **Bookings:** Volunteer · Session · Status (Booked / Attended / Missed / Cancelled / Changed) ·
  Confirmation sent at · Reminder 24h sent at · Reminder 1h sent at.
- **Sessions:** Date and time · Host · Status (Open / CANCELLED, never deleted) · Roster sent at.

If you can reach their tool, offer to create these and do it only after a yes. If not, give the
fields as a list they can create in five minutes. A spreadsheet with three tabs is a fine start.

### 4. Write the message kit
Draft every message in their voice, with `[placeholders]` for names, links and times. Keep each
short. Show them all, then revise until they approve.

| Message | When it goes | Sent by |
|---|---|---|
| Invite (signup link + agreement) | after the approver's click | routine / automation |
| Booking confirmation + calendar invite | on every booking | routine / automation |
| Reminder | 24 hours before | routine / automation |
| Reminder | 1 hour before | routine / automation |
| Re-invite after a no-show | the next day, once ever | routine / automation |
| Re-invite after a cancel | after 7 days, once ever | routine / automation |
| Nudge | day 5 after the invite, if never booked | routine / automation |
| Rebook link | within minutes of a host cancelling | routine / automation |
| Your session moved | when a host moves a booked session | **a person**, always |
| Host roster | the day before, only if someone booked | routine / automation |
| Welcome + chat invite | host clicked Send Welcome, agreement on file | routine / automation |
| Signing link only | host clicked Send Welcome, no agreement on file | routine / automation |
| Check-in | welcomed but not in chat after 24 hours | a person |

### 5. The daily routine (day one)
Give them a checklist that runs the whole process by hand in about half an hour a day, in this order:
1. **New sign-ups:** check each against existing people by exact email. One match: it's a returning
   volunteer, so update, don't duplicate. Zero or several: stop and look. Queue the rest for the approver.
2. **Approved yesterday:** send invites.
3. **New bookings:** send confirmations and calendar invites.
4. **Tomorrow's sessions:** send 24-hour reminders; send each host their roster, or nothing if empty.
   **Today's sessions:** send 1-hour reminders.
5. **Missed or cancelled:** send the one re-invite if it hasn't been used. If it has, flag it for a person.
6. **Invited 5 days ago, never booked:** one nudge.
7. **Host clicked Send Welcome:** agreement on file → welcome + chat invite. None → signing link only.
8. **Welcomed 24 hours ago, not in chat:** flag for a check-in.

Mark a message sent only after it has actually gone.

**With an AI assistant:** the organizer can paste or connect the tracker each morning and say "run
today's onboarding routine". Then you: list what's due under each step above, draft every message
from the kit, and list the decisions that need a person (approvals, unmatched sign-ups, second
misses, moved sessions). Draft only. A person sends, or approves sending, and you update the tracker
only after they confirm.

### 6. The first three automations
Walk them through these in **their** automation tool, click by click if they want. These three are
where the playbook says to start, and they remove most of the daily routine:
- **Confirmations.** Trigger: a new booking. Action: send the confirmation and calendar invite, then
  set *Confirmation sent at*.
- **Reminders.** Trigger: a schedule, hourly. Find bookings with status Booked, a session 24 hours
  (or 1 hour) away, and no reminder sent. Send, then set the timestamp.
- **Re-invites and the nudge.** Trigger: a schedule, daily. Missed yesterday and *Re-invite used* is
  no → send and set it to yes. Cancelled 7 days ago, same rule. Invited 5 days ago with no booking → nudge.

Every automation follows two rules: write the "sent" timestamp only after the send succeeds, so a
failure retries next run; and never send a second re-invite.

### 7. The build list
Hand over the rest as a list. For each item give what it does, the rule it must follow, and how
they'll know it works. Don't build these in this session unless they ask.

| Item | What it does | The rule it must follow |
|---|---|---|
| Duplicate matching on intake | Matches a new sign-up to an existing person by exact email | Never create a person to fix a booking |
| Signature gate | On Send Welcome, sends the welcome or the signing link based on evidence | The click is the judgment; evidence, not a checkbox |
| Welcome on signing | When an agreement arrives, sends the welcome without anyone asking | Version, date and submission ID must match |
| Calendar sync | Keeps calendar guests matching the bookings | Bookings are the source of truth; the calendar only mirrors them |
| Moved-session detection | Notices a booked session's time changed and flags it | Flag it for a person; never guess |
| Chat routing | Adds new chat members to their skill channels | Unmatched requests go to a person |
| Stalled-joiner alert | Flags welcomed people not in chat after 24 hours | One alert per person |

End with the freeze date from the interview: no automation changes in the weeks before their crunch.

---

## Guardrails
The six guardrails in the README apply to everything above, including drafts. In particular: never
create a person to fix a booking, never send a second automatic re-invite, retitle cancelled
sessions instead of deleting them, and leave the three human decisions with people.
