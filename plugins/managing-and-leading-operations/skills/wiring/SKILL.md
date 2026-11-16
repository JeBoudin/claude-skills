---
name: "wiring"
description: How work flows between teams, remembered. Keeps the Brain, a memory of the flows that connect the user's teams - recurring processes, each project's chain from building to running, and the handoffs along the way - using the team names from the team-map skill. Builds new workflows on flows that already work and shows what a change will ripple into. Use when the user describes, plans, documents or changes a workflow, process or handoff, explains who does what in a project, or asks how work moves between teams or what breaks if something changes (also in German - Ablauf, Prozess, Übergabe, Schnittstelle). Use it even when the user doesn't say workflow, as long as work moves from one team or role to another.
---

# Wiring

**Why this exists:** team-map knows *who* exists. Wiring knows *how work flows* between them: the recurring processes, each project's chain from building to running, and the handoffs where one team finishes and another picks up. Plans usually break at those handoffs. Once flows are in the Brain, Claude can build new workflows on handoffs that already work and see what a change will ripple into.

## Rules
- Use the team and role names from the team map (`/topics/team-map.md`), written as `Team / role`. If a flow mentions a team or role that isn't on the map, offer to add it there. Never keep a separate team list.
- No people's names, only teams and roles.
- Save nothing without the user's OK. Mark arrows you inferred yourself as *(suggested)* until the user confirms them.
- Keep the user's own wording and language.

## The Brain
The Brain is one memory file, `/topics/brain.md`, with the standard memory frontmatter (`name: brain`, aliases: Brain, wiring, flows, handoffs). It has two kinds of sections:

```
## Recurring
- [stated] Sales / Account managers → Operations: forecasts
- [stated] Operations → Support: schedules and capacity

## Website Relaunch
- [stated] Product / Product manager: requirements, QA, onboarding, alignment
- [stated] Product / Product manager → Engineering / Developers: requirements
- [stated] Leadership / Head of engineering → Engineering / Developers: technical foundation
```

**Recurring** holds handoffs that happen again and again, whatever the project. A **project section** holds who did what in one project and who handed what to whom. When a handoff from a project turns out to recur, it goes under Recurring and isn't repeated in the project section. One line per item keeps the file small. If the file gets close to its size limit, condense finished projects to their key handoffs.

If the Brain isn't visible inside a claude.ai Project, that Project's memory is probably set to stay separate. Say so in one line instead of starting a second Brain.

## Feeding the Brain
- **Directly:** when the user describes a flow ("in the Website Relaunch, product writes the requirements…"), turn it into lines, split it into recurring and project parts, mark inferred arrows, and save on yes.
- **From chats and projects:** when a conversation reveals a new or changed handoff, end with one line: "New for the Brain: X → Y: what. Add it?"

## Using the Brain
- **Planning a workflow:** write numbered text steps, each tagged `Team / role`, with each handoff marked `→` and saying who receives what. Reuse the recurring handoffs instead of inventing new ones.
- **Changing something:** when a plan changes what a team hands over or receives, list what sits downstream. For example: "If the forecast format changes: Operations' review and the schedules and capacity handed to Support."
- **Saving:** once the user adopts a workflow, save it under its project section.
