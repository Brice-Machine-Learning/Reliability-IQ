# Python Version & Environment Standardization

## Purpose

To ensure reproducibility and avoid environment-related issues, Reliability IQ standardizes on a single Python version across all contributors.

The project does not standardize on a specific Conda installer (Miniconda, Miniforge, Anaconda), but it does standardize the Python interpreter and core dependencies via a shared Conda environment.

---

## Python Version Policy

- Python 3.11 is required
- All contributors must use Python 3.11 within the project Conda environment
- Python version differences are a common source of subtle bugs and inconsistent behavior in ML workflows

The Python version is enforced by the Conda environment and should not be overridden locally.

---

## Conda Distribution Policy

Contributors may use any Conda-compatible distribution, including:

- Miniconda (recommended)
- Miniforge / Mambaforge
- Anaconda

The specific Conda installer version is not enforced.

What matters is the environment behavior, not the installer.

---

## Environment Creation (Python 3.11 via conda-forge)

The project environment must be created using the conda-forge channel.

### Create the environment

Use the following command to create a new environment with the latest available Python 3.11 patch release from conda-forge:

conda create -n reliability-iq -c conda-forge python=3.11

This command:

- Pulls Python 3.11 from conda-forge
- Installs the most recent compatible 3.11.x version
- Creates an isolated environment named `reliability-iq`

---

### Activate the environment

conda activate reliability-iq

---

## Source of Truth

Once created, the authoritative environment definition will live in:

- environment.yml

Contributors must not modify Python versions locally outside of this file.
Any required changes should be discussed before updating the environment definition.

---

## Summary

- Python version is standardized: 3.11
- Conda installer choice is flexible
- conda-forge is the required channel
- Environment consistency matters more than individual setup preferences

This policy exists to reduce friction, not to police tooling choices.
