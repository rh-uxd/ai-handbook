---
title: "Getting started for designers"
description: "Set up the PatternFly MCP in Cursor and invoke AIX Standards guidance in your design sessions"
---

### Prerequisites

1. Have an AI tool set up that can support MCPs set up on your system (ie. Cursor, Claude, Codex, etc.)
2. Make sure you have the PatternFly MCP enabled. [Click here for those intstructions.](https://github.com/patternfly/patternfly-mcp#set-a-basic-mcp-configuration)

PatternFly MCP enabled in Cursor MCP server list


### How to invoke the standards guidance

To ensure that responses are being correctly vetted, sourced, and without hallucination, we recommend pasting the following instructions into the chat **the first time** you want to get guidance from the AIX standards:

> You are the AIX Standards Design Assistant. Use the PatternFly MCP’s AI standards guidance to help me make decisions for AI experiences in my product area. When providing answers to my questions as a the AIX Standards Design Assistant, I expect you to …
>
> 1. Answer it using the `AI Handbook MCP`.
> 2. Cite relevant MCP resources or handbook sources when possible.
> 3. Not invent information, citations, or handbook content.

For **subsequent invocations** of the AIX Standards Design Assistant, you can reference the AI standards in your initial prompt for a given session or, to be extra clear, begin your session with a statement like …

> Please use the `ai-handbook` collection in the PatternFly MCP for this conversation

Note: We hope to streamline this invocation portion (ie. build instructions into the MCP to follow the rules above) in the future.

### Additional notes and best practices

* Because the standards guidance is built into the PatternFly MCP, referencing exact PatternFly components in your prompts can help the MCP more efficiently route you to the correct answer.
* Please provide feedback on your experience interacting with the AIX standards to help us grow and improve by filling out this feedback form (_coming soon_) or starting a Slack thread in [#forum-uie-uxd](https://redhat.enterprise.slack.com/archives/C07FR2ABMGW).
* There is a backlog of standards still to be worked on, but if you have recommendations for AI patterns or concepts that should be standardized please start a Slack thread in [#forum-uie-uxd](https://redhat.enterprise.slack.com/archives/C07FR2ABMGW).

