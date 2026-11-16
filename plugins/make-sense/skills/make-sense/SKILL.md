---
name: "make-sense"
description: Does it make sense? Judge relentlessly whether a request, plan, feature, budget, process, code or design makes sense from a named role's point of view, with a verdict and score, key reasons, stakeholder views and questions for the requester. Use when the user writes "As [role], does it make sense?", "As [role], willing to [find out X]", "/make-sense", or "Als [Rolle], macht das Sinn?", or asks "does this make sense?" about a plan or request without naming a role. Not for proofreading.
metadata:
  category: business
---

# Make sense

The user wants a second opinion before they act on something, approve it, or pass it on: a request from a colleague, their own plan, a feature idea, a budget, some code, a design. They choose whose eyes to look through. Your job is to look at it the way that person would, honestly, and give the user something they can act on at a glance: a clear verdict with a score, the key reasons, how the people around it will react, and the questions to send back to whoever asked.

## Step 1: Find what's being judged, and the focus

The thing to judge can be text pasted with the question, an attached file, something earlier in the conversation, or a link. Read it properly before judging; a verdict on something skimmed is worthless.

The user may also name a focus: "As CFO, willing to find out if this pays back within a year", "As support agent, want to know if this slows down ticket handling". Then the focus is the question the verdict answers. Center the reasons and questions on it, and raise other issues only if they would change the answer. Without a focus, judge the thing as a whole.

If it isn't clear what to judge, ask, together with any question from Step 2.

## Step 2: Settle the role and the stakeholders

Before judging, ask for whatever is missing, all in one message. If you have a tool for tappable choices, use it, one question per item below with multi-select; the user can always type their own answer. Otherwise ask with short lists. Then stop and wait.

**Role, if none is named.** The point of the skill is the user's choice of lens, and a guessed role hides that choice. Offer 2–3 roles that fit what's being judged, drawn from the conversation, any files, and what you know about the user's work. Each option gets a few words on its focus, e.g. "CFO: cost and payback". The user can pick several or add their own.

A named role is used as given. A role can be anything: a job title (CFO, head of support, backend engineer), a function (controlling, customer operations), a stakeholder (regular customer, supplier, investor), or a type of person (new hire, first-time visitor). Don't swap it for one you think fits better.

**Stakeholders, whenever the thing affects people beyond the role.** Ask who else should be considered. Offer 2–3 stakeholders drawn from the context (teams, customers, partners, the requester) plus "None, just the role". Their likely reactions often decide whether a request goes anywhere, and the user knows the people involved better than you do. Skip this question when the user already named the stakeholders or asked to skip it, or when the thing plainly affects nobody beyond the role.

If the role is named and stakeholders are settled or not relevant, go straight to judging.

Example: "Does this make sense?" with a plan to switch a loyalty program from points to tiers → two tappable questions:

> **Which role should I judge this as?** (pick one or more)
> CFO: reward cost and margin · CRM manager: engagement, points carry-over · Regular customer: what they gain or lose
>
> **Who else should I take into account?**
> Support team · Marketing · Existing members · None, just the role

## Step 3: Build the lens

Before judging, work out who this role is: what they're accountable for, how their success is measured, what worries them, and what they'd need to see before saying yes. A CFO thinks in cash, margin, payback and risk; a head of support in ticket backlog, customer experience and staff load; an engineer in complexity, maintenance and data quality; a customer in value, effort and trust. Work this out fresh for each role instead of reaching for a generic checklist. The specific angle is what makes the review useful.

Do the same, briefly, for each stakeholder: what they gain or lose, and how they're likely to react.

Stay inside the role's interests and knowledge. If the thing falls outside what the role could judge (a support agent reviewing a SQL query), say so in one line, judge only what touches them, and suggest a better-placed role. Stay in role for the whole review; don't add your own view unless the user asks.

If the user names several roles ("as CFO and as head of support"), review each one.

## Step 4: Judge and score

Go through these questions as the role would, and keep only the ones that actually drive the verdict:

- **Problem**: is it clear what problem this solves, and for whom?
- **Evidence**: what supports it (data, customer feedback, a test, precedent), or is it assumption?
- **Cost**: money, time, people, complexity, and what else won't get done meanwhile.
- **Fit**: does it fit the goals, strategy, existing processes and systems?
- **Risk**: what could go wrong, how badly, and how easily can it be reversed?
- **Alternatives**: is there a simpler or cheaper way to get most of the value? What happens if nothing is done?

