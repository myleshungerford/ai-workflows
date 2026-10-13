---
name: review-team
description: Review a completed deliverable through Quality Advocate followed by Executive Review, with an optional plain-language pass. Use for a final cold review or a request to pressure-test existing work.
---

# Review Team

Review the actual deliverable against the user's goal and sources. Do not recreate the work or review only the author's summary.

## Establish scope

Identify the artifact, version, intended audience, requirements, and available source material. If no artifact is named, use the most recent completed artifact only when unambiguous. Otherwise ask which one to review.

Default to review only. Apply fixes if the user has authorized editing or completion of the deliverable. A review request alone does not authorize sending, publishing, or modifying external records.

Read [reviewer roles](references/reviewer-roles.md). These instructions are included with this skill; no other installed skills or named model tiers are required.

## Choose an honest review mode

When separate agents are available and allowed, use a fresh reviewer context for Quality Advocate. Supply the actual artifact, original requirements, audience, sources, and necessary access constraints. Do not prime the reviewer with the author's preferred conclusion. The reviewer should inspect underlying evidence directly when possible.

Use a model capable of the task within the user's budget. A different model or another agent does not make the evidence independent. Do not claim a particular model was used unless the tool confirms it.

If delegation is unavailable or disallowed, perform the roles sequentially in the current context and label the result a **single-assistant review**, not an independent or cold review. If a truly independent review was explicitly required, report that requirement as unmet and provide a review packet for another reviewer. Never invent agent responses.

## Run sequentially

1. Finish the drafting or domain work before review begins.
2. Run Quality Advocate using the first role in the reference. Every Quality Advocate must return before Executive Review starts.
3. Run Executive Review with the original task, artifact, source access, and every Quality Advocate critique in full. If critiques disagree, say so rather than merging them. Executive Review must examine and adjudicate the findings rather than merely summarize them.
4. Run the plain-language role when requested or when the visible deliverable is for a general, external, or non-technical audience. Honor an explicit request to skip it. Limit this pass to audience-facing content and preserve factual caveats.

One Quality Advocate is the default. Use two or three when the work could fail in clearly different ways or is headed to leadership or an outside audience. For long or multi-part work, split reviewers by section or by focus. Add a reviewer only if you can name what it will look for that the others will not.

When using more than one, give each a distinct focus and state it in its instructions so they do not return the same critique. Common focuses are **evidence** (each number, citation, and factual claim traced to a source), **argument** (whether the reasoning holds and what the strongest counterargument is), and **completeness** (what is missing and what the audience will ask that the work does not answer). Quality Advocates can run at the same time as each other. The stages still run in order: all Quality Advocates, then Executive Review, then the plain-language pass. Pass each critique to Executive Review intact and labeled with its focus.

Do not run review rounds indefinitely or seek agreement by majority vote.

For factual work, source consequential claims, use short relevant excerpts where permitted, and distinguish facts from inference. If evidence is missing, say so. Never invent a source or a numerical confidence score.

## Resolve and verify

Return one integrated review: readiness judgment, material findings with source locations, required corrections, and unresolved checks. Distinguish demonstrated errors from validation gaps and optional improvements. If more than one Quality Advocate ran, say how many and which focus each covered. "No material findings" is a valid result.

When edits are authorized, apply the accepted corrections and verify the changed claims or behavior. Re-review only the affected parts unless changes invalidate broader conclusions. Clearly distinguish findings fixed and rechecked from recommendations still pending. Approval of a previous draft does not automatically cover an altered version.
