---
title: "Structured prompts"
description: "Form-based input that guides users to provide well-formed AI prompts through structured fields, reducing cognitive load when free-form typing is too open-ended."
category: "Input & Authoring"
status: "Experimental"
date: 2026-08-12
last_updated: 2026-08-12
contributors:
  - "Anh Nguyen"
  - "Lisa Lyman"
  - "Applied AI UX"
---

# Structured prompts

---

## Overview

Structured prompts are form-based inputs that guide users to provide well-formed AI prompts through discrete fields rather than a blank text box. Required fields, appropriate input types, and smart defaults help users supply the parameters the model needs without inventing prompt phrasing from scratch. The form composes those fields into a prompt the user can review before sending. Structured prompts sit alongside suggestions, clarification prompts, and templates as one of four conversational prompt types — they are especially useful when free-form typing is too open-ended or error-prone for the task.

---

## Purpose & Value

- **Reduces cognitive load** - Users fill known fields instead of inventing a complete free-form prompt.
- **Improves prompt quality** - Required fields and typed inputs collect the parameters the AI needs before generation starts.
- **Makes composition visible** - Showing how fields become the prompt builds trust and teaches what matters.
- **Speeds common tasks** - Smart defaults pre-select frequent values so experts spend time only on what differs.
- **Leaves an escape hatch** - An advanced or custom path preserves flexibility when the form is too rigid.

---

## When to Use

- **Required parameters are known** - The task needs a small set of fields (product, environment, scope) before a good answer is possible.
- **Free-form prompts regularly miss key context** - Users under-specify and trigger wrong or vague responses.
- **Input types map cleanly** - Dates, enums, and short values fit selects, radios, or text fields better than an essay box.
- **Defaults can be inferred safely** - The system can pre-select reasonable values and still let the user change them.
- **Composition should be reviewable** - Users benefit from seeing how their field values become the prompt before send.

---

## When NOT to Use

- **Flexibility is the point** - Exploratory or creative asks belong in free-form chat, not a fixed form.
- **Too many fields at once** - An overwhelming form increases abandonment — start with required fields only and progressive disclosure.
- **Open-ended answers forced into dropdowns** - Don't use selects when free text is the right control.
- **No custom or advanced fallback** - Structure without an escape path traps power users — offer a free-form or advanced option.

---

## Examples

No existing work. This is a new standard.

Product teams exploring structured prompt authoring can look to playground-style flows from the Prompt Management Competitive Analysis (guided/structured editing modes) and Ansible research on prompt-to-flow / natural-language config generation for inspiration — no Red Hat shipped UI examples are catalogued here yet.

---

## Recommended components

**Form:** Primary surface for required and optional prompt fields with validation and submit.

[Form — PatternFly](https://www.patternfly.org/components/forms/form)

**Form select / Radio:** Enumerated parameters (product, environment, severity) with appropriate input types instead of open-ended dropdowns for free text.

[Form select — PatternFly](https://www.patternfly.org/components/forms/form-select)

[Radio — PatternFly](https://www.patternfly.org/components/radio)

**Text input / Text area:** Short and longer field values that compose into the prompt.

[Text input — PatternFly](https://www.patternfly.org/components/text-input)

[Text area — PatternFly](https://www.patternfly.org/components/text-area)

**Helper text:** Explains how each field contributes to the composed prompt and what defaults were applied.

[Helper text — PatternFly](https://www.patternfly.org/components/helper-text)

**Expandable section:** Progressive disclosure for advanced or custom fields so the default view stays required-only.

[Expandable section — PatternFly](https://www.patternfly.org/components/expandable-section)

---

## Related Standards


---

