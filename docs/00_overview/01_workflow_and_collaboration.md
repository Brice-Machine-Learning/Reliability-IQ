# Development Workflow & Collaboration Model

This document defines how work is organized, how branches are used, and how changes are integrated into the main codebase for Reliability IQ.

The goal is to:

- Keep `main` stable and reviewable
- Make collaboration predictable
- Avoid merge conflicts and broken history
- Ensure everyone understands pull requests before contributing

This is a team project, but integration is centralized.

---

## Branching Model

### Main Branch (`main`)

- `main` is the integration and release branch
- It should always remain in a clean, working state
- No one merges directly into `main`

>- **Only the Project Manager (PM) merges pull requests into `main`**

---

### Integration Branch (`develop`)

- `develop` is the active integration branch
- All contributor pull requests target `develop`
- Work is reviewed and stabilized here before promotion to `main`

---

### Work Branches (Feature / Task Branches)

All contributors work in their own branches, created from `develop`.

Examples:

- `feature/data-ingestion`
- `feature/eda-initial`
- `feature/model-baseline`
- `feature/dashboard-prototype`
- `docs/data-sources-update`

>**Note:** These are just examples, see `docs/00_overview/02_collaborator_responsibilities.md` for the full list of branches and responsibilities.

Rules:

- One branch per logical task
- Keep changes focused and reviewable
- Regularly sync your branch with `develop`

---

## What Is a Pull Request (PR)?

A pull request (PR) is how changes are reviewed and merged into shared branches.

A PR:

- Shows exactly what changed
- Allows review and discussion
- Creates a permanent record of decisions
- Prevents unreviewed code from entering shared branches

Project rules:

- Contributors open PRs from their branch into `develop`
- The PM reviews and merges into `develop`
- Only the PM opens PRs from `develop` into `main`

---

## Standard Pull Request Workflow

### 1. Create a Work Branch

From `develop`:

git switch develop  
git pull origin develop  
git switch -c feature/your-branch-name  

---

### 2. Do Your Work

- Make small, logical commits
- Write clear, descriptive commit messages
- Commit regularly. Do not bundle all work for a day into a single commit.
- Do not mix unrelated changes within the same branch.

---

### 3. Push Your Branch

`git push origin feature/your-branch-name`  

---

### 4. Open a Pull Request

On GitHub:

- Base branch: `develop`
- Compare branch: your feature branch
- Ensure the arrow points **into** `develop`

Include the following in the PR description:

- What changed
- Why it changed
- Any assumptions or open questions

Maintaining a project diary is strongly encouraged to document decisions and progress.

- Keep your project diary under  
  `docs/11_project_diary/<your-branch-name>/<YYYYMMDD>_daily-diary.md`

Do **not** open pull requests directly to `main`.

---

### 5. Review & Merge

- The PM reviews the pull request.
- Changes may be requested via comments in the PR. Check the status of your PR regularly and address feedback until it is approved.
- Once approved, the PR is merged into `develop`.
- Promotion to `main` happens separately and is handled by the PM.

---

## Authentication: HTTPS vs SSH

### HTTPS Authentication

If you use HTTPS for Git operations, GitHub requires a Personal Access Token (PAT).

- Fine-grained tokens often fail authentication for Git operations
- GitHub may reject authentication even if the token appears valid
- This is a known limitation, not user error

If using HTTPS:

- Use a classic Personal Access Token
- Ensure `repo` scope is enabled

---

### SSH Authentication (Recommended)

SSH avoids token issues entirely and is the preferred method.

Benefits:

- No tokens required
- More reliable authentication
- Fewer permission-related failures

---

## Setting Up SSH (Linux)

### 1. Check for Existing SSH Keys

`ls ~/.ssh`

---

### 2. Generate a New SSH Key

`ssh-keygen -t ed25519 -C "your_email@example.com"`

Accept the default location and set a passphrase if desired.

---

### 3. Start the SSH Agent

`eval "$(ssh-agent -s)"`

---

### 4. Add the SSH Key

`ssh-add ~/.ssh/id_ed25519`

---

### 5. Add the Public Key to GitHub

`cat ~/.ssh/id_ed25519.pub`

Then add the key in GitHub under:
Settings → SSH and GPG keys

---

### 6. Test the Connection

`ssh -T git@github.com`

You should receive a success message.

---

### 7. Use SSH URLs

Use the SSH URL when cloning repositories:

`git clone git@github.com:ORG_NAME/REPO_NAME.git`

When copying the repository URL from GitHub, select the **SSH** option in the web interface.

---

## Summary

- Everyone works in feature branches
- All contributor PRs target `develop`
- Only the PM merges into `main`
- Pull requests are required for shared changes
- SSH is strongly recommended
- HTTPS requires a classic token and is more fragile

If anything is unclear, ask before pushing changes.
