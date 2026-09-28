---
title: "Clarification prompts"
description: "When the AI recognizes ambiguity in a query, ask a targeted multiple-choice or short-answer question before generating a response — instead of guessing and eroding trust."
category: "Conversation"
status: "Experimental"
date: 2026-08-06
last_updated: 2026-09-25
contributors:
  - "Anh Nguyen"
  - "Lisa Lyman"
  - "Mark Riggan"
  - "Jingfu Tan"
  - "Applied AI UX"
---

# Clarification prompts

## Overview
Clarification prompts are the pattern where the AI recognizes ambiguity in a query and asks a targeted question before generating an answer, rather than guessing. Instead of producing a potentially incorrect response, the AI names what's ambiguous and offers the user a focused way to resolve it — often as multiple-choice options to minimize effort. The purpose is to break the cycle of wrong answer → frustration → rephrasing → another wrong answer that steadily erodes user trust.

Clarification prompts are one of four conversational prompt types (alongside structured prompts, prompt templates, and prompt suggestions).

---
## Purpose and value
- **Prevents confidently wrong answers:** Speculative answers where certainty is required destroy trust. Clarifying up front avoids that anti-pattern entirely.
- **Signals thoughtfulness, not just speed:** Asking the right question shows the AI is being careful with user intent rather than racing to a guess.
- **Reduces wasted back-and-forth:** Getting the missing information upfront collapses several failed round-trips into one clean exchange.
- **Demonstrates transparency:** The AI is open about the boundary of what it understands, which builds trust in the answers it does give.
---
## When to use
- **When the AI can't safely pick a single interpretation:** The query could apply to multiple products, environments, or contexts.
- **A critical parameter is missing:** For example, which cluster, which host, or which version.
- **The user's intent is genuinely ambiguous:** Diagnostic vs. operational vs. educational.
- **Before executing actions where the wrong interpretation could cause harm:** Clarify first, act second.
---
## When not to use
- **Don't ask for information the system already has:** If the AI knows the cluster name from context, use it.
- **Don't chain multiple clarifications:** Means both — do not ask multiple clarifying questions in a single turn, and do not follow the user's answer with another clarification before giving a usable response. Ask one focused clarification, wait for the answer, then proceed (answer, act, or state a reasonable default). Chaining looks like: User: “Check certificate status.” → AI: “Which cluster?” → User: “prod-east.” → AI: “Which namespace?” → User: “openshift-ingress.” → AI: “30- or 90-day expiry?” Prefer one well-scoped question up front (or use context and defaults for secondary details). If the AI keeps needing a new clarification after each reply, query parsing or context gathering needs improvement — not another clarification turn.
- **Don't clarify when a reasonable default exists:** Answer with the default and note the assumption: “Assuming your current cluster (prod-east).
---
## Examples and visualizations
*Screenshots below may not match existing implementations in products.*

#### Guidance on how to structure prompts
**Clarification response shape:** Acknowledge what was understood (“I can help you check certificate status.”), name the ambiguity (“I see 3 clusters in your environment.”), then offer limited choices (about 3–5 clickable options plus an “Other” or free-text path) rather than an open-ended “Can you be more specific?”

**Chaining clarifications (anti-pattern):** Avoid this: after the user answers one clarification, asking another before delivering a usable answer. Example — User: “Check certificate status.” → AI: “Which cluster?” → User: “prod-east.” → AI: “Which namespace?” That second clarification is chaining. Prefer one focused question with choices (as in Clarification response shape above), then answer using the reply plus context or a stated default for any remaining details.

#### PatternFly Chatbot — Quick replies (stacked)
PatternFly’s Chatbot Design Framework shows stacked quick replies as clickable choice chips after a bot message — the closest published design for the limited-choice part of this clarification shape (about 3–5 options, including an “Other” / “Something else” path). The image below represents both examples above: the clarification response shape (acknowledge, name the ambiguity, then limited choices plus an Other path) and this PatternFly quick-replies choice UI. Pair the mock with acknowledge + name-the-ambiguity copy; it is not a shipped Red Hat product screenshot.

PatternFly Chatbot stacked quick replies with five choice chips including Something else

---
## Recommended components
- **[Radio](https://www.patternfly.org/components/radio):** Limited multiple-choice clarification options (about 3–5) that let users resolve ambiguity with minimal effort.
- **[Form](https://www.patternfly.org/components/forms/form) / [Form select](https://www.patternfly.org/components/forms/form-select):** Structured clarification when the missing parameter is best captured as a field rather than free text.
- **[Button](https://www.patternfly.org/components/button):** Clickable clarification choices, including an “Other” path that opens free text when needed.
- **[Helper text](https://www.patternfly.org/components/helper-text):** Supporting copy that acknowledges what was understood and names what is still ambiguous.
- **[React Chatbot](https://www.patternfly.org/patternfly-ai/react-chatbot/overview):** Conversation surfaces where clarification turns appear inline before the AI commits to an answer.
---
## Related standards
- [Prompt suggestions](../../wayfinders/prompt-suggestions/prompt-suggestions.md)
- [Prompt templates](../prompt-templates/prompt-templates.md)
- [Structured prompts](../../input-authoring/structured-prompts/structured-prompts.md)
- [Contextual AI Invocation](../../input-authoring/contextual-ai-invocation/contextual-ai-invocation.md)
- [Human-in-the-Loop (HITL)](../../governors/human-in-the-loop/human-in-the-loop.md)
---
## Notes for PatternFly
- **Clarification choice UI is not a PatternFly pattern yet:** Radio, Button, Form, Helper text, and React Chatbot cover the primitives, and Messages with quick responses provide clickable choice chips, but PatternFly does not document a standard recipe for an inline clarification turn — acknowledge what was understood, name the ambiguity, and offer about 3–5 choices plus an Other path before the assistant commits to an answer. Guidance for that clarification turn would help product teams implement this standard consistently.
---
## Assumptions and research questions
<a id="assumptions"></a>
#### Assumptions
No assumptions made.
#### Research questions
No research questions at this time.
