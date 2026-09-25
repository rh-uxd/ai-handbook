---
title: "Action Confirmation"
description: "Require explicit user approval before AI executes risky, irreversible, or high-impact actions — with a clear preview of what will happen."
category: "Governors"
status: "Recommended"
date: 2026-08-12
last_updated: 2026-09-25
contributors:
  - "Anh Nguyen"
  - "Applied AI UX"
---

# Action Confirmation

## Overview

Action Confirmation is the safety gate that requires a person to explicitly approve an AI-proposed action before it runs — especially when the action is risky, irreversible, or high-impact. The pattern shows what the AI understands, what it intends to do, and the expected impact, then asks for a clear approve, cancel, or modify decision. Approval is never implied by a prior “yes,” model confidence, or speed pressure; each consequential action is verified on its own.


---

## Purpose and value

- **Keeps humans accountable:** A named person authorizes consequential AI actions instead of letting the system act alone.
- **Surfaces impact before harm:** Previewing what will change reduces courtroom-style regret after the fact.
- **Supports modify, not only yes/no:** Users can adjust the plan or parameters rather than accepting a binary choice.
- **Uses specific action language:** Labels like “Delete cluster” or “Grant execute” beat generic OK / Submit / Continue.
- **Builds trust for automation:** People adopt AI agents more readily when approval gates are visible and reliable.

---

## When to use

- **Risky, irreversible, or high-impact actions:** Deleting resources, changing production config, sending external messages, or granting credentials.
- **Blast radius is wide:** The action touches shared systems, many users, or customer-facing surfaces.
- **Permissions or credentials are involved:** Users need to see what access is being granted before execute or analyze.
- **AI confidence is high but stakes are higher:** Confidence never replaces confirmation for consequential work.
- **Customers or policy require a human gate:** Including HITL chat / approval requirements such as DTUX-2820.

---

## When not to use

- **Low-risk, easily reversible steps:** Mandatory confirmation for every trivial action creates approval fatigue.
- **Do not auto-execute from prior approvals:** A previous “yes” does not authorize the next risky action.
- **Do not skip confirmation because the model is confident:** Confidence is not consent. ([AI for Companies: Why Liability Gating Matters](https://leena.ai/blog/ai-for-companies-liability-gating-governance))
- **Do not bypass safety for speed:** Latency is not a reason to remove the gate. <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a>
- **Do not use bare yes/no without details:** If the user cannot see what will happen, the confirmation fails the pattern.

---

## Examples and visualizations

*Only product examples with available visuals are shown here. Additional product opportunities remain documented in Related research until design or shipping screenshots are shared.*

#### Ansible agent-based automation (UXDR-4913)

An Ansible concept for AI-assisted automation building: users describe a job in natural language, the system turns that into a visual workflow (nodes/agents), and people can review, tweak, and run it — ideally tied into AAP (templates, inventories, credentials).

The study (Mary Tucker; design lead Anastasia Ratti) ran 7 technical users (5 existing AAP customers, 2 potential) through interviews + think-aloud prototype tasks.

Ansible agentic automation canvas with an Add Node panel and an Approval action


#### AAP Installer testing (UXDR-5343)

A proposed wizard-style installer for Ansible Automation Platform that replaces digging through docs and hand-editing inventory files. Users walk through configuration in a GUI (component selection, sizing, network/TLS, credentials, etc.), with the broader idea of living on console.redhat.com and eventually supporting upgrades / lifecycle, not only first install.

The study (Mary Tucker) ran 5 participants with hands-on AAP install experience through a moderated “drive-along” prototype test: they watched a demo via screen share, directed what to enter, and talked through impressions of the flow and chat/output.

AAP installer wizard on the license agreement step


#### DTUX-2820 confirmation UI (no product visual yet). Action types and need for a human gate are evidenced by customer requirements.

An RHDH Augment plugin story for in-chat human-in-the-loop capabilities, driven by customer (Citi) requirements. When an agent is about to take a sensitive action — for example apply a manifest, delete a resource, or modify configuration — chat should pause for an approval dialog that shows the tool and target, lets the user review or edit parameters, supports approve/reject, and keeps an audit trail of the decision. The same ticket also covers approval workflows for publishing AI agents (developer submit → admin approve/reject with status and escalation). No product visual is included here yet. Jira ticket for reference of this project [DTUX-2820](https://redhat.atlassian.net/browse/DTUX-2820)

---

## Recommended components

- **[Modal](https://www.patternfly.org/components/modal):** Focused review surface that pauses the workflow, shows impact, and collects approve / cancel / modify.
- **[Button](https://www.patternfly.org/components/button):** Explicit action-oriented controls (for example, “Approve delete” or “Cancel”) rather than generic OK / Submit.
- **[Alert](https://www.patternfly.org/components/alert):** Risk and impact messaging inside or above the confirmation so severity is visible before approval.
- **[Checkbox](https://www.patternfly.org/components/checkbox):** Optional acknowledgments when the user must explicitly accept a listed consequence before confirming.
- **[Form](https://www.patternfly.org/components/forms/form):** Structured confirmation when multiple parameters or scoped targets must be reviewed before execute.

---

## Related standards

- [Human-in-the-Loop (HITL)](../human-in-the-loop/human-in-the-loop.md)
- [Plan Approval](../plan-approval/plan-approval.md)
- [User Override](../user-override/user-override.md)
- [Audit Trails](../audit-trails/audit-trails.md)
- [Contextual AI Actions](../../wayfinders/contextual-ai-actions/contextual-ai-actions.md)
- [Contextual AI Invocation](../../input-authoring/contextual-ai-invocation/contextual-ai-invocation.md)

---

## Notes for PatternFly

- **Action confirmation is not a PatternFly pattern yet:** Modal, Button, Alert, Checkbox, and Form cover the primitives for a confirmation gate, but PatternFly does not document a standard recipe for AI action confirmation — preview of understood intent and impact, action-specific approve/cancel/modify language, and no implied approval from prior “yes” or model confidence. Guidance for that confirmation turn would help product teams implement this standard consistently.

---

## Assumptions and research questions

<a id="assumptions"></a>
#### Assumptions

Assumptions are indicated with <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a> throughout the standard.

- **[When not to use](#when-not-to-use):** Do not bypass safety for speed

#### Research questions

1. At what confirmation volume does approval fatigue set in for users?
2. Does showing confidence alongside the confirmation gate increase or decrease review quality? When presented with a high-confidence AI action, do users still examine the confirmation details, or do they rubber-stamp?

#### Metrics to track

1. Confirmation-to-execution rate: What percentage of confirmed actions complete successfully without requiring rollback?
2. Modification rate: How often do users modify the AI's proposed action vs. approving as-is?
3. Time-to-approve: Average time users spend reviewing the confirmation.
4. Ratio of rapid approvals (< 2 seconds) to total approvals: Approval fatigue/ rubber-stamping signal
