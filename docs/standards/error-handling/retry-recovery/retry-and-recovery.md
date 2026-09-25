---
title: "Retry and recovery"
description: "Recover from AI failures through intelligent retry, guided corrections, and alternative pathways so a failure becomes a next step, not a dead end"
category: "Error handling"
status: "Experimental"
date: 2026-09-25
last_updated: 2026-09-25
contributors:
  - "Mary Shakshober-Crossman"
  - "Applied AI UX"
---

# Retry and recovery

## Overview

Retry and recovery enables users to recover from AI failures through intelligent retry mechanisms, guided corrections, and alternative pathways — so a failure becomes a next step, not a dead end. The pattern covers when the system should auto-retry (transient failures with backoff), when it should ask the user to retry with a changed approach, how to preserve user input and context across attempts, and when to stop retrying and offer a human or manual path instead.


---



## Purpose and value

- **Turns failures into guided recovery:** Treat errors as opportunities to fix, resume, or take an alternate path — not as dead ends.
- **Respects limited retry patience:** Users tolerate only a small number of attempts (about 2–3) before abandoning AI and doing the work themselves.
- **Repairs trust after failure:** Trust recovery needs acknowledgment, a causal explanation, visible recovery paths, and reversibility (including “guaranteed rollbacks” where actions changed state).
- **Preserves progress:** Manual override and resume lets people fix a failed step and continue from that point instead of restarting costly workflows.
- **Reduces abandonment from “almost right” output:** When AI is close but wrong, guided correction and alternative pathways beat repeating the same failed request.

---

## When to use

