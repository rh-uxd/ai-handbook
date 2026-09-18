---
title: "Generation & Output"
description: "Standards for displaying, streaming, and presenting AI-generated content"
reviewstatus: "To Do"
date: 2026-03-12
---

## Overview

Generation & Output standards address how AI-created content is displayed, structured, and made available to users. Unlike traditional UI where content is static and known in advance, AI output is dynamic, non-deterministic, and arrives progressively. These standards ensure users can perceive, understand, and act on AI-generated content regardless of how it's delivered.

Modern AI systems stream output token-by-token or in chunks, requiring real-time UI updates that maintain readability and performance. Generated content may be lengthy, requiring progressive disclosure and skimming aids. Users need to save, share, edit, and export AI results in various formats. And all of this must work accessibly for screen readers, keyboard users, and users with cognitive needs.

These standards solve the unique challenges of AI output: managing streaming performance, providing structure to unstructured content, enabling user agency over generated results, and maintaining transparency about AI authorship and confidence.

---
## Key Principles
1. **Progressive revelation** - Stream content as it arrives, don't wait for completion
2. **Readable at every stage** - Output should be legible during generation and after
3. **User control** - Users can pause, stop, regenerate, edit, copy, and export
4. **Structured presentation** - Add structure to help users scan, skim, and navigate
5. **Transparent attribution** - Make clear what's AI-generated vs. human-authored
6. **Accessible updates** - Screen readers announce new content appropriately
---
## When to use these standards
- **Streaming AI content** - Text, code, or structured data arriving progressively
- **Completed AI results** - Displaying finished AI output with structure and controls
- **Long-form content** - AI-generated essays, reports, documentation, code files
- **Multi-part responses** - AI results with sections, lists, tables, code blocks
- **Actionable output** - Content users need to copy, edit, export, or share
- **Comparative results** - Multiple AI generations users need to evaluate
---
## Related Categories
- **Conversation**: Chat interfaces generate output in message format
- **Trust builders**: Citations and confidence indicators affect output display
- **Error handling**: Failed or incomplete generation requires error states
- **Accessibility**: All output must be perceivable via assistive technologies
- **Identifiers and branding**: AI attribution needs to be clear in output presentation
- **Input and authoring**: User edits to AI output transition to authoring standards
