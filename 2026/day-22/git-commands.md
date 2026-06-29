# Git Commands Reference

## Setup & Config

- `git --version` — Checks the installed Git version.
  - Example: `git --version`

- `git config --global user.name "Your Name"` — Sets your name for Git commits.
  - Example: `git config --global user.name "Jane Doe"`

- `git config --global user.email "you@example.com"` — Sets your email for Git commits.
  - Example: `git config --global user.email "jane@example.com"`

- `git config --global --list` — Displays your global Git configuration.
  - Example: `git config --global --list`

## Basic Workflow

- `git init` — Initializes a new Git repository in the current folder.
  - Example: `git init`

- `git status` — Shows the current state of tracked and untracked files.
  - Example: `git status`

- `git add <file>` — Stages a file for the next commit.
  - Example: `git add README.md`

- `git add .` — Stages all current changes in the repository.
  - Example: `git add .`

- `git commit -m "message"` — Saves the staged changes with a descriptive message.
  - Example: `git commit -m "Add Git notes"`

## Viewing Changes

- `git diff` — Shows changes in the working directory that are not staged yet.
  - Example: `git diff`

- `git diff --staged` — Shows changes that are staged but not committed.
  - Example: `git diff --staged`

- `git log` — Displays the commit history for the repository.
  - Example: `git log`

- `git log --oneline` — Shows a compact version of the commit history.
  - Example: `git log --oneline`

