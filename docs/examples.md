# Examples

This document explains representative EEC workflows.

## Basic export

Conversation:

```text
User: I'm building an API client.

[Many messages containing implementation decisions, debugging,
requirements, and testing.]

User: EEC
```

Expected result:

- identify the API client
- state its current implementation status
- preserve requirements and decisions
- list completed debugging
- identify remaining work
- give the receiving AI a clear next step

The output should not be a chronological transcript.

## File-aware export

Conversation:

```text
User: I'm debugging this parser.
[parser.py attached]

User: EECwF
```

Expected result:

- summarize the conversation
- inspect `parser.py` if available
- identify relevant implementation details
- connect the file contents to the conversation
- tell the receiving AI whether `parser.py` must be attached

## Missing file

If the conversation references a file that is not available:

```text
## Files / Attachments

- `model.py` — Required — contains the current implementation.

ATTACH THIS FILE TO THE NEXT AI: `model.py`
```

The implementation must not pretend to know the contents of `model.py`.

## Good vs bad export

### Bad

> We talked about your project for a long time. You were trying different things and then we fixed some errors. Continue from there.

### Good

> The project currently has the parser implemented and unit tests passing for valid resumes. PDF extraction remains unreliable for scanned documents. OCR has not yet been implemented. The next AI should first inspect the extraction pipeline, then add OCR fallback without changing the existing text-PDF path.

The second version gives the receiving AI actionable state.
