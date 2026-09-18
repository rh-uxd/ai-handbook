---
title: "Action Confirmation"
description: "Require explicit user approval before AI executes risky, irreversible, or high-impact actions — with a clear preview of what will happen."
category: "Governors"
status: "Recommended"
date: 2026-08-12
last_updated: 2026-08-12
contributors:
  - "Anh Nguyen"
  - "Applied AI UX"
---

# Action Confirmation

---

## Overview

Action Confirmation is the safety gate that requires a person to explicitly approve an AI-proposed action before it runs — especially when the action is risky, irreversible, or high-impact. The pattern shows what the AI understood, what it intends to do, and the expected impact, then asks for a clear approve, cancel, or modify decision. Approval is never implied by a prior “yes,” model confidence, or speed pressure; each consequential action is verified on its own.

Action Confirmation is a primary Human-in-the-Loop (HITL) control within the Governors category.

---

## Purpose & Value

- **Keeps humans accountable** - A named person authorizes consequential AI actions instead of letting the system act alone.
- **Surfaces impact before harm** - Previewing what will change reduces courtroom-style regret after the fact.
- **Supports modify, not only yes/no** - Users can adjust the plan or parameters rather than accepting a binary choice.
- **Uses specific action language** - Labels like “Delete cluster” or “Grant execute” beat generic OK / Submit / Continue.
- **Builds trust for automation** - People adopt AI agents more readily when approval gates are visible and reliable.

---

## When to Use

- **Risky, irreversible, or high-impact actions** - Deleting resources, changing production config, sending external messages, or granting credentials.
- **Blast radius is wide** - The action touches shared systems, many users, or customer-facing surfaces.
- **Permissions or credentials are involved** - Users need to see what access is being granted before execute or analyze.
- **AI confidence is high but stakes are higher** - Confidence never replaces confirmation for consequential work.
- **Customers or policy require a human gate** - Including HITL chat / approval requirements such as DTUX-2820.

---

## When NOT to Use

- **Low-risk, easily reversible steps** - Mandatory confirmation for every trivial action creates approval fatigue.
- **Do not auto-execute from prior approvals** - A previous “yes” does not authorize the next risky action.
- **Do not skip confirmation because the model is confident** - Confidence is not consent.
- **Do not bypass safety for speed** - Latency is not a reason to remove the gate.
- **Do not use bare yes/no without details** - If the user cannot see what will happen, the confirmation fails the pattern.

---

## Examples

**Modal:** Focused review surface that pauses the workflow, shows impact, and collects approve / cancel / modify.

[Modal — PatternFly](https://www.patternfly.org/components/modal)

**Button:** Explicit action-oriented controls (for example, “Approve delete” or “Cancel”) rather than generic OK / Submit.

[Button — PatternFly](https://www.patternfly.org/components/button)

**Alert:** Risk and impact messaging inside or above the confirmation so severity is visible before approval.

[Alert — PatternFly](https://www.patternfly.org/components/alert)

**Checkbox:** Optional acknowledgments when the user must explicitly accept a listed consequence before confirming.

[Checkbox — PatternFly](https://www.patternfly.org/components/checkbox)

**Form:** Structured confirmation when multiple parameters or scoped targets must be reviewed before execute.

[Form — PatternFly](https://www.patternfly.org/components/forms/form)

---

## Existing Work

**Ansible agent-based automation (UXDR-4913):** Participants consistently required human approval before risky automation; users wanted to modify plans, not only approve or reject.

**AAP Installer testing (UXDR-5343):** Confirmation needed before credential operations — users expect to know what permissions are granted on execute.

**DTUX-2820 customer HITL chat requirement:** Product demand for human-in-the-loop chat capabilities that pause for explicit confirmation before consequential agent actions.

**Agentic AI Approval Gates:** Workflows that explicitly pause before sensitive or irreversible steps and await confirmation with action-specific language.

---

## Related Standards

-
- Plan Approval
- User Override
- Audit Trails
-
-

---

