---
title: "Chain of thought"
description: "Reveal an AI's step-by-step reasoning in real time so users can observe, verify, and build trust in the system's logic"
category: "Trust Builders"
status: "Experimental"
date: 2026-08-04
last_updated: 2026-09-28
contributors:
  - "Jason Brock"
  - "Daragh McGrath"
  - "Jingfu Tan"
  - "Applied AI UX"
---

# Chain of thought

## Overview

Chain of Thought patterns reveal an AI's step-by-step reasoning process as it works toward a conclusion, streaming the thinking in real time so users can observe, verify, and build trust in the system's logic. Unlike [audit trails](../../governors/audit-trails/audit-trails.md), which surface rationale after the fact, Chain of Thought makes reasoning visible as it happens — showing users "My goal is X. To achieve this I first need Y. I will use Tool Z."

---
## Purpose and value
- **Real-time verification:** Users can catch flawed reasoning before the AI commits to a conclusion, rather than discovering errors only after reviewing a finished output ([arxiv: 2603.07306](https://arxiv.org/pdf/2603.07306)). This is critical for consequential actions where reversal is costly.
Showing the reasoning trace alongside the answer provides the evidence chain users need before acting on AI recommendations.
Reviewers can assess not just the conclusion but whether the AI's approach was sound.
- **Mental model building:** Watching an AI reason through a problem teaches users what the system is capable of, how it decomposes problems, and where its boundaries are. This accelerates onboarding and reduces misplaced trust ([arxiv: 2603.07306](https://arxiv.org/pdf/2603.07306)).
- **Debugging and intervention:** When reasoning is visible in real time, users can intervene mid-process using [PatternFly’s Message Bar with Start/Stop Button](https://www.patternfly.org/extensions/chatbot/ui/#message-bar-with-stop-button) if they see the AI heading in the wrong direction — providing corrections before wasted computation or harmful actions.
---
## When to use
- **Complex problem decomposition:** When the AI breaks a large problem into sub-problems (e.g., troubleshooting a multi-component system failure), show each sub-problem being identified and addressed sequentially.
- **Root cause analysis:** When AI is narrowing from many possible causes to a specific root cause, stream the elimination process: "Checked X — ruled out because Y.
- **Evaluation and scoring:** When AI is evaluating or scoring content (RAG retrieval quality, model output grading), force and display chain-of-thought reasoning before presenting the score. For batch or background evaluation pipelines, log the reasoning trace for post-hoc inspection rather than streaming it in real time (see [When not to use](#when-not-to-use)).
- **Multi-source synthesis in progress:** When the AI is actively pulling from multiple sources and assembling a response, show which sources it's consulting and what it's extracting from each, rather than presenting the final synthesis with no visibility into how it was assembled.
---
## When not to use
- **Post-hoc rationale is sufficient:** When the user only needs to understand reasoning after seeing the result, use [audit trails](../../governors/audit-trails/audit-trails.md) instead. Chain of Thought adds cognitive load during the wait; don't stream reasoning if users just want the answer and an optional "why."
- **Simple, fast responses:** When the AI response is near-instant and the reasoning is trivial (lookups, formatting, simple Q&A), streaming a reasoning trace adds latency and noise. Reserve Chain of Thought for responses where the thinking takes meaningful time.
- **Confidence scoring is the real need:** When users primarily need to calibrate how much to trust an answer, use Confidence Indicators. Chain of Thought shows the process; confidence shows the outcome certainty.
- **Users cannot act on the reasoning:** If showing the reasoning trace doesn't give users any intervention point or decision-making value (e.g., a fully autonomous background process), streaming it wastes attention. Log it for auditability instead.
---
## Examples and visualizations
*Screenshots below may not match existing implementations in products.*

#### Streamed reasoning in chat
Display the AI's thinking as a collapsible, visually distinct block above or within the response. Reasoning streams in real time as the model generates it, then collapses by default once the final answer appears. Users can re-expand to inspect.

Chat answer with a collapsible thought block listing crashloop checks, above the certificate-expiry conclusion

#### Agentic tool trace
When an AI agent invokes tools or APIs, show each step as a discrete entry: what the agent decided to do, the tool it called, and the result it received. Each step appears as the agent executes it, building a visible audit trail of the agent's decision-making process.

Chat answer with three tool-call cards for cluster info, upgrade path, and deprecated APIs

#### Sequential elimination log
For root cause analysis or diagnostic workflows, show the AI's elimination process as a numbered sequence: hypotheses tested, evidence found or not found, and conclusions drawn at each step. Each entry streams as the AI works, giving users a real-time view of the narrowing process.

Numbered root-cause log ruling out a network issue and confirming a missing database index

#### Background process with step status
For longer-running agentic tasks (installations, upgrades, multi-step automations), show a progress stepper with each reasoning/execution phase as a named step. Steps transition through pending, in-progress, completed, or failed states as the AI works through them.

Cluster security audit progress stepper with completed, in-progress, and pending steps

---
## Recommended components
The following PatternFly 6.5 components and extensions can be used to implement Chain of Thought patterns. Components are grouped by which example pattern they support.

#### Conversational / chat contexts
The [PatternFly Chatbot extension](https://www.patternfly.org/extensions/chatbot/overview) provides purpose-built props on the Message component for Chain of Thought in conversational AI:

- **[Deep thinking / reasoning](https://www.patternfly.org/extensions/chatbot/messages#messages-with-deep-thinking):** Primary component for CoT — renders the AI's step-by-step reasoning process as a collapsible, visually distinct block. Supports real-time streaming and collapses by default once the final answer appears. Use prop: `deepThinking` (`DeepThinkingProps`)
- **[Tool invocation trace](https://www.patternfly.org/patternfly-ai/chatbot/messages/#messages-with-tool-calls):** Show each tool the AI decided to invoke as a discrete step in the reasoning chain — what it called and why. Use prop: `toolCall` (`ToolCallProps`)
- **[Tool results](https://www.patternfly.org/patternfly-ai/chatbot/messages/#messages-with-tool-responses):** Display what came back from each tool call, completing the "decided → called → learned" trace for each agentic step. Use prop: `toolResponse` (`ToolResponseProps`)
- **[AI thinking indicator](https://www.patternfly.org/extensions/chatbot/ui/):** Pulsing color animation around the message bar indicating the AI is actively reasoning. Provides ambient feedback that thinking is in progress. Use prop: `isThinking` on MessageBar / Panel
- **[AI indicator border](https://www.patternfly.org/extensions/chatbot/ui/):** Gradient border around the message bar signaling active AI processing. Use prop: `hasAiIndicator` on MessageBar

#### Non-chat contexts (dashboards, operations UIs, background tasks)
Use these PatternFly components for Chain of Thought in dashboards, operations UIs, and background tasks:

- **[Progress stepper](https://www.patternfly.org/components/progress-stepper/overview):** Show each reasoning or execution phase as a named step with status (pending, in-progress, completed, failed). Vertical variant fits side panels; compact variant works in table rows. Use present participle tense for in-progress steps ("Analyzing logs"), past tense for completed ("Identified root cause").
- **[Expandable section](https://www.patternfly.org/components/expandable-section/overview):** Make reasoning blocks collapsible by default (a core Do from the standard). Use dynamic toggle text: "Show reasoning" / "Hide reasoning". The truncate variant can show the first few lines of reasoning with a "Show more" affordance.
- **[Accordion](https://www.patternfly.org/components/accordion/overview):** When reasoning has multiple distinct phases (e.g., "Hypotheses," "Evidence gathered," "Conclusion"), use a multi-expand accordion so users can open several sections simultaneously.
- **[Skeleton](https://www.patternfly.org/components/skeleton/overview):** Show the expected structure of reasoning output before content streams in. Match the skeleton shape to the final content layout (text lines, step items).
- **[Spinner](https://www.patternfly.org/components/spinner/overview):** Use inline with reasoning steps to indicate active processing. Pair with contextual status text ("Evaluating 3 candidates...").
- **[Description list](https://www.patternfly.org/components/description-list/overview):** Within each reasoning step, present structured data (e.g., "Tool: API call," "Input: cluster-id-42," "Result: 3 anomalies detected") as term/description pairs.
---
## Related standards
- [Action confirmation](../../governors/action-confirmation/action-confirmation.md)
- [Audit trails](../../governors/audit-trails/audit-trails.md)
- [Long-running operations](../../generation-output/long-running-operations/long-running-operations.md)
- [Plan approval](../../governors/plan-approval/plan-approval.md)
---
## Assumptions and research questions
<a id="assumptions"></a>
#### Assumptions
No assumptions made
#### Research questions
- **Reasoning expansion rate:** Percentage of users who expand collapsed reasoning blocks to inspect AI logic.
- **Intervention rate:** Frequency with which users pause, stop, or redirect AI execution mid-thought based on streamed reasoning.
- **Detail requirement by task type:** How does the required level of reasoning granularity vary across high-stakes vs. routine agentic tasks?
- **Mental model accuracy:** Does real-time reasoning streaming measurably improve user understanding of system capabilities and boundaries?
- **Update cadence:** Target a 3–5 second update interval for streaming reasoning state updates in non-chat agentic UIs to balance responsiveness and cognitive load.
