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

### Examples of Good Commit Messages (One Line)

>- data: validate required fields in raw transaction data
>- model: add retry-aware features to classifier
>- docs: clarify PR workflow and branch rules
>- fix: handle missing timestamps during ingestion
>- refactor: extract prioritization logic into service layer

---

### Example of a Good Commit Message (With Details)

When a change benefits from additional context, use a commit body.

**Commit message:**

>data: validate required fields in raw transaction data

**Commit body:**

>- Added checks for missing and null values in required columns
>- Enforced basic type validation for identifiers and timestamps
>- Logged validation failures to support downstream debugging

Use a detailed commit body when:

- assumptions are introduced,
- behavior changes in non-obvious ways,
- or the reasoning behind the change matters later.

The first line should always stand on its own as a clear summary.

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

## End-to-End Example

Below is a complete example showing how a pull request and its commits should look together.

### Example: One-Sentence Summary (PR Title)

>`data: add initial ingestion pipeline for Zenodo dataset`

From the title alone, a reviewer should understand:

- the type of work (`data`)
- the scope (ingestion pipeline)
- the subject (Zenodo dataset)

---

### Example: Pull Request Description (With Detail)

**What changed**  
Added an initial data ingestion pipeline to load the raw Zenodo dataset into the project’s standardized format.

**Why it changed**  
The modeling and EDA notebooks require a consistent, validated input dataset. This pipeline establishes a repeatable starting point for downstream analysis.

**Assumptions / Open Questions**  

- Assumes the current Zenodo schema is stable  
- Additional validation rules may be needed once edge cases are identified during EDA

Related notebook owners should review for alignment with their planned work.

---

### Example: Commit History Within the PR

>`data: add raw data loader for Zenodo files`
>`data: validate required columns and types`
>`data: normalize timestamps and identifiers`
>`docs: document ingestion assumptions and limitations`

Each commit:

- does one logical thing,
- uses a clear prefix,
- can be understood without opening the diff.

This makes review faster and history more useful.

---

### Anti-Example (What Not to Do)

**PR title:**  
`Updates`

**Commits:**  
`fix`
`more fixes`
`final version`

## Summary

- PR titles describe what changed
- Commits describe one logical step
- Use consistent prefixes
- Present tense, plain language
- Optimize for the person reviewing your work, not for cleverness
