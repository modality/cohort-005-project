# Using Grill with Docs

<CommitMap packageManager="npm">
  <Commit id="seed-liams-refund">Start the lesson: Liam's purchase seeded at $79, three names for a refund once you click through, no GLOSSARY.md yet</Commit>
  <Commit id="create-glossary-and-fix-refund-drift">See my solution: `GLOSSARY.md` created and the code renamed to Refund and Refund Request</Commit>
</CommitMap>

<Prerequisites title="Crash Course Prerequisites">
  <Prerequisite href="https://www.aihero.dev/workshops/ai-coding-crash-course/models-harnesses-agents-environments-2b9a99a1">
    What an agent actually is: a model, a harness and an environment working together.
  </Prerequisite>
  <Prerequisite href="https://www.aihero.dev/workshops/ai-coding-crash-course/sessions-and-the-context-241f60ee">
    What a session and its context are, so a fresh session and a well-loaded prompt make sense.
  </Prerequisite>
  <Prerequisite href="https://www.aihero.dev/workshops/ai-coding-crash-course/the-grill-execute-clear-loop-fac85414">
    How grilling works: the agent interviews you until you both share the same design.
  </Prerequisite>
  <Prerequisite href="https://www.aihero.dev/workshops/ai-coding-crash-course/what-are-agent-skills-20f91a4e">
    What a skill is and how you invoke one like `/grill-with-docs`.
  </Prerequisite>
</Prerequisites>

The app currently uses three different terms for the same thing: a button labelled "Cancel my purchase", a confirmation email that says "Reversal", and a settings page heading that reads "Pending Chargeback". A confused user can't tell if their request even worked.

The fix starts not in the code, but in the language. Before touching a single file, you'll use `/grill-with-docs` to find the one right word, define just enough around it to make it meaningful, and then unify the codebase to match.

## Steps To Complete

### Find the Right Word

- [ ] Start a fresh agent [session](https://www.aihero.dev/ai-coding-dictionary/session) and run the `/grill-with-docs` [skill](https://www.aihero.dev/ai-coding-dictionary/skill)

Think carefully about the prompt that will kick off this discussion. You want the [agent](https://www.aihero.dev/ai-coding-dictionary/agent) to help you discover the single best term for the thing the app variously calls:

| Location | Current term |
|---|---|
| Course page button | "Cancel my purchase" |
| Confirmation email subject | "Reversal" |
| Settings page heading | "Pending Chargeback" |

Your prompt should give the agent enough [context](https://www.aihero.dev/ai-coding-dictionary/context) about the feature to have a real discussion, not just pick an arbitrary synonym.

- [ ] Work with the agent to settle on one term

Expect to try and discard a few candidates before one feels right. A good term is precise enough that two people can't quietly mean different things by it.

### Create `GLOSSARY.md`

- [ ] Create a `GLOSSARY.md` at the root of the project

There is currently no `GLOSSARY.md` in the repo. You will need to create one from scratch.

- [ ] Define the term you settled on

The glossary should describe what the term *means*, not how it is implemented. Keep it focused: define just enough surrounding words that the new entry makes sense on its own.

- [ ] Review the entry before moving on

Ask yourself: if a new developer read only this glossary entry, would they know exactly what state the user is in and what they requested?

### Unify the Code

- [ ] Ask the agent to unify the codebase using the new `GLOSSARY.md`

The agent should find every inconsistent string and replace it with the agreed term. The drift is spread across a few files:

```
app/routes/courses.$slug.tsx       ← the button label
app/routes/courses.$slug.refund.ts ← the email subject and body
app/routes/settings.tsx            ← the settings page heading
```

- [ ] Verify the UI reflects the new language

Run the app and check each of the three locations above to confirm the old terms are gone and the new term appears consistently throughout.
