# Start here

This repository is a set of written instructions, called skills, that make Claude Code or Codex check its work more carefully. You do not need to know how to code to use them. Unfamiliar terms are explained in the [glossary](#glossary) at the bottom.

## Your first five minutes

Use a short piece of writing that contains facts or numbers, such as a summary an AI wrote for you, along with the source it came from. Put both in one folder.

1. Download this repository (on GitHub, **Code > Download ZIP**) and extract it. Then install [Review Team](skills/review-team/SKILL.md) by copying its whole folder, including `references/`, as described in [Install the skills](README.md#install-the-skills). In Claude Code, also copy the three reviewer files in the `agents/` folder into `~/.claude/agents/` (create the `agents` folder if needed), so each review runs in a fresh conversation, separate from the one that wrote the draft.
2. Open Claude Code or Codex in the folder that holds your draft and source. In the Claude desktop app, Claude Code is the **Code** tab; choose **Local** (it runs on your computer, where you installed the skill) and select the folder before your first message. In a terminal, move into the folder first, for example with `cd path/to/folder`.
3. Send this as one message, using your own file names. In Codex CLI or the IDE extension, type `$review-team` instead of `/review-team`.

   ```text
   /review-team Review draft.md against source.md for a general audience.
   Review only; do not edit the draft.
   ```

4. Read what it flags, then check one finding against the source yourself.

That last step is the habit these workflows build: the assistant points to its evidence, and you can confirm it in under a minute. Review Team is a good first skill because it needs only one draft and its source, and it shows the core sequence: a reviewer looks for problems, then a second role decides which ones need fixing. Leave [Goodnight](skills/goodnight/SKILL.md) until you work on a project across several sessions, since it saves notes for the next session.

## A worked example

This is an illustrative example adapted from the [practice scenarios](docs/practice-scenarios.md). It is not a recorded transcript.

**Source:** "Sign-up rate: 20% in spring, 25% in fall."

**Draft:** "The sign-up rate rose by 5% after the new email campaign, proving the campaign worked."

The 5 matches the difference between the source's two figures, so a quick check would pass this sentence. Review Team should catch two problems with it:

- **"Rose by 5%" is ambiguous.** The rate rose 5 percentage points, from 20% to 25%. As a relative increase, that is 25%, because 5 is a quarter of 20. A reader could also take "5%" to mean the rate went from 20% to 21%.
- **"Proving the campaign worked" claims a cause the source does not show.** Two numbers from two seasons cannot separate the campaign from anything else that changed between spring and fall.

Executive Review then decides what to do about the findings. Here it marks both as required corrections and, since nothing suggests the numbers themselves are wrong, does not ask for the analysis to be redone.

**A corrected version could read:** "The sign-up rate rose from 20% in spring to 25% in fall, an increase of 5 percentage points. The rise came after the new email campaign, but these figures alone do not show that the campaign caused it."

Both errors are in the wording, not the math, which is why they are easy to miss when you are only checking that the numbers match.

## Try next: Research Mindset, side by side

[Research Mindset](skills/research-mindset/SKILL.md) changes how the assistant answers research questions: it separates what the sources say from what it infers, and it says "I don't know" when the evidence runs out. The easiest way to see that is to ask the same question with and without it.

The steps below use one example source, the federal CIP 2020 to SOC 2018 crosswalk, which links college programs of study to the occupations they prepare students for. It lists only program and occupation codes and titles: nothing about how many graduates enter each job or what any job pays. Any public data file works instead; pick one you know well enough to judge the answers.

1. Download the crosswalk spreadsheet from the [NCES CIP resources page](https://nces.ed.gov/ipeds/cipcode/resources.aspx?y=56) into an empty folder. The assistant may ask permission to run a short command to read a spreadsheet. That is expected, and a command that only reads the file is safe to approve.
2. Before installing Research Mindset, open a session in that folder and ask a question the file cannot fully answer: "Using only this file, what jobs do graduates of [a program you know] get, and which of them pays best?"
3. Install Research Mindset the same way as Review Team. Then start a fresh session in the same folder, not a continuation of the first chat, and ask the same question, starting with `/research-mindset` in Claude Code or `$research-mindset` in Codex.
4. Compare the answers. Which one separates what the file shows from what it brings in from elsewhere? Which one says what it does not know and names the evidence it would need? Did either present a number or conclusion that is not in the file as if the file showed it?

If you use your own source, ask something it cannot fully answer. For a table of figures over several years, "why did [the figure] change?" works well, because the table shows what changed but not why.

One comparison is a demonstration, not a measurement, and results vary from run to run. If your global instructions already ask for sources, expect a smaller difference.

## Glossary

| Term | Meaning |
| --- | --- |
| Skill, workflow | A saved set of written instructions for an AI assistant, stored in a file called `SKILL.md`. This repository uses both words for the same thing. |
| Session | One working stretch with an assistant, usually one chat. |
| Handoff | A short note saved at the end of a session so the next session knows where things stand. |
| Artifact, deliverable | The thing being reviewed: a draft, report, spreadsheet, or code. |
| Source | The original material a claim should be checked against. |
| Fresh context, separate agent | A second chat or AI helper that has not seen the original work, so it is less likely to repeat the author's assumptions. A same-context review is one where the same chat checks its own work. |
| Quality Advocate, Executive Review | The main reviewer roles in Review Team. The first looks for problems; the second decides which ones need fixing. |
| Adjudicate | Weigh each finding and decide what to do about it. |
| Global and project instructions | Standing instructions the assistant reads every time. Global instructions apply everywhere; project instructions apply to one project. Claude Code reads files named `CLAUDE.md` and Codex reads files named `AGENTS.md`. |
| Process dictionary | A project file where Goodnight records how the project's processes and data work. |
| Repository, GitHub | An online folder of files, like this one. You can download it with **Code > Download ZIP**. |
| Git, commit, push | Git tracks versions of files. A commit saves a snapshot and a push uploads it online. You can ignore these unless you want version history. |
| Markdown, `.md` | Plain text with simple formatting marks. Any text editor opens it. |
| Frontmatter | The short block between `---` lines at the top of a skill file, holding its name and description. |
| Claude Code, Codex | AI assistants from Anthropic and OpenAI that work with the files in a folder on your computer and can run commands there. Claude Code is available in a terminal or as the **Code** tab of the Claude desktop app. |
| Folder, project root | The folder you open the assistant in. Skills that save files, such as Goodnight, write them there. |

## Where to go next

- [Install the skills](README.md#install-the-skills) in Claude Code or Codex.
- Read the [step-by-step usage guide](docs/how-to-use.md).
- Try the [practice scenarios](docs/practice-scenarios.md) before relying on a workflow.
- Adjust handoff locations, permissions, and review depth with the [customization guide](docs/customization.md).
