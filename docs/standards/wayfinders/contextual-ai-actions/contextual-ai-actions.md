---
title: "Contextual AI actions"
description: "AI-powered tasks surfaced in place, scoped to the object or state the user is working with, so the action runs without a separate chat or blank prompt."
category: "Wayfinders"
status: "Recommended"
date: 2026-08-05
last_updated: 2026-09-25
contributors:
  - "Anh Nguyen"
  - "Lisa Lyman"
  - "Applied AI UX"
---

# Contextual AI actions

## Overview
Contextual AI Actions are AI-powered tasks surfaced and scoped in place — on the object, field, view, or system state the user is already working with. The action already knows its target, so the user does not have to restate what they are doing or start from a blank prompt. The trigger is a single, named interaction in the current UI; the outcome may stay inline or open a drawer, panel, or assistant with that context already attached.

---
## Purpose and value
- **Reduced friction:** Operates on the right input by default and cuts steps — often multi-step work into a single click. Users prefer AI embedded in tools they already use rather than a separate portal or chat.
- **Context-aware relevance:** AI works on the correct target automatically, cutting down on noise and re-prompting. Embedding into the UI means users do not have to think about prompt engineering.
- **Discoverability:** Consistent AI markers make capabilities visible at the moment of need, including diagnostic and point-of-need help.
- **Consistency and trust:** A shared convention sets accurate expectations about the output and whether it needs review — preference is for integrating AI into familiar tools rather than a proprietary chat-only surface.
- **One legible interaction:** Keeps the affordance in the user’s current workflow as one understandable, in-place action — operators can see context and act without switching systems or decoding a multi-step path to the same outcome. ([Observability Interviews (UXDR-4188)](https://issues.redhat.com/browse/UXDR-4188); )
---
## When to use
- **Clear action target:** The action is scoped to a specific object or state the user is engaged with.
- **Reliably detected context:** There is a clear status or event signaling the action is relevant — prioritize embedding into the UI when context is known over chatbot-only flows.
- **Well-defined task:** A repeatable, nameable operation that maps cleanly to a single control (for example, Summarize, Optimize, Learn more).
- **High context-switching cost:** Surfacing the action saves the user from leaving their current tool or workflow — “no new portals” and in-tool placement were consistent Summit and booth themes. (;; [Observability Interviews (UXDR-4188)](https://issues.redhat.com/browse/UXDR-4188))
- **Reviewable AI role:** The AI output can be accepted, edited, or rejected by a human.
---
## When not to use
- **General assistants:** Avoid “Ask AI anything” surfaces that are not tied to the current task. Prefer a conversational or dedicated assistant pattern instead.
- **Open-ended tasks:** Exploratory work belongs in a conversational interface, not a single contextual action.
- **Interface clutter:** Do not surface actions everywhere; too many AI entry points create visual noise and dilute trust.
- **Unreliable detection:** If the system cannot confidently determine when an action applies, do not auto-surface it.
- **High-stakes without a human gate:** Do not bypass human-in-the-loop acknowledgment for irreversible or consequential operations.
---
## Examples and visualizations
*Only product examples with available visuals are shown here. Additional product opportunities remain documented in Related research until design or shipping screenshots are shared.*

#### Inline link (OpenShift Lightspeed)
An inline “Learn more” control with the AI cue opens Lightspeed from the current field context — for example, Headless mode on a VirtualMachine — so the action runs on that topic without leaving the page. Matches the “AI in existing tools / no new portals” preference from Summit and Ask Red Hat booth feedback.

OpenShift Lightspeed inline Learn more control opening from Headless mode on a VirtualMachine

(*Note: This example shows an in-place trigger with context carried into Lightspeed (drawer/assistant). A fully in-place result (AI output that stays on the page without opening chat) will be added when available from the upcoming prototype.*)

---
## Recommended components
- **[Button](https://www.patternfly.org/components/button):** Primary control for a single, obvious scoped action in place (for example, “Summarize with AI” or “Edit with AI”). Use when one named action is the clear default on the current object.
- **[Menu](https://www.patternfly.org/components/menus/menu) / [Menu toggle](https://www.patternfly.org/components/menus/menu-toggle):** Surfaces multiple contextual AI actions from an overflow or actions menu anchored to the current object or view. Use when two or more scoped actions share the same anchor or placement is secondary — including density/overflow cases.
- **[Link](https://www.patternfly.org/components/link):** Inline control for lightweight “learn more” or explain-then-act affordances at field level (for example, “Learn more with AI” beside a setting). Use when the action should feel secondary and stay in the flow of the page.
- **[Label](https://www.patternfly.org/components/label):** Consistent AI visual cue paired with a concrete action name — additive, not a standalone trigger. Use with Button, Link, or menu items so users recognize AI-driven actions at a glance.
- **[Popover](https://www.patternfly.org/components/popover):** Local help or explain-then-act scoped to the current view without leaving the page. Use to introduce context and host a link or button that launches the action.
- **[Code editor](https://www.patternfly.org/components/code-editor):** In-editor completion and checks that run against the file or selection in context. Use when the working surface is already a code editor.
---
## Related standards
- [Contextual AI Invocation](../../input-authoring/contextual-ai-invocation/contextual-ai-invocation.md)
- [Human-in-the-Loop (HITL)](../../governors/human-in-the-loop/human-in-the-loop.md)
- [Prompt suggestions](../prompt-suggestions/prompt-suggestions.md)
- [Clarification prompts](../../conversation/clarification-prompts/clarification-prompts.md)
---
## Notes for PatternFly
- **Contextual AI action affordance is not a PatternFly pattern yet:** Button, Menu, Label, Popover, and Code editor cover the primitives, but PatternFly does not document a shared recipe for in-product AI actions — concrete action naming (avoid “AI Assist”), consistent AI visual cue, and scoping to the current object or field. Guidance for that affordance would help products implement this Wayfinder consistently.
---
## Assumptions and research questions
<a id="assumptions"></a>
#### Assumptions
No assumptions were made.
#### Research questions
No research questions at this time.
