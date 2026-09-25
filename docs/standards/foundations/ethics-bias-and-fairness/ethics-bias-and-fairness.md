---
title: "Ethics: Bias and fairness"
description: "Keep AI outcomes equitable across people, languages, abilities, and contexts — including the accessibility of AI-specific UI"
category: "Foundations"
status: "Recommended"
date: 2026-09-14
last_updated: 2026-09-25
contributors:
  - "Mary Shakshober-Crossman"
  - "Jason Brock"
  - "Applied AI UX"
---

# Ethics: Bias and fairness

## Overview

Bias and fairness is the equity side of ethical AI: people get usable, comparable outcomes across populations, geographies, languages, and abilities — not merely an answer that works for a default user. Accessibility of AI-specific UI (streaming text, inline suggestions, approval flows) falls under this category.

---

## Purpose and value

- **Equitable outcomes & clear coverage limits:** PatternFly’s ‘Fairness’ principle requires inclusive, accessible systems that avoid amplifying bias. The UI must surface model limitations directly—such as language, regional, or domain gaps—to prevent homogenization and hidden coverage issues. ([PatternFly AI overview](https://www.patternfly.org/ai/overview#patternfly-ai-principles))
- **Safe, accurate & continuously evaluated:** Responsible AI requires eliminating hallucinations and harmful outputs while testing continuously across diverse demographics, languages, and assistive technologies throughout development.
- **Accessibility is fairness:** Features must offer complete task parity across keyboard, screen reader, and mouse/pointer interactions. ([PatternFly About accessibility](https://www.patternfly.org/accessibility/about-accessibility))

---

## Best practices

- **Audit UI & prompt examples for bias exposure:** Ensure starter prompts, empty states, error copy, and suggested actions span diverse roles, locales, contexts, and skill levels rather than assuming a single default expert profile.
- **Display model limitations in context:** State coverage limits directly alongside AI-generated outputs, rather than burying them in background documentation or legal footers.
- **Offer flexible, non-default options:** Provide controls to compare alternatives, rephrase suggestions, or hand off tasks to a human rather than presenting a single rigid answer.
- **Test continuously across diverse demographics & assistive tech:** Stress-test for stereotyping, language quality, and cultural contexts. Ensure keyboard and screen-reader paths achieve task parity, and monitor bias continuously post-launch.
- **Make dynamic AI features accessible to everyone:** Ensure streaming text, inline suggestions, and approval flows work seamlessly with keyboard, voice, and screen readers. Announce activity in chunks via live regions rather than every token, and maintain input focus. Compliance with color accessibility is also imperative to creating fair experiences. ([PatternFly About accessibility](https://www.patternfly.org/accessibility/about-accessibility))

---

## Things to avoid

- **Treating bias as only a model problem:** If starter prompts, empty states, screenshots, or evaluation flows assume a single narrow user profile (e.g., US English-speaking experts), the interface amplifies bias even if the model is fair.
- **Inaccessible or non-inclusive UI:** Shipping features that only work for sighted mouse users—such as untrackable streaming text, focus-stealing inline suggestions, or mouse-only approval gates—is a major equity failure. Additionally, relying solely on color for status and severity indication is not an acceptable form of communication. Accessibility must be built in from the start, not retrofitted later. ([PatternFly About accessibility](https://www.patternfly.org/accessibility/about-accessibility), [PatternFly About AI](https://www.patternfly.org/patternfly-ai/about-ai))
- **Token-by-token or overwhelming announcements:** Overusing aria-live="assertive" or reading every generated token makes the product unusable for screen-reader users. ([When Streaming Tokens Meet the Screen Reader](https://tianpan.co/blog/2026/06/29/streaming-tokens-meet-the-screen-reader))
- **Silent biased memory:** Avoid quietly accumulating conclusions about a person or team without surfacing and allowing them to edit stored data. ([Evaluating the Hidden Costs](https://arxiv.org/abs/2608.28833), [How Implicit Bias Accumulates and Propagates](https://arxiv.org/html/2602.01558))
- **Fairness as a substitute for oversight:** Highlighting a coverage gap does not replace giving users the direct ability to refuse, override, or correct the outcome.

---

## Ways to achieve ethical bias and fairness

#### Starter prompts and examples

Design starter prompts, empty states, and onboarding examples for diverse languages, locales, roles, and skill levels. Avoid assuming a standard ‘default’ user or relying on narrow expert workflows. Users from any background should immediately recognize how the tool applies to their work.

#### Flexible and challengeable outputs

Avoid presenting a single generated output as the only valid answer when multiple valid approaches exist. Provide options to compare alternatives, rephrase suggestions, or pass the task to a human. If an answer relies on a specific training default (such as a default platform or naming style), state it explicitly so users can adapt the result to their local requirements.

#### Continuous inclusive evaluation

Evaluate models and prompts continuously before launch and after updates. Include diverse demographic, language, and cultural scenarios during red-teaming and design reviews to catch bias or quality gaps early. Ensure all core tasks work via keyboard and screen reader, and continue monitoring bias after release.

#### Accessible UI for dynamic AI features

Ensure dynamic UI elements like streaming text, inline suggestions, chat, and approval flows are fully accessible. Provide complete keyboard functionality without relying on hover triggers, use polite live region announcements for key status changes rather than announcing every token, and maintain focus in the input area during text generation. Make sure all action controls are clearly labeled and operable without a mouse. ([PatternFly Accessibility overview](https://www.patternfly.org/accessibility/overview))

---

## Related standards

- [Ethics: Human oversight](../ethics-human-oversight/ethics-human-oversight.md)
- [Ethics: Transparency and information integrity](../ethics-transparency-and-information-integrity/ethics-transparency-and-information-integrity.md)
- [Prompt suggestions](../../wayfinders/prompt-suggestions/prompt-suggestions.md)
- [Clarification prompts](../../conversation/clarification-prompts/clarification-prompts.md)
- [Alert messages](../../error-handling/alert-messages/alert-messages.md)
- [Human-in-the-Loop (HITL)](../../governors/human-in-the-loop/human-in-the-loop.md)
- [Ethics: Harm reduction](../ethics-harm-reduction/ethics-hardm-reduction.md)
- [Ethics: Skill and expertise preservation](../ethics-skill-and-expertise-preservation/ethics-skill-expertise-preservation.md)

---

## Assumptions and research questions

<a id="assumptions"></a>
#### Assumptions

No assumptions made.

#### Research questions

1. When AI outputs are influenced by stored user context (memory), do users notice and do they care?

#### Metrics to track

1. A baseline accessibility audit of existing Lightspeed/chatbot implementations to establish where the gaps are. Accessibility task completion rate: % of core AI tasks (submit prompt, review output, approve action, provide feedback) that users can complete via keyboard-only and screen reader without assistance.
