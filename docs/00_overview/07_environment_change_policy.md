# Environment Change Policy

This document defines how changes to the project environment are proposed, reviewed, and applied for the Reliability IQ project.

The goal is to keep all contributors working in a consistent environment without introducing unnecessary gatekeeping or micromanagement.

---

## Guiding Principle

The project environment, defined by `environment.yml`, is treated as a shared contract.

Everyone is expected to use the same environment.
No one is expected to manage it alone.

Consistency matters more than convenience.

---

## Source of Truth

- `environment.yml` is the authoritative definition of the project environment
- All contributors must create and update their local environments from this file
- Local-only package installations are not acceptable if code depends on them

If it is required to run the project, it must appear in `environment.yml`.

---

## Who Can Change the Environment

- Any contributor may propose changes to the environment
- Environment changes must be made through a pull request
- Environment changes follow the same review process as any other contribution

The Project Manager (PM) reviews and merges environment changes as part of normal integration duties.

This is not a special permission process. It is standard review.

---

## When an Environment Change Is Required

You must update `environment.yml` if:

- You introduce a new dependency
- You use the conda-forge as a default channel when adding new dependencies
- You rely on functionality from a package not currently listed
- You need a newer version of an existing dependency
- You add tooling required to run notebooks, scripts, or services

Do not rely on packages that are “already installed” on your machine.

---

## Pull Request Requirements for Environment Changes

Any pull request that modifies `environment.yml` must include:

- What dependency was added, removed, or updated
- Why the change is necessary
- Where the dependency is used in the project

This explanation can be brief. Clarity matters more than length.

---

## What Is Not Allowed

The following practices are explicitly discouraged:

- Installing packages locally without updating `environment.yml`
- Using `pip install` inside the Conda environment without discussion
- Silent upgrades to Python or core libraries
- Committing code that depends on undeclared dependencies

These practices lead to environment drift and broken reproducibility.

---

## Handling Conflicts or Issues

If an environment change causes conflicts or breaks existing workflows:

- Stop and communicate the issue
- Do not attempt workarounds that diverge from the shared environment
- Propose fixes or alternatives through a pull request

Environment problems are project problems, not individual problems.

---

## Summary

- The environment is a shared contract
- Anyone may propose environment changes
- All changes go through pull requests
- `environment.yml` is the source of truth
- Silent or local-only changes are not acceptable

These rules exist to keep the project stable, reproducible, and collaborative.
