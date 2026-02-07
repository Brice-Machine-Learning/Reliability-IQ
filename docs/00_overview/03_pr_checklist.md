# Pull Request Checklist

This checklist is intended to keep pull requests focused, reviewable, and easy to integrate.
All contributors should review this checklist before opening a PR.

---

## Pull Request Scope

- [ ] This PR addresses **one clearly defined task or feature**
- [ ] Unrelated changes have been excluded or moved to a separate PR
- [ ] Branch name reflects the work performed

---

## Code & Content Quality

- [ ] Code follows existing project conventions and structure
- [ ] New logic is placed in the appropriate module or directory
- [ ] Temporary code, debug prints, and commented-out blocks have been removed
- [ ] Variable, function, and file names are clear and intentional

---

## Data & Assumptions

- [ ] No raw data files are committed
- [ ] Data sources used are documented (if applicable)
- [ ] Assumptions or limitations introduced by this PR are clearly described

---

## Testing & Validation

- [ ] Changes were tested locally
- [ ] Existing functionality was not broken by these changes
- [ ] New logic behaves as expected for edge cases (where applicable)

---

## Documentation

- [ ] Relevant documentation has been updated (README, docs, comments)
- [ ] Architectural or design changes are reflected in the architecture docs
- [ ] Any follow-up work or known issues are noted in the PR description

---

## Pull Request Details

In your PR description, include:

- **What changed:** Brief summary of the work performed
- **Why it changed:** Motivation or problem being addressed
- **How to review:** Any specific areas reviewers should focus on

---

## Final Confirmation

- [ ] This PR targets the `develop` branch (not `main`)
- [ ] I am ready for review and understand that changes may be requested
- [ ] I have reviewed this checklist before submitting the PR

---

Thank you for helping keep the project clean, readable, and collaborative.
