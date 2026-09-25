---
title: "Source Attribution"
description: "Show which data sources, documents, or knowledge bases informed AI outputs, enabling users to verify claims"
category: "Trust Builders"
status: "Recommended"
date: 2026-09-17
last_updated: 2026-09-17
contributors:
  - "Lisa Lyman"
  - "Jingfu Tan"
  - "Applied AI UX"
---

<p>🚧 <strong><em style="color:#c86500">Work in progress</em></strong> <em>(remove when ‘done’)</em></p>

# Source Attribution

## Overview
Source attribution makes the origins of AI-generated content visible by citing the data sources, documents, or knowledge bases that informed an output. It appears in conversational answers, RAG results, and other generated views where users need to check a claim before they act. Unlike a search results list, attribution maps parts of a synthesized answer back to the evidence they came from.

---
## Purpose and value
- **Required evidence:** Users treat source references as a condition of trust, not an optional extra. Every RHOKP participant required citations before they would rely on an AI answer. (RHOKP User Interview Feedback)
- **Trust but verify:** Attribution supports the common habit of checking AI output before production use, and it should help people compare more than one source.
- **Grounded answers:** Showing retrieved context lets users judge whether an answer is factually based on that context, which is the groundedness check used in RAG and agent evaluations. (RAG/Agentic Eval User Research)
- **Provenance labels:** Distinguishing copied source text from AI inference, and tracing a data point back to its origin, makes accountability possible.
- **Internal RAG with exact citations:** Teams can require answers derived from internal sources, with links to the exact document or lines of code. (Embedded and Applied AI Opportunities)
- **Honest limitations:** Do not fabricate or approximate sources, hide staleness, or cherry-pick only supportive evidence. If a claim has no source, say so. <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a>
---
## When to use
- **Factual claims users will act on:** Use attribution in troubleshooting, research, and decision support whenever users require source references before they trust the output. (RHOKP User Interview Feedback)
- **Internal knowledge and RAG:** Use it when answers must come from internal docs or code and each claim should link to the exact passage. (Embedded and Applied AI Opportunities)
- **Support and knowledge-base answers:** Use it when users share logs or ask knowledge-base questions and expect a contextualized answer with sources. (Ask Red Hat Response Accuracy Q4 2025)
- **Comparing multiple sources:** Use it when people need to inspect and compare evidence, not only see a single citation.
- **Mixed verbatim and inferred content:** Use it when an output combines copied source text with AI inference and those must be visually distinct.
- **Specific, clickable citations:** Use this pattern when you can name the document, timestamp or version, and page or section, and make the citation open the source. <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a>
---
## When not to use
- **Creative or original generation:** Skip attribution when the output is original creative work rather than retrieved knowledge. Consider [identifiers](https://www.patternfly.org/components/label/overview) for AI-generated content instead of fake citations. <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a>
- **Sources that cannot be disclosed:** Do not expose restricted or proprietary sources in the product UI. <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a>
- **Undifferentiated training data:** Listing thousands of training examples does not help users verify a claim. Prefer grounded RAG over a training-data dump. <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a>
---
## Examples and visualizations
*Screenshots below may not match existing implementations in products.*

#### Ask Red Hat knowledge-base citations
Ask Red Hat answers knowledge-base questions with cited summaries. Use chatbot messages plus link buttons so each claim opens the supporting article, and keep source lists short enough to scan. Grounded citations are part of how that experience reports high knowledge-base summary accuracy. (Ask Red Hat Response Accuracy Q4 2025)

#### OpenShift Lightspeed troubleshooting sources
Lightspeed and related OLS assistants often receive error logs and expect a contextualized answer. Attach sources to the assistant message with labels for document type, and use a popover or drawer so users can open the passage without leaving the thread. Concept-test participants described a “trust but verify” habit and asked for ways to compare sources.

#### Developer Hub RAG citations
Red Hat Developer Hub research recommends RAG that answers only from internal sources, with explicit citations to the exact document or lines of code. Pair inline source links with a card or list of file paths so developers can jump to the referenced code. (Embedded and Applied AI Opportunities)

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
---
## Related standards
- Explainability
- Confidence indicators
- Version history
---
## Notes for PatternFly
- **No citation component:** PatternFly documents Chatbot, Label, Popover, Card, and List, but it does not document a source-attribution or citation pattern for mapping a claim to evidence.
- **Message sources are not claim-level:** Chatbot messages can carry files or a source list, yet that is not the same as inline citations, credibility metadata, or comparing sources side by side.
- **Provenance types are undefined:** There is no PatternFly guidance for labeling verbatim source text versus AI inference, which this standard needs for mixed generated content.
- **Compare-sources UI is a gap:** Users asked for features that help compare multiple sources; PatternFly has Drawer and Card, but no documented comparison layout for citations.
---
## Assumptions and research questions
<a id="assumptions"></a>
#### Assumptions
Assumptions are indicated with <a href="#assumptions" class="assumption-marker" style="color:#ee0000;font-weight:700;text-decoration:none">*</a> throughout the standard.
- **[Purpose and value](#purpose-and-value):** Honest limitations
- **[When to use](#when-to-use):** Specific, clickable citations
- **[When not to use](#when-not-to-use):** Creative or original generation, Sources that cannot be disclosed, Undifferentiated training data
#### Research questions
- <mark>Research team to add assumptions or further research questions.</mark>
