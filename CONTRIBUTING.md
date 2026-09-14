# Contributing to EEC

Thanks for your interest in improving EEC.

EEC is intentionally simple: the goal is to make AI context transfer reliable, portable, and easy to understand.

## Before contributing

Please read:

- `README.md`
- `SKILL.md`
- `docs/specification.md`
- `docs/portability.md`

## Good contributions

Useful contributions include:

- clearer export structures
- better file-handling rules
- portability improvements
- examples from real workflows
- ambiguity/edge-case handling
- validation and test cases
- documentation improvements
- integrations with AI platforms or developer tools

## Design principles

Contributions should preserve:

1. AI-agnostic behavior
2. explicit current state
3. accurate file handling
4. no invented information
5. minimal unnecessary verbosity
6. easy continuation by another AI

## Pull requests

Please explain:

- what changed
- why it changed
- which behavior is affected
- whether examples/specification need updates

Keep unrelated changes out of the same pull request where possible.

## Reporting issues

When reporting a problem, include:

- the input command (`EEC` or `EECwF`)
- a sanitized example of the conversation context
- expected output
- actual output
- relevant files, if applicable

Do not include secrets, credentials, API keys, personal data, or private project information.
