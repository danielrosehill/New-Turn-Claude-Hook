[![Part of the Claude Code Repos Index](https://img.shields.io/badge/Claude%20Code%20Repos-Index-blue?style=flat-square&logo=github)](https://github.com/danielrosehill/Claude-Code-Repos-Index)

# New-Turn-Claude-Hook

A concept for a Claude Code hook that intelligently detects when a user should start a new conversation rather than continuing the current one.

## The Problem

When working with AI agents like Claude Code, context management is crucial. Users often find themselves in situations where the prior conversation context is no longer helpful for their next request. Continuing in the same conversation adds "bloat" to the context window, potentially degrading performance and relevance.

Currently, users must manually recognize when to start fresh - a skill developed through extensive use of these tools.

## The Idea

Create a lightweight hook that automatically determines whether a new user message should:

1. **Continue** in the existing conversation (prior context is helpful)
2. **Start fresh** as a new conversation (prior context is not relevant)

### Implementation Concepts

- **Lightweight Agent**: A small, efficient model that makes a single binary decision
- **Front-end Logic Gate**: Intercepts user input before it's sent to the main agent
- **User-in-the-Loop Option**: Could prompt user with "I advise starting this as a new task. Continue?" rather than being fully automatic
- **Mode Settings**: Different levels of automation (fully automatic, recommendation-based, disabled)

### Technical Considerations

- Must be incredibly fast to avoid slowing down the chat interface
- Needs to evaluate both the conversation history and the incoming message
- Could leverage a small instruction-tuned model for the binary decision
- Returns simple binary response to the orchestration framework

## Status

This is currently a planning/idea stage project. Next steps:

1. Research if similar solutions already exist in the AI tooling ecosystem
2. Explore Claude Code hooks API to determine feasibility
3. Prototype with a lightweight model

## Philosophy

> "Don't start from scratch what doesn't need to be started from scratch. If you have an idea and someone's hopefully done it better, use their software."

## Files

- [transcript-raw.md](transcript-raw.md) - Verbatim transcript of the original idea capture
- [transcript-edited.md](transcript-edited.md) - Lightly edited transcript for readability

---

For more Claude Code projects, visit [my Claude Code Repos Index](https://github.com/danielrosehill/Claude-Code-Repos-Index).
