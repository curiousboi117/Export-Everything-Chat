# Basic EEC Example

## Input conversation

```text
User:
I'm building a command-line weather app.

We decided to use Python and the standard library for the CLI.
The API request layer is complete.
JSON parsing is complete.
The current bug is that the application crashes when the API returns
an empty `results` array.

We already rejected rewriting the project in Node.js.

The next step is to fix the empty-results handling and add tests.

EEC
```

## Example EEC output

```text
# PROJECT CONTEXT EXPORT

## 1. Project / Topic

**Name:** Command-line weather app
**Type:** Python CLI
**Purpose:** Retrieve and display weather information from an API.

## 2. Current State

The API request layer and JSON parsing are complete.
The application currently crashes when the API returns an empty
`results` array.

## 3. Main Objective

Finish the CLI weather app with reliable handling of valid and empty API responses.

## 4. Requirements

### Technical
- Python
- Standard-library CLI approach
- Existing API request layer should be preserved

### Constraints
- Do not rewrite the project in Node.js.

## 5. Completed Work

- API request layer implemented.
- JSON parsing implemented.

## 6. Important Decisions

- Keep Python as the implementation language.
- Use the standard library for the CLI.
- Do not migrate to Node.js.

## 7. Approaches Already Tried

- Node.js rewrite was considered and rejected.

## 8. Problems / Bugs / Blockers

- Empty `results` array causes a crash.
- Root cause has not yet been established.

## 9. Current Implementation / Configuration

The existing request and JSON parsing layers are working for normal responses.

## 10. Files / Attachments

No files are required by this example.

## 11. Pending Work

### Immediate
1. Fix empty-results handling.

### Remaining
2. Add regression tests for empty API responses.

## 13. Instructions for the Next AI

Continue from the existing Python implementation.
Do not rewrite the project in Node.js.
Do not redo the completed API request or JSON parsing work.
First investigate the empty-results crash, then add tests.

## 14. Recommended Immediate Next Step

Inspect the code path that accesses `results` and add explicit handling for an empty array.
```
