# Searching For Shallow Modules

<CommitMap packageManager="npm">
  <Commit id="add-deep-modules-skills">Start the lesson: the vibe-coded app with the codebase design skills installed</Commit>
</CommitMap>

<Prerequisites title="Crash Course Prerequisites">
  <Prerequisite href="https://www.aihero.dev/workshops/ai-coding-crash-course/models-harnesses-agents-environments-2b9a99a1">
    The basic vocabulary of model, harness and agent that the exercise leans on.
  </Prerequisite>
  <Prerequisite href="https://www.aihero.dev/workshops/ai-coding-crash-course/hallucination-77d5b4c6">
    Why you judge the agent's candidates yourself instead of trusting its verdict.
  </Prerequisite>
  <Prerequisite href="https://www.aihero.dev/workshops/ai-coding-crash-course/codebase-exploration-205910ac">
    How an agent explores a codebase it knows nothing about, which is how it finds candidates.
  </Prerequisite>
  <Prerequisite href="https://www.aihero.dev/workshops/ai-coding-crash-course/what-are-agent-skills-20f91a4e">
    What a skill is and how you invoke one like `/codebase-design` yourself.
  </Prerequisite>
</Prerequisites>

You now have the vocabulary for depth: interface, implementation, leverage and locality. Let's put it to work by hunting for shallow modules in our own codebase.

You'll use the `/codebase-design` [skill](https://www.aihero.dev/ai-coding-dictionary/skill) to ask your [agent](https://www.aihero.dev/ai-coding-dictionary/agent) for candidates. You won't change any code in this lesson. The agent does the hunting, but you do the judging.

## Two Ways To Fix A Shallow Module

Once you've found a shallow module, there are two options.

| Fix | What it means | Example |
| --- | --- | --- |
| Delete | Inline the module back into its callers | A `stringify` function whose whole body is a call to `JSON.stringify` |
| Deepen | Pull more behavior behind a single, smaller interface | Callers repeat the same steps against the module, so move those steps inside it |

The **deletion test** helps you choose. Imagine deleting the module and replacing it with its implementation. If the code looks equally complex and behaves the same, the module wasn't earning its keep.

In the `stringify` case, deleting it is even easier on the reader. They can rely on what they already know about `JSON.stringify` instead of learning a custom function.

## Steps To Complete

### Hunt For Candidates

- [ ] Start your agent in the project and invoke the `/codebase-design` skill, asking for candidates to delete (using the deletion test) or deepen

Here's the prompt to use:

```
/codebase-design Take a look inside the codebase and give me a few potential candidates of shallow modules that we could either delete using the deletion test or deepen. I'm especially interested in the back end of the application because that's where the most security risk is, and I want to improve the test coverage over time.
```

Don't ask it to modify any code. You're only looking at the candidates it proposes.

### Read The Agent's Language

- [ ] Watch how the agent describes each candidate

Look for how it uses **interface**, **implementation**, **leverage** and **locality**. If a term is used in a way you don't follow, make sure you understand it before moving on.

### Judge The Candidates

- [ ] For each candidate, decide whether to delete or deepen it

Apply the deletion test yourself rather than accepting the agent's verdict. Ask whether the module hides anything, or whether callers repeat the same ways of using it.

- [ ] Pick one candidate you would delete and one you would deepen

Some of the agent's suggestions may be borderline, so be critical about which ones are actually good.

- [ ] Write down why you chose each one, in your own words

Use the vocabulary from the previous lessons. These are candidates for improvement that you might take on later.
