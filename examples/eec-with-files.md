# EECwF Example

## Input conversation

```text
User:
I'm building a resume parser.

The parser currently extracts text from normal PDFs.
The scoring logic is complete.
The problem is that scanned PDFs return almost no text.

I attached:
- `resume_parser.py`
- `sample_scanned_resume.pdf`

We decided to add OCR as a fallback instead of replacing the existing
text extraction path.

EECwF
```

## Example EECwF output

```text
# PROJECT CONTEXT EXPORT

## 1. Project / Topic

**Name:** Resume parser
**Type:** Document-processing project
**Purpose:** Extract and process resume content.

## 2. Current State

Normal text-based PDFs are handled successfully.
Scanned PDFs produce little or no extracted text.
Scoring logic is already complete.

## 3. Main Objective

Add OCR fallback for scanned PDFs while preserving the existing
text-PDF extraction path.

## 4. Requirements

- Preserve existing normal-PDF extraction.
- Add OCR only when normal extraction is insufficient.
- Preserve the completed scoring logic.

## 5. Completed Work

- Normal PDF text extraction.
- Scoring logic.

## 6. Important Decisions

- Use OCR as a fallback.
- Do not replace the existing extraction path.

## 8. Problems / Bugs / Blockers

- Scanned PDFs contain image-based pages, so the existing text
  extraction path produces little or no useful text.

## 10. Files / Attachments

| File | Required? | Why it matters | What the next AI needs |
|---|---|---|---|
| `resume_parser.py` | Yes | Current parser implementation | Attach the original file so implementation can be modified accurately. |
| `sample_scanned_resume.pdf` | Yes | Reproduction input | Attach the original file to reproduce and test the OCR fallback. |

## 15. File-Derived Context

### `resume_parser.py`

**Purpose:** Current parser implementation.

**Relevant contents:** The receiving AI should inspect the current extraction
pipeline before implementing the OCR fallback.

**Relationship to current work:** This is the implementation that must be
modified.

### `sample_scanned_resume.pdf`

**Purpose:** Reproduction/test input.

**Relevant contents:** A scanned/image-based resume that demonstrates the
text-extraction failure.

**Relationship to current work:** Use it to validate OCR fallback behavior.

## 13. Instructions for the Next AI

Continue from the current parser implementation.
Do not replace the existing normal-PDF extraction path.
Do not redo the completed scoring logic.
Inspect `resume_parser.py`, reproduce the failure with
`sample_scanned_resume.pdf`, and implement OCR as a fallback.

## 14. Recommended Immediate Next Step

Inspect the extraction pipeline and determine the threshold/condition
that should trigger OCR when normal text extraction returns insufficient text.
```

> Note: In a real `EECwF` run, file-derived claims should only be included after the implementation has actually inspected the files.
