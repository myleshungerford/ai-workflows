# AI Workflows

Reusable instructions for checking AI work, preserving useful lessons, and making uncertainty visible. Copy the workflows you need and adapt them to your tools.

Start with **Review Team** before sharing important work. Add **Goodnight** once a project spans several sessions, and the other skills when you need closer attention to sources or unfinished checks.

New to Claude Code or Codex? Read [Start here](START-HERE.md) first. It has a five-minute first try, a worked example, and a glossary. Then follow the [step-by-step usage guide](docs/how-to-use.md) for loading a skill, supplying evidence, running reviews, and maintaining your copies.

These are practical workflows, not a measured guarantee of fewer hallucinations. An AI reviewer can repeat an author's mistake. Verification still needs source material, calculations, tests, or human expertise appropriate to the task.

## Choose a workflow

| Skill | Use it when | What it does |
| --- | --- | --- |
| [Goodnight](skills/goodnight/SKILL.md) | You are ending a work session | Captures reusable lessons, checks for stale guidance, records how your project's processes and data behave, and writes or updates a source-backed handoff when the next session needs one |
| [Review Team](skills/review-team/SKILL.md) | A deliverable is ready for review | Runs one or more Quality Advocates, then Executive Review, with a plain-language pass when useful |
| [Quality Advocate](skills/quality-advocate/SKILL.md) | You want a standalone critical review | Identifies concrete defects, unsupported claims, and missing checks |
| [Executive Review](skills/executive-review/SKILL.md) | Quality Advocate has finished | Adjudicates findings and decides what needs correction before use |
| [Research Mindset](skills/research-mindset/SKILL.md) | You are researching or analyzing sources | Separates evidence from inference and permits an explicit "I don't know" |
| [Fact Check Loop](skills/fact-check-loop/SKILL.md) | A draft contains factual or numerical claims | Traces claims to sources and corrects or qualifies unsupported statements |
| [Loose Ends](skills/loose-ends/SKILL.md) | You want to know what the assistant skipped | Audits the current session's assumptions and runs cheap checks |

You do not need every workflow on every task. Research Mindset guides the work as it happens. Fact Check Loop checks the draft. Review Team challenges the completed result. Loose Ends examines shortcuts known to the current assistant. Goodnight preserves what the next session needs.

Review Team already contains both reviewer roles. Use the standalone Quality Advocate and Executive Review skills when you want to run those stages yourself, always in that order. Each standalone skill can be copied on its own.

If separate agents are unavailable, Review Team runs the roles in the current session and labels the result a single-assistant review. That fallback is disclosed because a same-context review is not independent review.

## Install the skills

Download this repository using GitHub's **Code > Download ZIP**, then extract it. Alternatively, clone it:

```sh
git clone https://github.com/myleshungerford/ai-workflows.git
```

Each skill is a folder under `skills/`. Copy the whole folder, including any `references/` directory. Before copying, check for an existing skill with the same name; merge deliberately or rename your copy instead of overwriting it. `~` means your user profile folder on Windows and your home folder on a Mac. On a Mac, folders whose names start with a dot are hidden in Finder (press Cmd+Shift+. to show them). Once the assistant is open in a folder, you can also ask it to copy a skill folder for you.

These skills are written for Claude Code and Codex. The steps below follow each tool's documentation; if a step does not match what you see, check the linked page.

### Claude Code

Claude Code runs in a terminal and in the **Code** tab of the Claude desktop app. Both read the same skills folder on your computer, so one installation covers both. (Cloud sessions are the exception: they use the skills enabled for your claude.ai account instead.)

Copy each skill folder into `~/.claude/skills/` to use it in all your projects, or into a project's `.claude/skills/` folder to use it in that project only. Claude Code picks up new skills without a restart; if the `skills` folder did not exist when your session started, run `/reload-skills`.

Invoke a skill by name, for example `/goodnight` or `/review-team reports/draft.md`, or describe the task and Claude can use a matching skill. See the [Claude Code skills documentation](https://code.claude.com/docs/en/skills), checked October 13, 2026.

### Codex

Copy each skill folder into your personal `~/.agents/skills/` directory, or your project's `.agents/skills/` directory.

In Codex CLI or the IDE extension, use `/skills` or mention an installed skill with `$`, for example:

```text
$goodnight Close this session and write a handoff. Do not commit or push.
$review-team Review reports/draft.md against sources/ for a general audience.
$quality-advocate Review reports/draft.md against sources/. Review only.
$executive-review Adjudicate the completed critique against the draft and sources.
$research-mindset Compare these proposals using the supplied documents.
$fact-check-loop Verify the claims in reports/draft.md against sources/.
$loose-ends What did we assume or leave unverified in this session?
```

If a skill does not appear, restart Codex and check its location. These locations and invocation methods follow the [official OpenAI skill documentation](https://learn.chatgpt.com/docs/build-skills), checked October 13, 2026. Other clients may expose a different selection interface.

The examples are prompts, not shell commands.

## Customize it

Use the [configuration guide](docs/customization.md) to choose handoff locations, Git permissions, review depth, and privacy boundaries. The [project instruction starter](templates/project-instructions.md) contains a small set of general rules you can merge into your existing instructions.

There are no package dependencies, install scripts, required model subscriptions, or background services in this repository. Your assistant may need tools or paid capabilities to execute parts of a workflow. Separate agents consume additional usage.

## Check that it works for you

Run the [practice scenarios](docs/practice-scenarios.md) on disposable material before relying on the workflows. They describe observable behavior to look for, including admitting missing evidence and preserving unrelated files. Passing these examples does not establish accuracy on other tasks.

The standalone reviewer skills and Review Team's bundled roles intentionally cover the same methods so each can be installed independently. When changing the shared review method, keep both versions consistent.

When improving a skill, describe the observed failure and make the smallest useful correction. Avoid turning one unusual incident into a rule for every future task. Remove private material before contributing examples or issue reports.

## License

[MIT](LICENSE). You can copy, adapt, and redistribute these workflows under its terms.
