---
title: "Prompt suggestions"
description: "Pre-written example prompts at an AI entry point that solve the blank-canvas problem, teach effective phrasing, and advertise what the AI can do — without executing on selection."
category: "Conversation"
status: "Recommended"
date: 2026-08-06
last_updated: 2026-08-17
contributors:
  - "Anh Nguyen"
  - "Lisa Lyman"
  - "Mark Riggan"
  - "Applied AI UX"
---

# Prompt suggestions

---

## Overview

Prompt suggestions are pre-written example prompts presented at an AI entry point before the user has typed anything. They remove the blank-canvas problem by giving the user something to act on immediately, and they teach by example — modeling effective phrasing and advertising the range of what the AI can actually do. Suggestions inherit the context of the user's current object, project, or environment so they stay concrete rather than generic. Selecting a suggestion populates the input for the user to review, edit, or send — it is a starting point, not a committed request.

Prompt suggestions are one of four conversational prompt types (alongside structured prompts, clarification prompts, and prompt templates).

---

## Purpose & Value

The goal is to lower the cost of the first prompt while raising its quality — turning an empty box into a guided, learnable entry point.

- **Solves the blank-canvas problem** - Replaces an empty prompt field with viable openings. (; )
- **Teaches effective phrasing by example** - Users learn what a good prompt looks like by seeing one, which improves the quality of prompts they write later.
- **Advertises capability range** - Surfaces abilities users might not think to ask about.
- **Reduces ambiguity upstream** - Well-formed, correctly scoped prompts generate fewer clarification cycles and fewer wrong answers. (; )
- **Sets accurate expectations** - The suggestion set implicitly bounds what the AI does, protecting users from discovering limits by hitting them. (; )

---

## When to Use

- **Zero state** - The entry point has an empty input with nothing for the user to act on. (; )
- **Capability is new or not self-evident** - Users need help discovering what to ask.
- **Context supplies concrete parameters** - Current object, project, or environment can make suggestions specific rather than generic. (; )
- **Output quality is sensitive to phrasing** - Good starter phrasing materially improves results. (; )
- **Discoverable high-value tasks** - There is a set of tasks worth advertising that users might not know to ask for. (; )

---

## When NOT to Use

- **User already has intent** - Once typing starts, suggestions become an obstruction — hide or deprioritize them. (; )
- **Suggestions can't be scoped to context** - Generic, context-blind examples teach little.
- **Capability set is too narrow to need teaching** - If there is only one obvious task, use a direct action or button instead of a suggestion.
- **Suggestion can't be reliably fulfilled** - Advertising something the AI does poorly is worse than not advertising it. (; )
- **Selection would execute something consequential** - Suggestions must populate the input for review; they must not chain straight into an irreversible operation without a HITL (human-in-the-loop) review/approval gate. (; )

---

## Examples and visualizations

*Screenshots below may not match existing implementations in products.*

**Ask Red Hat:** Starter prompts in Ask Red Hat’s empty chat can teach capability range and ease the blank-canvas problem for users who do not yet know what to ask. Use this as an example of zero-state starters that populate the input for review — not Ask Red Hat as a whole product. Caveat: Ask Red Hat research more often shows people arriving with a problem already, and starters may be weakly scoped when the chat lacks cluster, project, or object context; prefer Lightspeed-style context-scoped suggestions when illustrating the pattern at its strongest. (; )

Ask Red Hat empty chat with starter prompt suggestions Tell me about Ask Red Hat and What technologies are used in Ask Red Hat

**Search prompts (Lightspeed):** An Omni-bar style interaction that provides visibility for a search-style experience with Lightspeed — suggestions help users see what they can ask without starting from a blank field. In OpenShift Lightspeed, the masthead “Ask AI about this cluster…” entry point surfaces a Suggested prompts menu scoped to the current cluster and project. (; )

![OpenShift Lightspeed omni-bar showing Suggested prompts on a Pod details page](./assets/search-prompts.png)

---

## Recommended components

**Menu:** List of starter prompt examples users can select before typing.

[Menu — PatternFly](https://www.patternfly.org/components/menus/menu)

**Button:** Chip- or button-style suggestion affordances that populate the input on select (without executing).

[Button — PatternFly](https://www.patternfly.org/components/button)

**Search input / Input group:** Empty-state entry points where suggestions appear beside or above the prompt field.

[Search input — PatternFly](https://www.patternfly.org/components/search-input)

[Input group — PatternFly](https://www.patternfly.org/components/input-group)

**Hint:** Empty-state coaching that points users to example prompts without blocking the input.

[Hint — PatternFly](https://www.patternfly.org/components/hint)

**React Chatbot:** Chat entry points that present suggested prompts in the zero state.

[React Chatbot — PatternFly](https://www.patternfly.org/patternfly-ai/react-chatbot/overview)

---

## Related Standards

-
-
-
- Structured prompts
-
-

---

## Notes for PatternFly

- **Context-scoped starter prompts are not a PatternFly pattern yet** - React Chatbot covers zero-state suggested prompts as a list of starters, but PatternFly does not document a recipe for scoping those starters to the current object, project, or environment — for example, “Ask AI about this cluster…” with cluster- or project-bound suggestions. Guidance for context-aware prompt suggestions would help product teams implement this standard consistently.

---

