---
title: "Canvas mode"
description: "Place a conversation thread alongside a live workspace pane so users can co-create and refine exportable assets through direct editing and continuous dialogue"
category: "Conversation"
status: "Experimental"
date: 2026-09-25
last_updated: 2026-09-25
contributors:
  - "Liz Clayton"
  - "Mary Shakshober-Crossman"
  - "Applied AI UX"
---

# Canvas mode

## Overview

Canvas mode is a split-pane layout that places a conversation thread alongside a live workspace pane, optimized for continuous ideation and generation. It enables users to co-create and refine exportable assets—such as code snippets, documents, or topology nodes—through direct editing, version history, and continuous dialogue. You can accept an AI-generated baseline and immediately mold it with direct keystrokes, creating a seamless partnership over a shared deliverable. Unlike task-based flows, canvas mode supports live, open-ended editing without a forced completion trigger; users can iterate endlessly, pause their work, and revisit canvas edits later.

The defining trait is the persistent, resizable split between the chat and the canvas: both panes remain visible simultaneously so users can edit manually while maintaining conversational context with the AI. Since both panes remain visible simultaneously, users maintain full conversational context with the AI while driving manual edits in the workspace. This architecture accommodates two distinct workflows at once: delegating broad tasks to the AI (via chat) and direct manual manipulation (via the canvas), eliminating the cognitive load of scrolling and context-switching.

---

## Purpose and value

- **Reduces context switching:** Keeping the conversation and the generated artifact side by side eliminates the need to toggle between views, letting users refine output without losing the thread.
- **Supports iterative refinement:** Users can ask follow-up questions and immediately see changes reflected in the canvas, shortening the feedback loop between intent and result.
- **Enables seamless co-authorship:** Instead of strictly dividing human work from AI work, the canvas blends them. It allows users to accept an AI-generated baseline and immediately mold it with manual keystrokes, creating a frictionless partnership over a shared deliverable.
- **Enables direct manipulation:** Users can edit canvas content without re-prompting, giving them control over the final output without leaving the interface.
- **Accelerates handoff:** Inline export and copy actions mean users can act on content immediately rather than switching to a separate tool.

---

## When to use

- **Structured AI output:** Use canvas mode when the AI produces content that users need to edit, revise, and reuse — such as code snippets, documents, summaries, or configuration files.
- **Non-linear, open-ended exploration:** Use when the user's process is exploratory and cyclical rather than sequential. Unlike a guided step-by-step task, the canvas supports workflows where the user is "sculpting" a central asset—experimenting, pivoting, undoing, and continuously molding the deliverable without a predetermined finish line or forced completion state.
- **Side-by-side analysis:** Use in observability, monitoring, or planning contexts where viewing a live data pane alongside a conversation is critical to decision-making.

---

## When not to use

- **Simple Q&A exchanges:** If the AI response is a short answer with no structured artifact to edit, a standard chat interface is sufficient. Consider raw text input instead.
- **Mobile-only or narrow viewports:** The split-pane layout depends on sufficient horizontal space. Avoid canvas mode on small screens where both panes cannot be usably displayed simultaneously.
- **Very large node graphs:** Canvas mode can degrade when the workspace contains more than approximately 50 nodes; consider alternate navigation or progressive disclosure approaches.
- **Read-only outputs:** If users have no need to edit or export the generated content, a simpler response format reduces cognitive load and interface complexity.
- **Guided and multi-step workflows:** Canvas mode is explicitly designed for open-ended, non-linear iteration. Guided workflows—such as forms, setup wizards, onboarding flows, checkout processes, or sequential data entry—require the exact opposite: strict guardrails, sequential progression, and a definitive completion trigger.

---

## Best practices

When deciding between canvas mode and a standard chat interface, consider the complexity and intent of the interaction. Use the comparison table below as a guide.

| Consideration | Opt for Canvas Mode | Opt for Standard Chat |
| --- | --- | --- |
| Task nature & flow | The user is engaged in an open-ended, iterative process requiring continuous refinement without a strict endpoint. | The workflow is linear, guided (like a setup wizard), or involves a simple, single-turn Q&A. |
| Artifact interaction | The output is a tangible asset (code, document, configuration) that the user must directly manipulate, revise, and eventually export. | The output is informational or read-only, where the user just needs an answer without needing to edit the result. |
| Context & visibility | Successful task completion relies on viewing the generated asset or live data simultaneously with the AI conversation. | The context is easily maintained within a scrolling message thread, or the visual payload is small enough to fit inline. |
| System viewport | The user is operating on a large desktop viewport capable of supporting a persistent split-pane view, and the asset (e.g., node graph) is of manageable size. | The interface is constrained by narrow viewports (e.g., mobile) or the data being rendered (e.g., massive topology maps) would overwhelm a split layout. |

