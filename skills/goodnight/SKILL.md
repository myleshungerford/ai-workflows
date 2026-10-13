---
name: goodnight
description: Close a work session by spotting reusable lessons, observed workflow failures, stale artifacts, knowledge about how things work, and context worth preserving. Use when asked for goodnight, session closeout, or a handoff for next time.
---

# Goodnight

Review the session before closing it. Do not assume it is nighttime. Complete the requested closeout rather than simply promising to remember.

Use the user's project conventions and existing authorization. This workflow does not authorize global configuration changes, deletion, commits, or publication by itself. If files or earlier context are unavailable, identify the gap and provide a handoff draft in the conversation instead of claiming to have saved it.

## 1. Spot reusable lessons

Look for a repeated method, a useful technique discovered through trial and error, or an explicit user correction that applies to future tasks.

Distinguish a reusable process from a durable collaboration preference. Put a process in a relevant skill; put a general preference in the project's or assistant's instruction file. A fact about how a process, system, or data source behaves goes to step 4 instead. A repeated specialist role may justify reusable agent instructions when the host supports them, but do not invent a configuration format.

Reject one-off narratives, transient errors, speculative improvements, and machine-specific workarounds presented as universal rules. Check existing instructions for overlap. Prefer a small patch to a relevant skill over creating another skill.

For each worthwhile lesson, cite the session evidence and identify its proposed home. Apply an authorized, scoped change; otherwise present the exact proposed edit. Before creating a new skill, establish that no existing one fits. A fresh reviewer can check a borderline case if available and authorized, but is not a required gate for routine closeout.

## 2. Spot observed workflow failures

Inspect only workflows exercised in this session. A finding needs an actual missed case, wrong result, manual workaround, or clear trigger failure. Age, wording preferences, and hypothetical edge cases are not defects.

State which instruction failed, the evidence, and the smallest correction. Do not count the same correction again if step 1 already handled it. Preserve a recoverable copy or version-control diff before changing durable instructions. Check naming, metadata, linked files, and the behavior the change is meant to improve.

If nothing warrants a change, say so. Do not manufacture work to make the closeout look useful.

## 3. Spot stale guidance and misleading artifacts

Inspect files touched or relied on during this session for verified contradictions or scratch artifacts likely to be mistaken for current output. Cite the file and the session fact that contradicts or supersedes it.

Correct an unambiguous factual error when authorized and in scope. Do not reorganize or delete files for tidiness. Preserve uncertain or unrelated files. If cleanup requires a consequential choice, record the specific issue and proposed action instead.

## 4. Record how things work

