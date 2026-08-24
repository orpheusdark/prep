# GIT & GITHUB COMPLETE PREPARATION
## Tech Passport Phase 1 + Phase 2

---

# PART 1 — CORE CONCEPTS

## Three Areas You Must Know

```
Working Directory   →   Staging Area (Index)   →   Repository (.git)
   (your files)         (git add)                 (git commit)
```

1. **Working Directory:** Where you edit files on your computer.
2. **Staging Area (Index):** Files you've marked to include in next commit.
3. **Repository (.git):** Where committed snapshots are stored.

## Key Terms

| Term | Definition |
|------|-----------|
| Repository (repo) | A project tracked by Git |
| Commit | A snapshot of staged changes |
| Branch | An independent line of development |
| Remote | A repository hosted elsewhere (GitHub) |
| Origin | Default name for the main remote |
| HEAD | Pointer to current commit/branch |
| Clone | Copy a remote repo locally |
| Fork | GitHub copy of someone else's repo to your account |
| Pull Request (PR) | Request to merge your changes into a repo |

---

# PART 2 — ESSENTIAL COMMANDS

## Setup (First Time)

```bash
git config --global user.name "Your Name"
git config --global user.email "email@example.com"
```

## Starting a Repository

```bash
git init                   # Create new local repo in current folder
git clone <url>            # Copy a remote repo to your computer
git clone https://github.com/user/repo.git
```

## Core Workflow (MUST MEMORIZE)

```bash
git status                 # See what's changed, what's staged
git add filename.txt       # Stage specific file
git add .                  # Stage ALL changed files
git commit -m "message"    # Commit staged files with message
git push                   # Push commits to remote (origin)
git push origin main       # Push main branch to origin
git pull                   # Pull + merge remote changes
git pull origin main       # Pull main branch from origin
```

## Viewing History

```bash
git log                    # Full commit history
git log --oneline          # Compact version (one line per commit)
git log -5                 # Last 5 commits only
git diff                   # Differences not yet staged
git diff --staged          # Differences staged but not committed
```

## Branches — HIGH PRIORITY

```bash
git branch                 # List all local branches
git branch -a              # List all branches (local + remote)
git branch feature         # Create new branch called 'feature'
git switch feature         # Switch to 'feature' branch
git checkout feature       # Old way to switch (still works)
git checkout -b feature    # Create AND switch to 'feature'
git switch -c feature      # Create AND switch (modern way)
git merge feature          # Merge 'feature' into current branch
git branch -d feature      # Delete branch (safe, only if merged)
git branch -D feature      # Force delete branch
```

## Remote Operations

```bash
git remote -v              # Show remote connections
git remote add origin <url>  # Connect local repo to remote
git fetch                  # Download changes but DON'T merge
git pull                   # fetch + merge (combines both)
git push -u origin main    # Push + set tracking (-u = upstream)
```

## Undoing Changes

```bash
git restore filename.txt   # Discard working dir changes (unstage/revert file)
git reset HEAD filename.txt # Unstage a file (keep changes)
git revert <commit-hash>   # Create new commit that undoes a commit (safe)
git reset --hard HEAD      # Discard ALL uncommitted changes (DANGER!)
```

---

# PART 3 — GIT WORKFLOW (Complete Picture)

```
Start project:
  git init  OR  git clone <url>

Daily work:
  1. git status              (check what changed)
  2. git add .               (stage all changes)
  3. git commit -m "msg"     (save snapshot)
  4. git push                (send to GitHub)

When collaborating:
  1. git pull                (get latest from team)
  2. Make changes
  3. git add + commit + push

Working on feature:
  1. git branch feature-x   (create branch)
  2. git switch feature-x   (go to branch)
  3. Make changes + commit
  4. git switch main        (go back to main)
  5. git merge feature-x    (merge feature)
  6. git push               (push to GitHub)
```

---

# PART 4 — git fetch vs git pull

| Feature | git fetch | git pull |
|---------|-----------|----------|
| Downloads from remote | YES | YES |
| Merges automatically | NO | YES |
| Updates local branch | NO | YES |
| Safe to run | YES (no changes to working dir) | YES (but merges) |
| When to use | See what others did without changing your code | Get and apply latest changes |

> EXAM TIP: `git pull = git fetch + git merge`

---

# PART 5 — MERGE CONFLICTS

**When do they happen?**
When two people edit the same lines of the same file in different branches.

**What it looks like:**
```
<<<<<<< HEAD
This is your version
=======
This is their version
>>>>>>> feature-branch
```

**How to resolve:**
1. Open the conflicted file
2. Decide which version to keep (or combine them)
3. Delete the conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`)
4. `git add .` → `git commit -m "Resolved conflict"`

---

# PART 6 — .gitignore

```
# .gitignore file — files/folders Git will ignore
node_modules/     # don't track dependencies
.env              # don't track secrets
*.log             # don't track log files
dist/             # don't track build output
.DS_Store         # macOS system files
```

---

# PART 7 — GITHUB PAGES

GitHub Pages lets you host a static website directly from a GitHub repo for free.

**Steps:**
1. Push your HTML/CSS/JS project to a GitHub repo
2. Go to repo Settings → Pages
3. Source: Deploy from branch → main → / (root)
4. Your site is at: `https://username.github.io/repo-name`

> EXAM TIP: GitHub Pages only works for static sites (HTML/CSS/JS). No server-side code.

---

# PART 8 — README.md

- README.md is the first thing people see on GitHub
- Written in Markdown
- Should describe: what the project does, how to use it, dependencies

```markdown
# Project Name

Brief description of what the project does.

## Installation
git clone https://github.com/user/repo.git
cd repo
npm install

## Usage
npm start

## Technologies
- HTML, CSS, JavaScript

## License
MIT
```

