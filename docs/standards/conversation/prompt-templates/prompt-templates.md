---
title: "Prompt templates"
description: "Reusable prompt structures with fillable variables that encode proven phrasing for repeated tasks — saved instruments for practiced users, not starter suggestions."
category: "Conversation"
status: "Recommended"
date: 2026-08-06
last_updated: 2026-08-12
contributors:
  - "Anh Nguyen"
  - "Lisa Lyman"
  - "Applied AI UX"
---

# Prompt templates

---

## Overview

Prompt templates are reusable prompt structures with fillable variables that users customize for repeated tasks. The template holds the stable part — framing, constraints, and phrasing — while variables mark the parts that change between uses. Instead of rewriting from scratch, the user fills in slots and sends. Templates are typically user- or team-authored.

They differ from prompt suggestions: suggestions are system-offered examples for newcomers; templates are saved instruments for power users. The presence of a variable is the defining trait — a reusable prompt without fillable parts is a saved prompt, not a template.

Prompt templates are one of four conversational prompt types (alongside structured prompts, clarification prompts, and prompt suggestions).

---

## Purpose & Value

- **Encodes proven phrasing** - Successful prompts become reusable assets.
- **Eliminates rewriting** - Users provide specifics without recreating the scaffolding.
- **Separates stable from variable** - Protects parts of the prompt that shouldn't change and clarifies what should.
- **Drives consistency across a team** - The same task is asked the same way regardless of who runs it, which makes output more comparable.
- **Makes expertise transferable** - Non-expert prompt writers benefit from the expertise of the template author.

The value is turning a good prompt into reusable infrastructure — captured once and parameterized for everyone.

---

## When to Use

- **Recurring task, consistent shape** - The work repeats with the same structure but different specifics.
- **Structure is non-obvious and quality-sensitive** - Phrasing matters enough that a proven frame is worth keeping.
- **Consistency across users or runs** - The team needs the same ask every time.
- **Few, enumerable variables** - Named slots, not an open-ended form with many fields.
- **Users have cleared the learning curve** - Templates serve practiced users; use prompt suggestions for newcomers.

---

## When NOT to Use

- **Task doesn't recur** - Template overhead isn't worth a one-off request.
- **Nothing actually varies** - If there are no fillable parts, call it a saved prompt.
- **Too many variables** - A crowded slot list becomes a form — often worse than typing freely.
- **Context can supply the value** - Don't ask the user for information the system can already capture and pre-fill.
- **Consequential execution on send** - Templates must not trigger irreversible operations without a HITL (human-in-the-loop) review/approval gate.

---

## Examples

**Intelligent Assistant (Developer Hub):** Templates for the in-chat experience in the Developer Hub Intelligent Assistant — reusable, saved prompts for repeated developer tasks. Users author a prompt once in Settings, then reopen it from Saved prompts, starter cards, or the chat input.

Red Hat Developer Hub Intelligent Assistant Saved prompts flow for Debug Application

**Saved Views:** Reusable AI-generated views that users save and reopen from the prompt entry point. After asking for a filtered list (for example, RHEL systems and OpenShift clusters), the user can save the custom view and return to it later from Saved custom views.

Hybrid Cloud Console flow for saving a custom view and accessing it from Saved custom views

---

## Recommended components

**Form:** Template fill experience where stable prompt framing stays fixed and variables are collected as fields.

[Form — PatternFly](https://www.patternfly.org/components/forms/form)

**Form control / Input group:** Named variable slots users complete before sending a reusable prompt.

[Input group — PatternFly](https://www.patternfly.org/components/input-group)

**Helper text:** Guidance that distinguishes required variables from optional ones and explains what each slot controls.

[Helper text — PatternFly](https://www.patternfly.org/components/helper-text)

**Menu:** Picker for saved templates before the fill step.

[Menu — PatternFly](https://www.patternfly.org/components/menus/menu)

**React Chatbot:** In-chat template selection and fill flows for repeated conversational tasks.

[React Chatbot — PatternFly](https://www.patternfly.org/patternfly-ai/react-chatbot/overview)

---

## Related Standards

- Structured prompts

---

