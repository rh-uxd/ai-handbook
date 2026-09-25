---
title: "Retry and recovery"
description: "Notify users when AI work will take five or more minutes, keep the task running in the background, and deliver clear completion (or failure) signals so they can leave and return with confidence"
category: "Generation & Output"
status: "Experimental"
date: 2026-08-04
last_updated: 2026-08-06
contributors:
  - "Lisa Lyman"
  - "Applied AI UX"
---

# Long-Running Operations

---

## Overview

Long-running operations guide users through AI work that takes five or more minutes — analyzing large log sets, compiling architecture, or other heavy jobs. They set expectations up front, keep processing in the background when possible, and notify users when the work finishes (or fails) so they do not have to watch a spinner.

---

## Purpose & Value

- **Preserve trust**: Honest duration and status messaging beats silent waits that feel broken — business-critical downtime even for half an hour can be costly (State of Gen AI Practitioner Needs JTBD)

---

## When to Use

- **Architecture or codebase compilation**: Generating or synthesizing large structural outputs that cannot stream usefully in under five minutes

---

## When NOT to Use

- **Interactive clarification loops**: If the AI still needs turn-by-turn answers, do not background the conversation mid-clarification
- **Tasks that fail silently if the session ends**: If work cannot survive navigation or logout, do not offer “email me when ready” or background processing

---

## Examples

Uses [**PatternFly Chatbot — deep thinking wait state**](https://www.patternfly.org/extensions/chatbot/messages#messages-with-deep-thinking) as a baseline. Additionally, chat assistant sets a 5+ minute expectation, invites the user to leave and keep working, shows expandable deep-thinking progress with completed and in-progress steps, and offers Cancel operation.

![PatternFly Chatbot long-running wait state with deep thinking progress and cancel](./assets/pf-ai-wait-state-mockup.png)

---

## Existing work

N/A

---

## Related / Dependent

- [Deep Thinking](https://www.patternfly.org/extensions/chatbot/messages#messages-with-deep-thinking) — PatternFly Chatbot deep thinking wait state
- Chain of Thought standard (link TBD)

---