---

## Artifact-specific use cases (writing & coding)

While standard chat is suitable for isolated requests, canvas mode excels when the AI acts as a collaborative copy editor or code reviewer with the entire project in mind.

#### Document creation and editing

- **Canvas mode:** Use for long-form projects (e.g., a blog post) requiring ongoing revisions. Canvas enables highlighting specific sections for targeted edits, adjusting length, modifying the reading level, or applying a final polish for grammar and consistency.
- **Standard Chat:** Use for general Q&A tasks (e.g., "Help me cook a new recipe") or when requesting short, one-off informational responses that do not require side-by-side text manipulation.

#### Code generation and editing

- **Canvas Mode:** Use for iterative coding processes where tracking revisions is critical. Canvas allows for inline code reviews, adding debugging logs or comments, detecting and fixing targeted bugs, and porting code to different languages (e.g., Python, TypeScript).
- **Standard Chat:** Use for isolated syntax queries, simple explanations of programming concepts, or generating small standalone snippets where maintaining the broader context of an entire file is unnecessary.

---

## Edge cases and workspace states

To maintain user trust and prevent data loss in a synchronized workspace, the interface must provide clear, predictable patterns for handling critical edge cases. Designers should adhere to the following behavioral guidelines:

- **Save Indicators:** Provide passive, non-intrusive autosave feedback (such as a "Draft saved" label or cloud checkmark icon) in the canvas header toolbar. In the event of a sync failure, escalate the visual hierarchy to an empty state component with actionable reload buttons and a text notification of failure to load. Allowing the user to manually reload, save or copy their work to the clipboard helps to communicate status.
- **Pane Bounds & Resizing:** Implement a clear drag handle along the vertical splitter between the chat and canvas panes. Define strict minimum widths (e.g., 300px for the chat pane) to ensure the layout remains usable.
- **Interaction Collisions:** If a user attempts to manually type or edit content in the exact zone where the AI is actively streaming text, the system must prioritize human intent. Immediately pause or gracefully halt the AI generation, and display a brief, non-blocking notification (e.g., "AI generation paused by manual edit") to explain the interruption.
- **Human Recovery (Undo/Redo):** Standardize error recovery by supporting native platform keyboard shortcuts (Ctrl/Cmd + Z) alongside clearly visible, on-screen undo/redo action buttons in the canvas formatting toolbar. Treat AI-generated structural changes or blocks of text as distinct, reversible states in the document's history to allow users a quick rollback to their prior state.

---

## Guardrails and compliance

To address data privacy and maintain brand consistency, all canvas mode integrations must adhere to the following guardrails and compliance protocols:

