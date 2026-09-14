# EEC Specification

## Overview

EEC defines a convention for exporting the useful state of an AI conversation into a structured handoff that another AI can consume.

The specification intentionally separates **conversation-derived context** from **file-derived context**.

## Commands

### EEC

`EEC` requests a conversation-context export.

The implementation should analyze the relevant conversation and produce a standalone handoff.

### EECwF

`EECwF` requests a conversation-context export with available file/attachment inspection.

The implementation should include relevant file-derived facts and identify files that the receiving AI must receive separately.

## Required information

A conforming export should preserve, when applicable:

1. Project/topic
2. Current state
3. Main objective
4. Requirements
5. Constraints
6. Completed work
7. Important decisions
8. Approaches already tried
9. Problems/blockers
10. Current implementation/configuration
11. Files/attachments
12. Pending work
13. Continuation instructions
14. Recommended next step

## State precedence

When the conversation contains conflicting states:

1. Prefer the latest explicit user-confirmed state.
2. Prefer confirmed tool/file results over speculation.
3. Mark unresolved contradictions rather than silently guessing.

## File semantics

A summary of a file is not equivalent to the file itself.

If the receiving AI needs the actual artifact, the export must say so explicitly.

Example:

> **ATTACH THIS FILE TO THE NEXT AI:** `dataset.csv`

For `EECwF`, file-derived facts may be included, but the original artifact should still be transferred when exact contents matter.

## Information density

EEC should maximize useful context per token.

Include details that change what the next AI should do.

Exclude:

- greetings
- repeated explanations
- conversational filler
- irrelevant tangents
- duplicated history

## Non-goals

EEC does not attempt to:

- reproduce an entire chat transcript
- guarantee that two AI systems interpret context identically
- replace source files
- invent missing project state
- preserve every piece of conversational history
