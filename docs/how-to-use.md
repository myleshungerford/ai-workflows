# How to use this repository

This repository contains reusable instructions for Claude Code and Codex. You can install one workflow at a time. You do not need to run this repository as an application.

## 1. Install the skills you want

Follow the [installation instructions](../README.md#install-the-skills) for your tool. Copy the whole skill folder to the skills location for your tool; Review Team needs its `references/reviewer-roles.md` file, while the standalone Quality Advocate and Executive Review skills each contain their own complete instructions. Merely downloading this repository, or copying it with Git (called cloning), does not install its `skills/` folders. Do not overwrite an existing skill without comparing it first.

## 2. Supply the work and evidence

Tell the assistant which artifact and version to examine, who will use it, and what the work is supposed to accomplish. Provide the original requirements and source files or accessible source links. State whether it may edit or should only recommend changes.

For example:

```text
Review reports/draft.md for a general audience. sources/table.csv is the
evidence for its numerical claims. Identify unsupported conclusions
and the smallest corrections needed. Review only; do not edit or publish.
```

If the assistant cannot open a source, supply its relevant contents through an approved channel. Do not upload confidential material to a new service just to complete a review.

## 3. Pick a review route

Use **Review Team** for the complete sequence. It already includes Quality Advocate, Executive Review, and the optional plain-language role. Installing the two standalone skills is optional, and there is no need to run them again after Review Team without a specific reason.

Use the standalone skills when you want to control the stages yourself. In Codex, after installation (in Claude Code, use `/quality-advocate` and `/executive-review`):

```text
$quality-advocate Review reports/draft.md against sources/table.csv.
The audience is non-technical. Review only. Include source locations,
consequences, and the smallest remedy for each material finding.
```

Wait for the critique to finish. Then provide the original request, artifact, sources, and complete critique to Executive Review:

```text
$executive-review Assess reports/draft.md using the completed Quality
Advocate critique above and sources/table.csv. Decide which findings need
correction, which can wait, and whether the draft is ready for its audience.
Do not edit or publish.
```

In a new session, attach the critique or save it to a file the reviewer can read. "The critique above" only works when it is actually present in that session. Separate agents or sessions can provide a fresh perspective, but they must receive the underlying artifact and evidence. Another AI's agreement is not source verification.

If you want corrections applied, explicitly ask for them and for the affected claims or behavior to be rechecked. A review-only judgment does not mean the artifact was edited.

## 4. Use the other workflows where they help

| Moment | Workflow | Example request |
| --- | --- | --- |
| Starting factual work | Research Mindset | Compare these sources; distinguish facts from inference |
| Checking a factual draft | Fact Check Loop | Trace the draft's claims to the supplied evidence |
| Checking session shortcuts | Loose Ends | What did we assume or leave unverified? Run cheap checks |
| Ending a session | Goodnight | Capture lessons and write a handoff; keep changes local |

Loose Ends works best in the session that did the work because that assistant knows which checks it skipped. Goodnight should also use the working session's context. Start the next session by providing the saved handoff and asking the assistant to verify the relevant current files before continuing.

## 5. Customize and maintain your copies

Use the [customization guide](customization.md) for local paths, permissions, and review depth. Merge selected rules from the [project instruction starter](../templates/project-instructions.md) into your existing instructions; do not replace them wholesale.

After downloading an updated version of this repository, compare changes with your installed copies before replacing them. Updates to a downloaded repository do not update separately copied skills. If you rename a skill to avoid a collision, update both its folder name and frontmatter `name`.

Try the [practice scenarios](practice-scenarios.md) in a disposable project. Look for observed behavior: honest missing-source reports, preserved unrelated files, source-backed findings, and checks actually performed. Adapt the instructions when a specific failure demonstrates a need.
