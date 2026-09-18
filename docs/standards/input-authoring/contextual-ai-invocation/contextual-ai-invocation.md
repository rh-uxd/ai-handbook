---
title: "Contextual AI Invocation"
description: "Call AI with the user's current context captured at the trigger — the entry point and handoff that engages the AI without requiring the user to reconstruct what they were doing."
category: "Input & Authoring"
status: "Recommended"
date: 2026-08-05
last_updated: 2026-08-13
contributors:
  - "Anh Nguyen"
  - "Lisa Lyman"
  - "Applied AI UX"
---

# Contextual AI Invocation

---

## Overview

Contextual AI Invocation is the mechanism by which the AI is called — the trigger, entry point, and the automatic handoff of the user's current context into that call. Where Contextual AI Actions describe what the AI does (the discrete, scoped tasks offered to the user), invocation describes how and when the AI is engaged and how the surrounding context travels with it. The defining trait is that the relevant context — the object, field, view, selection, or system state the user is working within — is captured and passed to the AI at the moment of invocation, so the user doesn't have to reconstruct or describe it. Invocation can be explicit (user-initiated through a trigger such as a button, command, hotkey, or @-mention) or implicit (system-initiated when a detected condition or event calls the AI automatically).

---

## Purpose & Value

The value comes down to getting the AI called correctly and with full context, through a predictable trigger — so the action that follows starts from the right place without the user doing the setup.

- **Zero-setup context** - The user's situation is gathered and supplied automatically at call time, so the AI starts with the right inputs instead of an empty prompt the user has to fill in.
- **Consistent entry points** - Standardizing how the AI is invoked — the same trigger patterns across a product — makes the capability predictable and learnable, rather than a different mechanism in every feature.
- **Right-moment engagement** - Invocation can fire exactly when it's useful — when the user reaches for it, or when the system detects a condition that warrants it — instead of relying on the user to know the AI exists and go find it.
- **Separation of trigger from task** - Treating invocation as its own layer lets the same context-handoff mechanism power many different actions, keeping the interaction model consistent even as the catalog of actions grows.

---

## When to Use

- **Capturable context** - The context can be captured automatically at the point of invocation — a selection, an active object, a field, or a detected state that can travel with the call.
- **Consistent trigger pattern** - A consistent trigger pattern fits the surface — a button, command, hotkey, menu item, or @-mention the user can learn once and reuse.
- **Intent without prompt craft** - The user knows what they want but not how to ask — explicit invocation lets them engage the AI without composing a full prompt.
- **Reliable condition for implicit call** - A condition reliably signals the AI is warranted — for implicit invocation, a well-defined event or state that shouldn't require the user to notice and act first.
- **Visible and interruptible** - The invocation can be made visible and interruptible — the user can tell the AI was called, and can dismiss or cancel before anything consequential happens.

---

## When NOT to Use

- **Context can't be captured or passed reliably** - If invocation can't gather the right inputs automatically, it offers little over a plain prompt and may hand the AI the wrong target.
- **Implicit invocation would fire unpredictably** - System-initiated calls on weak or noisy signals feel intrusive and erode trust — if the condition isn't dependable, keep invocation explicit.
- **The trigger competes with core interactions** - An invocation pattern that hijacks a common gesture, hotkey, or menu slot creates friction and accidental calls.
- **Invocation is silent or unaccountable** - If the user can't tell the AI was engaged, or can't interrupt it, the mechanism becomes opaque — especially risky when it feeds a consequential action.
- **Invocation would chain straight into execution without a human gate** - Calling the AI must not, on its own, carry through to a consequential or irreversible operation — implicit invocation may surface a suggestion, but execution still passes through the HITL (human-in-the-loop) review/approval gate and remains reversible via the kill switch. (; )

---

## Examples and visualizations

*Screenshots below may not match existing implementations in products.*

**Context switch:** AI inherits the user's current working context, reducing the need for re-establishing the workflow when the AI is engaged. In Red Hat Developer Hub Intelligent Assistant, the current search term is carried into the chat as context and offered as a one-click suggested invocation.

Red Hat Developer Hub Intelligent Assistant carrying the Development search context into a suggested AI invocation

**Hybrid Cloud Console:** An AI prompt helps users get properly set up with the Hybrid Cloud Console, carrying setup context into the call instead of starting from a blank prompt. Selecting a setup-related suggestion opens the related HCC setup tasks panel.

Hybrid Cloud Console dashboard where a setup suggestion invokes the HCC setup tasks panel

---

## Recommended components

**Button:** Explicit invocation trigger that calls the AI with the current context already attached.

[Button — PatternFly](https://www.patternfly.org/components/button)

**Menu / Menu toggle:** Command or actions-menu entry points that invoke AI from the user’s current object or view.

[Menu — PatternFly](https://www.patternfly.org/components/menus/menu)

[Menu toggle — PatternFly](https://www.patternfly.org/components/menus/menu-toggle)

**Search input:** Omni-bar / search-style entry points where invocation starts from a typed query while still inheriting surrounding context.

[Search input — PatternFly](https://www.patternfly.org/components/search-input)

**Input group:** Composite entry points that combine a field with an invoke control (for example, send or “Ask AI”).

[Input group — PatternFly](https://www.patternfly.org/components/input-group)

**Hint:** Lightweight, dismissible cue that the AI can be invoked for the current situation without forcing a context switch.

[Hint — PatternFly](https://www.patternfly.org/components/hint)

---

## Related Standards

-
-
-
-

---

## Notes for PatternFly

- **Context handoff is not a PatternFly pattern yet** - Recommended components cover invocation triggers (Button, Menu, Search input, Input group, Hint), but PatternFly does not document a standard recipe for attaching page, object, or selection context at invoke time — for example, context chips, a prefilled prompt, or a clear “context carried” disclosure. A PatternFly guidance or demo for context-aware invocation would help product teams implement this standard consistently.

---

