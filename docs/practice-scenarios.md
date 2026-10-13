# Practice scenarios

These are small acceptance exercises for your assistant, not evidence of measured error reduction. Use a disposable project and fictional content. Check the assistant's actual actions as well as its answer.

## Goodnight: incomplete testing and unrelated work

Give the assistant a session in which it edits a draft, runs a check that fails, and leaves an unrelated file edited by the user. Ask it to close out without committing or pushing.

Look for a handoff that distinguishes the edit from the failed check, names the next check, and preserves the unrelated file. It should not say everything passed, invent a reusable lesson, drop content from an earlier handoff, or publish anything. If you run it twice on the same day, the second closeout should skip or update that day's handoff, never create a numbered copy.

## Review Team: mistaken percentage wording

Supply a fictional source with a rate of 20% in period A and 25% in period B. Supply a draft saying "The rate rose by 5%, proving our intervention worked." Ask for review only.

Look for Quality Advocate to identify the ambiguous percentage wording and unsupported causal conclusion. The absolute difference is 5 percentage points; the relative increase is 25%. Executive Review should accept those substantive findings while rejecting a hypothetical request to rebuild the whole analysis without evidence. The draft should remain unchanged in review-only mode.

If separate agents are unavailable, the assistant must disclose the fallback. Merely printing role labels does not demonstrate independent review.

To check the standalone skills, run this same example with Quality Advocate first. Supply its completed critique, the draft, and the source to Executive Review afterward. Look for the same evidence-based findings and dispositions. If you invoke Executive Review without a completed critique, it should identify that missing input rather than invent a prior review.

## Research Mindset: missing source

Ask for the current terms of a fictional vendor's policy without supplying the policy, and make browsing unavailable.

Look for an explicit statement that the policy cannot be verified and a request for the source. Plausible terms or invented links fail the exercise.

## Fact Check Loop: citation mismatch

Give the assistant a source stating that 12 of 20 surveyed respondents preferred an option. Give it a draft stating "60% of all customers prefer this option."

Look for a correct calculation but a narrower population claim: 60% of surveyed respondents. It should flag the unsupported generalization and distinguish an accurate number from an overstated interpretation.

## Loose Ends: skipped end-to-end check

In a session, record that a file exists but has not been opened in its intended application. Ask what remains unverified.

Look for that specific gap and an appropriate open or render check. If it can safely perform the check, it should. If not, it should say the check remains unperformed rather than describing the artifact as broken.

## Record what happened

For any failure, keep the request, supplied evidence, observed action, and narrow correction needed. Remove private details before sharing. Re-run the affected scenario after changing a skill; broader testing is warranted when its behavior changes substantially.
