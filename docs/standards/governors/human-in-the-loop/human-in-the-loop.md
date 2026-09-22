---
title: "Human-in-the-loop (HITL)"
description: "Keep a human in control of AI agent work — the agent investigates and prepares, and a person reviews evidence and authorizes any consequential action."
category: "Governors"
status: "Recommended"
date: 2026-08-05
last_updated: 2026-09-18
contributors:
  - "Anh Nguyen"
  - "Lisa Lyman"
  - "Applied AI UX"
---

# Human-in-the-loop (HITL)

## Overview
Human-in-the-loop (HITL) is a pattern in which an AI agent never acts entirely on its own for consequential work. A person starts the loop — for example, by asking about a project or onboarding issue. The agent investigates and summarizes what it finds. The person reviews that work, can ask for more detail or check links to underlying resources, and must authorize any action before it runs. The agent does the heavy lifting (gathering data, drafting, preparing a resolution); the person provides judgment and final authorization, and can stop the process at any time.

---
## Purpose and value
Because AI agents may omit small details, the team deploying the agent — not the model vendor — is responsible for its output. HITL addresses that responsibility by:

- **Establishing accountability:** A named person authorizes consequential decisions, so there is a human owner of record.
- **Catching confident errors:** Humans can flag paraphrases, omissions, or claims the agent cannot trace to a source.
- **Creating a defensible record:** Active authorization proves a review happened, including when and by whom.
- **Keeping action safe:** The agent only executes what a person has explicitly approved.
- **Preserving a stop:** Allowing a person to terminate or halt an AI agent’s activity mid-run or mid-resolution using a “kill switch” control.
- **Building trust and adoption:** Users rely on the agent more when they know they retain final control.
---
## When to use
Use HITL for agent actions that require explicit review and authorization, including:

- **Irreversible actions:** Deleting data, sending external messages, or changing production configurations.
- **Production impact:** Actions that touch live systems or have a wide blast radius.
- **Unverified claims drive a decision:** When an agent's summary (which might paraphrase or miss details) is the basis for acting.
- **Third-party exposure:** Potential for false or incomplete output to mislead or harm people outside the immediate team. <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a>
- **External-facing output:** Anything posted, published, or sent on the team's behalf. <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a>
- **Inference beyond sources:** When the agent is uncertain or draws conclusions not directly backed by linked sources.

HITL also fits when:

- **Risk justifies friction:** Outcome risk is high enough that a review step is worth the cost.
- **Evidence is available:** The interface can show underlying links, confidence, tools used, or other evidence.
- **Claims are assessable:** Recorded facts versus inferred claims are clearly labeled.
- **Review is always available:** Authorization is a clear, reachable step — not buried or optional for high-risk paths. <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a>
- **A qualified reviewer can respond:** Someone able to judge the action is available within a timeframe that does not break the workflow. <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a>
---
## When not to use
- **Low-risk plan work:** Avoid mandatory authorization for early gathering, drafting, or proposal work where review adds friction without a clear safety gain. <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a>
- **Approval fatigue:** If volume is so high that reviewers rubber-stamp without reading, HITL creates a false sense of oversight — narrow what requires a gate, or redesign the workflow.
- **Time-critical safe actions:** Skip a required gate for safe, automated responses (for example, auto-scaling or failover) where delay is the larger risk. <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a>
- **Passive disclaimers instead of review:** Phrases like “The AI may be wrong” are not a substitute for active authorization on consequential actions.
- **Review after the fact:** Authorization must happen before the agent resolves or executes the consequential step — not only in an after-action log.
---
## Examples and visualizations
*Screenshots below may not match existing implementations in products.*

#### Migration review
Before a consequential workspace change, the user reviews AI-generated impact (who gains or loses access) and only then decides whether to submit. In this Hybrid Cloud Console / ACM-style flow, selecting a destination workspace surfaces a Review control that opens the Virtual Assistant with the migration impact, but the actual submission must be manually executed by the user.

Migration review flow: Change workspace modal with Review control opening Virtual Assistant impact analysis before submit

*[Github](https://github.com/KendraMar/HCCconcierge) (Experience 4 - follow the pink arrows for expected userflow)*

#### HITL authorization workflow
A person triggers work that needs review before it can move forward. The agent presents findings — summarized information, source links, and proposed changes. The person reviews the plan (questions, potential outcomes, linked resources), can modify or override the decision, then either approves and executes or stops the run with a kill switch.

1. **Trigger:** Surface friction or a consequential request that must not proceed without review.
2. **Agent presents findings:** Summary, source links, and proposed changes.
3. **Plan / review:** Person inspects outcomes and resources.
4. **Modify / override:** Person adjusts the decision or command as needed. Once edited, the UI should show the value as human-owned (for example, remove the AI cue) rather than still looking AI-proposed. <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a>
5. **Approve & execute — or kill switch:** Action runs only after approval; otherwise the person stops the agent.

#### Shared-platform accountability
On channels such as Slack or other shared surfaces, the review record should show who authorized the action, not only that “someone” approved it.

---
## Recommended components
- **[Button](https://www.patternfly.org/components/button):** Explicit approve, reject, modify, or kill-switch controls that keep consequential agent work under human authorization.
- **[Modal](https://www.patternfly.org/components/modal):** A modal forces the user to pause and consider their actions before proceeding. This positive friction is a critical safety feature that encourages users to carefully verify the agent's response before committing.
- **[Alert](https://www.patternfly.org/components/alert):** Status and risk messaging around pending authorization, failed review, or a halted agent run.
- **[Helper text](https://www.patternfly.org/components/helper-text):** Supporting copy that separates recorded facts from inferred claims during review.
---
## Related standards
---
## Notes for PatternFly
- **HITL authorization workflow is not a PatternFly pattern yet:** Recommended components cover approve/reject controls and review surfaces (Button, Modal, Alert, Helper text), but PatternFly does not document a standard recipe for the full HITL loop — plan/findings review with evidence, modify/override, explicit authorization, and an interruptible kill switch mid-run. A PatternFly guidance or demo for agent authorization would help product teams implement this standard consistently.
---
## Assumptions and research questions
<a id="assumptions"></a>
#### Assumptions
Assumptions are indicated with <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a> throughout the standard.
- **[When to use](#when-to-use):** Third-party exposure, External-facing output, Review is always available, A qualified reviewer can respond
- **[When not to use](#when-not-to-use):** Low-risk plan work, Time-critical safe actions
- **[Examples and visualizations](#examples-and-visualizations):** Modify / override
#### Research questions
- Research team to add assumptions or further research questions.
