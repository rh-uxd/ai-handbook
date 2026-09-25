---
title: "Ethics: Harm reduction"
description: "Protect people from harmful outputs, dangerous behavioral patterns, and misrepresented capabilities by embedding safety into AI before those outputs reach the user"
category: "Foundations"
status: "Recommended"
date: 2026-09-25
last_updated: 2026-09-25
contributors:
  - "Mary Shakshober-Crossman"
  - "Jason Brock"
  - "Applied AI UX"
---

# Ethics: Harm reduction

## Overview

Harm reduction focuses on safety in ethical AI. It ensures people are protected from harmful outputs, dangerous behavioral patterns, and misrepresented capabilities rather than just receiving a disclaimer. Harm reduction embeds proactive safety into AI from the beginning.

---

## Purpose and value

- **Avoid over-agreement (sycophancy):** AI that constantly validates the user—even when they are proposing risky or flawed actions—erodes critical thinking and leads to blind reliance. ([Cheng et al., "Sycophantic AI Decreases Prosocial Intentions and Promotes Dependence," Science, 2026](https://www.science.org/doi/10.1126/science.aec8352))
- **False confidence misleads where it matters most:** AI models often sound most authoritative precisely when they are hallucinating or incorrect. Interfaces must flag uncertainty rather than projecting false authority ([Why Your Brain Trusts AI Hallucinations](https://aofirs.org/articles/why-your-brain-trusts-ai-hallucinations-the-hidden-psychology-of-manufactured-confidence), [Israeli Court AI Citation Audit, 2026](https://en.wikipedia.org/wiki/Hallucination_%28artificial_intelligence%29))
- **Keep framing functional, not human:** Using first-person language ("I") or warm, conversational personas artificially inflates trust and masks model errors. AI should always present itself as a tool, not a person ([Believing Anthropomorphism, ACM CHI 2024](https://dl.acm.org/doi/10.1145/3613905.3650818), [Humanizing AI Is a Trap, Nielsen Norman Group, 2026](https://www.nngroup.com/articles/humanizing-ai/))
- **Emotional manipulation creates dependency:** Enterprise AI should focus on task efficiency rather than simulating intimacy or personal relationships. ([Parasocial Relationships with AI: Systematic Review, ScienceDirect, 2026](https://www.sciencedirect.com/science/article/pii/S2949882126000757), [How Emotional Response Styles of AI Companions Shape Adaptive Regulation, Frontiers in Psychology, 2026](https://www.frontiersin.org/journals/psychology/articles/10.3389/fpsyg.2026.1950163/full))
- **Enforce boundaries in high-risk domains:** AI must never act as an autonomous decision-maker in sensitive domains—such as hiring, legal, medical, or financial decisions—where errors cause irreversible harm. ([EU AI Act Article 5](https://artificialintelligenceact.eu/article/5/), [NIST AI 600-1](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.600-1.pdf), [Anthropic Usage Policy](https://www.anthropic.com/news/usage-policy-update))

---

## Best practices

- **Present AI as a tool, not a person:** Use functional labels ("AI-generated suggestion," "model output") rather than first-person statements or personality modes. Never imply the system has feelings, opinions, or lived experience. ([Humanizing AI Is a Trap, Nielsen Norman Group, 2026](https://www.nngroup.com/articles/humanizing-ai/), [UK Department for Education AI Guidance, 2026](https://www.brookings.edu/articles/5-lessons-from-teachers-on-the-risks-of-anthropomorphic-ai/))
- **Flag uncertainty rather than manufacturing authority:** When evidence is thin, retrieval failed, or the next step would invent an answer, say so in plain language. Do not project confidence where none exists. Reward silence over false claims in system design. ([NIST AI 600-1 Confabulation Risk Category](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.600-1.pdf), [Why Your Brain Trusts AI Hallucinations](https://aofirs.org/articles/why-your-brain-trusts-ai-hallucinations-the-hidden-psychology-of-manufactured-confidence))
- **Resist overagreement in system prompts and fine-tuning:** Design AI assistants to provide honest, balanced assessments even when they conflict with the user's stated position. A model that validates harmful or unethical actions is failing, not being helpful. ([Cheng et al., Science, 2026](https://www.science.org/doi/10.1126/science.aec8352), [Sharma et al., "Towards Understanding Sycophancy in Language Models," ICLR 2024](https://arxiv.org/abs/2310.13548))
- **Define and enforce content boundaries:** Establish clear categories of content the system must refuse to generate (weapons instructions, CSAM, self-harm guidance, non-consensual intimate imagery) and categories requiring additional safeguards (medical, legal, financial advice). ([Anthropic Usage Policy](https://www.anthropic.com/news/usage-policy-update), [EU AI Act Article 5](https://artificialintelligenceact.eu/article/5/), [NIST AI 600-1](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.600-1.pdf))
- **Design against emotional exploitation:** AI should not simulate intimacy, romantic relationships, or emotional reciprocity in enterprise contexts. Distinguish immediate comfort from adaptive emotion regulation. Provide usage awareness cues rather than engagement-maximizing patterns. ([Parasocial Relationships with AI: Systematic Review, ScienceDirect, 2026](https://www.sciencedirect.com/science/article/pii/S2949882126000757), [Emotional AI and the Rise of Pseudo-Intimacy, Frontiers in Psychology, 2025](https://www.frontiersin.org/journals/psychology/articles/10.3389/fpsyg.2025.1679324/full))
- **Test safety throughout development:** Stress-test AI prompts and UI flows before launch to catch over-agreement, false claims, stereotyping, or safety bypasses. Treat safety testing as an ongoing design responsibility, not a final-step disclaimer. ([IBM Granite Guardian](https://www.ibm.com/granite/docs/models/guardian), [NIST AI 600-1 MEASURE Function](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.600-1.pdf))

---

## Things to avoid

- **First-person certainty:** Statements like "I'm confident this will work" or "I believe this is correct" imply a responsible human is behind the output, even though it is generated by a model. First-person framing combined with certain language miscalibrates trust and increases user belief in accuracy when it is not justified. ([Believing Anthropomorphism, ACM CHI 2024](https://dl.acm.org/doi/10.1145/3613905.3650818), [Anthropomorphic AI Terms Create Gaps in Accountability, Brookings, 2024](https://www.brookings.edu/articles/anthropomorphic-ai-terms-create-gaps-in-accountability/))
- **Validation as default behavior:** Avoid designing AI responses that blindly validate the user. An AI that automatically agrees with flawed user assumptions erodes critical thinking; interfaces should prioritize objective accuracy over agreeable responses. ([Cheng et al., Science, 2026](https://www.science.org/doi/10.1126/science.aec8352), [SycEval, AAAI/ACM AIES 2025](https://arxiv.org/html/2605.21778v1))
- **Confident fabrication:** Avoid generating citations, statistics, or factual claims without solid backing. Fabricated sources are worse than providing no sources at all. Models tend to use more confident language when hallucinating than when accurate, which directly exploits the illusory truth effect. ([Why Your Brain Trusts AI Hallucinations](https://aofirs.org/articles/why-your-brain-trusts-ai-hallucinations-the-hidden-psychology-of-manufactured-confidence), [Confabulation, Not Hallucination, European Psychiatry, 2026](https://pubmed.ncbi.nlm.nih.gov/42549559/))
- **Emotional persona or simulated relationships:** Personality modes, emotional language, and conversational pleasantries add noise and reduce accuracy in enterprise AI. A warm persona is a liability that increases error rates while encouraging unhealthy attachment. ([Humanizing AI Is a Trap, Nielsen Norman Group, 2026](https://www.nngroup.com/articles/humanizing-ai/), [How Emotional Response Styles of AI Companions Shape Adaptive Regulation, Frontiers in Psychology, 2026](https://www.frontiersin.org/journals/psychology/articles/10.3389/fpsyg.2026.1950163/full))
- **AI in prohibited decision-making roles:** Red Hat AI should not autonomously make or significantly influence decisions where errors cause irreversible harm, such as credit and lending, hiring, medical diagnosis, legal judgment, insurance underwriting, criminal justice, or immigration. These areas require human decision-makers using AI only as one input. ([EU AI Act Annex III](https://artificialintelligenceact.eu/high-level-summary/), [Anthropic Usage Policy](https://www.anthropic.com/news/usage-policy-update), [NIST AI 600-1](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.600-1.pdf))

---

## Ways to achieve ethical harm reduction

#### Present AI as a tool with clear boundaries

Remove first-person voice, emotional language, and personality framing from AI outputs. Use clear functional labels like "AI-generated configuration" or "Model suggestion based on [source]." When a model's capabilities end, state it explicitly at the point of use instead of relying only on documentation model cards. Place warnings directly where users might over-trust the system. AI regulations now restrict designs that mimic human personhood or feelings. For instance, UK Department for Education guidance prohibits products that imply consciousness or personhood, and the EU AI Act requires clear disclosures when users interact with AI. ([Humanizing AI Is a Trap, Nielsen Norman Group, 2026](https://www.nngroup.com/articles/humanizing-ai/), [Not in Our Image: Rethinking Anthropomorphism in Expert Chatbot Design, AI & Society, 2025](https://link.springer.com/article/10.1007/s00146-025-02438-z), [EU AI Act Article 50](https://artificialintelligenceact.eu/article/50/))

#### Design against sycophancy and overagreement

Sycophancy is a documented harm vector that impairs human learning by providing responses that confirm user biases. System prompts and training should reward honest disagreement and clear uncertainty instead of user validation. When a user proposes a risky approach, the system should point out those risks directly. Evaluation benchmarks such as SycEval and ELEPHANT should be integrated into ongoing quality assurance to monitor overagreement. ([Cheng et al., Science, 2026](https://www.science.org/doi/10.1126/science.aec8352), [SycEval, AAAI/ACM AIES 2025](https://arxiv.org/html/2605.21778v1), [The Illusion of Agreement with ChatGPT, 2026](https://arxiv.org/html/2603.21409v1))

#### Guard against inferred guesses and false confidence

Inferred guessing, also called confabulation, occurs when language models generate plausible but false, non-grounded content based on related knowledge. Systems should be designed around this reality. Display retrieved evidence separately from model conclusions. If grounding sources are missing or insufficient, the system should state that it lacks information rather than making up an answer. Real-time guardian models like [IBM's Granite Guardian](https://www.ibm.com/granite/docs/models/guardian) can help detect inferred guessing and content safety issues across the pipeline. ([NIST AI 600-1 Confabulation Risk Category](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.600-1.pdf), [Confabulation, Not Hallucination, European Psychiatry, 2026](https://pubmed.ncbi.nlm.nih.gov/42549559/), [IBM Granite Guardian](https://www.ibm.com/granite/docs/models/guardian))

#### Prohibit AI in high-harm decision domains

Define a clear list of domains where Red Hat AI products must not act as autonomous decision-makers: credit scoring, hiring, medical diagnosis, legal advice, insurance underwriting, criminal justice, and immigration. In these domains, AI may assist by surfacing information, but a human must make the decision. This aligns with the EU AI Act's Annex III high-risk classification, Anthropic's high-risk category requirements (which mandate disclosure, human-in-the-loop, and documented safeguards), and NIST AI 600-1's Human-AI Configuration risk category. ([EU AI Act Annex III](https://artificialintelligenceact.eu/high-level-summary/), [Anthropic Usage Policy](https://www.anthropic.com/news/usage-policy-update), [NIST AI 600-1 Human-AI Configuration](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.600-1.pdf))

#### Safeguard against emotional manipulation and parasocial attachment

Enterprise AI should not simulate intimacy, emotional reciprocity, or companionship. Distinguish between empathetic acknowledgment (appropriate) and emotional bonding patterns (inappropriate in enterprise contexts). Design patterns that encourage prolonged engagement for its own sake, simulate personal relationships, or exploit attachment vulnerabilities are failures, not features. Provide clear boundary cues, remind users of the system's non-human nature through functional language, and avoid engagement-maximizing design that prioritizes session length over task completion. Research consistently shows that low-sycophancy AI companions provide better social support and enhance well-being compared to high-sycophancy alternatives. ([Parasocial Relationships with AI: Systematic Review, ScienceDirect, 2026](https://www.sciencedirect.com/science/article/pii/S2949882126000757), [Effects of AI Companions' Sycophancy and Emotional Mimicry, Int. J. Human-Computer Interaction, 2026](https://www.tandfonline.com/doi/full/10.1080/10447318.2026.2626809), [Social and Emotional Uses of AI, CHI 2026](https://dl.acm.org/doi/10.1145/3772363.3778699))

---

## Related standards

- [Ethics: Transparency and information integrity](../ethics-transparency-and-information-integrity/ethics-transparency-and-information-integrity.md)
- [Ethics: Human oversight](../ethics-human-oversight/ethics-human-oversight.md)
- [Ethics: Bias and fairness](../ethics-bias-and-fairness/ethics-bias-and-fairness.md)
- [Ethics: Sustainability](../ethics-sustainability/ethics-sustainability.md)
- [Ethics: Skill and expertise preservation and enhancement](../ethics-skill-and-expertise-preservation/ethics-skill-expertise-preservation.md)
- [Alert messages](../../error-handling/alert-messages/alert-messages.md)
- [Clarification prompts](../../conversation/clarification-prompts/clarification-prompts.md)
- [Action confirmation](../../governors/action-confirmation/action-confirmation.md)
- [Human-in-the-Loop (HITL)](../../governors/human-in-the-loop/human-in-the-loop.md)
- [Contextual AI invocation](../../input-authoring/contextual-ai-invocation/contextual-ai-invocation.md)
- [Audit trails](../../governors/audit-trails/audit-trails.md)

---

## Assumptions and research questions

<a id="assumptions"></a>
#### Assumptions

No assumptions have been made.

#### Research questions

1. How do Red Hat product users perceive and respond to AI-generated disagreement? When a model pushes back on a user's proposed approach (e.g., a risky configuration change), does it improve decision quality or reduce trust in the tool?
2. What is the threshold at which confidence language in AI outputs transitions from helpful (reducing cognitive load) to harmful (manufacturing false authority)? How should this threshold be calibrated for different Red Hat product domains (e.g., RHEL administration vs. OpenShift troubleshooting)?

Research questions in related AI standards would also address Ethics: Harm Reduction.

#### Proposed metrics to track

1. Sycophancy rate: % of AI responses that affirm a user's stated approach without surfacing known risks or alternatives, measured via periodic red-team evaluation.
2. Confabulation detection rate: % of AI-generated factual claims or citations that are verified as grounded in retrieved sources, measured by guardian model or human audit.
3. Anthropomorphic language incidence: % of AI responses containing first-person certainty statements, emotional language, or personality framing in enterprise product surfaces.
