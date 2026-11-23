---
name: what-stays-human
description: >-
  Keeps one register of every way a team uses AI, sets how much review each use gets, and
  loosens that review as a use earns trust. Each use gets an owner (a role, not a person), a review
  level from 0 to 3, and a check against four bars for what stays human: judgment, relationship,
  legal standing, and voice and strategy. Four modes: setup (where the register lives, who owns
  what, and the team's hard lines), log (one new AI use, one intake), sweep (inventory what's
  already in use), and check-in (move review levels up or down from the record, and write what the
  register says about buying, guidance and training). Use when someone says "log this AI use",
  "can we use AI for this", "what AI are we using", "set up our AI register", "run the AI
  check-in", "who owns this tool", or "does this need legal".
license: MIT
---

# What Stays Human

> **One line:** every AI use your team has, in one place, with an owner and the right amount of
> review. **You can't steer what you can't see.**

Most teams handle AI in one of two ways. Either nobody tracks it, so leaders can't say what the team
is actually doing, or every use goes through the same heavy review, so people stop asking and use
it quietly. This skill does neither. It logs every use in one register, gives each one only as much
review as it needs, and lets that review loosen as the use proves itself.

It is not a policy, and it is not legal advice. It tells you which uses need a lawyer or a
specialist to look. It doesn't stand in for them.

It is built on five beliefs:

1. **You can't steer what you can't see.** One register beats five trackers and a Slack thread.
   Once every use is in one place, it can tell you what to buy, what guidance to write, and who
   should be talking to whom.
2. **Some steps stay human no matter how good the tool gets.** A step stays human if it needs
   judgment, a relationship, legal standing, or voice and strategy. Everything else is a candidate
   for automation. See [The four bars](#the-four-bars).
3. **Review earns its way down.** A new use starts with more review than it probably needs. Each
   clean stretch earns one notch less. A problem moves it back up at once. Relationship steps
   never loosen.
4. **The owner is a role, not a person.** "Head of post" owns it, not Dana. When Dana leaves, the
   use still has an owner. An empty role is an honest answer, and a hiring signal.
5. **Nothing gets written until a person says so.** The skill proposes. A human approves.

---

## Modes

| Mode | When | What you get |
|---|---|---|
| **setup** | Once, at the start | The register, the roles, and the team's hard lines, written into `standard.md` |
| **log** | Someone wants to start using AI for something | One register row, a starting review level, and the steps that stay human |
| **sweep** | Once at the start, then whenever you suspect drift | Proposed rows for everything already in use, gaps first |
| **check-in** | Monthly or quarterly | Review levels moved up or down from the record, unowned uses flagged, and a short read-out |

If the ask doesn't name a mode, pick one from the table and say which in one line.
**No `standard.md` yet?** Run setup first, say so in one line, and keep it short.

---

## The register (one row per AI use)

A use is one job AI does for the team, not one tool. "Drafting first-pass captions" and "summarizing
client calls" are two rows even if both run in the same tool. Columns, in this order (the same as
[`register-template.csv`](register-template.csv)):

