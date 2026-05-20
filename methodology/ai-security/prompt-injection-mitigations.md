# Prompt Injection Mitigations

## Overview

Prompt injection attacks manipulate LLM behavior by introducing malicious or adversarial instructions through user-controlled input.

These attacks become more severe in systems with:
- tool usage
- agentic workflows
- RAG pipelines
- external API access
- memory persistence

---

# Common Attack Surfaces

- User prompts
- Retrieved documents
- Tool outputs
- Web content ingestion
- Multi-agent communication

---

# Architectural Mitigations

## Input Isolation

Separate:
- system instructions
- developer instructions
- user-controlled content

Avoid mixing trust boundaries.

---

## Context Segmentation

Prevent direct propagation of untrusted content into privileged prompts or tool execution chains.

---

## Tool Permission Restrictions

LLM agents should not receive unrestricted:
- filesystem access
- shell execution
- API privileges

Use scoped permissions.

---

## Output Validation

Validate:
- generated commands
- URLs
- API requests
- tool invocation arguments

before execution.

---

# Detection Strategies

- anomaly monitoring
- prompt logging
- suspicious token sequence detection
- tool misuse analysis

---

# Notes

Prompt injection is fundamentally a trust boundary failure problem rather than purely an LLM problem.
