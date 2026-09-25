---
title: "Source Attribution"
description: "Show which data sources, documents, or knowledge bases informed AI outputs, enabling users to verify claims"
category: "Trust Builders"
status: "Recommended"
date: 2026-09-17
last_updated: 2026-09-25
contributors:
  - "Lisa Lyman"
  - "Jingfu Tan"
  - "Applied AI UX"
---

# Source Attribution

## Overview

Source attribution makes the origins of AI-generated content visible by citing the data sources, documents, or knowledge bases that informed an output. It appears in conversational answers, RAG results, and other generated views where users need to check a claim before they act. Unlike a search results list, attribution maps parts of a synthesized answer back to the evidence they came from.

---

## Purpose and value

- **Required evidence:** Users treat source references as a condition of trust, not an optional extra. Every RHOKP participant required citations before they would rely on an AI answer.
- **Trust but verify:** Attribution supports the common habit of checking AI output before production use, and it should help people compare more than one source.
- **Grounded answers:** Showing retrieved context lets users judge whether an answer is factually based on that context, which is the groundedness check used in RAG and agent evaluations.
- **Provenance labels:** Distinguishing copied source text from AI inference, and tracing a data point back to its origin, makes accountability possible.
- **Internal RAG with exact citations:** Teams can require answers derived from internal sources, with links to the exact document or lines of code.
- **Honest limitations:** Do not fabricate or approximate sources, hide staleness, or cherry-pick only supportive evidence. If a claim has no source, say so. ([Citations and Trust in LLM Generated Answers](https://ar5iv.labs.arxiv.org/html/2501.01303))

---

## When to use

- **Factual claims users will act on:** Use attribution in troubleshooting, research, and decision support whenever users require source references before they trust the output.
- **Internal knowledge and RAG:** Use it when answers must come from internal docs or code and each claim should link to the exact passage.
- **Support and knowledge-base answers:** Use it when users share logs or ask knowledge-base questions and expect a contextualized answer with sources.
- **Comparing multiple sources:** Use it when people need to inspect and compare evidence, not only see a single citation.
- **Mixed verbatim and inferred content:** Use it when an output combines copied source text with AI inference and those must be visually distinct.
- **Specific, clickable citations:** Use this pattern when you can name the document, timestamp or version, and page or section, and make the citation open the source. ([Citation Design for RAG](https://medium.com/operations-research-bit/citation-design-for-rag-generate-validate-and-display-source-references-so-users-trust-your-bde76a7d0169))

---

## When not to use

- **Creative or original generation:** Skip attribution when the output is original creative work rather than retrieved knowledge. Consider [identifiers](https://www.patternfly.org/components/label/overview) for AI-generated content instead of fake citations.
- **Sources that cannot be disclosed:** Do not expose restricted or proprietary sources in the product UI.
- **Undifferentiated training data:** Listing thousands of training examples does not help users verify a claim. Prefer grounded RAG over a training-data dump. ([Common Pitfalls + Quick Fixes](https://medium.com/operations-research-bit/citation-design-for-rag-generate-validate-and-display-source-references-so-users-trust-your-bde76a7d0169))

---

## Examples and visualizations

*Screenshots below may not match existing implementations in products.*

#### Chat bot source attribution example

#### Contextual source attribution example

#### Ask Red Hat knowledge-base citations

Ask Red Hat answers knowledge-base questions with cited summaries. Use chatbot messages plus link buttons so each claim opens the supporting article, and keep source lists short enough to scan. Grounded citations are part of how that experience reports high knowledge-base summary accuracy.

#### OpenShift Lightspeed troubleshooting sources

Lightspeed and related OLS assistants often receive error logs and expect a contextualized answer. Attach sources to the assistant message with labels for document type, and use a popover or drawer so users can open the passage without leaving the thread. Concept-test participants described a “trust but verify” habit and asked for ways to compare sources.

#### Developer Hub RAG citations

Red Hat Developer Hub research recommends RAG that answers only from internal sources, with explicit citations to the exact document or lines of code. Pair inline source links with a card or list of file paths so developers can jump to the referenced code.

#### Redacted citation

Chat keeps the source card, but the title is redacted. A Restricted label and an inline info alert explain that the title, excerpt, and link are withheld.

#### Permissioned view

Same GUI insight as the disclosed popover. Opening Source 1 shows a popover with PatternFly empty state (lock icon) and a Request access button instead of the article.

#### Audit trail for authorized reviewers

A reviewer-only Source access audit page. Conversation metadata sits in a description list; a compact table logs source IDs and events without exposing titles or excerpts in the product UI.

---

## Recommended components

- **[Chatbot](https://www.patternfly.org/extensions/chatbot/overview):** PatternFly Chatbot is the conversation surface for assistant messages. Use it as the home for inline source chips and a per-message source list.
- **[Label](https://www.patternfly.org/components/label/overview):** Compact metadata for source type, recency, or provenance such as verbatim versus inference.
- **[Popover](https://www.patternfly.org/components/popover/overview):** A short overlay for title, timestamp, excerpt, and a link to the full source without leaving the answer.
- **[Button](https://www.patternfly.org/components/button/overview):** Link buttons that open the original document, article, or code location.
- **[Card](https://www.patternfly.org/components/card/overview):** A container for richer source metadata when a popover is not enough.
- **[Drawer](https://www.patternfly.org/components/drawer/overview):** A side panel for a full source list, document preview, or side-by-side comparison.
- **[List](https://www.patternfly.org/components/list/overview):** A structured list of cited sources under or beside the generated answer.
- **[Tooltip](https://www.patternfly.org/components/tooltip/overview):** A hover label for an inline citation when the full source title would clutter the sentence.
- **[Expandable section](https://www.patternfly.org/components/expandable-section/overview):** Collapse long source lists so the answer stays readable.
- **[Messages](https://www.patternfly.org/extensions/chatbot/messages#bot-messages):** Inline Footnotes

---

## Related standards

- [Chain of thought](../chain-of-thought/chain-of-thought.md)
- [Audit trails](../../governors/audit-trails/audit-trails.md)
- [Ethics: Transparency and information integrity](../../foundations/ethics-transparency-and-information-integrity/ethics-transparency-and-information-integrity.md)
- [Human-in-the-Loop (HITL)](../../governors/human-in-the-loop/human-in-the-loop.md)

---

## Notes for PatternFly

- **Message sources are not claim-level:** Chatbot messages can carry files or a source list, yet that is not the same as inline citations, credibility metadata, or comparing sources side by side.
- **Provenance types are undefined:** There is no PatternFly guidance for labeling verbatim source text versus AI inference, which this standard needs for mixed generated content.
- **Compare-sources UI is a gap:** Users asked for features that help compare multiple sources; PatternFly has Drawer and Card, but no documented comparison layout for citations.

---

## Assumptions and research questions

<a id="assumptions"></a>
#### Assumptions

No assumptions made

#### Research questions

1. When an AI answer cites a source user can't access, what do they do next? Do they try to get access, ask someone who has access, accept the answer anyway, or distrust it?
2. If users can't see the actual source document, how do they react to a redacted citation, a permissioned view, or an audit trail for authorized reviewers?

#### Metrics to track

1. Source verification rate: % of AI responses with citations where users interact with at least one source (hover, click, or expand).
