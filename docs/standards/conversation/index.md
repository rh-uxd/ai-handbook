---
title: "Conversation"
description: "Standards for multi-turn dialogue and conversational AI interactions"
reviewstatus: "To Do"
date: 2026-03-12
---

## Overview

Conversation standards address the unique challenges of multi-turn dialogue with AI systems. Unlike single-shot interactions, conversations maintain context, build on previous exchanges, and allow for clarification, refinement, and exploration. These standards help users understand how to engage in productive dialogues with AI while managing expectations about the AI's conversational capabilities.

Good conversation design balances natural language flexibility with structured guidance. It helps users understand when they're in a conversation, how to navigate dialogue history, and how to recover when conversations go off track.

---
## Key Principles
1. **Maintain context** - Keep track of conversation history and reference it appropriately
2. **Enable refinement** - Allow users to clarify, correct, and build on previous turns
3. **Show conversation state** - Make it clear where users are in the dialogue
4. **Support branching** - Allow users to explore different conversational paths
5. **Graceful degradation** - Handle context limits and memory constraints transparently
6. **Clear turn-taking** - Make it obvious when the AI is thinking, responding, or waiting
---
## When to use these standards
- **Multi-turn interactions** where context builds over time
- **Exploratory tasks** that benefit from iterative refinement
- **Complex problem-solving** requiring back-and-forth dialogue
- **Tutoring or coaching** scenarios with guided conversations
- **Customer service** interactions requiring context awareness
- **Collaborative creation** where ideas develop through dialogue
---
## Related Categories
- **Input and authoring**: Each conversation turn involves crafting new inputs
- **Generation and output**: Conversation responses use generation standards
- **Error handling**: Conversations need recovery standards for misunderstandings
- **Trust builders**: Transparent conversation management builds confidence
- **Wayfinders**: Help users navigate long or complex conversations
- **Tuners and controls**: Mode selector enables switching between different conversation paradigms