Then give a score from 0% to 100% for how well it holds up from this role's view. 0% is a clear no; 100% is perfection, nothing left to improve, so it is rare. The verdict must match the score's band, so the number confirms the verdict:

| Verdict | Score | Meaning |
|---|---|---|
| ✅ **Makes sense** | 85–100% | go ahead as is |
| 🤏 **Almost there** | 75–84% | go ahead after small fixes |
| 🙂 **Good, could be better** | 50–74% | worth doing, with clear changes |
| 🛠️ **Needs work** | 35–49% | promising core, real rework first |
| ❌ **Doesn't make sense** | 0–34% | as it stands, this role would say no |
| ❓ **Can't tell yet** | score on what's known, marked "so far" | the deciding information is missing |

A score on a boundary belongs to the higher band: 85% is ✅, 75% is 🤏, 50% is 🙂, 35% is 🛠️.

Use ❓ when missing information could move the score into another band. As a rough calibration, a sound plan needing only small fixes sits around 75–84%, a good idea with one or two open conditions around 55–70%, and a promising idea that needs real rework around 40%.

Be honest rather than diplomatic. Don't drift up a band to soften a no, don't round scores up, and don't invent figures to reach a verdict. When the deciding information is missing, ❓ is the right answer, and the questions in the output are how the user gets that information.

## Step 5: Write the answer

The answer should be grasped in seconds. Write in short fragments, not full sentences. Bold the 2–3 elements that drive the verdict so the eye lands on them first. No filler, no intro, no recap at the end.

Use this structure:

```
### [emoji] [Verdict label] · [score]%
**[The reason behind the verdict, in 5–7 words]**
As [role]: [1–2 short lines with the bottom line; for 🤏, 🙂 and 🛠️, what it takes to move up]

**Why**
- **[Key element]** → [why it matters to this role, a few words]
- **[Key element]** → [a few words]
- [Element] → [a few words]

**Stakeholders**
- 👍 **[Stakeholder]** → [likely opinion, a few words]
- 🤔 **[Stakeholder]** → [a few words]
- 👎 **[Stakeholder]** → [a few words]

**Questions to ask the requester**
1. [Short, specific question]
2. …
```

Notes on each part:

- **Headline.** The verdict leads, so the answer is clear before anything else is read. For ❓, write the score as "~50% so far". With a focus from Step 1, the line under the headline reads "As [role], on [focus]: …".
- **Why.** 2–4 points, most important first. When the thing is large or spans several areas (a full concept, a multi-part plan), group the points under short labelled headings instead, each with an *In short* line:

  ```
  **💰 Cost** · *In short:* **payback unclear**
  - no subscriber target
  - €18k committed upfront
  ```

- **Stakeholders.** Only when stakeholders were chosen in Step 2 or clearly matter. 👍 likely for, 🤔 mixed or needs convincing, 👎 likely against. Keep each to its likely opinion and the reason behind it.
- **Questions.** 3–5, ordered by how much the answer would move the verdict. Short enough to paste straight into a reply to the requester, neutral in tone, and specific: ask for the number, the date or the example, not "can you elaborate?".

With several roles, give one block per role (headline, line, Why), then **Where they disagree** in 1–2 bullets, then Stakeholders and Questions once for all roles, without repeats.

Answer in the language the user wrote in. If the user follows up with "and as [another role]?", repeat Steps 3–5 for the new role on the same thing.

## Example

"As head of customer support, does it make sense?" about a request to add live chat to the website; the user picked support agents, customers and marketing as stakeholders:

> ### 🙂 Good, could be better · 60%
> **Pilot first, with one shared ticket queue**
> As head of customer support: pilot on one page, only if chats land in the same queue as email tickets.
>
> **Why**
> - **Split queue** → two inboxes to watch, slower replies overall
> - **Chat hours not staffed** → who answers outside office hours?
> - **Fewer help-center visits** → self-service deflection at risk
>
> **Stakeholders**
> - 👎 **Support agents** → extra parallel chats, two queues to watch
> - 👍 **Customers** → instant answers, no waiting for email
> - 🤔 **Marketing** → more conversions, less control over tone
>
> **Questions to ask the requester**
> 1. Same queue and tooling as email tickets?
> 2. Who answers chats, and is that in the staffing plan?
> 3. Which page pilots it, and what result means roll out or stop?
> 4. Which problem does this solve: slow replies, or something else?
