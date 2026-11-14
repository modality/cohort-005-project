# Day 1, Afternoon

<Prerequisites title="Crash Course Prerequisites">
  <Prerequisite href="https://www.aihero.dev/workshops/ai-coding-crash-course/smart-zone-dumb-zone-d4b92bd0">
    Why an agent gets worse as its context fills, and why you break up work to stay in the smart zone.
  </Prerequisite>
  <Prerequisite href="https://www.aihero.dev/workshops/ai-coding-crash-course/hallucination-77d5b4c6">
    What a faithfulness hallucination is, the risk that grows as the context fills.
  </Prerequisite>
  <Prerequisite href="https://www.aihero.dev/workshops/ai-coding-crash-course/navigation-pointers-0fed78e6">
    What navigation pointers are, the alternative to a code graph.
  </Prerequisite>
  <Prerequisite href="https://www.aihero.dev/workshops/ai-coding-crash-course/executing-your-tickets-8389d87c">
    How tests act as a red-green feedback loop for the agent.
  </Prerequisite>
  <Prerequisite href="https://www.aihero.dev/workshops/ai-coding-crash-course/enforcing-your-coding-standards-f1656d67">
    What automated checks are, and why they're cheaper than an agent's review.
  </Prerequisite>
</Prerequisites>

This is the afternoon session from Day 1 of office hours, edited down to the useful parts. Each chapter below covers one topic, so you can skip straight to whatever you need.

## What we covered

- **Is TDD still worth it?** Red-green-refactor is designed for humans: it optimizes for a very small working memory, so you can stop at any point and get a coffee. [Agents](https://www.aihero.dev/ai-coding-dictionary/agent) can hold more in their working memory, so I don't care whether they follow the loop. But just saying "do TDD" is a very [token](https://www.aihero.dev/ai-coding-dictionary/token)-efficient way to get the agent to care about tests.
- **Fixing obvious grilling questions:** You're in charge of the [grilling](https://www.aihero.dev/ai-coding-dictionary/grilling) session, so you don't have to answer every question. Give the agent the why behind the work, not just the what, and it can make more of those judgment calls itself.
- **Trusting the agent's tests:** Instead of reviewing long test files, tell the agent to make the change fully verifiable. Give it good data and access to the services it calls, then check the evidence it gives you. Relying entirely on tests has never been enough.
- **Turning retros into deterministic tooling:** Retro looks back over agent [sessions](https://www.aihero.dev/ai-coding-dictionary/session) and turns what it learns into [automated checks](https://www.aihero.dev/ai-coding-dictionary/automated-check), like lint rules and type checking, which don't cost you tokens in the future. As long as they don't make your CI run too long, layer on lots of them.
- **Can factories build quality products?** Yes, that's the intent. The agent takes your codebase in as a massive input, not just your prompt, and it's very happy to repeat the status quo. So you need to focus on quality before you can focus on speed.
- **Migrating with a ratchet:** First, your project has to be factory ready, which means you can run it in a [sandbox](https://www.aihero.dev/ai-coding-dictionary/sandbox). Then run the old and new tools side by side, say ESLint and Oxlint, and never let the new one's error count go up. A [software factory](https://www.aihero.dev/ai-coding-dictionary/software-factory) pays the errors down a few at a time until you can delete the legacy one.
- **Pruning a real glossary:** I open the 170-term glossary from my Course Video Manager and prune it live, cutting each definition down to one line and deleting the common-sense terms. Along the way I explain why I keep a single glossary, and why ADRs stay in the repo until their feature is deleted or a new ADR supersedes them.
- **Do you need a code graph?** Having a graph doesn't make a codebase easy to navigate, and you pay to re-index it every time the code changes. I'd rather make the [file system](https://www.aihero.dev/ai-coding-dictionary/filesystem) easier to navigate, with navigation pointers.
- **Is 150K still the smart zone?** 150K is still where I start getting nervous. It's not a cliff: past it you risk faithfulness [hallucinations](https://www.aihero.dev/ai-coding-dictionary/hallucination), but you also spend more tokens and get slower responses. So I break up work to stay in the [smart zone](https://www.aihero.dev/ai-coding-dictionary/smart-zone).
- **Taming 30 years of legacy code:** A legacy system is full of Chesterton's fences, code nobody remembers the reason for. The hard part is figuring out why each fence is there. After that, it's classic software engineering. I recommend _Working Effectively with Legacy Code_ by Michael Feathers.
- **Practicing in a team:** If you're in a team, apply these practices to your real work straight away, especially domain language, which you build between your team, your agent, your code and your domain experts. And grill where your team already communicates, like Slack or Discord, not in a terminal.