- **Align with AI Visual Language:** Ensure that any custom UI additions within the canvas layout—such as active canvas labels, AI-generated text highlighting, or edit-attribution markers—strictly follow the AI Visual Language standard. This includes correctly applying [sparkle icons](https://www.patternfly.org/ai/guidelines/iconography), labeling, and [visual treatments](https://www.patternfly.org/ai/guidelines/color) to clearly indicate AI contributions.
- **Integrate Compliance Checks:** Due to the continuous and iterative nature of [data exchange in AI](https://www.patternfly.org/ai/guidelines/legal-requirements) and canvas mode, teams must ensure their workflows handle regulatory and risk audits appropriately. Be sure to consult the [AI Assessment](https://source.redhat.com/departments/strategy_and_operations/it/it_information_security/data_privacy/aia~2) (AIA) compliance flow.
- **Address Sensitive Data Masking:** Users may frequently paste or generate code, configurations, or logs within the canvas. Designers must incorporate visual guidelines and inline warnings prompting users to [mask sensitive data](https://www.patternfly.org/ai/guidelines/transparency-notices) (such as hostnames, credentials, or PII) inside the canvas container before any edits are passed back to the underlying model.

---

## Examples and visualizations

*Screenshots below may not match existing implementations in products.*

#### PatternFly - Canvas label in message bar

After prompting the AI bot to utilize the canvas mode feature, a dismissable label should be enabled within the message bar to indicate to the user that canvas mode is currently active.

Custom message bar label not in official API: [The canvas label](https://www.patternfly.org/extensions/chatbot/ui#message-bar-with-custom-attach-menu-and-additional-actions) in the custom message bar on patternfly.org was added as a custom prop. This approach is not part of the official @patternfly/chatbot component API; it may need to be upstreamed or documented as an extension pattern for other teams to replicate.

Message bar with a dismissible Canvas label next to the model selector

#### PatternFly - Ai transparency label

The user should always display a [clickable label](https://www.patternfly.org/components/label) with a paired [AI transparency notice](https://www.patternfly.org/ai/guidelines/transparency-notices) on canvas mode. A popover or tooltip component should be displayed upon hover or click.

Generated with AI label open to a popover explaining what canvas mode is

#### PatternFly - Canvas mode layout

Canvas lets users work with generated or editable content alongside a conversation. Canvas content is fully flexible, allowing you to render any content suitable for your use case. It is recommended to only utilize canvas mode with a fullscreen Chatbot.

When utilizing a canvas layout, it's recommended to use a PatternFly [drawer](https://chatbot-pr-chatbot-909.surge.sh/components/drawer). You must apply the `pf-chatbot__canvas*` classes from `@patternfly/chatbot` so the drawer matches ChatBot backgrounds and fills the fullscreen layout.

Split-screen chatbot with an empty canvas pane beside the conversation

#### PatternFly - Canvas mode with code editor

*Demo link coming soon.*

Canvas code editor showing an HTML document beside the chatbot conversation

#### PatternFly - Canvas with topology nodes <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a>

This pattern is an assumption. This pattern has yet to be implemented. The topology node output and wired up logic should be determined by the product area.

Canvas topology layout with connected nodes beside the chatbot conversation

#### PatternFly - Canvas with document editor <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a>

This pattern is an assumption. This example serves as a general design pattern recommendation for structuring document editing.

Canvas document editor with formatting toolbar and export beside the chatbot conversation

#### PatternFly - Canvas with error state

Utilize the patternfly [empty state](https://www.patternfly.org/extensions/component-groups/error-state/#custom-footer) component to convey connection status.

Canvas pane showing an unable-to-connect empty state with a reload action

#### PatternFly - Canvas with loading state

Utilize the patternfly [loading empty state](https://www.patternfly.org/components/empty-state#spinner) component to convey connection status. Also consider a [skeleton loader](https://www.patternfly.org/components/skeleton/design-guidelines) to expose new loaded content incrementally. A skeleton should match the exact structure of the element you’re loading in.

Canvas pane showing a spinner while content is generating

#### PatternFly - Attachment menu component

The user can enable canvas mode 3 ways:

A.) Manually clicking the “Enable canvas mode” menu item in the custom attach menu. Below you will see a visual of a message bar with a custom attach menu where a PlusIcon is positioned at the start.

B.) Conversationally prompting the AI bot to use canvas mode.

C.) Clicking the attachment chip provided by the bot in the conversation flow.

Chatbot attach menu with Enable Canvas Mode highlighted

---

## Recommended components

- **[Chatbot](https://www.patternfly.org/extensions/chatbot/overview):** The @patternfly/chatbot package provides the conversation pane components (Chatbot, ChatbotContent, MessageBox, MessageBar) used on the left side of a canvas layout. The embedded chatbot demo is the closest existing reference.

---

## Related standards

- [Action confirmation](../../governors/action-confirmation/action-confirmation.md)
- [Plan approval](../../governors/plan-approval/plan-approval.md)
- [Audit trails](../../governors/audit-trails/audit-trails.md)
- [Long-Running Operations](../../generation-output/long-running-operations/long-running-operations.md)
- [Raw text input](../../input-authoring/raw-text-input/raw-text-input.md)

---

## Notes for PatternFly

- A dedicated demo for canvas mode is in progress. Coming to the next Patternfly 6.7 release.
- A [RFE proposal](https://redhat.atlassian.net/browse/FELTRFE-72?atlOrigin=eyJpIjoiMzFhMzQxODA4M2IwNDdmNmIzZjYwNzQ2ZGM0OWI4ZjYiLCJwIjoiaiJ9) has been submitted for a version history pattern. Pending acceptance, this pattern can be implemented within canvas mode for version control monitoring.

---

## Assumptions and research questions

<a id="assumptions"></a>
#### Assumptions

Assumptions are indicated with <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a> throughout the standard.

- **[Example visualizations](#examples-and-visualizations):** PatternFly - Canvas with topology nodes, PatternFly - Canvas with document editor,

#### Research questions

1. At what content complexity threshold do users switch from preferring inline chat responses to wanting a canvas? (Using task-based concept/usability testing with varying content complexity to evaluate user preference.)
2. During active troubleshooting, how do users distribute attention between the chat pane and the canvas pane? (Observe user behavior using Canvas mock-ups during concept/usability testing).

#### Proposed metrics to track

1. Canvas activation rate: % of eligible sessions where users open/engage with the canvas pane vs. remaining in chat-only mode
2. Direct edit vs. re-prompt ratio: frequency of direct canvas edits vs. chat-based revision requests
3. Export/copy rate: % of sessions where canvas content is exported or copied
4. Pane resize frequency: how often users adjust the split ratio (indicates whether the default ratio is appropriate)
