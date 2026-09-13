---
name: goodnight
description: Close a work session by spotting reusable lessons, observed workflow failures, stale artifacts, and context worth preserving. Use when asked for goodnight, session closeout, or a handoff for next time.
---

# Goodnight

Review the session before closing it. Do not assume it is nighttime. Complete the requested closeout rather than simply promising to remember.

Use the user's project conventions and existing authorization. This workflow does not authorize global configuration changes, deletion, commits, or publication by itself. If files or earlier context are unavailable, identify the gap and provide a handoff draft in the conversation instead of claiming to have saved it.

## 1. Spot reusable lessons

Look for a repeated method, a useful technique discovered through trial and error, or an explicit user correction that applies to future tasks.

Distinguish a reusable process from a durable collaboration preference. Put a process in a relevant skill; put a general preference in the project's or assistant's instruction file. A repeated specialist role may justify reusable agent instructions when the host supports them, but do not invent a configuration format.

Reject one-off narratives, transient errors, speculative improvements, and machine-specific workarounds presented as universal rules. Check existing instructions for overlap. Prefer a small patch to a relevant skill over creating another skill.

For each worthwhile lesson, cite the session evidence and identify its proposed home. Apply an authorized, scoped change; otherwise present the exact proposed edit. Before creating a new skill, establish that no existing one fits. A fresh reviewer can check a borderline case if available and authorized, but is not a required gate for routine closeout.

## 2. Spot observed workflow failures

Inspect only workflows exercised in this session. A finding needs an actual missed case, wrong result, manual workaround, or clear trigger failure. Age, wording preferences, and hypothetical edge cases are not defects.

State which instruction failed, the evidence, and the smallest correction. Do not count the same correction again if step 1 already handled it. Preserve a recoverable copy or version-control diff before changing durable instructions. Check naming, metadata, linked files, and the behavior the change is meant to improve.

If nothing warrants a change, say so. Do not manufacture work to make the closeout look useful.

## 3. Spot stale guidance and misleading artifacts

Inspect files touched or relied on during this session for verified contradictions or scratch artifacts likely to be mistaken for current output. Cite the file and the session fact that contradicts or supersedes it.

Correct an unambiguous factual error when authorized and in scope. Do not reorganize or delete files for tidiness. Preserve uncertain or unrelated files. If cleanup requires a consequential choice, record the specific issue and proposed action instead.

## 4. Write the handoff

Skip a saved handoff if the user requests it or the current directory is only a general workspace with no meaningful project. Explain the skip briefly.

Otherwise use the project's configured handoff location. If none exists, use `handoffs/YYYY-MM-DD-handoff.md` under the verified project root, with the session's local date. Add a numeric suffix if the filename exists. Do not overwrite earlier handoffs or automatically archive them without a project convention.

Keep it short enough to read in a minute or two. Omit empty sections:

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

## 5. Handle Git only within authorization

If the project uses Git, inspect status and the relevant diff. Distinguish session changes from unrelated user work. If commits are authorized, stage only reviewed paths. Before an authorized push, verify the destination, visibility, and exact staged or committed contents for unintended disclosure.

Never infer push permission from the repository being private. Honor permission already given for this session, and do not ask again for the same authorized action. Without permission to commit or push, leave the work local and report that state. Never force-push, reset, or revert user changes as part of closeout.

## 6. Close out

Briefly report the result of all three spotters, even if each found nothing. Include the handoff location or reason it was skipped, verification gaps, Git status if relevant, and the next useful action. Do not reproduce the whole handoff.
