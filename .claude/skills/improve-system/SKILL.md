---
name: improve-system
description: Review what just happened in the current session and update the personal operating system (/home/user/Claude) to reflect it — refine a skill's instructions if its output was corrected, save lessons/stories to Knowledge/me, and flag stale or duplicated content. Use when the user calls /improve-system at the end of a working session.
---

# Improve System

Use the current session as feedback for the personal operating system itself.
This skill doesn't do new work — it looks back at what just happened and
updates `Knowledge/`, `Skills/`, and `.claude/skills/` so the system gets
better over time.

## Step 1 — Review the session

Scan back through the conversation (as far as context allows) for three kinds
of signal:

1. **Skill iteration**: Did the user invoke a skill (e.g. `/ingest-resource`)
   and then correct, redirect, or refine its output? Look for patterns like
   "actually, put it in...", "no, summarize it differently", "next time
   do X", "that's too long/short", "you missed...".
2. **Lessons or stories**: Did the user share something personal — an
   anecdote, a lesson learned, a preference, a reflection, a decision and its
   reasoning — that isn't yet captured in `Knowledge/me/`?
3. **Staleness or duplication**: While working, did you notice (or does the
   user point out) content in `Knowledge/` that's now outdated, contradicted,
   or duplicated across files?

If none of these signals are present, say so plainly — don't manufacture
busywork.

## Step 2 — Update skill instructions (if iterated on)

If the user corrected a skill's output:

1. Identify the relevant skill file under `.claude/skills/<name>/SKILL.md`.
2. Generalize the correction into an instruction — don't just patch for this
   one case. Ask: "what rule would have produced the right output the first
   time?"
3. Edit the SKILL.md to add or adjust that instruction in the appropriate
   step. Keep edits minimal and targeted — don't restructure the whole file.
4. Briefly tell the user what changed and why, e.g. "Updated
   `/ingest-resource` to default video summaries to bullet form per your
   correction just now."

## Step 3 — Capture lessons/stories to Knowledge/me

If the user shared a personal lesson, story, or reflection:

1. Check `Knowledge/me/` for an existing file it belongs in (e.g.
   `my-story.md`, `workview.md`, `lifeview.md`) vs. whether it warrants a new
   file (e.g. recurring journal-style entries could go in something like
   `Knowledge/me/lessons-learned.md`).
2. Write it up concisely in the user's voice/tone (see
   `Knowledge/me/personal-brand-identity.md` for voice guidance) — don't
   over-edit or sanitize the substance.
3. If appending to an existing file, add a dated entry or new section rather
   than rewriting what's there.
4. Cross-reference related existing notes the same way `/ingest-resource`
   does (grep `Knowledge/` for related topics, add short links).

## Step 4 — Flag stale or duplicated content

For anything stale/duplicated/contradictory you noticed:

1. Don't silently edit or delete other files — flag them.
2. Report each as: file path(s), what's stale/duplicated, and a suggested
   resolution (merge, update, archive, delete).
3. If the fix is trivial and obviously safe (e.g. a one-line factual update
   the user just gave you, like a new job title), apply it directly and note
   that you did.
4. For anything bigger, ask the user before changing it.

## Step 5 — Summarize and commit

1. Give the user a short summary: what was updated, what was added, what was
   flagged (and left for them to decide).
2. Stage, commit (e.g. `Improve system: <short description>`), and push to
   the current branch per this repo's normal git workflow.
3. If nothing actionable was found in Step 1, skip the commit — don't create
   empty/no-op commits.

## Notes

- This skill is reflective, not generative — its job is to make the *next*
  session better, not to produce new deliverables.
- Be conservative with edits to skill files: a skill should still generalize
  well to other inputs, not be overfit to one session's example.
- When in doubt about where something belongs in `Knowledge/`, follow the
  folder definitions in the top-level `CLAUDE.md`.
