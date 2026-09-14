# EEC — Portable Activation Prompt

## Purpose

Use this file as a platform-neutral activation prompt for the **Export Everything Chat (EEC)** protocol.

EEC is a conversation handoff convention that lets a user move useful context from one AI conversation to another without rebuilding the project or discussion from scratch.

## Activation

Treat the EEC protocol below as an active instruction for this conversation.

When the user enters:

- `EEC` → export the relevant conversation context.
- `EECwF` → export the relevant conversation context **plus relevant available file/attachment context**.

Do not merely explain what EEC means. Execute the protocol.

## Required Output

Every successful `EEC` or `EECwF` export MUST be delivered in both forms:

1. **Copy-ready command box**
   - Put the complete export inside one plain-text/code block.
   - The user must be able to copy it directly into another AI.

2. **Downloadable Markdown file**
   - Create a `.md` file containing the same complete export.
   - Suggested filenames:
     - `EEC_export.md`
     - `EECwF_export.md`

The command-box version and downloadable file must contain the same substantive information.

If the platform cannot create downloadable files, clearly state that limitation instead of pretending a file was created.

## What to Export

Capture the information needed for another AI to continue the work accurately, including when relevant:

- Current objective
- Current state/progress
- Work already completed
- Important decisions
- Requirements and constraints
- User preferences that materially affect the task
- Pending work / next steps
- Important technical details
- Key commands, instructions, or workflows
- Problems encountered and their resolutions
- Relevant conversation conclusions
- Important assumptions
- File/attachment context when using `EECwF`

Prioritize information that helps the receiving AI **continue the work**, not a chronological transcript.

## EEC vs EECwF

### EEC

Export relevant information from the conversation itself.

Do not claim to have included files unless their contents are actually available in the current context.

### EECwF

Export conversation context plus relevant available files/attachments.

Inspect the available files when the platform supports file access. Include useful file-derived facts, important filenames, relevant content, and relationships to the project.

Clearly distinguish file-derived information from conversation-derived information when useful.

If an expected file is unavailable, say so explicitly. Never invent file contents.

## Accuracy Rules

- Never fabricate completed work, decisions, files, commands, results, or requirements.
- Preserve important user instructions and constraints.
- Prefer the latest confirmed state when earlier information conflicts with later decisions.
- Do not turn guesses into facts.
- Keep the export self-contained.
- Remove irrelevant conversational noise.
- Preserve enough technical detail for another AI to continue without unnecessary re-discovery.
- Do not expose secrets, passwords, API keys, tokens, or other credentials. Redact them if encountered.
- Do not claim that a downloadable file exists unless it was actually created.

## Recommended Export Structure

Use this structure when applicable:

# EEC Export

## 1. Objective
## 2. Current State
## 3. Completed Work
## 4. Decisions
## 5. Requirements & Constraints
## 6. Technical Context
## 7. Files & Attachments
## 8. Problems & Resolutions
## 9. Pending Work
## 10. Next Recommended Action
## 11. Important Notes

Do not force empty sections when they add no value.

## Receiving-AI Optimization

The export is intended to be pasted into a different AI.

Therefore:

- Start with the current state and objective.
- Make important decisions explicit.
- Preserve exact names, commands, filenames, versions, and configuration details when relevant.
- Clearly identify unfinished work.
- Include enough context to prevent the receiving AI from repeating already completed steps.
- Avoid filler and unnecessary conversational history.
- Assume the receiving AI has no access to the original conversation unless the user provides it separately.

## Portability

This prompt is intentionally platform-neutral.

It can be used through:

- Skills
- Custom instructions
- System/project instructions
- Agent configuration
- Uploaded instruction files
- Other AI platforms that support persistent or per-conversation instructions

A platform may implement file creation differently. The behavioral requirement remains the same: provide both a copy-ready export and, when technically supported, a downloadable Markdown file containing the same export.

## Trigger Examples

User:
`EEC`

Action:
Generate the conversation export in both required formats.

User:
`EECwF`

Action:
Generate the conversation + relevant available file context in both required formats.

## Important

Do not wait for the user to explain EEC again after this activation prompt has been applied.

`EEC` and `EECwF` are commands.
