---
title: "Ethics: Transparency and information integrity"
description: "Help people see what is AI-generated, where it came from, how sure it is, what it cannot do, and what data it used"
category: "Foundations"
status: "Recommended"
date: 2026-09-10
last_updated: 2026-09-25
contributors:
  - "Mary Shakshober-Crossman"
  - "Jason Brock"
  - "Applied AI UX"
---

# Ethics: Transparency and information integrity

## Overview
Transparency and information integrity is the perception side of ethical AI: people can see what is AI-generated, where it came from, how sure it is, what it cannot do, and what data it used — not merely receive an answer.

---
## Purpose and value
- **Grounded enough to verify:** People will not trust an answer they cannot check. 100% of RHOKP participants required source references to trust AI answers.
- **Honest about uncertainty:** If the model does not know, it should say so — not invent a completion. Responsible AI development is a top priority: no harmful responses or hallucinations; products for children need to be safe but also right.
- **Limits in view:** Overstated capability creates dependence and bad decisions. Users need to see what the system cannot do at the moment they would over-trust it. Transparently communicate capabilities and limitations to manage expectations. Experienced admins also fear AI can replace key learning and prevent problem-solving instincts.
- **Data use you can see:** Privacy belongs here because it is perception — users need to see what data is collected and how it is used. ([Transparency Obligations](https://artificialintelligenceact.eu/article/50/))
- **Provenance that can survive scrutiny:** In regulated work, incorrect or unattributed generated material can mean fines in the millions. Users need to trace an output back to sources, model, or human edit.
---
## Best practices
1. **Separate verbatim from inference:** Show what was retrieved or quoted versus what the model inferred so people could see which claims were directly sourced.
2.
3. Indicate recommendations: When multiple paths forward exist and/or supporting evidence is scarce, it is best to show a clear indicator of the best recommendation or most likely cause for an error.
4. **Disclose limits where over-trust would happen:** Capability and limitation copy belongs next to the action, not only in a model card. Users benefit when the AI experience is narrowly scoped, and they need capabilities and limitations communicated to manage expectations.
5. **Keep users informed of what AI is doing:** What was sent, stored, or used to generate this answer should be visible in the flow, not only in a legal footer. ([Not All Transparency Is Equal](https://doi.org/10.48550/arxiv.2512.12207))
---
## Things to avoid
- **Unlabeled generated content:** If a summary, patch, or recommendation can be mistaken for a system fact or a human author, it is not transparent. ([The EU AI Act’s Transparency Rules](https://artificialintelligenceact.eu/transparency-rules-article-50/), [Implied Authenticity Effect](https://ojs.aaai.org/index.php/ICWSM/article/view/42721))
- **Fake or approximate sources:** Do not invent citations, round to a nearby doc, or hide staleness. Fabricated provenance is worse than no provenance.
- **Arbitrary confidence measurement:** A percentage with no meaning (“67% match”) trains users to ignore uncertainty. Confidence should be backed by real calibration — not an arbitrary score. If you cannot explain what the number measures, do not show it.
- **Anthropomorphic voice:** First-person certainty (“I’m confident this will work”) implies a responsible person. It is a model. ([Believing Anthropomorphism](https://dl.acm.org/doi/10.1145/3613905.3650818))
- **Transparency as a substitute for oversight:** Explaining the AI is not the same as letting someone approve, stop, or correct it. ([Transparency Is Not the Same as Truth](https://cispa.de/user-study-ai-labels))
---
## Ways to achieve ethical transparency and information integrity

#### Clearly label where AI is being used
Whenever generated text, code, configuration, a summary, or an image will be read or applied, mark it as AI-generated on that surface — a table cell, a YAML preview, a ticket comment, not only the chatbot. Pair the label with functional copy (“AI-suggested configuration”), never a persona. Keep the mark on exported or copied artifacts so provenance survives the UI. ([EU AI Act Article 50](https://particula.tech/blog/eu-ai-act-article-50-ai-content-marking-implementation))

Chat and logs surfaces with AI labels on the bot, diagnosis card, synthesis column, and most-likely cause

#### Provide viewable sources
When a claim depends on retrieved knowledge, show the [specific sources](https://www.patternfly.org/extensions/chatbot/messages/#messages-with-sources) with a title and a link the user can follow. Prefer inline or adjacent citations over a buried “learn more.” Distinguish retrieved or quoted material from model inference. If there is no source, say so — do not approximate.

Chatbot message with a viewable sources card linking to Getting started with Red Hat OpenShift

#### Surface data and actions to the user before, during and, after AI execution
Show what context was sent, stored, or used to produce this output — files attached, cluster state, conversation memory — at the moment of use. Link to deeper privacy details, but do not make the product disclosure a legal-only page. A plain-English “AI-generated summary” ranked 11 of 12 in observability prioritization — people want evidence, not a narrative recap.

---
## Related standards
- [Ethics: Human oversight](../ethics-human-oversight/ethics-human-oversight.md)
- [Ethics: Harm reduction](../ethics-harm-reduction/ethics-hardm-reduction.md)
- [Audit trails](../../governors/audit-trails/audit-trails.md)
- [Alert messages](../../error-handling/alert-messages/alert-messages.md)
- [Clarification prompts](../../conversation/clarification-prompts/clarification-prompts.md)
- [Log summary & synthesis](../../generation-output/log-summary-and-synthesis/log-summary-synthesis.md)
- [Contextual AI invocation](../../input-authoring/contextual-ai-invocation/contextual-ai-invocation.md)
- [Source attribution](../../trust-builders/source-attribution/source-attribution.md)
- [Ethics: Skill and expertise preservation](../ethics-skill-and-expertise-preservation/ethics-skill-expertise-preservation.md)
- [Ethics: Bias and fairness](../ethics-bias-and-fairness/ethics-bias-and-fairness.md)
---
## Assumptions and research questions
<a id="assumptions"></a>
#### Assumptions
No assumptions made.
#### Research questions
1. How do users perceive first-person voice on AI generated content?
#### Metrics to track
1. Source verification rate: % of AI responses with sources where users click at least one source link. Low rates may indicate source links are ignored (users trust blindly) or inaccessible (too much friction to verify).
