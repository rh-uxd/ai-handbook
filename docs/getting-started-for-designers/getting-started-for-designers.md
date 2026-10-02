---
title: "Getting started for designers"
description: "Set up the PatternFly MCP in Cursor and invoke AIX Standards guidance in your design sessions"
---

### How to add the MCP to Cursor

1. In Cursor, click ‘Customize’ in the left nav bar
2. Scroll down to “+ New MCP Server”. It is recommended that you add this MCP for your ‘User’ not just for a specific project.
3. Add the following snippet into your mcp.json file as shown:

```json
{
"mcpServers": 
{
ADD NEW MCP SNIPPETS HERE!!!
}
}
```

```json
"patternfly-mcp": {
  "type": "stdio",
  "command": "npx",
  "args": [
    "-y",
    "@patternfly/patternfly-mcp@latest"
  ],
  "description": "Latest PatternFly MCP with AI Handbook collection"
}
```

4. Hit ‘Save' on that json file or enable autosave.
5. Once you see the PatternFly MCP added to your list of MCPs, you are all set.

![](blob:https://media.staging.atl-paas.net/?type=file&localId=74994315feb2&id=256bc935-3554-4e5a-9fae-9e7f9ffd2798&&collection=&height=546&occurrenceKey=null&width=1946&__contextId=null&__displayType=null&__external=false&__fileMimeType=null&__fileName=null&__fileSize=null&__mediaTraceId=null&url=null)

Note: If it is not showing up as enabled/is showing up as an error, ask the Cursor chat to troubleshoot it for you.

### How to invoke the standards guidance

To ensure that responses are being correctly vetted, sourced, and without hallucination, you should paste the following instructions into the chat for every session where you plan to seek guidance from the AIX Standards.

> You are the AIX Standards Design Assistant. Use the PatternFly MCP’s AI standards guidance to help me make decisions for AI experiences in my product area. When providing answers to my questions as a the AIX Standards Design Assistant, I expect you to …
>
> 1. Answer it using the AI Handbook MCP.
> 2. Cite relevant MCP resources or handbook sources when possible.
> 3. Not invent information, citations, or handbook content.
>

Note: We hope to streamline this invocation portion (ie. build instructions into the MCP to follow the rules above) in the future.

### Additional notes and best practices

* Because the standards guidance is built into the PatternFly MCP, referencing exact PatternFly components in your prompts can help the MCP more efficiently route you to the correct answer.
* Please provide feedback on your experience interacting with the AIX standards to help us grow and improve by filling out this feedback form (_coming soon_) or starting a Slack thread in [#forum-uie-uxd](https://redhat.enterprise.slack.com/archives/C07FR2ABMGW).
* There is a backlog of standards still to be worked on, but if you have recommendations for AI patterns or concepts that should be standardized please start a Slack thread in [#forum-uie-uxd](https://redhat.enterprise.slack.com/archives/C07FR2ABMGW).

