# Common Pull Request Rejection Reasons

This document lists common reasons a pull request may be rejected or sent back for revision in the Reliability IQ project.

The intent is not punitive. These guidelines exist to:

- Maintain project quality
- Keep reviews efficient
- Avoid repeated back-and-forth on preventable issues

Reviewing this list before opening a PR will significantly improve approval speed.

---

## PR Targets the Wrong Branch

- PR opened against `main` instead of `develop`
- Direct commits pushed to `main`

**Action:**  
All contributor PRs must target `develop`. Only the PM merges into `main`.

---

## Scope Is Too Large or Unfocused

- Multiple unrelated changes in a single PR
- Feature work mixed with refactoring, formatting, or documentation cleanup

**Action:**  
Split work into smaller, logically scoped PRs.

---

## Missing or Unclear Description

- PR description does not explain what changed
- No explanation of why the change was made
- Reviewer must infer intent from the diff

**Action:**  
Update the PR description to clearly state:

- What changed
- Why it changed
- Any assumptions or limitations

---

## Raw or Generated Data Included

- Raw datasets committed to the repository
- Generated artifacts or outputs committed unintentionally

**Action:**  
Remove data files and ensure `.gitignore` rules are respected.

---

## Inconsistent Project Structure

- Files placed outside the documented directory structure
- New directories added without documentation

**Action:**  
Follow the architecture and directory guides. If structure needs to change, document it first.

---

## Debug or Temporary Code Left In

- Debug prints or logging left enabled
- Commented-out blocks committed
- Temporary test code included

**Action:**  
Clean up before submitting the PR.

---

## Naming or Style Issues

- Ambiguous variable, function, or file names
- Inconsistent naming conventions
- Non-descriptive branch or commit names

**Action:**  
Rename for clarity. Optimize for the next person reading the code.

---

## Breaking Existing Functionality

- Changes break previously working behavior
- No acknowledgment of known breakage

**Action:**  
Fix the issue or clearly document known limitations in the PR description.

---

## Undocumented Assumptions or Logic

- New logic introduced without explanation
- Implicit assumptions not stated anywhere

**Action:**  
Document assumptions in code comments or relevant documentation.

---

## PR Is Marked “Ready” Too Early

- Work-in-progress submitted as ready for review
- Reviewer asked to comment on incomplete work

**Action:**  
Use draft PRs for early feedback. Mark as ready only when complete.

---

## Summary

Most PR rejections are not about correctness. They are about clarity, scope, and maintainability.

Addressing the items above before submitting a PR helps:

- Speed up reviews
- Reduce rework
- Keep the project cohesive

When in doubt, ask before opening the PR.
