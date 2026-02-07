# Pull Request Titles & Commit Message Conventions

This document defines how pull requests and commits should be titled in Reliability IQ.

The goal is not perfection. The goal is:

- Faster reviews
- Clear history
- Fewer clarification questions
- Less time spent guessing what changed and why

These conventions are intentionally simple and opinionated.

---

## Pull Request Title Convention

Pull request titles should describe what changed, not how much work it took.

_**Format**_

`<type>: <short, clear description>`

---

### Allowed Types

Use one of the following prefixes:

- feat — New functionality or capability
- fix — Bug fixes or corrections
- docs — Documentation-only changes
- refactor — Code changes that do not alter behavior
- data — Data ingestion, validation, or transformation work
- model — Modeling or evaluation changes
- infra — Infrastructure, config, or environment changes
- chore — Cleanup, formatting, or maintenance work

---

### Examples of Good PR Titles

- feat: add baseline transaction outcome classifier
- data: add initial ingestion pipeline for Zenodo dataset
- docs: document data source provenance and access rules
- refactor: separate ranking logic from classification pipeline
- infra: add docker configuration for local development

---

### Examples of Bad PR Titles

- Updates
- Final version
- Fix stuff
- WIP
- Trying something
- Changes requested

If a reviewer cannot understand what the PR does from the title alone, the title needs improvement.

---

## Commit Message Convention

Commits should be:

- Small
- Focused
- Understandable without opening the diff

_**Format**_

`<type>: <present-tense description>`

Use the same type prefixes as pull requests.

---

### Examples of Good Commit Messages

- data: validate required fields in raw transaction data
- model: add retry-aware features to classifier
- docs: clarify PR workflow and branch rules
- fix: handle missing timestamps during ingestion
- refactor: extract prioritization logic into service layer

---

### Examples of Bad Commit Messages

- updates
- fix
- changes
- asdf
- working now
- trying to fix bug

These make history useless and slow down reviews.

---

## Commit Size Guidelines

- A commit should do one logical thing
- Avoid mixing unrelated changes in the same commit
- If you need “and also” in your commit message, it is probably too big

Rule of thumb:
If you cannot explain the commit in one sentence, split it.

---

## Squashing & History

- Do not worry about making your branch history perfect
- The PM may squash commits during merge if appropriate
- Focus on clarity during development; cleanliness happens at integration

---

## Summary

- PR titles describe what changed
- Commits describe one logical step
- Use consistent prefixes
- Present tense, plain language
- Optimize for the person reviewing your work, not for cleverness
