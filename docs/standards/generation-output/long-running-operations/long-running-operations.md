---
title: "Long-Running Operations"
description: "Guide users through AI work that takes longer than a brief interaction, with progressive wait tiers, honest expectations, and a clear signal when work finishes or fails"
category: "Generation & Output"
status: "Experimental"
date: 2026-08-04
last_updated: 2026-09-25
contributors:
  - "Lisa Lyman"
  - "Applied AI UX"
---

# Long-Running Operations

## Overview

Long-running operations guide users through AI work that takes longer than a brief interaction. They cover progressive wait tiers (from an active 10 to 30 second wait through multi-minute background jobs), set honest expectations, keep processing visible or backgrounded as appropriate, and notify users when work finishes or fails so they can leave and return with confidence.

---

## Purpose and value

- **Set time expectations:** Tell users early when a task will take more than a few seconds so they can plan their next action.
- **Protect productivity and flow:** Background the job so users can keep working while AI analyzes logs, plans upgrades, or synthesizes large outputs. Latency is sometimes caused by product-specific controller reconciliation (e.g., waiting for pods to terminate, CRDs to update, or secrets to mount). Use appropriate Deep Think messaging to accurately describe the product's latency.
- **Close the loop with deep links:** Deliver completion toasts, notification drawer items, or email with a URL that opens the completed output view with filter and state pre-loaded.
- **Reduce abandonment:** Transparent step-level progress and recoverable status prevent users from assuming the AI stalled or failed. Additionally, we recommend defining distinct UI notification states for System Errors (retryable infrastructure crashes) versus Domain/Objective Escalations (clean handoffs to human operators).
- **Preserve trust with AI identity:** Mark background AI jobs with an AI badge (and sparkle iconography where appropriate) so they are distinct from standard system tasks. ([All That Sparkles is AI; Pozos and Shmidt](https://design.google/library/ai-sparkle-icon-research-pozos-schmidt))
- **Support cancel and recovery:** Allow cancel mid-process, survive session logout when the job can continue server-side, and recover cleanly from network or socket disconnects. For agentic operations (such as modifying live cluster state), differentiate between a simple Cancel (stopping analysis/queued tasks) and an Emergency Abort (which must clearly communicate whether the backend triggers a rollback or leaves active cluster resources untouched). ([https://github.com/agentpatternscatalog/patterns/blob/main/patterns/stop-cancel.md](https://github.com/agentpatternscatalog/patterns/blob/main/patterns/stop-cancel.md))

---

## When to use

- **Heavy analysis jobs:** AI is processing large artifacts (for example, gigabytes of system logs) with multi-minute runtime.
- **Active wait (about 10 to 30 seconds):** Work that is still in view but long enough that a bare spinner erodes trust; show Deep Thinking steps. ([Response Time Limits](https://www.nngroup.com/articles/response-times-3-important-limits/); [Progress Indicators Ease the Wait](https://www.uxtigers.com/post/progress-indicators); [Progress Indicators Make a Slow System Less Insufferable](https://www.nngroup.com/articles/progress-indicators/))
- **Async handoff (about 30+ seconds):** Users benefit from leaving via notification, toast, drawer, or email when ready.
- **Non-chatbot surfaces:** Dashboard actions, drawers, tables, and wizards that start AI work outside a chatbot. ([Agentic UX: Frontend Design Patterns for AI Agents in 2026](https://zylos.ai/research/2026-05-28-agentic-ux-frontend-design-patterns-ai-agents))
- **Multi-step agent workflows:** Upgrade simulations, compliance scans, and fleet analysis where step status matters. Progress indicators and timelines adapt to the declared workflow shape, hiding non-applicable steps entirely rather than rendering them as greyed-out or empty future states.

#### The psychology of wait times and thresholds

UX guidelines regarding response times dictate how we handle AI processing delays. (Supporting Research: [Response Times: The 3 Important Limits](https://www.nngroup.com/articles/response-times-3-important-limits/); [Powers of 10: Time Scales in User Experience](https://www.nngroup.com/articles/powers-of-10-time-scales-in-ux/); [Website Response Times](https://www.nngroup.com/articles/website-response-times/))

- 0.1 seconds: Limit for users feeling the system is reacting instantaneously.
- 1.0 seconds: Limit for the user's flow of thought to stay uninterrupted.
- 10 seconds: Hard limit for keeping user attention focused on the screen.
- 30+ seconds: The optimal threshold for explicitly offering the "walk away and we'll notify you" experience (Async Handoff).

#### Use-case based timelines and architectural routing

If the AI architecture cannot predict exactly how long a prompt will take, route the UX based on the workflow type (Intent):

1. **Synchronous tasks** (<10 seconds): Basic Chat Q&A, single-document summarization, simple text/code completion.

   *Do not background* - use the PatternFly [spinner](https://www.patternfly.org/components/spinner).

2. **Active wait times** (10-30 seconds): Complex RAG over multiple docs, querying single cluster status, bounded log parsing.

   *Keep in-view but show progress* - use the PatternFly [spinner](https://www.patternfly.org/components/spinner) and

3. **Agentic / heavy workflows** (30+ seconds): Multi-file code refactoring, autonomous root-cause analysis, multi-step agentic workflows.

   *Default to Backgrounding* - use the PatternFly [spinner](https://www.patternfly.org/components/spinner),  and Long-running operation standards.

---

## When not to use

- **Short or streaming responses:** For generation under 10 seconds, use [Deep Thinking](https://www.patternfly.org/extensions/chatbot/messages/#messages-with-deep-thinking) only.
- **Interactive clarification loops:** If the AI still needs turn-by-turn answers, do not background the conversation mid-clarification. ([https://aidesignblueprint.com/en/background-work-visibility](https://aidesignblueprint.com/en/background-work-visibility))
- **Unknown duration with no progress signal:** Do not claim a long-running pattern if you cannot show status, cancel, or completion; prefer a bounded progress state first — do not invent fake milestones.
- **Tasks that die with the session:** If work cannot survive navigation or logout, do not offer background processing or "email me when ready." ([Managing AI Response States; Den Odell](https://frontendpatterns.dev/guides/managing-ai-response-states))

---

## Examples and visualizations

*Screenshots below may not match existing implementations in products.*

#### Chatbot active wait and walk-away copy

Uses PatternFly Chatbot deep thinking as a baseline. The assistant sets a time expectation, invites the user to leave and keep working, shows expandable Deep Thinking progress, and offers Cancel operation. <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a>

Chatbot active wait with a time expectation, expandable deep thinking steps, and Cancel operation

#### Active wait (10 to 30 seconds) on a product page

Show an inline AI-labeled progress card with Deep Thinking-style steps when a non-chat action is still in view but past a bare spinner. Offer Cancel and, as duration approaches about 30 seconds, a Run in background action.

#### Dashboard walk-away (non-chatbot)

On a full-page dashboard, trigger AI analysis from a primary action, then offer Run in background so the SRE can return to triage. Mark the job with an AI badge. <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a>

#### Drawer-triggered background job

From a details drawer, start AI work and keep a compact inline banner for status while the drawer can close. Completion lands in a toast and notification drawer with a deep link.

#### Completion toast with deep link

Benefit-first sentence case microcopy. Example: "System log analysis complete. Select to view the architecture report." The toast and notification item share a URL parameter that opens the output view with filter and state pre-loaded.

---

## Recommended components

- **[Spinner](https://www.patternfly.org/components/spinner/overview):** Brief waits under about 4 seconds, and inline step progress inside Deep Thinking.
- **[Deep Thinking](https://www.patternfly.org/extensions/chatbot/messages#messages-with-deep-thinking):** Active wait (about 10 to 30 seconds) with completed and in-progress steps.
- **[Alert](https://www.patternfly.org/components/alert/overview) (toast variant):** Async completion and non-blocking failures; success toasts use role="status" and aria-live="polite".
- **[Notification drawer](https://www.patternfly.org/components/notification-drawer/overview):** Persistent record of background AI jobs and completions outside the immediate view.
- **[Inline banner](https://www.patternfly.org/components/alert#inline-alerts-variants) (Alert inline):** In-page status when the user remains on the originating surface.
- **[Label](https://www.patternfly.org/components/label) / [AI badge](https://www.patternfly.org/ai/guidelines/transparency-notices#indicating-ai-generated-content):** Differentiate AI background jobs from standard system tasks.
- **[Button](https://www.patternfly.org/components/button):** Run in background, Cancel operation, and deep-linked View results.
- **[Drawer](https://www.patternfly.org/components/drawer/overview):** Non-chatbot surfaces that start or monitor long AI work beside a full page.

---

## Related standards

- [Deep Thinking](https://www.patternfly.org/extensions/chatbot/messages#messages-with-deep-thinking)
- [Alert Messages](../../error-handling/alert-messages/alert-messages.md)
- [Chain of Thought](../../trust-builders/chain-of-thought/chain-of-thought.md)

---

## Notes for PatternFly

- **Non-chat Deep Thinking equivalent:** Document a PatternFly-aligned step list pattern for dashboards and drawers that mirrors Chatbot Deep Thinking outside chat surfaces.
- **Async handoff threshold guidance:** Consider documenting a default ~30 second walk-away offer and accessible toast/drawer completion patterns for AI background jobs.

---

## Assumptions and research questions

<a id="assumptions"></a>
#### Assumptions

Assumptions are indicated with <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a> throughout the standard.

- **[Example visualizations](#examples-and-visualizations):** Dashboard walk-away (non-chatbot), Chatbot active wait and walk-away copy

#### Research questions

1. At what time threshold should the system suggest async handoff (validate the 30+ second threshold)?
2. How should users be notified when long-running operations complete?

#### Metrics to track

1. Async handoff acceptance rate: When the system offers to background a task, what % of users accept vs. choose to wait? This measures whether the 30-second threshold is correctly calibrated.
2. Notification delivery rate: What % of completion notifications actually reach the user?
