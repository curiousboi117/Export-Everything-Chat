# EEC — Export Everything Chat

## Purpose

EEC (Export Everything Chat) is a portable workflow for converting a conversation into a concise, self-contained, AI-ready context package.

Its purpose is to let a user move ongoing work from one AI conversation to another without manually reconstructing the project history.

EEC has two modes:

- `EEC` — export the relevant conversation context.
- `EECwF` — export the relevant conversation context and incorporate useful information from available files/attachments.

The output should be optimized for another AI to continue the work immediately, not written as a casual conversation recap.

## Required Output Formats

Every successful `EEC` or `EECwF` export must be provided in **two forms**:

1. **Command box** — Put the complete AI-ready export inside a single plain-text/code block so the user can copy it directly into another AI.
2. **Downloadable file** — Also create a downloadable Markdown file containing the same complete export.

The command-box version and downloadable file must contain the same substantive information. Do not provide only one of them.

Use a clear filename such as:

- `EEC_export.md`
- `EECwF_export.md`

If the platform supports file creation, generate the downloadable file automatically. If file generation is unavailable, clearly state that limitation rather than pretending a file was created.


## Trigger Rules

### `EEC`

When the user enters exactly `EEC`, treat it as:

> Export the entire relevant context of this conversation for use in another AI.

Analyze the conversation and produce a standalone handoff document.

Include all information that materially affects continuation, while removing conversational filler, repetition, jokes, greetings, and irrelevant discussion.

### `EECwF`

When the user enters exactly `EECwF`, treat it as:

> Export the entire relevant conversation context and incorporate information from the available attachments/files.

In addition to the normal EEC workflow:

1. Identify every relevant attachment/file.
2. Inspect available file contents when the environment permits it.
3. Extract information another AI needs to continue the work.
4. Distinguish facts found in files from facts established in the conversation.
5. Do not invent or infer file contents that were not actually available.
6. If a file is important but cannot be fully inspected, explicitly identify it as a required attachment.

## Core Workflow

### 1. Identify the subject

Determine what the conversation is actually about.

### 2. Establish the current state

Describe where the work stands **right now**.

Use states such as:

- Completed
- Working
- Partially working
- Broken
- Blocked
- Not yet implemented
- Awaiting user input

### 3. Recover important history

Extract only history that affects future work:

- approaches attempted
- decisions
- rejected approaches when relevant
- bugs and causes
- fixes attempted
- discoveries
- reasons behind significant decisions

Do not dump the conversation chronologically.

### 4. Preserve requirements

Capture:

- functional requirements
- technical requirements
- output requirements
- relevant preferences
- constraints
- things explicitly requested not to do
- compatibility requirements
- deadlines or milestones

### 5. Prevent duplicated work

Record completed work clearly.

> Do not redo completed work unless new evidence shows it needs to be changed.

### 6. Identify pending work

Separate:

- immediate next step
- remaining implementation
- unresolved bugs
- optional improvements

### 7. Give continuation instructions

Tell the receiving AI:

- what it inherited
- what it should do next
- what it should not redo
- what files it needs
- what assumptions it must not make

## Standard Output Format

# PROJECT CONTEXT EXPORT

## 1. Project / Topic

**Name:**  
**Type:**  
**Purpose:**  

## 2. Current State

Describe the exact current state.

## 3. Main Objective

State what the user ultimately wants.

## 4. Requirements

### Functional
- ...

### Technical
- ...

### Output / UX
- ...

### Constraints
- ...

## 5. Completed Work

- ...

## 6. Important Decisions

- **Decision:** ...
  - **Reason:** ...

## 7. Approaches Already Tried

- **Approach:** ...
  - **Result:** ...
  - **Important lesson:** ...

## 8. Problems / Bugs / Blockers

- **Problem:** ...
- **Cause:** ...
- **Current status:** ...
- **Attempted fix:** ...

## 9. Current Implementation / Configuration

Include relevant implementation details, versions, settings, commands, APIs, architecture decisions, or other technical context.

Do not create a full codebase structure unless necessary.

## 10. Files / Attachments

| File | Required? | Why it matters | What the next AI needs |
|---|---|---|---|
| `example.ext` | Yes/No | ... | ... |

If a required file is unavailable:

> **ATTACH THIS FILE TO THE NEXT AI:** `filename.ext`

## 11. Pending Work

### Immediate
1. ...

### Remaining
2. ...

### Optional
3. ...

## 12. Important Context

- ...

## 13. Instructions for the Next AI

Continue from the current state. Do not restart the project or repeat completed work. Use listed files as authoritative where applicable. If information is missing, identify exactly what is missing instead of inventing it.

## 14. Recommended Immediate Next Step

State the single most useful next action.

## File Handling Rules

### For `EEC`

Do not reproduce large file contents.

Instead:

- identify relevant files
- explain why they matter
- state whether they must be attached to the next AI

### For `EECwF`

Inspect available files and summarize relevant portions.

Include:

- filename
- type
- purpose
- important contents
- relevant configuration/data/code
- important findings
- relationship to conversation decisions
- caveats

Do not unnecessarily reproduce entire large files.

If exact code/data is essential and cannot be safely summarized, tell the user to attach the original file to the receiving AI.

## Accuracy Rules

1. Never invent missing information.
2. Never claim a file was inspected when it was not.
3. Never claim a task is complete without evidence.
4. Prefer the latest confirmed state.
5. Resolve contradictions using the most recent explicit decision.
6. Preserve exact technical names, filenames, commands, versions, identifiers, and error messages when they matter.
7. Do not silently change requirements.
8. Do not include irrelevant information.
9. Do not over-summarize away continuation-critical information.
10. Avoid repetitive history.

## Final Quality Check

Before returning an EEC/EECwF export, verify:

- Current state is clear.
- Main objective is clear.
- Completed work is separated from pending work.
- Important decisions are preserved.
- Known bugs/blockers are preserved.
- Requirements and constraints are preserved.
- Relevant files are identified.
- Missing required files are explicitly marked.
- EECwF includes relevant available file-derived context.
- No unavailable file contents were invented.
- The receiving AI can understand the project without reading the original conversation.
- The complete export is provided in both a copy-ready command box and a downloadable Markdown file.
- Both versions contain the same substantive information.
- The export does not contain unnecessary conversational noise.

## Portability

This specification is AI-agnostic and can be implemented through Skills, custom instructions, project rules, system prompts, agent frameworks, or application-level workflows.

The implementation mechanism may vary; the expected behavior should remain consistent.
