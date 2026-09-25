---
title: "Ethics: Skill and expertise preservation and enhancement"
description: "Help people develop and sharpen professional capabilities through AI-assisted work rather than outsourcing the skills their job depends on"
category: "Foundations"
status: "Recommended"
date: 2026-09-25
last_updated: 2026-09-25
contributors:
  - "Mary Shakshober-Crossman"
  - "Jason Brock"
  - "Applied AI UX"
---

# Ethics: Skill and expertise preservation and enhancement

## Overview

Skill and expertise preservation and enhancement is the growth side of ethical AI. People develop, practice, and sharpen their professional capabilities through AI-assisted work rather than outsourcing them, instead of merely completing a task faster.

---

## Purpose and value

- **Critical thinking atrophies without use:** In a study of 319 knowledge workers, participants with higher trust in generative AI were observed to engage in less critical thinking (such as idea generation, topic learning, and decision-making) when using the technology. In this cohort, cognitive offloading correlated strongly with AI tool usage (r = +0.72) and inversely with critical thinking behaviors (r = -0.75). ([Microsoft Research & Carnegie Mellon, 2025](https://phys.org/news/2025-01-ai-linked-eroding-critical-skills.html), [AI-Overdependence and Human Cognitive Decline, ScienceDirect, 2026](https://www.sciencedirect.com/science/article/pii/S2451958826001764))
- **Novices are most vulnerable:** Specific domain studies suggest that passive reliance on AI can impair unaided performance. For example, software engineers using passive AI assistance performed 17% worse on conceptual understanding, code reading, and debugging in test settings without notable efficiency gains. Similarly, in a medical study following the introduction of AI-assisted colonoscopy, endoscopists' unaided adenoma-detection rate dropped from 28.4% to 22.4%. These findings indicate that skills most at risk are often those critical when AI tools are unavailable or inaccurate. ([Shen & Tamkin, 2026](https://arxiv.org/html/2606.06253), [Budzyń et al., 2025](https://www.sciencedirect.com/science/article/pii/S1389041726000665))
- **Slop creates more work than it saves:** "Workslop"—AI-generated output that appears polished but lacks substantive value—can create significant operational overhead. Some estimates project productivity losses up to $9 million annually for a 10,000-person organization, with individual instances taking nearly two hours to remediate. As uncorrected errors compound across teams, an organization's broader knowledge base risks degradation. ([BetterUp Labs & Stanford Social Media Lab, HBR, 2025](https://thenextweb.com/news/ai-workslop-knowledge-decay-harvard-business-review-productivity), [Holweg & Davenport, HBR, 2026](https://thenextweb.com/news/ai-workslop-knowledge-decay-harvard-business-review-productivity))
- **Organizations are losing the skills they need most:** BCG research finds that the skills leaders consider most critical to long-term performance (judgment, decision-making, problem framing, and creative thinking) are the very skills most at risk from AI deskilling. GenAI doesn't merely support human thinking; increasingly, it substitutes for it. ([BCG, "When Everyone Uses AI, Companies Risk Losing Critical Skills," 2026](https://www.bcg.com/publications/2026/when-everyone-uses-ai-companies-risk-critical-skills))
- **This topic has no industry standard (Red Hat can lead):** No direct counterpart exists in the five major external frameworks studied (LFAI RGAF, NIST 600-1, IBM Trustworthy AI, Microsoft RAI, Anthropic RSP). This represents a position Red Hat can own: an ethics stance that addresses the longitudinal risk of AI degrading human expertise, mentoring culture, and innovative capacity.

---

## Best practices

- **Scaffold before answering:** When a user's task has learning value, guide problem-solving rather than delivering a finished answer. Research shows that students who engaged with a task independently before consulting an LLM produced significantly stronger outputs. Design AI interactions that preserve productive cognitive friction, which is the effortful engagement with ambiguity that builds expertise. ([Scaffolding Critical Thinking with Generative AI, ScienceDirect, 2026](https://www.sciencedirect.com/science/article/pii/S2666920X26000342))
- **Distinguish augmentation from automation:** AI should make people better at their work, not invisible in it. When a task requires judgment, reasoning, or domain knowledge, present AI output as a starting point the user must evaluate and refine, not as a finished result to accept or reject. ([AI Can't Augment What It Erodes, Workshift, 2026](https://workshift.org/ai-cant-augment-what-it-erodes/), [AI Deskilling Is a Structural Problem, AI & Society, 2025](https://link.springer.com/article/10.1007/s00146-025-02686-z))
- **Encourage human collaboration over AI substitution:** When the task would benefit from peer input, mentoring, or collaborative reasoning, surface that path prominently. AI should not be the default replacement for human feedback, code review, or design critique.
- **Build periodic manual practice into workflows:** Incorporating routine manual practice alongside AI assistance helps mitigate complacency. In specific task trials, rotating weekly between AI-assisted and manual modes reduced complacency-related errors by up to 42% compared to continuous AI usage. Designing deliberate "manual flying" intervals encourages users to re-engage domain knowledge and maintain critical judgment. ([Journal of Applied Psychology, 2025](https://www.uxmatters.com/mt/archives/2026/06/designing-for-doubt-how-to-prevent-automation-complacency-in-ai-workflows.php), [Designing for Doubt, UXmatters, 2026](https://www.uxmatters.com/mt/archives/2026/06/designing-for-doubt-how-to-prevent-automation-complacency-in-ai-workflows.php))
- **Hold authors accountable for AI-generated output:** The person who submits AI-generated work is its author. Quality gates, review processes, and accountability structures should treat AI-assisted output the same as any other deliverable. The tool does not absorb responsibility for errors or lack of substance. ([An Endless Stream of AI Slop, arXiv, 2026](https://arxiv.org/html/2603.27249v1))
- **Use AI to actively develop capabilities:** AI can accelerate skill development through Socratic questioning, transparent step-by-step reasoning, worked examples, and personalized feedback. The goal is not to restrict AI but to ensure it serves as a cognitive partner that builds independence over time, not a crutch that erodes it. ([From Model to Mentor: Cognitive Apprenticeship in AI Agent Prompts](https://edtechbooks.org/promptbook/from-model-to-mentor), [Architecture of Cognitive Amplification, ScienceDirect, 2026](https://www.sciencedirect.com/science/article/pii/S1389041726000665))

---

## Things to avoid

- **Answer-first design when learning matters:** Delivering a finished answer when the user would benefit from working through the problem trains dependency, not competence. In education contexts, students who received immediate AI answers demonstrated weaker neural connectivity and reduced critical thinking compared to those who used less direct tools. ([MIT Electroencephalography Study, 2026](https://www.aitrove.ai/blog/ai-chatbots-critical-thinking-mit-study-2026), [Outsourcing Thinking to AI, Nature Humanities & Social Sciences Communications, 2026](https://www.nature.com/articles/s41599-026-07153-8))
- **Speed as the primary value proposition:** Centering AI marketing and design on how fast work gets done, rather than how well, normalizes the displacement of quality with volume. A 2025 MIT Media Lab report found that 95% of organizations saw no measurable return on their generative AI investments — speed without substance is not productivity. ([MIT Media Lab, 2025](https://thenextweb.com/news/ai-workslop-knowledge-decay-harvard-business-review-productivity))
- **Slop as an acceptable trade-off:** AI-generated content that creates a review burden for peers is not a productivity gain; it is a cost externalized onto the team. The curl project shut down its bug bounty program after AI-generated vulnerability reports consumed maintainer time without producing valid findings. Apache Log4j 2 and Godot reported similar drains from AI-generated contributions. When machines produce and humans triage, humans are demoted from authors to janitors of machine output. ([An Endless Stream of AI Slop, arXiv, 2026](https://arxiv.org/html/2603.27249v1), [AI Slop and Software Commons, 2026](https://www.emergentmind.com/papers/2604.16754))
- **AI as a substitute for mentoring:** AI cannot replace the rupture-and-repair dynamics that build professional judgment, the cultural knowledge transfer that happens in peer relationships, or the accountability structures of human mentorship. Products that position AI as a replacement for these relationships undermine the organizational capacity that makes expertise possible. ([Adults Lose Skills to AI.
- **Ignoring the complacency paradox:** More accurate AI systems create more dangerous complacency: the higher the AI's accuracy, the more rational it becomes for humans to accept outputs uncritically, and the more difficult it becomes to catch the remaining errors. Designing trustworthy AI without complacency mitigation achieves nominal compliance while failing to achieve genuine oversight. ([Designing for Doubt, UXmatters, 2026](https://www.uxmatters.com/mt/archives/2026/06/designing-for-doubt-how-to-prevent-automation-complacency-in-ai-workflows.php), [When Humans Stop Thinking, ScienceDirect, 2026](https://www.sciencedirect.com/org/science/article/pii/S1757581826000095))

---

## Ways to achieve ethical skill and expertise preservation and enhancement

#### Scaffold reasoning before providing answers

When a task has learning value (such as troubleshooting, configuration, architecture decisions, or root cause analysis), design the AI interaction to guide user reasoning rather than delivering a finished solution. Effective scaffolding preserves productive cognitive friction: ask the user to hypothesize before revealing, show graduated hints rather than complete answers, and surface relevant documentation the user can reason with. Research consistently shows that the sequence matters: users who attempt a problem independently before consulting AI produce stronger outcomes than those who lead with AI. The scaffold should fade over time, transferring responsibility back to the user as competence grows. ([Scaffolding Critical Thinking with Generative AI, ScienceDirect, 2026](https://www.sciencedirect.com/science/article/pii/S2666920X26000342), [Designing for Critical Thinking in AI-Enhanced Learning, Springer, 2026](https://link.springer.com/chapter/10.1007/978-3-032-30542-8_11), [Architecture of Cognitive Amplification, ScienceDirect, 2026](https://www.sciencedirect.com/science/article/pii/S1389041726000665))

#### Design quality gates that prevent slop

AI-generated output (including code, documentation, configurations, and reports) must pass through the same quality and review standards as any human-authored work. Make the person who submits the output its accountable author: they are responsible for its accuracy, completeness, and usefulness, regardless of how it was produced. Build review friction proportional to the blast radius: a generated YAML file that will be applied to a production cluster deserves more scrutiny than a draft email. Surface signals that help reviewers distinguish AI-generated material from human-authored work using the latest PatternFly standards for component behavior, and ensure review processes are designed to catch the characteristic failure modes of generated content where surface plausibility masks substantive errors. ([An Endless Stream of AI Slop, arXiv, 2026](https://arxiv.org/html/2603.27249v1), [AI Slop Is Flooding Academic Journals, Forbes, 2026](https://www.forbes.com/sites/johndrake/2026/04/30/ai-slop-is-flooding-academic-journals-a-top-journal-measured-it/), [HBR Knowledge Decay, 2026](https://thenextweb.com/news/ai-workslop-knowledge-decay-harvard-business-review-productivity))

#### Incorporate periodic manual practice intervals

Design periodic moments where users work without AI assistance — the cognitive equivalent of a pilot's mandatory manual-flying requirements. A study in the *Journal of Applied Psychology* found that rotating between AI-assisted and manual task modes on a weekly cadence reduced complacency-related errors by up to 42% in experimental task settings. These "manual flying" intervals force users to re-engage domain knowledge, recalibrate their baseline judgment, and maintain the skills they need when the AI is unavailable or wrong. This is not anti-AI — it is pro-competence. In product design, this could mean optional "challenge mode" features, periodic skill assessments, or workflows that require the user to demonstrate understanding before the AI proceeds. ([Journal of Applied Psychology, 2025](https://www.uxmatters.com/mt/archives/2026/06/designing-for-doubt-how-to-prevent-automation-complacency-in-ai-workflows.php), [BCG Critical Skills, 2026](https://www.bcg.com/publications/2026/when-everyone-uses-ai-companies-risk-critical-skills), [Preventing Skill Decay as AI Use Expands, Uptime Institute, 2026](https://journal.uptimeinstitute.com/preventing-skill-decay-as-ai-use-expands/))

#### Surface human collaboration paths alongside AI assistance

When a task would benefit from peer review, mentoring, or collaborative problem-solving, make that path as prominent and accessible as the AI path. AI should not be the default replacement for a colleague's expertise: a junior engineer learning to troubleshoot a cluster benefits more from a senior engineer's reasoning than from a model's answer, even if the model's answer is correct. Design patterns should suggest human escalation, either as a traditional UI flow or conversationally within the chatbot context, when the task involves high stakes, professional development, or organizational knowledge transfer. The goal is to use AI to enhance human collaboration, not replace it. ([The Human Touch in AI, Frontiers in Psychology, 2025](https://www.frontiersin.org/journals/psychology/articles/10.3389/fpsyg.2025.1568239/full), [APA: How AI Is Reshaping Human Skills and Thinking, 2026](https://www.apa.org/monitor/2026/07-08/ai-job-skills-thinking))

#### Use AI as a capability accelerator

The highest ethical value of AI is not task completion; it is skill development. Design AI interactions that teach while they assist: Socratic questioning that guides users to their own conclusions, worked examples that show reasoning processes rather than just answers, and personalized feedback that helps users recognize patterns in their own work. When a user asks "how do I configure X," the most ethical response may not be the configuration itself, but a guided walkthrough that leaves the user able to do it independently next time. This turns AI from a dependency into an investment in human capability. ([From Model to Mentor: Cognitive Apprenticeship in AI Agent Prompts](https://edtechbooks.org/promptbook/from-model-to-mentor), [Reframing Human-AI Collaboration in Higher Education, Springer, 2026](https://link.springer.com/article/10.1007/s12528-026-09501-8), [Developing Generative AI Literacies Through Self-Regulated Learning, ScienceDirect, 2025](https://www.sciencedirect.com/science/article/pii/S2666920X25001225))

#### Teach by example and transparent reasoning

To help users develop strong mental models, AI tools should show the step-by-step reasoning behind their answers and provide clear, worked examples. Explaining behind-the-scenes processes allows users to understand the logic behind solutions rather than just receiving an outcome. Over time, this transparency helps users learn the underlying patterns of complex tasks, equipping them to solve similar problems independently in the future.

---

## Exceptions and edge cases

| **Scenario / Edge Case** | **Design Guidance & Behavior** | **Fallback / Governance** |
| --- | --- | --- |
| **Time-critical operations** | Bypass cognitive friction and scaffolds during production emergencies or automated runbook execution where delays pose direct operational risk. | Require post-incident review and audit logging to verify bypass justification. |
| **Expert vs. novice users** | Implement adaptive scaffolding that automatically fades as user proficiency and domain tenure increase, avoiding unnecessary friction for seasoned staff. | Allow manual override of assistance levels in user profile preferences. |
| **User dismissal of scaffolds** | Allow users to explicitly skip guided reasoning steps and request direct answers when needed for task momentum. | Log scaffold bypasses to track reliance trends and evaluate safety margins. |
| **Absence of peer for mentoring** | When no live peer or mentor is available for escalation, switch to interactive documentation or asynchronous review queues. | Route non-blocking queries to internal community channels or ticketing systems. |
| **Full automation conditions** | Allow direct full automation for low-risk, repetitive boilerplate generation with minimal blast radius. | Maintain automated linting and policy checks on generated outputs. |

---

## Annotated product scenarios

#### Scenario 1: Scaffolded troubleshooting for a failing OpenShift cluster pod

When an administrator investigates a **CrashLoopBackOff** error in an OpenShift pod, the AI assistant presents diagnostic hints (such as examining container log tailing or checking resource limits) before suggesting a direct fix command. This preserves cognitive engagement while guiding root-cause analysis.

#### Scenario 2: Quality gate review for generated Kubernetes YAML configuration

When generating complex deployment configurations, the assistant labels AI-generated code blocks using standard pattern visual indicators. A mandatory quality gate highlights critical parameters (e.g., privilege escalation, storage mounts) for explicit author verification prior to applying changes to the cluster.

#### Scenario 3: Human-escalation path beside AI assistance for high-stakes compliance

During sensitive security standard compliance checks or firewall configuration updates, the AI prompt interface prominently features a "Request Senior Peer Review" action alongside automated suggestions, facilitating seamless human collaboration for high-stakes decisions.

---

## Related standards

- [Ethics: Harm reduction](../ethics-harm-reduction/ethics-hardm-reduction.md)
- [Ethics: Transparency and information integrity](../ethics-transparency-and-information-integrity/ethics-transparency-and-information-integrity.md)
- [Ethics: Human oversight](../ethics-human-oversight/ethics-human-oversight.md)
- [Ethics: Bias and fairness](../ethics-bias-and-fairness/ethics-bias-and-fairness.md)
- [Ethics: Sustainability](../ethics-sustainability/ethics-sustainability.md)
- [Clarification prompts](../../conversation/clarification-prompts/clarification-prompts.md)
- [Human-in-the-Loop (HITL)](../../governors/human-in-the-loop/human-in-the-loop.md)
- [Action confirmation](../../governors/action-confirmation/action-confirmation.md)
- [Audit trails](../../governors/audit-trails/audit-trails.md)
- [Contextual AI invocation](../../input-authoring/contextual-ai-invocation/contextual-ai-invocation.md)
- [Prompt suggestions](../../wayfinders/prompt-suggestions/prompt-suggestions.md)

---

## Assumptions and research questions

#### Assumptions

No assumptions made. All claims are supported by cited research.

#### Research questions

1. How do Red Hat product users currently split their work between AI-assisted and manual approaches? What factors drive the decision to use AI versus work independently, and do those factors align with the tasks where AI assistance actually preserves or develops skills?
2. What is the impact of AI-assisted troubleshooting on long-term skill development for RHEL and OpenShift administrators? Do users who rely heavily on AI assistance perform measurably worse when troubleshooting novel issues without AI support?
3. How do teams perceive and manage the quality burden of AI-generated contributions (code, documentation, configurations)? Is the review cost of AI-assisted output accounted for in productivity assessments?

Research questions in related AI standards would also address Ethics: Skill and Expertise Preservation and Enhancement.

#### Proposed metrics to track

1. Unaided task completion rate: % of users who can complete key domain tasks (troubleshooting, configuration, root cause analysis) without AI assistance, measured periodically.
2. AI-generated output revision rate: Percentage of AI-assisted deliverables that require substantive revision by reviewers before acceptance, as an indicator of slop burden.
3. Scaffolding engagement rate: % of AI interactions where users engage with guided reasoning paths (hints, documentation, Socratic prompts) versus requesting direct answers.
4. Human collaboration referral rate: Percentage of AI interactions that result in human escalation, peer review requests, or collaborative problem-solving, indicating a healthy handoff between AI and human expertise.
