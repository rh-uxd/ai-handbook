---
title: "Ethics: Sustainability"
description: "Design AI so compute, tokens, and cost are justified, visible, and capped — and so a non-AI path remains available"
category: "Foundations"
status: "Recommended"
date: 2026-09-16
last_updated: 2026-09-25
contributors:
  - "Mary Shakshober-Crossman"
  - "Jason Brock"
  - "Applied AI UX"
---

# Ethics: Sustainability

## Overview

Sustainability is the resource side of ethical AI: people can tell whether invoking a model is worth the compute effort, see what a run will cost, and choose a cheaper path — not merely get an answer that happened to use a large model. Sustainability in AI is a fundamental design decision. Designers reduce energy and compute impact by choosing standard non-AI automation where appropriate, sending only the data the AI actually needs, and selecting efficient ways for the AI to respond.

---

## Purpose and value

- **Social responsibility:** Environmental risk is a crucial piece of corporate social responsibility. AI should not use excessive compute for trivial tasks. If a non-AI solution would do, the carbon and cost are not justified. ([Estimating GHG Emissions from AI Use](https://arxiv.org/pdf/2608.06733), [PWC 2026 AI Business Predictions](https://www.pwc.com/us/en/tech-effect/ai-analytics/ai-predictions.html))
- **Consumption people can see:** Provide clear visibility into cost, token usage, and compute impact before heavy AI tasks run—helping teams manage budgets, set latency expectations, and avoid unexpected resource consumption.
- **A cheaper path that still finishes the work:** Designers directly impact AI sustainability by providing standard, non-AI automation for routine workflows. While engineering can optimize model size on the backend, UX choices determine whether an expensive LLM call was even necessary in the first place.

---

## Best practices

- **Verify AI is necessary:** Prefer non-AI solutions (rules, search, caches, or forms) when reasonable.
- **Optimize model and context size:** Default to the smallest viable model that can complete the task and send only essential task context. ([Agentic FinOps](https://www.institutepm.com/knowledge-hub/agentic-finops-guide))
- **Reserve streaming for interactive AI features:** For API-based inference, streaming and non-streaming have identical token pricing. Use streaming for interactive workflows to improve perceived responsiveness, and batch non-interactive tasks where batch APIs offer real savings. ([Streaming, Batching, and Latency Budgets](https://thepromptbench.com/cost-and-performance/streaming-batching-and-latency-budgets/))
- **Display consumption at point of use:** Show tokens, cost, or budget remaining directly next to invoke actions using clear text labels alongside progress bars.
- **Set spend guardrails and prompt clarifications:** Provide budget caps before execution and clarify vague prompts to avoid wasted runs.
- **Log resource utilization:** Record model selection and consumption metrics in audit trails for governance.

---

## Things to avoid

- **Performative AI:** Adding AI for marketing rather than user value wastes compute and trust. If a non-AI solution works, do not invoke a model. ([Amazon Killed Its AI Leaderboard](https://blog.searchless.ai/posts/amazon-killed-ai-leaderboard-performative-adoption-backfires/))
- **Invisible token burn & oversized context:** Auto-invoking models, attaching entire workspaces by default, or retrying silently creates unexpected cost. Scope context specifically to the task.
- **Hiding lower-cost paths:** Deterministic or non-AI options must be prominent and first-class, not hidden behind engineering defaults. ([The AI Features Users Actually Pay](https://apnahive.com/the-ai-features-users-actually-pay-for-vs-the-ones-that-look-good-in-demos/))
- **Color-only usage indicators:** Always pair status indicators with explicit numbers and units rather than relying solely on color. ([PatternFly About AI](https://www.patternfly.org/patternfly-ai/about-ai))

---

## Ways to achieve ethical sustainability

These methods turn the practices above into product behavior. Each one is a design outcome, not a prescribed layout. Match the method to the moment: before you add AI, at invoke, during a run, or when a cheaper path would do.

#### Justify model choice and stay token-efficient

Verify a non-AI solution (rule, cache, search, or simple form) cannot achieve the goal before adding a model. When AI is required, select the smallest model and context window, request clarification before expensive runs, stream only when partial results are immediately necessary, and keep stop controls accessible.

#### Visible usage and budget caps

Provide upfront token/cost estimates at invoke and during long runs. Place labeled progress or donut indicators next to trigger actions, notify users before exceeding budget caps with clear next steps, and record model and token usage in audit trails.

#### Ensure a viable non-AI path

Default to lower-cost options (such as search, templates, or small models) for automated or suggested surfaces. Keep non-AI workflows fully functional, make contextual invocation optional, and ensure users can complete tasks regardless of AI availability or budget limits.

---

## Recommended components

- **[Progress](https://www.patternfly.org/components/progress/design-guidelines):** Horizontal bar for how much of a budget, token allotment, or cap is used. Pair the bar with a value and unit — not a bare percent.
- **[Donut utilization](https://www.patternfly.org/charts/donut-utilization-chart/design-guidelines):** Percent of a whole, with optional warning and danger thresholds. Use for remaining budget on a dashboard or invoke header.
- **[Alert](https://www.patternfly.org/components/alert/design-guidelines):** Inline warning before a run that would exceed a cap, with Cancel, shrink context, or raise cap.
- **[Label](https://www.patternfly.org/components/label/design-guidelines):** Compact token or cost chip next to invoke. Always include text, not color alone.
- **[Helper text](https://www.patternfly.org/components/helper-text):** Estimate copy under the composer (“This run will use about 4k tokens”).
- **[Number input](https://www.patternfly.org/components/number-input):** Numeric budget or token cap.
- **[Slider](https://www.patternfly.org/components/slider):** Bounded range when the cap is a scale, not a precise invoice.

---

## Related standards

- [Ethics: Human oversight](../ethics-human-oversight/ethics-human-oversight.md)
- [Ethics: Transparency and information integrity](../ethics-transparency-and-information-integrity/ethics-transparency-and-information-integrity.md)
- [Ethics: Bias and fairness](../ethics-bias-and-fairness/ethics-bias-and-fairness.md)
- [Contextual AI invocation](../../input-authoring/contextual-ai-invocation/contextual-ai-invocation.md)
- [Clarification prompts](../../conversation/clarification-prompts/clarification-prompts.md)
- [Long-running operations](../../generation-output/long-running-operations/long-running-operations.md)
- [Audit trails](../../governors/audit-trails/audit-trails.md)
- [Alert messages](../../error-handling/alert-messages/alert-messages.md)
- [Prompt templates](../../conversation/prompt-templates/prompt-templates.md)
- [Ethics: Harm reduction](../ethics-harm-reduction/ethics-hardm-reduction.md)

---

## Assumptions and research questions

<a id="assumptions"></a>
#### Assumptions

No assumptions made.

#### Research questions

1. Do users want to see token/cost information at the point of AI invocation, and does showing it change their behavior?
2. What cost information format is most useful: tokens, dollars, budget percentage, or comparison to a non-AI alternative?
3. At what cost threshold do users choose a non-AI path over an AI path?
