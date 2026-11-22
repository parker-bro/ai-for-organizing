# Strategy Series

A drop-in AI skill that runs a planning series end to end: from the first look at everything on
your plate to a short list of goals your leaders agree to, on schedule.

**Nothing in scope gets ignored, and only a few things get chosen.**

It works before and after each session, never live in the room. It proposes; a person approves.
Nothing is written, sent or booked until someone says "go".

## What it does

| Mode | When you use it | What you get |
|---|---|---|
| **setup** | Once, at the start | A short interview (it reads what you already have first) and a series profile every other mode reads |
| **plan** | After setup | A session calendar with prep blocks and pre-read dates |
| **intake** | Start of the series, and before each session | Every live project matched to where it gets decided, with the gaps first |
| **build** | Before each session | The agenda and the deck outline, built around written asks |
| **wrap** | After each session | One verdict for every ask, an owner for every decision, and the changes queued |
| **goals** | After each wrap, and once at the end | The goals, drafted and pressure-tested in your format |

## Any goal format

OKRs, goals and KPIs, Rocks, OGSM, V2MOM, or your own template. Setup recommends one if you don't
have one, or builds an adapter from the template you already use. Every mode drives your format the
same way: each session feeds it, each wrap writes to it, and the final pass tests it for quality,
measurability and size. See [`frameworks.md`](frameworks.md).

## Install

1. Download this folder.
2. Add it as a skill in your AI tool (in Claude: Settings → Capabilities → Skills, or drop the
   folder into your skills directory).
3. Say "set up our strategy series". It will ask for anything you can link, read it, and ask only
   what it still needs.

It works with whatever you already use: any doc tool, any tracker, or plain notes. Connecting your
docs and tracker makes it faster, not different.

## Files

- [`SKILL.md`](SKILL.md) — the beliefs, the profile, the guardrails and the edit pass
- [`frameworks.md`](frameworks.md) — the goal formats, as eight slots each
- [`modes/`](modes/) — one file per mode
- [`profile-example.yaml`](profile-example.yaml) — a filled example profile (made up)

Built by Alex Parks from a planning series he runs for a volunteer-run organization.
MIT License.
