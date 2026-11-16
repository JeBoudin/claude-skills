---
name: "team-map"
description: Never forget a team when planning. Keeps a living map of the user's teams (no personal names) - what each one owns, when to involve it and its roles - and checks every plan against it. The map grows when the user adds teams directly, and Claude offers updates whenever chats or projects reveal something new. Use whenever the user plans work across or within teams (project plan, kickoff, launch, rollout, workflow, ticket breakdown), asks who to involve or inform, or mentions teams, departments, org chart, Organigramm, Zuständigkeiten or RACI. Use it even when teams aren't mentioned, as long as the work is planning.
---

# Team map

**Why this exists:** Plans rarely fail inside a team. They fail where work passes from one team to another, or when a team that should have been involved hears about it too late. This skill keeps a small, living map of the user's teams in memory and checks it every time the user plans, so no team is forgotten. How work moves between teams lives in the wiring skill's Brain.

The map stays useful only if it stays current. It grows in two ways: the user feeds it directly ("add a team…"), and Claude offers updates whenever a chat or project reveals something the map doesn't have yet.

## Rules
- Teams and roles only, never people's names.
- Save nothing without the user's OK. Show the lines first, then wait for a yes.
- Only the team name is required. Suggest any missing fields once, marked *(suggested)*.
- Keep the user's own wording and language.

## The map
The map is one memory file, `/topics/team-map.md`, shared by all projects. It uses the standard memory frontmatter, with one line per team:

```
## Teams
- [stated] Operations · owns: day-to-day delivery, scheduling · involve when: anything that changes how work is delivered · roles: operations lead, coordinators
```

If the map isn't visible inside a claude.ai Project, that Project's memory is probably set to stay separate. Say so in one line instead of starting a second map.

## Keeping it current
- **Directly:** when the user adds, renames or removes a team, show the changed lines and save them on yes.
- **From chats and projects:** when the conversation reveals something the map lacks (an unknown team or role, or a change in what a team owns), end with one line: "Not on your map yet: … Add it?"
- **Now and then:** if the map was last updated more than about three months ago, offer a quick review once, at the end of a planning answer.

## When planning
1. Read the map, plus the project's memory file if there is one, in a single `memory_read`.
2. Do the planning as usual.
3. End with a short block:
```
**Teams to loop in**
- Brand & Content: the plan adds new customer-facing copy
Not on your map yet: Customer Service. Add it?
```
   List only teams the plan touches but leaves out, each with a one-line reason. If nothing is missing, write "Team check: no team missing." If there's no map yet, offer to set one up instead.
4. For a project, offer once to save its teams, with a one-line reason each. If the Brain (`/topics/brain.md`, from the wiring skill) exists, save them in that project's section there, so each project has one home. Otherwise, save them under `## Teams involved` in the project's memory file. A RACI letter per team is optional.