- **Transient technical failures:** Timeouts, rate limits, and temporary service unavailability — treat each as its own state, not one generic retry. Timeouts: auto-retry with backoff, then offer a clear manual retry. Rate limits: wait for the allowed window (show when retry is available) before trying again — do not hammer immediate retries. Temporary service unavailability: auto-retry with backoff; if it persists, offer retry, a fallback path, or wait guidance rather than only “try again.” ([What Should an AI App Show When the Model Fails?
- **Partial or interrupted results:** Streaming cutoffs or incomplete runs where the user can continue, regenerate, or resume from the last good step. ([What Should an AI App Show When the Model Fails? Error State Design](https://ai-tldr.dev/learn/building-ai-apps/ai-ux-patterns/ai-error-state-design/))
- **Quality failures that need a different approach:** “Almost right” or inconsistent outputs where retrying unchanged is unlikely to help — guide a correction, parameter change, or alternate path.
- **Long-running or multi-step agent workflows:** Pause at the failure point, let the user investigate or override, then resume without losing prior progress.
- **After repeated failures:** Offer alternatives — docs, troubleshooting, support, or a fully manual path — once retries are exhausted.

---

## When not to use

- **Do not retry infinitely:** Cap automatic and user-driven retries; after a small number of attempts, stop and offer another path. Error State Design](https://ai-tldr.dev/learn/building-ai-apps/ai-ux-patterns/ai-error-state-design/))
- **Do not silently retry expensive or high-impact operations:** Costly model calls, production mutations, or credentialed actions need visibility and often confirmation before another attempt.
- **Do not reset context on retry:** Preserve prompts, attachments, selections, and workflow state so users are not punished for the failure. ([Error state](https://uxpatternsguide.com/patterns/error-state/), [Silence is a Design Decision](https://www.thetruecode.com/the-true-code-of-production-systems/silence-is-a-design-decision/), [What Should an AI App Show When the Model Fails? Error State Design](https://ai-tldr.dev/learn/building-ai-apps/ai-ux-patterns/ai-error-state-design/))
- **Do not retry the identical failed request unchanged:** If the same inputs already failed, change something (parameters, guidance, provider, or approach) or escalate. Error State Design](https://ai-tldr.dev/learn/building-ai-apps/ai-ux-patterns/ai-error-state-design/))
- **Do not hide retry history:** Users and operators need to see what was tried, what changed, and why further retries stopped. ([Override Patterns: When AI Needs Human Correction](https://www.operion.io/learn/component/override-patterns), [XAgen: An Explainability Tool for Identifying and Correcting Failures in Multi-Agent Workflows](https://arxiv.org/pdf/2512.17896))
- **Do not use retry for permanent failures:** Permission denials, policy blocks, and invalid inputs need explanation and a different action — not another attempt at the same request. Error State Design](https://ai-tldr.dev/learn/building-ai-apps/ai-ux-patterns/ai-error-state-design/))

---

## Examples and visualizations

*Only product examples with available visuals are shown here. Additional product opportunities remain documented in Related research until design or shipping screenshots are shared.*

#### Guided error recovery (Agentic AI Orchestration patterns)

Platform guidance treats errors as opportunities for guided recovery: plain-language explanation of what went wrong and what to do next (for example, retry a step or wait), plus manual override and resume so long-running workflows can pause at the failure point, allow a human fix, and continue without restarting from scratch.


*(No product visual is included here yet; treat visual treatment as an assumption until design or shipping screenshots are shared)* *

#### Ansible agent-based automation (UXDR-4913)

Usability testing showed strong demand for certainty before modifications and for the ability to adjust plans rather than only approve or reject — recovery after a failed or uncertain agent step should preserve human control and avoid blind re-runs of the same action.

Ansible automation canvas before and after adding an API trigger to a Backup Database workflow


#### Competitor patterns: retry actions in execution output

Competitive analysis of agent-based UIs notes that some tools embed retry, edit, and fix actions directly in execution logs or step output — so recovery is available at the point of failure, not only as a global “try again.”

*(Treat this as a design opportunity and assumption until Red Hat product screenshots are available)* *

---

## Recommended components

- **[Alert](https://www.patternfly.org/components/alert):** Surfaces the failure, attempt status (for example, “Retrying… attempt 2 of 3”), and next-step guidance without burying recovery in a dead-end message.
- **[Button](https://www.patternfly.org/components/button):** Explicit Retry, Resume, Continue, or Fix actions with specific labels rather than a generic OK.
- **[Progress / loading indicators](https://www.patternfly.org/components/progress):** Show automatic backoff retries as progress, not as an unexplained spinner.
- **[Empty state](https://www.patternfly.org/components/empty-state):** Structured recovery layout when the primary AI path has failed — primary retry, secondary alternative, and optional support link.
- **[Modal](https://www.patternfly.org/components/modal):** Confirm retry of expensive or high-impact operations before re-executing.
- **[Chatbot messages](https://www.patternfly.org/extensions/chatbot/messages):** Inline failure messaging with retry / continue affordances in conversational AI.

---

## Related standards

- Graceful Degradation

---

## Notes for PatternFly

- **Retry & Recover is not a PatternFly pattern yet:** Alert, Button, Progress, Empty state, Modal, and Chatbot messages cover the primitives, but PatternFly does not document a standard recipe for AI retry — auto-retry with capped backoff, explaining what changed on retry, preserving context, exposing retry history, and escalating to guided alternatives after repeated failures. Guidance for that recovery turn would help product teams implement this standard consistently.

---

## Assumptions and research questions

#### Assumptions

Assumptions are indicated with * throughout the standard.

- **[When not to use](#when-not-to-use):** Do not reset context on retry; Do not hide retry history
- **[Examples and visualizations](#examples-and-visualizations):** Guided error recovery visual treatment; Competitor retry-in-logs as a Red Hat design opportunity

#### Research questions

- Research team to add assumptions or further research questions.

1. What retry strategies do users expect: same approach modified, or a completely different path?
2. How should the system communicate what changed between retry attempts?
3. At what point should the system suggest human intervention instead of more retries?
4. What undo and rollback mechanisms do users consider essential after a failed AI action?
5. How should retry history be preserved for learning?

#### Metrics to track

1. Auto-retry success rate
2. Retry abandonment rate: % of retry sequences where the user abandons AI entirely. Segment by number of attempts.
3. Guided correction acceptance rate: When the system suggests a modified approach, % of users who follow it vs. retry unchanged or abandon.

