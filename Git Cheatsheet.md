# Git Cheatsheet

A simple list of go-to Git commands for common workflows.

---

# 1. Push a Local Project to GitHub

### Step 1 — Create a repository on GitHub
Create a new repository where you want to push your project.

### Step 2 — Initialize Git locally
```bash
git init
```

### Step 3 — Check file status
```bash
git status
```

Shows untracked files in **red**.

### Step 4 — Add files to staging area

Add all files

```bash
git add .
```

Add specific directory

```bash
git add directory-name
```

Add specific file

```bash
git add path/to/file
```

### Step 5 — Verify staged files
```bash
git status
```

Staged files appear in **green**.

### Step 6 — Commit the changes

```bash
git commit -m "your message"
```

Use meaningful messages like:

- add
- update
- delete

### Step 7 — Add remote repository

```bash
git remote add origin <REMOTE_URL>
```

Example

```bash
git remote add origin https://github.com/username/repo.git
```

### Step 8 — Verify remote

```bash
git remote -v
```

### Step 9 — Push code to GitHub

```bash
git push -u origin branch-name
```

Example

```bash
git push -u origin main
```

---

### Windows credential helper

To stop Git from asking credentials repeatedly:

```bash
git config credential.helper store
```

---

# 2. Clone a Project from GitHub

### Step 1 — Create a local folder

Navigate into the folder.

### Step 2 — Clone repository

```bash
git clone <REMOTE_URL>
```

Example

```bash
git clone https://github.com/username/repo.git
```

### Step 3 — Pull latest changes

```bash
git pull origin branch-name
```

Example

```bash
git pull origin main
```

### Handling conflicts

If both **local and remote files changed**, you must:

1. Pull changes
2. Resolve conflicts
3. Commit again

---

# 3. Branching

### Create and switch to new branch

```bash
git checkout -b branch-name
```

### Create branch only

```bash
git branch branch-name
```

### Switch branch

```bash
git checkout branch-name
```

### Show all branches

```bash
git branch
```

### Merge branches

```bash
git merge branch-name
```

Important rule:

- Checkout the branch you want to merge **into**
- Merge the branch you want to merge **from**

Example

```bash
git checkout main
git merge feature
```

### Delete local branch

```bash
git branch -d branch-name
```

### Delete remote branch

```bash
git push origin --delete branch-name
```

### Rename branch

```bash
git branch -m new-branch-name
```

### Fix unrelated histories error

```bash
git merge --allow-unrelated-histories branch-name
```

### Restore branch from history

```bash
git reflog
```

---

# 4. Useful Git Utilities

### Show file differences

```bash
git diff file-name
git diff branch-name
```

### Show commit history

```bash
git log
```

Last 5 commits

```bash
git log -5
```

### Show specific commit

```bash
git show commit-hash
```

---

# 5. Restore and Undo Changes

### Restore file changes

```bash
git restore file-name
```

### Remove from staging area

```bash
git restore --staged file-name
```

---

### Undo last commit (keep changes)

```bash
git reset --soft HEAD^
```

### Undo last commit (delete changes)

```bash
git reset --hard HEAD^
```

### Reset to specific time

```bash
git reset --hard master@{"10 minutes ago"}
```

### Reset to branch

```bash
git reset --hard branch-name
```

### Reset to commit

```bash
git reset --hard commit-id
```

---

# 6. Reverting Commits

Revert a specific commit

```bash
git revert commit-hash
```

---

# 7. Force Push (Use Carefully)

```bash
git push --force origin branch-name
```

---

# 8. Undo Last Pull

```bash
git reset --keep HEAD@{1}
```

---

# 9. Pull Without Merge Commits

```bash
git pull --rebase
```

Useful when you committed locally before pulling.

---

# 10. Change Remote URL

```bash
git remote set-url origin <NEW_URL>
```

---

# Useful Resources

### Git Handbook
https://guides.github.com/introduction/git-handbook/

### .gitignore Guide
https://www.pluralsight.com/guides/how-to-use-gitignore-file

### Undo Specific Commit
https://stackoverflow.com/questions/2318777/undo-a-particular-commit-in-git-thats-been-pushed-to-remote-repos

### Revert vs Reset
https://stackoverflow.com/questions/4114095/how-do-i-revert-a-git-repository-to-a-previous-commit

### Git Rebase
https://www.youtube.com/watch?v=f1wnYdLEpgI

https://kernowsoul.com/blog/2012/06/20/4-ways-to-avoid-merge-commits-in-git/

### Undo Pull
https://stackoverflow.com/questions/5815448/how-to-undo-a-git-pull/5815626

### Configure Git User

https://www.codegrepper.com/code-examples/shell/vscode+make+sure+you+configure+your+%27user.name%27+and+%27user.email%27+in+git

### Create GitHub Token

https://stackoverflow.com/questions/68775869/support-for-password-authentication-was-removed-please-use-a-personal-access-to

---
