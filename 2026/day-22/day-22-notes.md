### Task 1 :

- git -v
- git config --global user.name "<username>"
- git config --global user.email "<email>"

- git config user.name
- git config user.email

- git config --global --list  (to list name and email)

### Task 2 :
- git init 
- git status
#### Inside the .git directory, the following key components are stored:

- Objects Folder: The core database storing all project data as compressed snapshots. It contains Blob objects (file contents), Tree objects (directory structures and file names), and Commit objects (snapshots with metadata like author, timestamp, and parent links). 
- Refs Folder: Acts as a catalog of bookmarks, storing pointers to specific commits. It includes refs/heads for local branches, refs/tags for immutable tags, and refs/remotes for tracking remote repository states. 
- HEAD File: A simple text file pointing to the currently checked-out branch or commit, allowing Git to know which state is active. 
- Index File: The staging area, a binary file that records exactly which changes from the working directory are queued up for the next commit. 
- Config File: Stores repository-specific settings, such as remote URLs, default branches, and merge behaviors. 
- Hooks Folder: Contains scripts (e.g., pre-commit, post-merge) that run automatically at specific points in the Git workflow for automation or validation. 
- Logs Folder: Holds the reflog, a safety net that records every time the HEAD or branches have been updated, allowing recovery of "lost" commits. 

### Task 3 :

## Git Commands Reference

### Setup & Config
- `git --version` checks whether Git is installed.
- `git config --global user.name "Your Name"` sets your Git username.
- `git config --global user.email "you@example.com"` sets your Git email.
- `git config --global --list` shows the current global Git settings.

### Basic Workflow
- `git init` creates a new Git repository.
- `git status` shows which files are modified, staged, or untracked.
- `git add <file>` stages a file for the next commit.
- `git commit -m "message"` saves the staged changes permanently in Git history.

### Viewing Changes
- `git diff` shows changes that are not yet staged.
- `git diff --staged` shows changes that are staged but not committed.
- `git log` shows the commit history.
- `git log --oneline` displays a compact commit history.

## Answers to the Git Workflow Questions

1. `git add` prepares changes for the next commit, while `git commit` saves those staged changes into the repository history.
2. The staging area is a temporary holding area that lets you choose exactly which changes should be included in the next commit. Git uses it so you can review and group related changes before saving them.
3. `git log` shows the commit history, including commit IDs, authors, dates, and commit messages.
4. The `.git/` folder is the internal Git metadata directory. It stores the repository data, history, config, and staging information. If you delete it, the repository is no longer a Git repository and its history is lost.
5. The working directory is where you edit files, the staging area holds selected changes before a commit, and the repository stores the committed history.


### Task 4: Stage and Commit
1. git add <file_name> or git add .
2. git diff --staged
3. git commit -m "your meaningful message"
4. git log 

### Task 5: Make More Changes and Build History

- git log --oneline
- git diff HEAD (difference btween last commit and both staging and unstaged changes )
- git diff (check only unstaged changes)
- git diff --staged (git diff --cached both do the same thing)

### Task 6 : Understand the Git Workflow
1. `git add` stages changes for the next commit, and `git commit` records those staged changes as a saved snapshot in Git history.
2. We stage first so we can review and select exactly which changes should be included in the next commit. This makes commits cleaner and avoids saving unwanted edits.
3. `git log` shows the commit history with commit IDs, author/date metadata, and commit messages.
4. The `.git/` folder stores all Git metadata and history. If it is deleted, the repository loses its commit history and stops being a Git repo.
5. - working directory: the current files you are editing.
   - staging area: the place where selected changes are prepared for the next commit.
   - repository: the stored commit history and metadata inside `.git/`.
   



