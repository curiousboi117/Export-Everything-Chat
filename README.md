# EEC — Export Everything Chat

> **Your AI changed. Your context shouldn't.**

EEC (Export Everything Chat) is a portable, AI-agnostic workflow for transferring the useful context of an ongoing AI conversation to another AI without manually reconstructing the entire history.

## The problem

Long AI conversations accumulate valuable context:

- project state
- requirements
- decisions
- implementation details
- failed approaches
- bugs and blockers
- pending work
- files and datasets

Moving that work to another AI often means starting with a giant explanation from scratch.

EEC provides a simple convention for creating a structured handoff.

## Commands

### `EEC`

Export the relevant conversation context into an AI-ready handoff.

### `EECwF`

Export the relevant conversation context **plus relevant information from available files/attachments**.

If the receiving AI needs the original artifact, the original file should still be attached alongside the generated export.

## What EEC captures

- Current state
- Main objective
- Requirements
- Constraints
- Completed work
- Important decisions
- Approaches already tried
- Problems and blockers
- Current implementation/configuration
- Relevant files
- Pending work
- Instructions for the next AI
- Recommended immediate next step

## Example

```text
User: EEC
```

The AI should return a compact, standalone context package that another AI can understand without reading the original conversation.

For file-aware export:

```text
User: EECwF
```

The AI should inspect available attachments when possible and include relevant file-derived context.

## AI-agnostic

EEC is a specification, not a provider lock-in.

It can be adapted to:

- ChatGPT Skills
- Claude instructions/projects/skills
- Gemini custom instructions
- Cursor rules
- system prompts
- agent frameworks
- custom LLM applications

The core behavior should remain consistent regardless of platform.

## Repository structure

```text
export-everything-chat/
├── README.md
├── SKILL.md
├── LICENSE
├── CONTRIBUTING.md
├── CHANGELOG.md
├── docs/
│   ├── specification.md
│   ├── portability.md
│   └── examples.md
└── examples/
    ├── basic-eec.md
    └── eec-with-files.md
```

## Design principles

1. **Continuation over narration** — describe what the next AI needs, not the whole conversation.
2. **Current state first** — the latest confirmed state takes priority.
3. **No hallucinated context** — unavailable information must be marked as unavailable.
4. **Don't redo work** — completed work and rejected approaches should be preserved when relevant.
5. **Files are first-class context** — identify artifacts that must travel with the handoff.
6. **Portable by design** — avoid provider-specific assumptions.

## Status

**EEC v0.1.0 — Initial specification**

The project is intentionally small at this stage. The goal is to establish a useful convention before adding automation or provider-specific integrations.

## License

MIT. See [LICENSE](LICENSE).
