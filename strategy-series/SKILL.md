---
name: strategy-series
description: >-
  A goal-setting companion that runs a strategy series end to end, from the first look at
  everything on your plate to a short list of goals your leaders agree to. It works before and
  after each session, never live in the room. Six modes: setup (interview you and write the series
  profile), plan (propose the session calendar), intake (check that nothing in scope has been
  forgotten), build (write each session's agenda and deck outline), wrap (check the transcript
  against the agenda and give every ask one verdict), and goals (draft and pressure-test the final
  goals in whatever format you use: OKRs, goals and KPIs, Rocks, OGSM, V2MOM or your own). Use when
  someone says "set up our strategy series", "plan our planning sessions", "what are we forgetting",
  "build the agenda for session 2", "wrap the strategy session", "draft our goals", or "check our
  OKRs".
license: MIT
---

# Strategy Series

> **One line:** it turns everything on your plate into a few goals your leaders agree to, on
> schedule. **Nothing in scope gets ignored, and only a few things get chosen.**

Most planning fails in one of two places. Either the sessions are good conversations that end in
"let me think on it", or the goals come out as a long list nobody can hit. This skill works on both.
Every session is built around written asks, every ask gets a verdict, and every output ranks before
it trims.

It is built on five beliefs, each learned by running a real series:

1. **Silence is not a decision.** A topic the room never reached is not settled, whatever the
   agenda's default said.
2. **Agreeing on something is not owning it.** Every decision needs an owner and a date, or it
   is a wish.
3. **Rank, don't trim.** Keep the few things that clearly move a goal. Everything else goes on a
   "not now" list that names the goal it failed to move. Nothing is silently dropped.
4. **A session is only as good as its asks.** If the options can't be written before the meeting,
   the topic isn't ready for a decision. Call it a discussion and cap its minutes.
5. **Nothing gets written until a person says so.** The skill proposes. A human approves.

---

## Modes

| Mode | When | File |
|---|---|---|
| **setup** | Once, at the start. Again if the series changes shape | [`modes/setup.md`](modes/setup.md) |
| **plan** | After setup: propose the sessions, dates and prep blocks | [`modes/plan.md`](modes/plan.md) |
| **intake** | Series start, after any change to the series, and before each session's prep | [`modes/intake.md`](modes/intake.md) |
| **build** | Each session's prep: the agenda and the deck outline | [`modes/build.md`](modes/build.md) |
| **wrap** | After each session, with the transcript or notes | [`modes/wrap.md`](modes/wrap.md) |
| **goals** | After every wrap (small writes), and once at the end (the full pass) | [`modes/goals.md`](modes/goals.md) |

Read only the mode file you need, plus this file. If the person's ask doesn't name a mode, pick it
from the table and say which one you picked in one line.

**No profile yet?** Every mode except setup needs the series profile. If none exists, run setup
first, say so in one line, and keep the interview short.

---

## The series profile (the one shared config)

Every mode reads one file, the **series profile**. Setup writes it; the person can edit it by hand
any time. It holds the facts about this series, so no mode ever hardcodes them.
A filled example is in [`profile-example.yaml`](profile-example.yaml).

```yaml
org: "<name>"
series: "<e.g. 2027 planning>"
period: "<what the goals cover, e.g. 2027-01-01 to 2027-12-31>"
ratify_by: "<date the final goals are agreed>"
people:
  drafter: "<who writes the drafts>"
  approver: "<who signs off>"           # can be the same person, or a small group
  decision_makers: ["<name>", "<name>"] # the only people who can own a decision
standing_goals:                         # what every topic is tested against
  - "<goal the org already has>"
goal_framework: okr | goals_kpis | rocks | ogsm | v2mom | custom   # see frameworks.md
framework_rules: {}                     # only for custom, or to override a framework's defaults
homes:
  tracker: "<where projects and tasks live: Airtable, Asana, Notion, Linear, a sheet, or none>"
  decisions: "<where decisions and open questions live>"
  goals_doc: "<link to the goals doc>"
  not_doing_list: "<heading or doc that holds what you decided not to do>"
  deck: "<link to the series deck, if there is one>"
sessions:
  - key: s1
    title: "<short title>"
    date: "<YYYY-MM-DD>"
    minutes: 120
    agenda_doc: "<link>"
    covers: ["<theme>", "<theme>"]
solo_streams:                           # work one person runs alone, with no session of its own
  - "<e.g. fundraising, owned by the director>"
```

---

## Guardrails (every mode)

- **Read-only until "go".** Every write to a tracker, a doc or a calendar is staged first, as one
  numbered review. A person replies `go`, or edits by number.
- **Edit in place.** Agendas, decks and the goals doc already have links in calendar invites and
  chat. Never make a "v2" or a clean copy. Before rewriting existing text, copy it into an
  "Earlier content" section (or tab) of the same doc, dated, newest first.
- **No new docs without a yes.** Outputs land in the homes in the profile. A one-time report goes
  in the chat.
- **Nobody is notified without a go.** No email, chat message or calendar change from this skill
  until a person approves the exact text.
- **Only the profile's `decision_makers` own decisions.** Anyone else goes in the notes.
- **Confidential by default.** Strategy sessions name people, money and politics. Nothing from a
  transcript goes to a shared channel unless a person approves it.
- **Historical numbers are directional.** Say where a baseline came from, how many rows it rests on
  and how old it is. Never set a target or deadline from old data alone.
- **Never invent a number.** No baseline in the source means `baseline: none yet`.

---

## The edit pass (every output, before a person sees it)

Run it on every agenda row, slide line, review and goals-doc entry.

1. **Rank, don't trim.** Keep the few that clearly move a standing goal. The rest go to "Not now",
   each naming the goal it didn't move.
2. **The title is the takeaway.** A sentence with the so-what, never a label. "43 of 108 clients
   never came back, and we don't record why", not "Client retention".
3. **One question per topic,** open enough to make the decider think, not a yes or no.
4. **Same words everywhere.** The deck title, agenda row, recap line and goals entry for one topic
   match word for word.
5. **One line, one idea, and no shorthand.** Write "we'll decide this at the March 4 session", not
   "→ Mar 4".
6. **Show where a summary came from** (the doc, the record, the speaker), and write lines that can
   be said out loud.
7. **Fewer words than feels safe.** Then cut again.

---

_Built by Alex Parks from a planning series he runs for a volunteer-run organization. Shared under
the MIT License._
