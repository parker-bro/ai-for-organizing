# Volunteer Onboarding: Automate Everything Except Judgment

**Category:** Volunteer Engagement · **Type:** Workflow · **License:** CC BY 4.0
**Visual:** [Volunteer Onboarding Visuals](https://docs.google.com/presentation/d/1tL_y3qTbsalg2yBNouJ1_39k1SnZV0V-S_nxgedPSY4/edit). Lead with the "Every Path" map slide.

Before this, volunteer onboarding ran through one or two people. Volunteers often sat in our
queue for weeks without a response, and many gave up before we got to them. Now onboarding runs as
a rolling series of short group sessions that any of several admins can host, and each volunteer
books through a personal signup link. The goal is first submission to matched with a project in
under a month.

---

## The method

1. **Write down the ideal volunteer journey end to end,** from first application to their first
   place in the team Slack. Include every detour: cancel, no-show, return, unsigned paperwork.
2. **Mark every step as human or machine.** A step stays human only if it needs judgment or a
   relationship. Everything else gets automated.
3. **Give each human one decision per stage** and make that decision a single click. Everything
   between the clicks runs on its own.

The result is three human decisions and dozens of automated steps. Our people spend their time
pitching the org and getting to know volunteers, not chasing calendars.

---

## The spine: five stages

| Stage | Volunteer experience | Who acts |
|---|---|---|
| **1. Apply** | Fills out the intake form. | Machine creates and dedupes the person record |
| **2. Invite** | Gets a personal signup link and the volunteer agreement. | 🧑 **Admin approves** (one click), then the machine sends |
| **3. Book** | Picks an orientation session. Gets a confirmation, a calendar invite, and reminders 24 hours and 1 hour before. | Machine |
| **4. Attend** | Joins a live group orientation. | 🧑 **Host runs it**: pitches the org, sets expectations, sense-checks fit |
| **5. Access** | Gets the welcome email and Slack invite, then is routed into their skill channels. | 🧑 **Host clicks "Send Welcome"**, then the machine picks the right email |

**One human judgment per stage: approve, host, clear. Everything between is automated.**

---

## The rules that make it work

### New vs. returning volunteers
- Returning volunteers use the **same open signup link and the same session** as newcomers. There's
  no separate track to maintain.
- **A refresher never moves anyone backwards.** Someone already active stays active. Someone
  who lapsed is reactivated. The system never resets their history.
- **A signup is matched to a person by exact email.** Exactly one match means they book like anyone
  else. Zero matches or more than one goes to "Needs Review", nothing is sent, and a human either
  links them to their existing record or sends them the intake form.
- ⛔ **Never create a new person to fix a booking.** An unmatched email is usually the same volunteer
  with a new address. Creating a duplicate splits their history from their registration. **The
  intake form is the only door that creates a person.**

### Indemnification (the volunteer agreement)
- **Access is gated on evidence of signature, not on a checkbox.** Each signature records how it was
  verified:
  - **Form, verified:** signed through their personal link. Version, date and submission ID must
    match exactly. All new signatures land here.
  - **Manual, ops-verified:** an admin confirmed a signature that arrived some other way. Rare.
  - **Legacy:** people flagged as signed in the old system before this process existed. They're
    trusted, they aren't asked to re-sign at a refresher, and the carve-out is never widened to
    anyone new.
- **The host never checks paperwork.** The host clicks "Send Welcome" for the people they're
  clearing, and the system decides:
  - Signed → welcome email and Slack invite, status set to active.
  - Unsigned → a signing link only, no access yet.
  - When they sign, the welcome sends itself. Nobody chases.
- **An unsigned attendee is the most common outcome, and it needs nothing from anyone.**

### Cancellations and changes: every detour has exactly one way back
| What happens | What the system does |
|---|---|
| Volunteer changes their session | They resubmit their personal link and the latest booking wins. Earlier bookings are cancelled automatically, and a new confirmation goes out. |
| Volunteer cancels or declines | Re-invite after 7 days |
| Volunteer misses the session | Re-invite after 1 day |
| Host cancels a session | Rebook link sent within minutes |
| Host moves or deletes a session | A human emails the volunteer. This one is deliberately human: see below. |
| Invited but never booked | One nudge on day 5 |

- **One automatic re-invite, ever,** across every path. After that, a human decides.
- **Hosts retitle a cancelled session "CANCELLED". They never delete it.** Deleting strands the
  bookings attached to it.
- **Why a host's move stays human:** a moved calendar block looks like an ordinary update, and it
  quietly rewrites the time under a live booking. We learned this when a reminder went out with the
  old time. The system now flags it so a person tells the volunteer, rather than guessing.

### Multi-owner scheduling
- **Admins** own approval. **Hosts** own their availability, by blocking time on a shared calendar
  that becomes bookable sessions, and they own the session itself. **The system** owns everything
  between.
- **One source of truth for who's booked.** The calendar only mirrors it. If an admin removes a guest
  in the calendar, the next hourly pass adds them back. Changes happen in one place.
- **Hosts hear about a session once, and only when it matters.** The day before, they get a roster,
  or nothing if nobody's booked.

### Access and Slack
- An hourly check matches new Slack members to cleared volunteers by email and adds them to the
  channels for their skills. Requests that don't map to a channel get a routing post for a human.
- **Joined Slack before being cleared:** one warning, then channels follow once they're welcomed.
- **Welcomed but never joined after 24 hours:** one alert per person. Two or more stalled at once
  usually means the invite link is broken.

---

## Guardrails (each one exists because breaking it once cost a volunteer an email, a booking or their history)

1. **The click is the judgment.** Only the host's "Send Welcome" grants access. No script clears
   anyone.
2. **Never create a person to fix a booking.** Unmatched signups are linked by hand or sent the
   intake form.
3. **Retitle, never delete.** A cancelled session says CANCELLED.
4. **One re-invite, ever.** Then a human decides.
5. **Never mark an email sent until the mail system confirms it.** A failure leaves the record
   unmarked so the next run retries.
6. **Freeze the system before a crunch.** No automation edits in the weeks before Election Day.

---

## How someone else would use this

- **Without our stack:** the stage table, detour table and guardrails are the playbook. Map them
  onto whatever you use (a form tool, a shared calendar, email, Slack) and decide which steps you
  automate first. Start with confirmations, reminders and the re-invite rules.
- **With an AI assistant:** give it this document as the operating rules for your onboarding, and
  have it compose reminders, nudges and rosters, while the three human clicks stay human.
- **Our build, for reference:** Airtable (records, forms, interfaces), Google Calendar (host
  availability), Gmail, Slack, and a set of small scheduled scripts run by an AI agent. The scripts
  are tied to our schema, so we're sharing the workflow, not the code.

---

## Status
Live since August 2026. We're judging it on time from first submission to project match; it's
too early for a meaningful number.

_Built by Alex Parks for a volunteer-run political organization, 2026. Shared for the AI for
Organizing Prize under CC BY 4.0._
