# 📁 FOLDER 12 — GIT & GITHUB 🟡 MEDIUM PRIORITY

---

## 📋 KEY COMMANDS CHEAT SHEET

| Command | What it does |
|---------|-------------|
| `git init` | Initialize a new repo |
| `git clone <url>` | Copy a remote repo locally |
| `git add <file>` | Stage changes for commit |
| `git add .` | Stage all changes |
| `git commit -m "msg"` | Save snapshot with message |
| `git status` | Show staged/unstaged/untracked files |
| `git push origin main` | Push to remote |
| `git pull origin main` | Fetch + merge from remote |
| `git fetch` | Download remote changes (no merge) |
| `git log` | View commit history |
| `git diff` | View unstaged changes |

---

## ❓ QUESTIONS + SOLUTIONS

---

### Q1. Git vs GitHub ⭐

| Git | GitHub |
|-----|--------|
| Version control tool (local) | Cloud hosting for Git repos |
| Tracks file history | Enables collaboration, PRs, Issues |
| CLI-based | Web UI + API |
| Free, open-source | Owned by Microsoft |

**Repository:** A folder tracked by Git (local) or hosted on GitHub (remote).
**Commit:** A saved snapshot of changes at a point in time.
**Branch:** A parallel line of development.

---

### Q2. Git Branching ⭐

```bash
git branch                    # list branches
git branch feature-login      # create new branch
git checkout feature-login    # switch to branch
git checkout -b feature-login # create + switch (shortcut)
git switch feature-login      # modern way to switch
git merge feature-login       # merge into current branch
git branch -d feature-login   # delete branch
```

---

### Q3. What causes a Merge Conflict? How to resolve? ⭐

**Cause:** Two branches edited the **same lines** of the same file.

```
<<<<<<< HEAD           ← your current branch changes
My version of the code
=======
Their version of the code
>>>>>>> feature-login  ← incoming branch changes
```

**Resolve:**
1. Open the conflicted file
2. Decide which version to keep (or combine)
3. Remove the conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`)
4. `git add <file>` then `git commit`

---

### Q4. git fetch vs git pull ⭐

| Command | What it does |
|---------|-------------|
| `git fetch` | Downloads remote changes — does NOT merge |
| `git pull` | `git fetch` + `git merge` (or rebase) |

**Best practice:** Use `git fetch` first to inspect changes, then merge manually.

---

### Q5. git reset vs git revert ⭐

| Feature | git reset | git revert |
|---------|-----------|------------|
| What it does | Moves HEAD back (removes commits) | Creates a NEW commit that undoes changes |
| Rewrites history | YES (dangerous on shared branches) | NO (safe for shared branches) |
| Use when | Local changes only | Already pushed to remote |

```bash
git reset --soft HEAD~1   # undo last commit, keep changes staged
git reset --hard HEAD~1   # undo last commit, DELETE changes
git revert HEAD           # create new commit that undoes last commit
```

---

### Q6. What is git stash? ⭐

**Use case:** You're mid-work and need to switch branch, but don't want to commit.

```bash
git stash           # temporarily save changes
git stash pop       # restore stashed changes
git stash list      # see all stashes
```

---

### Q7. Recover Accidentally Deleted Commit ⭐

```bash
git reflog          # shows ALL HEAD movements including deleted commits
git checkout <commit-hash>  # restore to that commit
# Or:
git cherry-pick <commit-hash>  # apply a specific commit
```

**git reflog:** Safety net — records every change to HEAD for 90 days.

---

### Q8. What is a Pull Request (PR)? ⭐

- A request to merge your branch into another branch (usually `main`)
- Enables **code review** before merging
- Team members can comment, approve, request changes

**Good PR habits:**
- Small, focused changes
- Descriptive title and description
- Reference related issues

---

### Q9. What makes a Good Commit? Bad Commit? ⭐

| Good Commit | Bad Commit |
|------------|-----------|
| Single, focused change | Multiple unrelated changes |
| Descriptive message: "Fix null pointer in login" | Vague: "fix", "update", "wip" |
| Present tense, imperative | Past tense, vague |
| References issue if applicable | No context |

**Why are commits important?**
- Traceable history — who changed what, when, why
- Enables rollback to specific points
- Communication in team environments

---

### Q10. What should NEVER be committed to GitHub? ⭐

- API keys, passwords, tokens, private credentials
- `.env` files (add to `.gitignore`)
- `node_modules/` (install with `npm install`)
- Build artifacts

```bash
# .gitignore example
.env
node_modules/
*.log
dist/
.DS_Store
```

**If API key was accidentally committed:**
1. Immediately revoke/rotate the key in the service dashboard
2. Remove from code
3. Use `git filter-branch` or BFG Repo Cleaner to scrub history
4. Force push (and warn team)

---

### Q11. Organize DSA Repository ⭐

```
DSA/
├── Arrays/
│   ├── TwoSum.java
│   ├── MissingNumber.java
├── Strings/
│   ├── LongestSubstring.java
├── LinkedList/
│   ├── ReverseList.java
├── Stack/
├── Queue/
├── Trees/
├── Graphs/
└── DP/
```

**Why organize by topic?**
- Easier to navigate during revision
- Clear separation of concepts
- Better for portfolio/showcase

---

## 🔑 QUICK MEMORY TRICKS

- **git add → commit → push** = stage → snapshot → upload
- **git pull = fetch + merge**
- **reset** = rewrite history (risky), **revert** = safe undo (new commit)
- **Stash** = "pause and save work temporarily"
- **Never commit:** API keys, .env, node_modules
- **PR** = "please review my branch before merging"

---

## ⚠️ COMMON MISTAKES

1. Using `git reset --hard` on shared branches — destroys others' work
2. Committing `.env` with secrets — use `.gitignore`
3. Confusing `git fetch` and `git pull`
4. Writing vague commit messages ("fix stuff", "update")
5. Not resolving conflict markers properly — leaving `<<<<<<<` in code
