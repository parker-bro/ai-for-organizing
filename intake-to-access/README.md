# Intake → Access: Automate Everything Except Judgment

**Type:** Playbook · **License:** CC BY 4.0
**Visual:** [Onboarding Visuals](https://docs.google.com/presentation/d/1tL_y3qTbsalg2yBNouJ1_39k1SnZV0V-S_nxgedPSY4/edit). Lead with the "Every Path" map slide.

For any flow where people apply, a person decides, and access follows: volunteers, new members, a
cohort, a freelance roster, clients. The people doing the deciding should spend their time on
judgment and relationships, not on chasing calendars and paperwork. Three human clicks, and the
rest is automated: confirmations, reminders, cancellations, no-shows and rebookings, on whatever
calendar, form and email your team already uses.

It started as volunteer onboarding for a volunteer-run organization. Before it, onboarding ran
through one or two people, and volunteers sat in a queue for weeks and gave up. That build is the
worked example below, in full.

**Three steps, three human clicks:**
1. **Intake.** Take the request and file it: one record per person, deduped, with a person
   approving who moves on.
2. **Connect.** Put them in front of a person: an onboarding session, a call, or a kickoff, booked
   through their own link.
3. **Access.** Grant what they joined for: tools, channels, materials or a first assignment,
   once the paperwork checks out.

---

## The method

1. **Write down the whole journey,** from first contact to full access. Include every detour:
   cancel, no-show, return, unsigned paperwork.
2. **Mark every step human or machine.** A step stays human only if it needs judgment or a
   relationship. Everything else gets automated.
3. **Give each human one decision per stage,** and make it a single click. Everything between the
   clicks runs on its own.

---

## The pattern: six stages

The three steps, in detail. Intake is stages 1 and 2, Connect is 3 and 4, Access is 5 and 6. Most
flows use most of them. Mark the ones yours skips.

| Stage | What happens | Who acts | Skip it when |
|---|---|---|---|
| **1. Intake** | A form or request creates the person's record, deduped | Machine | Never. This is the only door that creates a person |
| **2. Decide** | Someone approves, qualifies or declines | 🧑 **One click** | Anyone who applies gets in |
| **3. Schedule** | The person books a session or a call through their own link | Machine | Nothing live is needed |
| **4. Meet** | A group session, a one-to-one call, or a kickoff | 🧑 **The host runs it** | Nothing live is needed |
| **5. Gate** | Paperwork checked: an agreement, a waiver, a contract, a tax form | Machine checks evidence | Nothing needs signing |
| **6. Access** | Welcome, tools, channels, first assignment | 🧑 **One click to clear**, then the machine sends the right thing | Never |

**The judgments are approve, meet and clear. Everything between them is automated.**

The live meeting is the stage that changes most. Groups and cohorts get a rolling group session any
of several hosts can run. Clients and single hires get a one-to-one call. Paperwork-heavy flows
(contractors, crew) should stop at "paperwork verified" and hand payroll and tax forms to the tool
that already owns them.

---

## The rules that make it work

### One person, one record
- **The intake form is the only door that creates a person.** Everything after it matches to an
  existing record.
- **Match by exact email.** One match proceeds. Zero or several go to "Needs Review", nothing is
  sent, and a person either links the record or sends the intake form.
- ⛔ **Never create a person to fix a booking.** An unmatched email is usually the same person with a
  new address. A duplicate splits their history.
- **Returning people use the same link and the same path as new ones.** A refresher never moves
  anyone backwards: active stays active, lapsed is reactivated, history is never reset.

### The gate checks evidence, not a checkbox
- Every signature records how it was verified: **through their own link** (version, date and
  submission ID match), **confirmed by a person** (it arrived some other way, rare), or **legacy**
  (trusted from before this process existed, never widened to anyone new).
- **The host never checks paperwork.** They click "clear" and the system decides: signed gets the
  welcome, unsigned gets a signing link only. When they sign, the welcome sends itself.
- **Unsigned is the most common outcome, and it needs nothing from anyone.**

### Every detour has exactly one way back

| What happens | What the system does |
|---|---|
| They change their session | They resubmit their link. The latest booking wins, earlier ones cancel, a new confirmation goes out |
| They cancel or decline | Re-invite after 7 days |
| They miss the session | Re-invite after 1 day |
| The host cancels a session | Rebook link within minutes |
| The host moves or deletes a session | A person writes to them. This one stays human: see below |
| Invited but never booked | One nudge on day 5 |

- **One automatic re-invite, ever,** across every path. After that, a person decides.
- **Retitle a cancelled session "CANCELLED". Never delete it.** Deleting strands its bookings.
- **Why a host's move stays human:** a moved calendar block looks like an ordinary edit, and it
  quietly rewrites the time under a live booking. A reminder once went out with the old time.

### Several owners, one source of truth
- **Deciders** own approval. **Hosts** own their availability (time blocked on a shared calendar
  becomes bookable sessions) and the session itself. **The system** owns everything between.
- **One source of truth for who's booked.** The calendar only mirrors it. Remove a guest in the
  calendar and the next pass adds them back.
- **Hosts hear about a session once, when it matters:** a roster the day before, or nothing if
  nobody booked.

### Access follows the click
- After clearing, the system adds people where they belong (channels, folders, a tool) based on
  what they told you at intake. Anything that doesn't map goes to a person.
- **In before being cleared:** one warning, then access follows the click.
- **Cleared but never showed up after 24 hours:** one alert per person. Two or more at once usually
  means the invite link is broken.

---

## Guardrails (each one exists because breaking it once cost someone an email, a booking or their history)

1. **The click is the judgment.** Only a person's "clear" grants access. No script clears anyone.
2. **Never create a person to fix a booking.**
3. **Retitle, never delete.**
4. **One re-invite, ever.** Then a person decides.
5. **Never mark an email sent until the mail system confirms it.** A failure leaves the record
   unmarked so the next run retries.
6. **Freeze the system before your busiest weeks.** No automation edits right before a launch, a
   season or a deadline.

---

## Worked example: volunteers

The original build, for a volunteer-run political organization. Onboarding now runs as a rolling
series of short group sessions that any of several admins can host. Each volunteer books through a
personal signup link. The goal is first submission to matched with a project in under a month.

| Stage | Volunteer experience | Who acts |
|---|---|---|
| **1. Apply** (Intake) | Fills out the intake form | Machine creates and dedupes the person record |
| **2. Invite** (Decide) | Gets a personal signup link and the volunteer agreement | 🧑 **Admin approves** (one click), then the machine sends |
| **3. Book** (Schedule) | Picks an orientation. Gets a confirmation, a calendar invite, and reminders 24 hours and 1 hour before | Machine |
| **4. Attend** (Meet) | Joins a live group orientation | 🧑 **Host runs it**: pitches the org, sets expectations, sense-checks fit |
| **5. Access** (Gate + Access) | Gets the welcome email and Slack invite, then is routed into channels for their skills | 🧑 **Host clicks "Send Welcome"**, then the machine picks the right email |

Specifics of this build:
- **The gate is a volunteer indemnification agreement.** Signed gets the welcome and Slack invite,
  and the volunteer is set active. Unsigned gets a signing link only.
- **Slack routing:** an hourly check matches new Slack members to cleared volunteers by email and
  adds them to their skill channels. Skills that don't map to a channel get a routing post for a
  person.
- **The freeze:** no automation edits in the weeks before Election Day.
- **Stack:** Airtable (records, forms, interfaces), Google Calendar (host availability), Gmail,
  Slack, and small scheduled scripts run by an AI agent. The scripts are tied to that schema, so this
  shares the workflow, not the code.
- **Status:** live since August 2026, judged on time from first submission to project match.

## Other shapes it fits

- **A freelance roster.** Intake is the availability form. Decide is "add to roster". Meet is a
  short call, or nothing for people you've booked before. Gate is the contract and tax form, checked
  for evidence, with payroll left to the tool that owns it. Access is the roster, the shared drive
  and the first booking.
- **New members or a cohort.** Very close to the volunteer build: an application, an approval, a
  group welcome session, a code of conduct as the gate, then channels and a first event.
- **Clients.** Intake is the inquiry form. Decide is qualification. Meet is a one-to-one kickoff.
  Gate is the signed proposal and deposit. Access is the shared workspace and the first
  deliverable date.

---

## How to use it

- **Without new tools:** the pattern table, the detour table and the guardrails are the playbook.
  Map them onto what you already have (a form, a shared calendar, email, a team chat) and automate
  confirmations, reminders and the re-invite rules first.
- **With an AI assistant:** give it this document as the operating rules for your flow, and have it
  write the reminders, nudges and rosters. The human clicks stay human.

_Built by Alex Parks, 2026. The volunteer build won the AI for Organizing Prize. Shared under
CC BY 4.0._
