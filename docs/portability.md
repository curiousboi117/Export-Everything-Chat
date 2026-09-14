# Portability

EEC is designed to work across AI systems.

## Core idea

The specification is provider-independent:

```text
Conversation
    ↓
EEC / EECwF
    ↓
Structured Context Export
    ↓
Receiving AI
```

The receiving platform may implement the behavior through:

- a Skill
- custom instructions
- a project rule
- a system prompt
- an agent framework
- an application integration

## Platform adaptation

A platform-specific adapter should preserve:

- the `EEC` trigger
- the `EECwF` trigger
- the standard output sections
- file-handling semantics
- accuracy rules
- continuation-first behavior

Only the implementation mechanism should change.

## Important distinction

EEC transfers **context**.

It does not automatically transfer:

- private account access
- connected applications
- credentials
- hidden system instructions
- unavailable files
- inaccessible conversation history

If a receiving AI needs an actual file, attach the original file.

## Recommended portable prompt

A minimal implementation can load `SKILL.md` as its instruction source and define:

> When the user invokes `EEC`, perform the EEC workflow.
> When the user invokes `EECwF`, perform the EEC workflow and inspect available attachments.

For platforms with their own Skill/Rule format, `SKILL.md` can be adapted without changing the underlying specification.
