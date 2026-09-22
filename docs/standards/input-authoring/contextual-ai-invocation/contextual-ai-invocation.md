---
title: "Contextual AI Invocation"
description: "How a product opens an AI conversation or capability from the place the user already is, with enough of their current situation attached that they don't have to re-explain what they were doing."
category: "Input & Authoring"
status: "Recommended"
date: 2026-08-05
last_updated: 2026-09-18
contributors:
  - "Anh Nguyen"
  - "Lisa Lyman"
  - "Applied AI UX"
---

# Contextual AI Invocation

## Overview
Contextual AI Invocation is how a product opens an AI conversation or capability from the place the user already is — with enough of their current situation attached that they don’t have to re-explain what they were doing.

In practice, invocation is three things working together:

- **A trigger:** The control or signal that starts the call (for example, a button, command, hotkey, menu item, @-mention, or a system condition)
- **An entry point:** The UI surface where the AI experience appears (for example, a chat drawer, panel, omni-bar, or inline field). This may be the same control as the trigger, or a different surface that opens after the trigger. It is not always a blank prompt — the user may land on a prefilled or suggested turn
- **A context handoff:** The automatic capture and passing of relevant state into the AI (object, field, view, selection, page, project, cluster, or other system state)

Without that handoff, the user lands in a blank prompt and has to rebuild the situation in words; with it, the AI starts from the same frame the user already has.

Invocation can be explicit (the user chooses to call the AI through a button, command, hotkey, menu item, or @-mention) or implicit (the system calls the AI when a reliable condition or event warrants it). In both cases, the pattern is successful when the call is findable or timely, the carried context is visible enough to trust, and the user can dismiss or interrupt before anything consequential happens.

---
## Purpose and value
The value comes down to getting the AI called correctly and with full context, through a predictable trigger — so the action that follows starts from the right place without the user doing the setup.

- **Zero-setup context:** The user's situation is gathered and supplied automatically at call time, so the AI starts with the right inputs instead of an empty prompt the user has to fill in.
- **Consistent entry points:** Standardizing how the AI is invoked — the same trigger patterns across a product — makes the capability predictable and learnable, rather than a different mechanism in every feature. <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a>
- **Right-moment engagement:** Invocation can fire exactly when it's useful — when the user reaches for it, or when the system detects a condition that warrants it — instead of relying on the user to know the AI exists and go find it.
- **Separation of trigger from task:** Treating invocation as its own layer lets the same context-handoff mechanism power many different actions, keeping the interaction model consistent even as the catalog of actions grows. <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a>
---
## When to use
- **Capturable context:** The context can be captured automatically at the point of invocation. <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a>
- **Consistent trigger pattern:** A consistent trigger pattern fits the surface — a button, command, hotkey, menu item, or @-mention the user can learn once and reuse. <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a>
- **Intent without prompt craft:** The user knows what they want but not how to ask — explicit invocation lets them engage the AI without composing a full prompt.
- **Reliable condition for implicit call:** A condition reliably signals the AI is warranted — for implicit invocation, a well-defined event or state that shouldn't require the user to notice and act first. <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a>
- **Visible and interruptible:** The user can tell the AI was called, and can dismiss or cancel before anything consequential happens.
---
## When not to use
- **Context can't be captured or passed reliably:** If invocation can't gather the right inputs automatically, it offers little over a plain prompt and may hand the AI the wrong target. <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a>
- **Implicit invocation would fire unpredictably:** System-initiated calls on weak or noisy signals feel intrusive and erode trust — if the condition isn't dependable, keep invocation explicit.
- **The trigger competes with core interactions:** An invocation that hijacks a common gesture, hotkey, or menu slot creates friction and accidental calls.
- **Invocation is silent or unaccountable:** If the user can't tell the AI was engaged, or can't interrupt it, the mechanism becomes opaque — especially risky when it feeds a consequential action.
- **Invocation would chain straight into execution without a human gate:** Calling the AI must not, on its own, carry through to a consequential or irreversible operation — implicit invocation may surface a suggestion, but execution still passes through the HITL (human-in-the-loop) review/approval gate and remains reversible via the kill switch.
---
## Examples and visualizations
*Screenshots below may not match existing implementations in products.*

#### Context switch
AI inherits the user's current working context, reducing the need for re-establishing the workflow when the AI is engaged. In Red Hat Developer Hub Intelligent Assistant, the current search term is carried into the chat as context and offered as a one-click suggested invocation.

Red Hat Developer Hub Intelligent Assistant carrying the Development search context into a suggested AI invocation

* / [Working prototype](https://lightspeed-plugin-477a0f.pages.redhat.com/intelligent-assistant) (VPN required)*

#### Intent without prompt craft
An AI prompt helps users get properly set up with the Hybrid Cloud Console, carrying setup context into the call instead of starting from a blank prompt. Selecting a setup-related suggestion opens the related HCC setup tasks panel.

Hybrid Cloud Console dashboard where a setup suggestion invokes the HCC setup tasks panel

*[Github](https://github.com/KendraMar/HCCconcierge) (Experience 3 - follow the pink arrows for expected userflow)*

---
## Recommended components
- **[Button](https://www.patternfly.org/components/button):** Explicit invocation trigger that calls the AI with the current context already attached.
- **[Menu](https://www.patternfly.org/components/menus/menu) / [Menu toggle](https://www.patternfly.org/components/menus/menu-toggle):** Command or actions-menu entry points that invoke AI from the user’s current object or view.
- **[Search input](https://www.patternfly.org/components/search-input):** Omni-bar / search-style entry points where invocation starts from a typed query while still inheriting surrounding context.
- **[Input group](https://www.patternfly.org/components/input-group):** Composite entry points that combine a field with an invoke control (for example, send or “Ask AI”).
- **[Hint](https://www.patternfly.org/components/hint):** Lightweight, dismissible cue that the AI can be invoked for the current situation without forcing a context switch.
---
## Related standards
---
## Notes for PatternFly
- **Context handoff is not a PatternFly pattern yet:** Recommended components cover invocation triggers (Button, Menu, Search input, Input group, Hint), but PatternFly does not document a standard recipe for attaching page, object, or selection context at invoke time — for example, context chips, a prefilled prompt, or a clear “context carried” disclosure. A PatternFly guidance or demo for context-aware invocation would help product teams implement this standard consistently.
---
## Assumptions and research questions
<a id="assumptions"></a>
#### Assumptions
Assumptions are indicated with <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a> throughout the standard.
- **[Purpose and value](#purpose-and-value):** Consistent entry points, Separation of trigger from task
- **[When to use](#when-to-use):** Capturable context, Consistent trigger pattern, Reliable condition for implicit call
- **[When not to use](#when-not-to-use):** Context can't be captured or passed reliably
#### Research questions
- Research team to add assumptions or further research questions.