---

# PART 9 — 25 GIT COMMAND MCQs

**G1:** Which command initializes a new Git repository?
A) git start   B) git init   C) git create   D) git new
**Answer: B**

**G2:** Which command shows the current state of working directory and staging area?
A) git info   B) git show   C) git status   D) git check
**Answer: C**

**G3:** To stage ALL changed files:
A) git stage all   B) git add *   C) git add .   D) git commit all
**Answer: C**

**G4:** Which command creates a copy of a remote repository locally?
A) git fork   B) git copy   C) git clone   D) git download
**Answer: C**

**G5:** After `git add`, what is the next step?
A) git push   B) git commit   C) git merge   D) git pull
**Answer: B**

**G6:** Which command sends local commits to remote?
A) git upload   B) git send   C) git pull   D) git push
**Answer: D**

**G7:** `git pull` is equivalent to:
A) git push + git merge   B) git fetch + git merge   C) git clone + git add   D) git status + git commit
**Answer: B**

**G8:** How do you create a new branch called "develop"?
A) git new develop   B) git branch develop   C) git checkout develop   D) git switch develop
**Answer: B (creates it). C and D switch to existing.**

**G9:** To create AND switch to a new branch in one command:
A) git branch -c feature   B) git switch feature   C) git checkout -b feature   D) git create feature
**Answer: C (or `git switch -c feature`)**

**G10:** Which command merges branch "feature" into current branch?
A) git branch feature   B) git pull feature   C) git merge feature   D) git checkout feature
**Answer: C**

**G11:** What is the default name for the main remote?
A) master   B) main   C) origin   D) remote
**Answer: C**

**G12:** `git log --oneline` shows:
A) Full commit details   B) Short hash + commit message   C) Only file names   D) Only author names
**Answer: B**

**G13:** Which command shows differences between working dir and staged area?
A) git status   B) git diff   C) git log   D) git show
**Answer: B**

**G14:** To unstage a file (keep changes, just unstage):
A) git reset HEAD filename   B) git remove filename   C) git delete filename   D) git restore filename
**Answer: A**

**G15:** .gitignore is used to:
A) Delete files   B) Ignore tracked files   C) Tell Git to not track certain files   D) Remove commits
**Answer: C**

**G16:** What does `HEAD` refer to in Git?
A) The main branch   B) The first commit   C) The current commit/branch position   D) The remote
**Answer: C**

**G17:** A fork in GitHub means:
A) Splitting a branch   B) Copying a repo to your account   C) Merging two branches   D) Deleting a branch
**Answer: B**

**G18:** What is a pull request?
A) Pulling from remote   B) Requesting to merge your changes into someone's repo   C) Creating a new branch   D) Cloning a repo
**Answer: B**

**G19:** Which command downloads remote changes WITHOUT merging?
A) git pull   B) git download   C) git fetch   D) git clone
**Answer: C**

**G20:** GitHub Pages is used for:
A) Server-side applications   B) Hosting static websites for free   C) Code reviews   D) Issue tracking
**Answer: B**

**G21:** What happens if you commit without first using `git add`?
A) All files are committed   B) Nothing is committed   C) Error   D) Only new files are committed
**Answer: B — nothing staged = nothing committed**

**G22:** To view all branches (local + remote):
A) git branch   B) git branch -r   C) git branch -a   D) git remote
**Answer: C**

**G23:** Safe way to undo a past commit (without losing history):
A) git reset --hard   B) git revert   C) git delete   D) git undo
**Answer: B**

**G24:** First time pushing to GitHub with tracking:
A) git push origin main   B) git push -u origin main   C) git push all   D) git upload origin main
**Answer: B (-u sets tracking)**

**G25:** What does `git remote add origin <url>` do?
A) Creates a remote repo   B) Connects local repo to remote URL   C) Clones a repo   D) Pushes to remote
**Answer: B**

---

# PART 10 — GIT SCENARIO QUESTIONS

**S1:** You made changes to 3 files and want to only commit one specific file. What do you do?
**Answer:** `git add specificfile.txt` then `git commit -m "message"`

**S2:** You just committed with wrong message. How to fix the most recent commit message?
**Answer:** `git commit --amend -m "correct message"`

**S3:** You want to see all commits that changed file "app.java":
**Answer:** `git log -- app.java`

**S4:** You're working on feature-branch. You need to get latest changes from main without switching branches:
**Answer:** `git fetch origin` and then `git rebase origin/main` OR switch to main, pull, switch back, merge main

**S5:** Your team says there's a merge conflict after your pull. You open the file and see:
```
<<<<<<< HEAD
Your code
=======
Their code
>>>>>>> main
```
What do you do?
**Answer:** Manually edit the file to keep the correct version, delete conflict markers, then `git add .` and `git commit`

---

# PART 11 — GIT CHEAT SHEET

```
SETUP:
git config --global user.name "Name"
git config --global user.email "email"

START:
git init                    Start new repo
git clone <url>             Clone existing repo

SNAPSHOT:
git status                  Check state
git add .                   Stage all
git add <file>              Stage specific file
git commit -m "msg"         Commit
git push                    Push to remote
git pull                    Pull from remote

BRANCHES:
git branch                  List branches
git branch <name>           Create branch
git switch <name>           Switch branch
git checkout -b <name>      Create + switch
git merge <branch>          Merge into current
git branch -d <name>        Delete branch

REMOTE:
git remote -v               Show remotes
git fetch                   Download (no merge)
git push -u origin main     First push with tracking

UNDO:
git restore <file>          Discard working changes
git reset HEAD <file>       Unstage file
git revert <hash>           Safe undo commit
```
