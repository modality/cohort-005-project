# Chart The Map

<CommitMap packageManager="npm">
  <Commit id="add-wayfinder-skill">Start the lesson: the `wayfinder`, `prototype` and `research` skills added under `.agents/skills/`</Commit>
  <Commit id="add-notification-terms">The Notifications section added to `GLOSSARY.md` during the grilling</Commit>
  <Commit id="add-seed-wayfinder-issues">The `seed-wayfinder-issues` script, which loads my map and tickets into your GitHub issues</Commit>
  <Commit id="research-notification-vendors">The vendor research behind the first research ticket, in `docs/research/notification-vendors.md`</Commit>
  <Commit id="research-web-push-reach">The web push research, in `docs/research/web-push-reach.md`</Commit>
  <Commit id="remove-research-docs">See my solution: the lesson's end state, with the research docs removed again</Commit>
</CommitMap>

<Prerequisites title="Crash Course Prerequisites">
  <Prerequisite href="https://www.aihero.dev/workshops/ai-coding-crash-course/how-to-run-the-exercises-a0eb0474">
    How `npm run reset` moves your repo between the lesson's commits.
  </Prerequisite>
  <Prerequisite href="https://www.aihero.dev/workshops/ai-coding-crash-course/the-grill-execute-clear-loop-fac85414">
    How grilling works, since charting the map is one long grilling session.
  </Prerequisite>
  <Prerequisite href="https://www.aihero.dev/workshops/ai-coding-crash-course/how-to-tackle-massive-tasks-6199ee6b">
    Why big work splits into a spec (the destination) and tickets (the journey).
  </Prerequisite>
  <Prerequisite href="https://www.aihero.dev/workshops/ai-coding-crash-course/set-up-your-issue-tracker-30629075">
    How GitHub Issues and the `gh` CLI hold your specs and tickets.
  </Prerequisite>
  <Prerequisite href="https://www.aihero.dev/workshops/ai-coding-crash-course/split-features-across-context-windows-with-tickets-d9aa8395">
    How tickets block each other, which is how the map decides what's on the frontier.
  </Prerequisite>
</Prerequisites>

You now know what Wayfinder is, why it exists and the data structures it uses. Time to point it at a real feature.

The feature is in-app notifications for Cadence. Learners need a reason to come back, and instructors need to know when there are comments. We want real notifications, probably backed by a third-party service.

There's fog here: what does it look like in the app, where does the bell go, and which events need notifications? That nervousness is your cue to use Wayfinder.

## Two Paths

Your map will be different from mine. So from here on, you have two paths through this section:

- **Path 1: Follow my setup exactly.** Chart along with me. Then, if you want to, use the seed script to load my map and [tickets](https://www.aihero.dev/ai-coding-dictionary/ticket) into your repo's GitHub issues. Each lesson tells you which checkpoint to seed, and which commit to reset to with `npm run reset <slug>`.
- **Path 2: Follow your own way.** Chart and work your own map, on this feature or one of your own. Use my map as a guide, and compare with my solutions as you go.

You can switch to Path 1 at the start of any lesson by seeding its checkpoint. The seed script refuses to run while you have an open map, so close the previous one (`gh issue close <issue-number>`) before you seed a new checkpoint.

## Steps To Complete

### Start The Session

- [ ] Open your terminal and start a Wayfinder [session](https://www.aihero.dev/ai-coding-dictionary/session) in your [agent](https://www.aihero.dev/ai-coding-dictionary/agent)

```txt
/wayfinder
```

- [ ] Describe the feature you want built after the command

Cover these points in your own words:

- You want in-app notifications inside Cadence
- A real third-party service should handle them
- You're unsure what kinds of notifications to send
- You're unsure what it should look like in the app

Your job in this session is to figure out the **destination**. The destination is not the finished feature. It is a **[spec](https://www.aihero.dev/ai-coding-dictionary/spec)**, so be specific about that in your initial prompt.

### Chart The Map

- [ ] Answer the [grilling](https://www.aihero.dev/ai-coding-dictionary/grilling) questions

Saying "I don't know" is absolutely fine. This first session is for charting the map, finding where the fog of war is and working out the destination.

- [ ] Watch for research tickets

Notice if any research tickets land, and what happens when they do.

### Read What You Made

- [ ] Once things settle down, read the map

- [ ] Read each of the tickets

Your map and tickets will differ from anyone else's. On Path 1, swap yours for mine:

- [ ] Close the map you just charted, using its issue number. The seed script refuses to run while you have an open map.

```bash
gh issue close <issue-number>
```

- [ ] Reset to the commit that adds the seed script, then seed my map and tickets with the `01-chart-the-map` checkpoint

```bash
npm run reset add-seed-wayfinder-issues
npm run seed-wayfinder-issues 01-chart-the-map
```
