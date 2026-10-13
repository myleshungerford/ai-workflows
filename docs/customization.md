# Customize the workflows

The workflows are ordinary Markdown. Edit a copy and retain changes that fit your work. Do not paste your entire personal configuration into a public fork.

## Choose local conventions

| Setting | Starting point | When to change it |
| --- | --- | --- |
| Handoff location | `handoffs/` in the project root | Your project already has a continuity folder |
| Handoff retention | Keep existing files | You have an explicit archive policy |
| Notes on how processes and data work | `PROCESS_DICTIONARY.md` in the project root | Your project already has a reference document for this; Goodnight will use it instead |
| Durable instruction edits | Propose changes unless authorized | You want the assistant to maintain specified project files |
| Git actions | No commit or push permission implied by a skill | You explicitly authorize named actions or set a scoped standing rule |
| Review mode | Separate agents if allowed; disclose fallback | Your tool lacks delegation or usage cost matters |
| Reviewer model | Claude: never Sonnet or Haiku for Quality Advocate and Executive Review; otherwise the main session's choice, Opus by default. Other tools: a capable model within your budget | Your session has another allowed model, such as Fable, that suits the review |
| Plain-language review | Use for non-technical or external readers | The user requests it or asks to skip it |
| Source access | Use approved files and tools | You authorize an additional source or service |

For example, add this to the instructions for one project:

```text
Save handoffs in notes/handoffs/. You may update this project's guidance
when a correction is supported by session evidence. Propose changes to
global instructions. Do not delete old handoffs. You may commit reviewed
session changes locally; ask before pushing unless I already authorized
the push for this task. Use one reviewer, then Executive Review.
```

Settings written in prose are instructions to the assistant, not enforced permission controls. Use your tool's actual access and approval settings for enforcement.

## Adapt to your computer

Keep project paths relative wherever possible. Resolve the actual project root before writing. Use your operating system's file tools and your project's verification commands. These skills do not require a particular shell, secret store, model name, or account.

If separate agents are unavailable or not allowed, use the disclosed single-assistant review, or give the review packet to another session or person.

Never put credentials, personal records, private transcripts, or confidential source data into public skill files or practice examples. Supply sensitive evidence only through tools and storage approved for that data. A request to fact-check does not itself authorize uploading files to a new service.

## Keep the collection small

The additional skills recommended here are Research Mindset, Fact Check Loop, and Loose Ends because they address different points where unsupported claims can enter or survive a task. Use them selectively.

Further candidates for a later collection include a dependency review before installing packages, a source-data intake check, and a debugging workflow that reproduces a failure before editing code. Those need more environment-specific choices and are not included in this initial collection.

This public edition adapts a personal workflow collection. It keeps the closeout and sequential review methods while removing personal paths, domain-specific assumptions, mandatory new-skill approval rituals, and automatic Git actions.
