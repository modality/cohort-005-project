# Setting Up Your Agent

<Prerequisites title="Crash Course Prerequisites">
  <Prerequisite href="https://www.aihero.dev/workshops/ai-coding-crash-course/installing-claude-code-689b4791">
    How to install a coding agent, log in and pick a model.
  </Prerequisite>
  <Prerequisite href="https://www.aihero.dev/workshops/ai-coding-crash-course/resetting-to-a-clean-slate-f8126cee">
    The full reset prompt for backing up your skills, MCP servers and settings.
  </Prerequisite>
  <Prerequisite href="https://www.aihero.dev/workshops/ai-coding-crash-course/models-harnesses-agents-environments-2b9a99a1">
    What an agent actually is: a model, a harness and an environment working together.
  </Prerequisite>
  <Prerequisite href="https://www.aihero.dev/workshops/ai-coding-crash-course/the-steering-map-c061e049">
    What AGENTS.md and CLAUDE.md are, and why a global one gets loaded into every project.
  </Prerequisite>
  <Prerequisite href="https://www.aihero.dev/workshops/ai-coding-crash-course/what-are-agent-skills-20f91a4e">
    What a skill is, so you can see how a global skill could shadow the repo's own.
  </Prerequisite>
</Prerequisites>

Before we get acquainted with the exercises and the course repo itself, let's get your [agent](https://www.aihero.dev/ai-coding-dictionary/agent) ready. There are two parts to this:

- Which agent and model you're using.
- What your agent is already carrying around from your setup.

## Any agent that runs in a terminal

As I said before, this course will work with any agent that runs in a terminal and uses skills: Claude Code, Codex, OpenCode, Copilot, Pi. I'll be using Claude Code in the videos, but that's just my choice.

The [skills](https://www.aihero.dev/ai-coding-dictionary/skill) we're going to be using, if we zoom far ahead in the course, are all going to be provided inside the repository that we're working inside.

That means you don't have to install anything from my global skills. They're all just going to be provided for you as you need them. And because a skill is just a folder of Markdown files, any agent that can read them can follow along. Switch agents halfway through and you lose nothing.

## Any model, as long as it's Opus class

The same goes for the [model](https://www.aihero.dev/ai-coding-dictionary/model). Claude, GPT, Gemini, an open-weights model: the course doesn't care which lab made it.

What it does care about is how capable the model is. You want an **Opus-class model**: the most capable one your [provider](https://www.aihero.dev/ai-coding-dictionary/model-provider) offers. A smaller model will get through the short exercises, and then fall over on the long ones.

To check whether a model is Opus class, use the [DeepSWE leaderboard](https://deepswe.datacurve.ai/). It's a long-horizon software engineering benchmark: long coding tasks, written from scratch inside real open-source repos, so a model can't have memorised the answers. Every model runs through the same small [harness](https://www.aihero.dev/ai-coding-dictionary/harness), so it compares models, not agents.

Look at the group of models at the top. That's Opus class. If your model sits up there, you're good. If it's a long way down, expect it to struggle in the later sections, where the agent runs for a long time on its own. Scores move as new models land, so check the leaderboard yourself when you start.

## Watch out for your global configuration

What I want you to be wary of are the skills, settings or configuration that you have installed globally on your machine.

The course repo ships its own skills, like `/grill-me`, `/implement` and `/to-spec`. But you may well have older copies of those same skills installed globally. When a global skill and a repo skill share a name, your agent can pick up the global one, and you'd be running a different process from mine without knowing it.

It's not only skills. A global instructions file, like an `AGENTS.md` or `CLAUDE.md` in your home folder, gets loaded in every project. If it says "always use pnpm", it'll fight a repo that uses npm.

Clearing that global config out of the way will let you temporarily purge your complicated setup and allow your agent to work from a clean slate. Hopefully your results will be more similar to mine, because there will be less clattering around inside the [environment](https://www.aihero.dev/ai-coding-dictionary/environment).

## Let Your Agent Do It

Below, I'm going to give you a prompt that you can copy and paste into your agent. It checks which model your agent is running on, finds anything global that would shadow the course's skills, and backs it up out of the way. It asks before it moves anything.

Run it now, from your home folder. It names the course's skills itself, so it doesn't need the repo cloned.

If this machine has a setup you need to keep, for example for work, point `CLAUDE_CONFIG_DIR` at a separate folder instead of running the reset, and log in again.

```
You are the expert on your own configuration. I'm about to take a course whose repo ships its own skills in `.agents/skills`. Make sure nothing in my global setup gets in their way, and tell me which model you're running on.

**1. Report your model.** Tell me the exact model you're running on, as your harness reports it, and how to switch to the most capable model my provider offers if you're not already on it. If you can't tell, say so and tell me where to look rather than guessing. If you can browse the web, find the model on the DeepSWE leaderboard (https://deepswe.datacurve.ai/) and tell me whether it sits in the top group.

**2. Find shadowing skills.** The course repo ships these skills, or adds them in later lessons: ask-matt, code-review, codebase-design, database-migrations, diagnosing-bugs, domain-modeling, grill-me, grill-with-docs, grilling, handoff, implement, implement-spec, improve-codebase-architecture, knock-workflows, mutation-testing, pr, prototype, research, retro, setup-matt-pocock-skills, setup-ts-deep-modules, software-factory, tdd, teach, to-spec, to-tickets, wayfinder, wizard, writing-for-agents. Consult your own documentation for every place you load skills, commands or plugins from outside a project (global and user-level), check each one, and report every skill or command whose name matches one on that list, with its full path. Done when every location named in your docs has been checked and reported, including the ones that turned out to be empty.

**3. Find global instructions.** Report every global or user-level instructions file you load in every project (for example an AGENTS.md or CLAUDE.md in my home folder or in your config folder), with a one-line summary of anything in it that could fight a project's own conventions, such as package manager, test runner or git workflow rules.

**4. Ask before touching anything.** Show me a table of what you found in steps 2 and 3 (path, what it is, why it might conflict), then stop and wait for my answer. Do not remove, rename or move anything until I tell you which items to clear.

**5. Back up what I approve.** Create `~/agent-config-backup-<today's date>/` and MOVE each item I approved there, mirroring its original path inside the backup. Verify each move landed before continuing. Add `RESTORE.md` at the root of the backup listing every item, its original absolute path, and the exact commands to put it back, written well enough that a future agent with no memory of this conversation can restore everything from that file alone.

Keep me signed in: leave auth, credential and session files exactly where they are. Change nothing inside any project.

Finish with the one-line command I can give you later to restore everything. If you are running inside the course repo, also list every skill you can now see and where each one comes from.
```

If you want the full reset, with your [MCP servers](https://www.aihero.dev/ai-coding-dictionary/mcp), plugins, hooks and settings backed up too, use the prompt from **Resetting To A Clean Slate** in the AI Coding Crash Course instead.

## Check it worked

Once you've cloned the course repo, open your agent inside it and ask:

```
Which skills can you see, and where does each one come from?
```

Every one should come from the repo. If anything comes from your home folder, it's a leftover. Clear it out.

## Wrap up

There's not much to this lesson, really. Use any agent you want, on an Opus-class model with the DeepSWE leaderboard as your guide, and use the prompt above to clear out your global configuration.

Once that's done, you're ready for the next lesson. Good luck, and I'll see you in the next one.