Ask one question: what did this session learn about how something works (a process, a system, a data source, an organization's rules), or what did the user decide about how a kind of case is handled, that the next session would otherwise have to rediscover or ask about again?

The other steps miss this. A skill holds how to do a task, an instruction file holds how the user likes to work, and a handoff holds where the work stands. None of them records how the systems and processes behind the project actually behave. In a long project, re-deriving that and re-asking for decisions already made can be most of the rework.

- **Look in the user's messages.** Questions like "why does this look wrong?" or "what do I do about this?", and the answers or rulings that followed, show where the time went.
- **Keep the bar high.** Record it only if it cost real time to establish or is a ruling the user actually gave. Either way, it must be something that will come up again. Leave out one-off answers, current work state (it belongs in the handoff), procedures (they belong in a skill), collaboration preferences (they belong in the instruction file), and tool or environment problems. A useful test: would it still be true if someone else were doing the work? Most sessions add nothing; say so in one line.
- **Choose the home.** Prefer an existing reference document that covers the topic (not a skill file). Otherwise use `PROCESS_DICTIONARY.md` in the project root, one section per process, created with its first entry rather than empty. Later sessions need a pointer to find it: add one line to the project's instruction file if authorized, or propose that line. Keep the knowledge itself out of the instruction file, which typically loads in full every session.
- **Edit in place.** This is a reference, not a log. A correction to a fact replaces the old text. When a later ruling replaces an earlier one, keep the earlier ruling and mark it superseded, with the date and reason. Attribute a ruling to the user only if they actually gave it, with the date. Anchor everything else to a source, and mark unchecked inferences `unverified`.
- **File it where it belongs.** Read the `Contents:` line at the top of the file and the relevant section first. A trap goes under that process's **Traps** heading and a ruling under its **Rulings** heading (see the template below). Start a new section only when no process fits, and name it after the real-world process, not the incident or session. Keep a contents line at the top, and merge sections that turn out to cover one process.
- **Remove secrets, personal records, and confidential details**, as described at the end of step 5.

```markdown
# Process dictionary
Contents: Refunds, Month-end close

## Refunds
**How it works:** The real-world process, in plain terms.
**Where it shows up:** Systems, fields, timing, and what blank or unusual values mean.
**Traps:** What has misled earlier sessions.
**Rulings:** How a kind of case is handled (user, YYYY-MM-DD).
```

Omit any part with nothing in it.

## 5. Write, update, or skip the handoff

A handoff gives the next session, or another person, what it needs to continue. Decide whether this session needs one: would a fresh session that read only the project files, the version history, and the most recent handoff be missing something it needs?

Read the most recent handoff first, if one exists. Then choose one outcome and state it in one line with the reason:

1. **Skip** when nothing has changed that the next session needs to be told, for example because the results are already recorded in project files or the session produced no decisions, open questions, or changes in state. Also skip when the user asked to skip or the directory is only a general workspace. Skipping is a normal result.
2. **Update the most recent handoff** when the session produced a few points worth keeping but not a new picture, such as a resolved question, a changed next step, or one decision. This is the default when something is worth saving.
3. **Write a new handoff** when the project's state or direction changed materially, or the most recent handoff is now wrong in more places than an update can cleanly fix.

Use the project's configured handoff location. If none exists, use `handoffs/YYYY-MM-DD-handoff.md` under the verified project root, with the session's local date. Keep one file per day: if today's file already exists, outcome 3 becomes an update to that file rather than a numbered copy, since several sessions in one day are usually one working day. Before creating a file, check for existing handoffs, including older copies of the same day's file that carry a number or other suffix. If several exist for today, update the most recently modified one rather than creating another. Do not delete or automatically archive earlier handoffs without a project convention.

**When updating,** read the whole file, then edit it so it reads as one current document rather than a stack of session logs:

- *Completed* and *Decisions and constraints* are history. Add this session's items after the existing ones. If a new decision replaces an earlier one, mark the earlier entry superseded and say why, rather than leaving two conflicting entries.
- *Current state and verification*, *Next steps*, and *Open checks* describe the present. Update them to match where things stand. Remove an item only when this session verifiably finished or resolved it; when unsure, leave it. When you remove a resolved open check, record its answer under *Decisions and constraints*; if the answer explains how something works or is a ruling, put it in the reference document chosen in step 4 (by default `PROCESS_DICTIONARY.md`) and leave a one-line pointer under *Decisions and constraints*.
- Keep the original title. Add a missing section if this session needs it. When updating an earlier day's file, mark each new item `(added YYYY-MM-DD)` so a reader can tell what is new.

Keep it short enough to read in a minute or two. For a new handoff, use this structure and omit empty sections:

```markdown
# Session handoff: YYYY-MM-DD

## Completed
- Concrete outcome and relevant file.

## Current state and verification
- What works or remains broken, with a test result or source pointer.

## Decisions and constraints
- Decision, reason, and source anchor.

## Next steps
- The next useful action and any unresolved choice.

## Open checks
- What remains unverified and the check that would settle it.
```

Anchor important claims and decisions to a file and section, commit, source cell, test command and result, or a retrievable discussion. Mark a claim `unverified` if no anchor is available. A previous AI summary is a navigation aid, not independent evidence. Separate passed checks, failed checks, and checks not run.

Remove secrets, personal records, and confidential details before saving. Link to an appropriately protected source by description when needed; do not reproduce its contents in the handoff. Do not assume a local handoff is safe to publish.

## 6. Handle Git only within authorization

If the project uses Git, inspect status and the relevant diff. Distinguish session changes from unrelated user work. If commits are authorized, stage only reviewed paths. Before an authorized push, verify the destination, visibility, and exact staged or committed contents for unintended disclosure.

Never infer push permission from the repository being private. Honor permission already given for this session, and do not ask again for the same authorized action. Without permission to commit or push, leave the work local and report that state. Never force-push, reset, or revert user changes as part of closeout.

## 7. Close out

Briefly report the result of all three spotters and the process-dictionary question, even if each found nothing. Include what you added to the process dictionary or other reference document, the handoff outcome (skipped, updated, or new) with its location or the reason for skipping, verification gaps, Git status if relevant, and the next useful action. Do not reproduce the whole handoff.