| Column | What goes in it |
|---|---|
| `id` | `AI-001`, `AI-002`… Never reused, never renumbered |
| `use` | What AI does, as a sentence: "Drafts first-pass captions from the edit's transcript" |
| `team` | The team that runs it |
| `owner_role` | The role that answers for it. A role, never a name |
| `escalation_role` | Who the owner goes to when it goes wrong |
| `tool` | The tool and the plan or account it runs on (a personal account is worth knowing about) |
| `data_in` | The most sensitive thing it touches: `public` · `internal` · `personal` · `client or licensed` · `confidential` |
| `output_goes_to` | `team only` · `client` · `public` |
| `human_steps` | The steps that stay human, each tagged with its bar: "Approve final captions (voice)" |
| `review_level` | `0`–`3`, see [The review dial](#the-review-dial) |
| `floor` | The lowest level this use may ever reach, and why |
| `clean_runs` | Runs or weeks since the last problem or change |
| `last_check` | Date of the last check-in that looked at it |
| `status` | `proposed` · `active` · `paused` · `retired` |
| `notes` | What it's taught you. This column feeds the check-in read-out |

The register lives wherever the team already keeps lists: a sheet, Airtable, Notion, a tracker. A
CSV is fine to start.

---

## The four bars

A step stays human if it meets **any one** of these. Ask them in order; the first yes settles it.

| Bar | The test | Examples |
|---|---|---|
| **Judgment** | Is there a trade-off no rule settles, where someone has to weigh it and own the call? | Picking the take, approving a budget change, deciding a cut is done |
| **Relationship** | Does someone on the other end expect a person? Would they feel misled to learn it wasn't one? | A note to talent, a hard conversation with a vendor, a thank-you |
| **Legal standing** | Does it need a signature, consent, a license, or someone who can be held liable? | Clearing a likeness or a voice, signing a release, accepting delivery terms |
| **Voice and strategy** | Does it say what the team stands for, or set direction? | A public statement, a pitch's point of view, next year's priorities |

If none apply, the step is a candidate for automation, with whatever review the dial sets. Write
the bar next to every human step so the next person knows *why* it stays human.

**Two ways the line moves over time.** Approve and review steps shrink as trust grows: that is the
dial. Relationship steps never do. A thank-you note doesn't get more automatable because the last
fifty went well.

---

## The review dial

| Level | Name | What happens | Typical start |
|---|---|---|---|
| **3** | Specialist review | A named specialist (legal, rights, security, a client's own reviewer) clears it before use | Likeness or voice, licensed or client material, personal data, anything public that makes a claim |
| **2** | Sign-off | The owner role approves each output before it leaves the team | Anything going to a client or the public |
| **1** | Spot check | The owner samples outputs on a schedule (say one in ten, or weekly) | Internal work that touches internal data |
| **0** | Logged | It's in the register and the owner runs it. No routine review | Internal drafts on public or internal data |

**Starting level.** Take the highest level any of these call for: what data goes in (`data_in`),
where the output goes (`output_goes_to`), and the team's hard lines from `standard.md`. When unsure,
start one level higher. It's cheap to loosen and expensive to explain.

**The floor.** Some uses can never drop below a level, whatever the record says. A use that touches
someone's likeness or voice keeps specialist review. A use that sends anything to a client keeps at
least sign-off. The team sets its floors in setup, and each row records its floor and why.

**Moving down.** At a check-in, a use with a clean record since its last change drops **one** level,
never more, and never below its floor. "Clean" is set in setup (default: four weeks or ten runs,
whichever comes later, with no problems logged).

**Moving up.** Any problem moves a use back up to the level that would have caught it, right away,
not at the next check-in. A changed tool, model, plan or data source resets `clean_runs` to 0.

---

## Mode: setup

**Detect first, then ask only about the gaps.** Ask once for anything the person can link: an
existing AI policy, a tool list, a spreadsheet someone started, the org chart. Read all of it first.

Then ask what's still missing, in **one message, at most six questions**, each with a guess filled
in so the person can just say yes:

1. **Where should the register live?** *(Guess: a sheet next to your other trackers.)*
2. **Which roles own AI uses, and who do they escalate to?** Roles, not names. *(Guess: each team
   lead owns their team's uses and escalates to the head of operations.)*
3. **Who are your specialists for level 3?** *(Guess: outside counsel for rights and likeness, your
   IT lead for data.)* If there are none, say so; level 3 then means "ask before using, and log
   who you asked".
4. **What are your hard lines?** Things that always start at level 3, or that you don't use AI for
   at all. *(Guess: anything involving a real person's likeness or voice; anything under a client's
   confidentiality terms.)*
5. **What counts as a clean record?** *(Guess: four weeks or ten runs with no problems.)*
6. **How often do you want a check-in?** *(Guess: monthly for the first quarter, then quarterly.)*

Write the answers into `standard.md` (start from [`standard-template.md`](standard-template.md)),
filling every blank and marking anything you guessed `default, change me`. Stage it, and write it
only after a "go".

---

## Mode: log

One new use, one intake. Use it when someone asks "can we use AI for this?"

1. **Get the facts in one message.** What the AI would do, which tool and account, what data goes
   in, where the output goes, and who's asking. Fill in what you can from the ask itself.
2. **Check the register first.** If the same use, or a near match, already exists, say so and
   propose adding a note to that row instead of a new one. Two teams doing the same thing should
   probably be talking.
3. **Walk the steps.** Break the use into its steps. Run each one past the four bars. List the
   steps that stay human, each with its bar.
4. **Set the dial.** Propose a starting level and a floor, each with a one-line reason.
5. **Name the owner.** A role. If no role fits, say so plainly: "No one owns this yet." Don't
   invent one.
6. **Stage one numbered review** and wait for a "go", or edits by number.

If a hard line applies, say so first, before anything else, and name who to ask.

---

## Mode: sweep

The first inventory, or a re-check when you think the register has fallen behind.

1. **Gather.** Ask for whatever shows real use: software bills and expense reports, the tool admin
   pages, a quick survey ("what do you use AI for, and in which tool?"), meeting notes. Bills and
   admin pages beat memory. Recurring charges show tools nobody mentioned.
2. **Propose rows** for each use found, using the log steps above. Mark every value **found** (and
   where) or **guessed**.
3. **Put the gaps first:** uses with no owner, uses on personal accounts, uses that touch client or
   personal data with no review, and uses that look the same across teams.
4. **Stage it as one numbered review.** For more than about 15 rows, stage in batches of 15.

Never call a tool "unused" because nobody mentioned it. Say "not mentioned yet".

---

## Mode: check-in

Monthly or quarterly. This is where the register pays for itself.

1. **Move the dial.** For every active row, propose up, down or hold, each with its reason (clean
   runs, a logged problem, a changed tool). One level at a time, never below the floor.
2. **Flag what's drifting.** Rows with no owner, an owner role that's empty, a `last_check` older
   than two check-ins, or a `status` of proposed for more than a month.
3. **Write the read-out.** Five short sections, each a few lines, each citing the rows it rests on:
   - **What to buy or build.** Which uses are most common, and whether a team plan, a shared
     license or one in-house build would serve them better than many separate accounts.
   - **What guidance to write.** The questions people keep asking and the problems that keep
     showing up. Each is a line in your guidance.
   - **Who should talk.** Teams doing the same thing separately.
   - **What leadership can say.** Two or three plain, true sentences about how the team uses AI,
     backed by the register's numbers.
   - **What changed.** Levels moved, uses added, paused or retired.
4. **Stage the dial changes as one numbered review.** The read-out goes in the chat unless the
   person asks for a doc.

---

## Guardrails (every mode)

- **Read-only until "go".** Every write to the register or `standard.md` is staged first as one
  numbered review. A person replies `go`, or edits by number.
- **Not legal advice, ever.** Never say a use is "compliant", "cleared" or "safe". Say what level of
  review it gets and who does it. When a question is really a legal one, say so and name the
  level 3 specialist from `standard.md`.
- **Roles, not people.** Never write a person's name in `owner_role` or `escalation_role`.
- **No invented numbers.** If the register doesn't show it, the read-out says "not tracked yet".
  Say how many rows a claim rests on.
- **Edit in place.** One register, one `standard.md`. Never a "v2". Retired rows stay, marked
  `retired`, so the IDs and the history survive.
- **Nobody is notified without a go.** No message to an owner, a specialist or a team until a
  person approves the exact text.

---

_Built by Alex Parks from two pieces of his own work: the way a global studio tracked and steered
its generative AI use across every production, and the human-in-the-loop standard he wrote for a
volunteer-run organization. Shared under the MIT License._
