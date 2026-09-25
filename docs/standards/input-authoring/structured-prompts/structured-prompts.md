---
title: "Structured prompts"
description: "Form-based input that guides users to provide well-formed AI prompts through structured fields, reducing cognitive load when free-form typing is too open-ended."
category: "Input & Authoring"
status: "Experimental"
date: 2026-08-12
last_updated: 2026-09-25
contributors:
  - "Anh Nguyen"
  - "Lisa Lyman"
  - "Applied AI UX"
---

# Structured prompts

## Overview

Structured prompts are form-based inputs that guide users to provide well-formed AI prompts through discrete fields rather than a blank text box. Required fields, appropriate input types, and smart defaults help users supply the parameters the model needs without inventing prompt phrasing from scratch. The form composes those fields into a prompt the user can review before sending.

They differ from prompt templates: both involve filling things in, but templates keep mostly free-form prompt text with fillable {{variables}} that users or teams author and reuse; structured prompts replace the blank box with a task-specific guided form of discrete fields. Industry prompt-management practice treats guided / structured editing modes and variable templates as related but separate concepts. (Prompt Management Competitive Analysis April 2026)

Typical entry points: pick a known task via menu, button, starter card, or mode toggle → guided form replaces or overlays the blank chat input → fill fields → review the composed prompt → send in chat.

Structured prompts sit alongside suggestions, clarification prompts, and templates as one of four conversational prompt types — they are especially useful when free-form typing is too open-ended or error-prone for the task.

---

## Purpose and value

- **Reduces cognitive load:** Users fill known fields instead of inventing a complete free-form prompt.
- **Improves prompt quality:** Required fields and typed inputs collect the parameters the AI needs before generation starts.
- **Makes composition visible:** Showing how fields become the prompt builds trust and teaches what matters.
- **Speeds common tasks:** Smart defaults pre-select frequent values so experts spend time only on what differs. ([Promptions helps make AI prompting more precise with dynamic UI controls](https://www.microsoft.com/en-us/research/blog/promptions-helps-make-ai-prompting-more-precise-with-dynamic-ui-controls/))
- **Leaves an escape hatch:** An advanced or custom path preserves flexibility when the form is too rigid.

---

## When to use

- **Required parameters are known:** The task needs a small set of fields (product, environment, scope) before a good answer is possible.
- **Free-form prompts regularly miss key context:** Users under-specify and trigger wrong or vague responses.
- **Input types map cleanly:** Dates, enums, and short values fit selects, radios, or text fields better than an essay box.
- **Defaults can be inferred safely:** The system can pre-select reasonable values and still let the user change them. <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a>
- **Composition should be reviewable:** Users benefit from seeing how their field values become the prompt before send.

---

## When not to use

- **Flexibility is the point:** Exploratory or creative asks belong in free-form chat, not a fixed form.
- **Too many fields at once:** An overwhelming form increases abandonment — start with required fields only and progressive disclosure.
- **Open-ended answers forced into dropdowns:** Don't use selects when free text is the right control.
- **No custom or advanced fallback:** Structure without an escape path traps power users — offer a free-form or advanced option.
RHOAI team feedback on IBM PromptLab suggests heavily structured prompt UIs can go unused when free-form + variables cover the job — treat that as directional, not validated research. <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a>

---

## Examples and visualizations

*Screenshots below may not match existing implementations in products.*

#### RHOAI Gen AI Studio <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a>

Closest Red Hat prototype for prompt authoring: RHOAI Gen AI Studio Prompt Lab (https://rhoai-defc23.pages.redhat.com/gen-ai-studio/prompt-lab) (VPN required). In Gen AI Studio → Prompt Lab, users can load and save a prompt. Ashley Crago also shared Figma for loading prompts; the save flow in Figma was incomplete at review time, so the prototype is the better source for save behavior.

**How to read this example for this standard:** Per Jon Nemargut (RHOAI; work informed by IBM PromptLab per Megan Hall), Prompt Lab prompts are largely unstructured / free-form, with optional variables (for example `Hello {{first.name}}, how are you`) rather than a multi-field guided form. Anecdotal feedback from PromptLab was that few people used its structured-prompt surfaces. Nick Gagan notes PromptLab-era structured prompts predated standardized chat APIs (vLLM ~2023) and may be obsolete relative to modern chat. Validate before treating it as a canonical structured-prompt implementation.


---

## Recommended components

- **[Form](https://www.patternfly.org/components/forms/form):** Primary surface for required and optional prompt fields with validation and submit.
- **[Form select](https://www.patternfly.org/components/forms/form-select) / [Radio](https://www.patternfly.org/components/radio):** Enumerated parameters (product, environment, severity) with appropriate input types instead of open-ended dropdowns for free text.
- **[Text input](https://www.patternfly.org/components/text-input) / [Text area](https://www.patternfly.org/components/text-area):** Short and longer field values that compose into the prompt.
- **[Helper text](https://www.patternfly.org/components/helper-text):** Explains how each field contributes to the composed prompt and what defaults were applied.
- **[Expandable section](https://www.patternfly.org/components/expandable-section):** Progressive disclosure for advanced or custom fields so the default view stays required-only.

---

## Related standards

- [Prompt suggestions](../../wayfinders/prompt-suggestions/prompt-suggestions.md)
- [Prompt templates](../../conversation/prompt-templates/prompt-templates.md)
- [Clarification prompts](../../conversation/clarification-prompts/clarification-prompts.md)
- [Contextual AI Invocation](../contextual-ai-invocation/contextual-ai-invocation.md)
- [Human-in-the-Loop (HITL)](../../governors/human-in-the-loop/human-in-the-loop.md)

---

## Notes for PatternFly

- **Guided structured prompt authoring is not a PatternFly pattern yet:** Form, Form select, Radio, Text input, Text area, Helper text, and Expandable section cover the primitives, but PatternFly does not document a recipe for composing required fields into a reviewable AI prompt — with smart defaults, progressive disclosure for advanced fields, and a free-form escape hatch. Guidance for that structured-prompt flow would help product teams implement this standard consistently.

---

## Assumptions and research questions

<a id="assumptions"></a>
#### Assumptions

Assumptions are indicated with <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a> throughout the standard.

- **[When to use](#when-to-use):** Defaults can be inferred safely
- **[When not to use](#when-not-to-use):** A free-form prompt with variables is enough
- **[Example visualizations](#examples-and-visualizations):** RHOAI Gen AI Studio Prompt Lab load / save prompt

#### Research questions

No research questions at this time

#### Metrics to Track

1. Structured prompt completion rate: % of users who start a structured prompt form and submit it vs. abandon.
2. Default override rate: % of pre-filled defaults that users change before submitting.
3. Escape hatch usage rate: % of sessions where users switch from structured to free-form/advanced mode.
