# project-board — Working Guide

Project management content for view-markdown. Separate from the stable reference docs in `docs/`.

---

## Working Principles

We work incrementally towards a goal. In each step:

1. **Don't assume. Don't hide confusion. Surface tradeoffs.**
2. **Minimum code that solves the problem. Nothing speculative.**
3. **Touch only what you must. Clean up only your own mess.**
4. **Define success criteria. Loop until verified.**

A project may add overrides below. If it does, the project rule wins for that project.

---

## The rule

**Nothing gets worked on unless it is on the board.**

This applies to agents and humans equally. Before starting any work — a new feature, a fix, a refactor, an investigation, a one-off task — it must exist on the board in some form. If it is too small for a track, it goes in the [adhoc track](tracks/adhoc.md).

---

## Structure

- `board.md` — top-level view of all tracks and their current status
- `tracks/*.md` — one file per track (including `adhoc.md`)
- `project-docs.json` — legacy config (kept for reference)

---

## How tracks work

Each track file has three sections:

### Current focus
What is actively being worked on right now. One clear statement. If nothing is in flight, this should say "idle".

### Next steps
An ordered list of concrete upcoming work items. The top item is what gets picked up next.

### Work log
A reverse-chronological table of what has been completed. One row per session or meaningful unit of work. Date + what was done. This is the record of what we have achieved.

---

## Adhoc track

For work that does not belong to any named track — quick fixes, experiments, tooling tweaks, one-off investigations. Items still get logged. See [tracks/adhoc.md](tracks/adhoc.md).

The bar for adding an adhoc item is low. If you did it, log it.

---

## How we work — incremental by default

**Do one next step. Then stop and show the result.**

We work in small, deliberate increments. There is always a longer-term goal, but the direction changes frequently — after a single iteration, priorities shift, scope narrows, or something unexpected is discovered. Over-running wastes work and makes it harder to change course.

What this means in practice:

- **One step at a time.** Pick the top item from **Next steps**. Do that. Stop.
- **Do not chain steps without checking in.** Completing step 1 does not mean starting step 2. Show the result first.
- **Do not gold-plate.** Only do what was asked. Do not refactor adjacent code, add extra features, or improve things that were not mentioned.
- **Do not plan out loud and then execute everything.** Presenting a plan is fine; executing the whole plan unprompted is not.
- **Small is good.** A focused change that can be reviewed in a minute is better than a large change that requires re-reading the whole codebase.

The goal on the board is directional — it describes where we are heading, not a specification of everything that must be done. Expect the goal to evolve.

---

## Agent instructions

When an agent starts a session:
1. Read `board.md` to understand the current state of all tracks.
2. Read the relevant track file(s) before touching anything.
3. Update **Current focus** at the start of work.
4. Do the **single top item** from Next steps — then pause for review.
5. Update **Next steps** and append a row to the **Work log** after completing work.
6. Update the `Updated` date in `board.md` for any track that was touched.

Do not start work that is not reflected on the board. Do not finish a session without updating the board. Do not proceed to the next step without being asked.
