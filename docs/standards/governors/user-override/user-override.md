---
title: "User override"
description: "Modify, reject, or manually control AI recommendations before they are applied, keeping human agency over consequential output"
category: "Governors"
status: "Experimental"
date: 2026-09-25
last_updated: 2026-09-25
contributors:
  - "Mary Shakshober-Crossman"
  - "Applied AI UX"
---

# User override

## Overview

User override enables people to modify, reject, or manually control AI recommendations before they are applied — keeping human agency over consequential output. AI suggestions are treated as an editable draft, not a final decision: users can accept in part, edit inline, regenerate, or take over manually, and the system should be able to distinguish what the AI proposed from what the person finalized.


---

## Purpose and value

- **Keeps humans in charge of the plan**: Users want to modify the plan, not only approve or reject a binary choice.
- **Treats AI output as an editable draft:** Suggestions are starting points users can adjust before execution, similar to a PowerShell “WhatIf” preview mindset inspect and reshape before commit.
- **Supports partial acceptance:** People can keep what is useful, change what is wrong, and discard the rest — without forcing an all-or-nothing decision.
- **Preserves engineer control:** Practitioners explicitly want more control — including editing flows and exporting artifacts (for example YAML/JSON) into their own tooling.
- **Enables fork, version, and compare:** Industry prompt-management patterns (Save As / Fork, versioning, side-by-side diff) let users branch from AI output into their own durable version rather than accepting defaults.
- **Supports manual override and resume in workflows:** When an agent stalls, users can investigate, correct, and resume from that point — with a clear way to pause or cancel the whole run.

---

## When to use

- **AI proposes a plan or configuration before execution:** Users need to adjust steps, parameters, or scope before the agent runs — for example a generated test plan they can manually edit.
- **Binary accept/reject is too coarse:** The recommendation is partly right; users need inline edit, partial accept, or regenerate alongside modify.
- **Output becomes a reusable artifact:** Prompts, templates, playbooks, or flows that users will own — support Save As / Fork, versioning, and diff so overrides become durable.
- **Workflow failure needs human correction mid-run:** Pause at the failure point, let the user fix data or steps, then resume — rather than forcing a full restart.
- **Users will take the result into their own systems:** Export or handoff of editable source (YAML, JSON, code) so control continues outside the AI UI.
- **Accountability requires a human-finalized record:** Track what the AI suggested versus what the user changed before applying. ([Editable AI Output](https://uxpatternsguide.com/patterns/editable-ai-output/))

---

## When not to use

- **Do not force binary accept/reject only:** If the useful response is “change this part,” a yes/no gate fails the pattern.
- **Do not auto-apply AI recommendations:** Applying without an editable review step removes override entirely.
- **Do not make overriding harder than accepting:** If edit/reject is buried, slow, or high-friction compared to Accept, people rubber-stamp. ([Override Patterns](https://www.operion.io/learn/component/override-patterns))
- **Do not remove override for “repeat” scenarios:** Familiarity or prior approval does not justify locking future suggestions.
- **Do not confuse override with a simple patch/deny decision:** Some tasks only need a clear approve or deny (for example a single patch action). Use a simple gate there — not a heavyweight editor — but still keep an escape hatch when users need more control. ([TPA User Interview Study](https://doi.org/10.1145/3772363.3798555))
- **Do not treat confirmation alone as override:** Confirming impact is not the same as editing the recommendation; use both when the plan itself may need changes.

---

## Examples and visualizations

*Only product examples with available visuals are shown here. Additional product opportunities remain documented in Related research until design or shipping screenshots are shared.*

#### Ansible agent-based automation (UXDR-4913)

Users asked to modify agent-generated plans — not only approve or reject — including requests for a test plan the agent generates that they can manually adjust before execution. Override here means editable workflow/plan control before run.


*(No product visual is included here yet for a dedicated “edit the plan” override surface; treat visual treatment as an assumption until design or shipping screenshots are shared.)* <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a>

#### Prompt management: Save As / Fork and versioning

Competitive prompt platforms let users modify AI or template content, create new versions, compare with side-by-side diffs, and fork (“Save As”) into a personal or org copy — rather than accepting a default. RHOAI has historically lacked a clear Save As concept (called out as a gap toward 3.5).


#### Manual override and resume (Agentic AI Orchestration patterns)

For complex failures where auto-recovery is not enough, the workflow pauses at the failure point; the user investigates, manually corrects, and resumes from that exact point — with a clearly marked emergency exit to pause or cancel the entire workflow.


#### Ask Red Hat / Summit: preview-before-commit mental model

Booth and Summit notes frame AI output with a PowerShell “WhatIf” analogy, users expect to preview and reshape before anything is committed. Use as a mental model for override affordances until product screenshots are available.


---

## Recommended components

- **[Form](https://www.patternfly.org/components/forms/form)** / **[Text input](https://www.patternfly.org/components/forms/text-input):** Inline editing of AI-suggested fields, plans, or parameters before apply.
- **[Button](https://www.patternfly.org/components/button):** Explicit Accept, Reject, Edit, Regenerate, Resume, or Cancel — with action-specific labels.
- **[Code editor](https://www.patternfly.org/components/code-editor):** Override of generated YAML, JSON, scripts, or playbooks before execution or export.
- **[Modal](https://www.patternfly.org/components/modal):** Focused edit/review surface when override needs more space than an inline field.
- **[Drawer](https://www.patternfly.org/components/drawer):** Side-by-side review of AI suggestion versus user edits without leaving the primary workflow.
- **[Diff](https://www.patternfly.org/components/code-editor#diff-editor)** *(when available)* / compare views: Show what changed between AI suggestion and user-finalized content.

---

## Related standards

- [Human-in-the-Loop (HITL)](../human-in-the-loop/human-in-the-loop.md)
- [Action Confirmation](../action-confirmation/action-confirmation.md)
- [Retry & Recovery](../../error-handling/retry-recovery/retry-and-recovery.md)
- [Plan Approval](../plan-approval/plan-approval.md)
- [Audit Trails](../audit-trails/audit-trails.md)
- [Prompt templates](../../conversation/prompt-templates/prompt-templates.md)
- [Structured prompts](../../input-authoring/structured-prompts/structured-prompts.md)

---

## Notes for PatternFly

- **User Override is not a PatternFly pattern yet:** Form, Button, Code editor, Modal, and Drawer cover the primitives, but PatternFly does not document a standard recipe for AI override — editable-draft treatment, partial accept, AI-vs-user tracking, regenerate-alongside-edit, and mid-workflow manual override and resume. Guidance for that control turn would help product teams implement this standard consistently.

---

## Assumptions and research questions

<a id="assumptions"></a>
#### Assumptions

Assumptions are indicated with <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a> throughout the standard.

- **[Examples and visualizations](#examples-and-visualizations):** Ansible agent-based automation (UXDR-4913)

#### Research questions

1. When do users prefer full inline editing versus modify-then-confirm versus simple approve/deny?
2. How should the UI show what the AI suggested versus what the user changed?
3. What override affordances are essential mid-workflow vs. only at end of plan?

#### Proposed Metrics to track

1. Override rate: % of AI suggestions where users modify at least one element before accepting.
2. Override-to-accept friction ratio: Number of interactions required to override vs. accept. Evaluate if override ≤ accept.
