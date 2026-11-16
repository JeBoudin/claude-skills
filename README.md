# Claude skills for managing & leading operations

Three small skills for Claude. I use them day to day as a product manager, but nothing in them is specific to product work. If you plan work across teams, hand work from one team to another, or have to say yes or no to someone's request, you can use them too.

Each skill is a single plain-text file (`SKILL.md`) that tells Claude how to do one job. You can open any of them and read exactly what it will do before you install it.

## Managing & leading operations: team-map + wiring

Two skills that work as a pair. They keep a small picture of your organization in Claude's memory, so every plan you make is checked against it.

| Skill | What it does |
|---|---|
| **team-map** | Keeps a living map of your teams (what each owns, when to involve it, its roles) and checks every plan against it, so no team gets forgotten. |
| **wiring** | Remembers how work flows between your teams: recurring handoffs and each project's chain from building to running. It builds new workflows on handoffs that already work and shows what a change will ripple into. |

Install both, because wiring uses the team names from team-map. They keep their data in Claude's memory (files such as `/topics/team-map.md`), so **memory must be turned on**. They store only team and role names, never people's names, and they save nothing until you say yes.

## make-sense

A second opinion on a request, plan, budget, feature, piece of code or design, judged from a role you choose (CFO, head of engineering, new hire, customer, anything). You get a verdict with a score, the key reasons, how the people around it will likely react, and questions to send back to whoever asked. It works on its own and does not need memory.

## Install

### Claude.ai and Claude Desktop

1. Download the zip for each skill you want from the [latest release](https://github.com/JeBoudin/claude-skills/releases/latest): `team-map.zip`, `wiring.zip`, `make-sense.zip`.
2. Open **Settings**, find the **Skills** section, and upload the zip.
3. Switch the skill on.

Custom skills need a Pro, Max, Team or Enterprise plan with code execution enabled ([Anthropic's overview](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview)). For team-map and wiring, also turn on **memory**.

Tip: Safari sometimes unzips downloads automatically. Upload the zip, not the unpacked folder. If your browser unpacked it, zip the folder again.

### Claude Code

**Option A: as a plugin** (updates arrive automatically)

```bash
claude plugin marketplace add JeBoudin/claude-skills
claude plugin install managing-and-leading-operations@claude-skills   # team-map + wiring
claude plugin install make-sense@claude-skills
```

Inside a running Claude Code session you can use `/plugin marketplace add ...` and `/plugin install ...` instead. Plugin skills are called with the plugin name in front, for example `/make-sense:make-sense`. Claude also picks them up on its own when your request fits.

**Option B: copy the folders**

```bash
cp -r plugins/managing-and-leading-operations/skills/team-map  ~/.claude/skills/
cp -r plugins/managing-and-leading-operations/skills/wiring    ~/.claude/skills/
cp -r plugins/make-sense/skills/make-sense                     ~/.claude/skills/
```

Use `.claude/skills/` inside a project folder instead of `~/.claude/skills/` if you want them for that project only. See [Claude Code's plugin docs](https://code.claude.com/docs/en/plugins/publish) for details.

## How to use them

**team-map**: tell Claude about your teams (`Add a team: Customer Support, owns tickets and refunds`), then plan as usual. Plans end with a short **Teams to loop in** block listing any team the plan touches but leaves out.

**wiring**: describe a flow (`In the website relaunch, product writes the requirements, engineering builds, support gets a handover`). Claude turns it into handoff lines, shows them to you, and saves them once you agree. Later it can show what a change will affect downstream.

**make-sense**: paste or attach the thing, then ask:

- `As head of engineering, does it make sense?`
- `As CFO, willing to find out if this pays back within a year`
- `/make-sense`

If you don't name a role, Claude asks which lens you want. Follow up with "and as a customer?" to get a second view of the same thing.

All three answer in the language you write in.

## License

MIT, see [LICENSE](LICENSE).
