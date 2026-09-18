---
title: "Ethics: Sustainability"
description: "Design AI so compute, tokens, and cost are justified, visible, and capped — and so a non-AI path remains available"
category: "Foundations"
status: "Recommended"
date: 2026-09-16
last_updated: 2026-09-18
contributors:
  - "Mary Shakshober-Crossman"
  - "Jason Brock"
  - "Applied AI UX"
---

<p>🚧 <strong><em style="color:#c86500">Work in progress</em></strong> <em>(remove when ‘done’)</em></p>

# Ethics: Sustainability

## Overview
Sustainability is the resource side of ethical AI: people can tell whether invoking a model is worth the compute effort, see what a run will cost, and choose a cheaper path — not merely get an answer that happened to use a large model. Every choice to invoke AI rather than a deterministic approach, every choice about context window size, and every choice about whether to stream or batch is a design decision.

---
## Purpose and value
- **Social responsibility:** Environmental risk is a crucial piece of corporate social responsibility. AI should not use excessive compute for trivial tasks. If a non-AI solution would do, the carbon and cost are not justified. <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a>
- **Consumption people can see:** Mature MCP adopters already raise token-consumption concerns. Cost and budget visibility belong in the product, not only in a backend dashboard.
- **A cheaper path that still finishes the work:** Users already separate deterministic workflows from AI-appropriate ones. Sustainability is whether that cheaper path is designed, not only whether engineering could have used a smaller model.
---
## Best practices
- **Verify AI is necessary:** Prefer non-AI solutions (rules, search, caches, or forms) when reasonable. <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a>
- **Optimize model and context size:** Default to the smallest viable model and send only essential task context. <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a>
- **Prefer batch processing over streaming:** Avoid real-time token streaming unless incremental outputs are actively needed. <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a>
- **Display consumption at point of use:** Show tokens, cost, or budget remaining directly next to invoke actions using clear text labels alongside progress bars.
- **Set spend guardrails and prompt clarifications:** Provide budget caps before execution and clarify vague prompts to avoid wasted runs.
- **Log resource utilization:** Record model selection and consumption metrics in audit trails for governance.
---
## Things to avoid
- **Performative AI:** Adding AI for marketing rather than user value wastes compute and trust. If a non-AI solution works, do not invoke a model. <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a>
- **Invisible token burn & oversized context:** Auto-invoking models, attaching entire workspaces by default, or retrying silently creates unexpected cost. Scope context specifically to the task.
- **Unnecessary streaming:** Token-by-token display adds overhead. Batch outputs like reports, plans, or files. <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a>
- **Hiding lower-cost paths:** Deterministic or non-AI options must be prominent and first-class, not hidden behind engineering defaults. <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a>
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
-
-
-
-
-
-
-
-
-
-
---
## Assumptions and research questions
<a id="assumptions"></a>
#### Assumptions
Assumptions are indicated with <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a> throughout the standard.
- **[Purpose and value](#purpose-and-value):** Social responsibility
- **[Best practices](#best-practices):** Verify AI is necessary, Optimize model and context size, Prefer batch processing over streaming
- **[Things to avoid](#things-to-avoid):** Performative AI, Unnecessary streaming, Hiding lower-cost paths
#### Research questions
- <mark>Research team to add here</mark>
