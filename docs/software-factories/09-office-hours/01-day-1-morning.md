# Day 1, Morning

<Prerequisites title="Crash Course Prerequisites">
  <Prerequisite href="https://www.aihero.dev/workshops/ai-coding-crash-course/subagents-756fafe5">
    What a subagent is: a fresh context you hand work to.
  </Prerequisite>
  <Prerequisite href="https://www.aihero.dev/workshops/ai-coding-crash-course/compaction-2388148c">
    What compaction does, and what a summary of a long session loses.
  </Prerequisite>
  <Prerequisite href="https://www.aihero.dev/workshops/ai-coding-crash-course/what-are-agent-skills-20f91a4e">
    What a skill is, and how progressive disclosure keeps a big set of them manageable.
  </Prerequisite>
  <Prerequisite href="https://www.aihero.dev/workshops/ai-coding-crash-course/enforcing-your-coding-standards-f1656d67">
    The layers of review: automated checks, automated review and human review, and what belongs in each.
  </Prerequisite>
  <Prerequisite href="https://www.aihero.dev/workshops/ai-coding-crash-course/where-you-go-from-here-4c6bb9b1">
    Where AFK agents, prototyping and sandboxes fit beyond the five-step system.
  </Prerequisite>
</Prerequisites>

This is the morning session from Day 1 of office hours, edited down to the useful parts. Each chapter below covers one topic, so you can skip straight to whatever you need.

## What we covered

- **Using a factory across many repos:** Keep your [skills](https://www.aihero.dev/ai-coding-dictionary/skill), steering files and wiki in one [agent](https://www.aihero.dev/ai-coding-dictionary/agent) repo, and let it clone the other repos as it needs them. With hundreds of repos, use [progressive disclosure](https://www.aihero.dev/ai-coding-dictionary/progressive-disclosure) to keep the list manageable.
- **Metrics against code degradation:** I don't think there's a settled metric, and turning a metric into a goal can distort it. First we need to settle what a good codebase for agents looks like.
- **Is a factory worth it for a solo dev?** Yes, if you have the time budget. A [software factory](https://www.aihero.dev/ai-coding-dictionary/software-factory) is a set of practices, and the investment pays off on every future project.
- **Handling UI design:** Agents are primarily text-based, so I rely on my own instincts and a lot of [prototyping](https://www.aihero.dev/ai-coding-dictionary/prototyping). Design skills can help too.
- **Keeping track of the factory:** This is two questions. An observability tool shows you what your agents are doing. Planning and domain modeling keep you in touch with where your project is going, which helps you avoid cognitive debt.
- **The Chief of Staff skill:** This is an experiment that's outside the course: one long-running session per project, with the work done by [subagents](https://www.aihero.dev/ai-coding-dictionary/subagent), knowledge kept in a dated wiki, and aggressive [compaction](https://www.aihero.dev/ai-coding-dictionary/compaction). The wiki and subagents work well, but it almost never suggests strategic improvements.
- **Code quality and security:** Think in one-way and two-way doors. A one-way door can't easily be walked back, like a migration that deletes data or a security hole that was exposed for a while.
- **Automated QA:** Have one agent implement and another review before anything reaches [human review](https://www.aihero.dev/ai-coding-dictionary/human-review). I also tell the story of building the office hours app, where I gave the agent a dummy Discord server and a second bot so it could try to break the app.
- **Proving a retro change helped:** [Automated checks](https://www.aihero.dev/ai-coding-dictionary/automated-check) are cheap, so you can add plenty as long as they stay fast. [Automated review](https://www.aihero.dev/ai-coding-dictionary/automated-review) spends [tokens](https://www.aihero.dev/ai-coding-dictionary/token), so watch for no-ops and sediment. If you keep running retro, it should catch its own mistakes.
- **Docker Sandboxes vs Sandcastle:** I can't give an accurate comparison, but my impression is that Docker Sandboxes suit [human-in-the-loop](https://www.aihero.dev/ai-coding-dictionary/human-in-the-loop) work and Sandcastle suits [AFK](https://www.aihero.dev/ai-coding-dictionary/afk) workflows.
- **Factories under time pressure:** A factory is a long-term investment, so skip it for a hackathon or a very tight deadline.
- **Factories in a team:** Teams are the setting I think needs the most help. My recommendation is to [grill](https://www.aihero.dev/ai-coding-dictionary/grilling) where your team already is, such as Slack, Teams or Discord, and to do more pair and mob programming with agents.
- **Learning from each other:** Why I love the Discord community, and why it's worth talking to people who are at the same point in the journey.
