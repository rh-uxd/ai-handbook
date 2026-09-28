---
title: "Prompt templates"
description: "Reusable prompt structures with fillable variables that encode proven phrasing for repeated tasks — saved instruments for practiced users, not starter suggestions."
category: "Conversation"
status: "Recommended"
date: 2026-08-06
last_updated: 2026-09-25
contributors:
  - "Anh Nguyen"
  - "Lisa Lyman"
  - "Jingfu Tan"
  - "Applied AI UX"
---

# Prompt templates

## Overview

Prompt templates are reusable prompt structures with fillable variables that users customize for repeated tasks. The template holds the stable part — framing, constraints, and phrasing — while variables mark the parts that change between uses. Instead of rewriting from scratch, the user fills in slots and sends. Templates are typically user- or team-authored.

They differ from prompt suggestions: suggestions are system-offered examples for newcomers; templates are saved instruments for power users. The presence of a variable is the defining trait — a reusable prompt without fillable parts is a saved prompt, not a template. Industry prompt-management practice draws the same line: starter / sample prompts and variable prompt templates are distinct concepts that need separate treatment.

Typical user flow: create or save a template in the product → pick it later → fill {{variables}} → review the composed prompt → send in chat.

Prompt templates are one of four conversational prompt types (alongside structured prompts, clarification prompts, and prompt suggestions).

---

## Purpose and value

The value is turning a good prompt into reusable infrastructure — captured once and parameterized for everyone.

- **Encodes proven phrasing:** Successful prompts become reusable assets instead of one-off text that disappears after a session.
- **Eliminates rewriting:** Users provide specifics without recreating the scaffolding around them.
- **Separates stable from variable:** Protects parts of the prompt that shouldn't change and clarifies what should — typically with named placeholders such as `{{variable}}`.
- **Drives consistency across a team:** The same task is asked the same way regardless of who runs it, which makes output more comparable. <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a>
- **Makes expertise transferable:** Non-expert prompt writers benefit from the expertise of the template author — including non-technical editors updating shared templates while engineers keep governance.

---

## When to use

- **Recurring task, consistent shape:** The work repeats with the same structure but different specifics — the industry “template reuse” need that Save As / fork patterns support.
- **Structure is non-obvious and quality-sensitive:** Phrasing matters enough that a proven frame is worth keeping.
- **Consistency across users or runs:** The team needs the same ask every time. <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a>
- **Few, enumerable variables:** Named slots, not an open-ended form with many fields. <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a>

---

## When not to use

- **Task doesn't recur:** Template overhead isn't worth a one-off request. <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a>
- **Nothing actually varies:** If there are no fillable parts, call it a saved prompt — not a template.
- **Too many variables:** A crowded slot list becomes a form — often worse than typing freely. <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a>
- **Context can supply the value:** Don't ask the user for information the system can already capture and pre-fill.
- **Consequential execution on send:** Templates must not trigger irreversible operations without a HITL (human-in-the-loop) review/approval gate.

---

## Examples and visualizations

*Screenshots below may not match existing implementations in products.*

#### Intelligent Assistant (Developer Hub)

Templates for the in-chat experience in the Developer Hub Intelligent Assistant — reusable, saved prompts for repeated developer tasks such as debugging, documentation, or test strategy. Users author a prompt once (title, prompt body, and optional model binding), then reopen it from Saved prompts in the left nav, starter cards on the assistant zero state, or as editable text in the chat input.

Caveat: this product surface often ships first as **saved prompts** (reuse without fillable slots). Treat fillable variables as the bar for calling the pattern a true prompt template; model binding is optional and should stay secondary to the reusable prompt body.

Red Hat Developer Hub Intelligent Assistant Saved prompts flow for Debug Application

*[Developer Hub Intelligent Assistant Prototype](https://lightspeed-plugin-477a0f.pages.redhat.com/intelligent-assistant)*

#### Saved views <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a>

Reusable AI-generated views that users save and reopen from the prompt entry point — the recall-side cousin of prompt templates. After asking for a filtered list (for example, RHEL systems and OpenShift clusters), the user can save the custom view and return to it later from Saved custom views without retyping the request. Engineering should clarify whether reopening re-runs a live query or shows a frozen snapshot.

Use this as an adjacent reuse / recall example, not as a substitute for parameterized prompt templates with fillable slots.

Hybrid Cloud Console flow for saving a custom view and accessing it from Saved custom views

*[GitHub](https://github.com/KendraMar/HCCconcierge)* *(Experience 2 - follow the pink arrows for expected userflow)*

---

## Recommended components

- **[Form](https://www.patternfly.org/components/forms/form):** Template fill experience where stable prompt framing stays fixed and variables are collected as fields.
- **[Form control / Input group](https://www.patternfly.org/components/input-group):** Named variable slots users complete before sending a reusable prompt.
- **[Helper text](https://www.patternfly.org/components/helper-text):** Guidance that distinguishes required variables from optional ones and explains what each slot controls.
- **[Menu](https://www.patternfly.org/components/menus/menu):** Picker for saved templates before the fill step.
- **[React Chatbot](https://www.patternfly.org/patternfly-ai/react-chatbot/overview):** In-chat template selection and fill flows for repeated conversational tasks.

---

## Related standards

- [Prompt suggestions](../../wayfinders/prompt-suggestions/prompt-suggestions.md)
- [Clarification prompts](../clarification-prompts/clarification-prompts.md)
- [Structured prompts](../../input-authoring/structured-prompts/structured-prompts.md)
- [Human-in-the-Loop (HITL)](../../governors/human-in-the-loop/human-in-the-loop.md)
- [Action Confirmation](../../governors/action-confirmation/action-confirmation.md)

---

## Notes for PatternFly

**Parameterized prompt templates are not a PatternFly pattern yet:** React Chatbot covers saved / suggested prompts as reusable starters, but PatternFly does not document a recipe for templates with fillable variables — stable framing plus named slots, a fill-before-send step, and a clear distinction from zero-state prompt suggestions. Guidance for that parameterized fill experience would help product teams implement this standard consistently.

---

## Assumptions and research questions

<a id="assumptions"></a>
#### Assumptions

Assumptions are indicated with <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a> throughout the standard.

- **[Purpose and value](#purpose-and-value):** Drives consistency across a team
- **[When to use](#when-to-use):** Consistency across users or runs; Few, enumerable variables
- **[When not to use](#when-not-to-use):** Task doesn't recur; Too many variables
- **[Examples and visualizations](#examples-and-visualizations):** Saved views (adjacent recall pattern; not a parameterized template)

#### Research questions

1. When does a product “saved prompt” need to graduate into a true template with fillable variables?
2. For Saved views, should reopen re-run a live query or restore a frozen snapshot?

#### Metrics to track

1. Template reuse rate: % of prompt submissions that use a template vs. freeform input.
2. Variable fill rate: % of template variables that users fill vs. leave at defaults or delete.
