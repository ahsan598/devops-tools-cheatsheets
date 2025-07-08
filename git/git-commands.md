### ✅ Basic Git Commands

| Command                        | What It Does                                                       |
| ----------------------------- | ------------------------------------------------------------------ |
| `git init`                    | Initialize a new Git repository                                   |
| `git clone <repo-url>`        | Clone a remote repository to local                                |
| `git status`                  | Show changes (staged/unstaged/untracked)                          |
| `git add <file>`              | Stage a specific file for commit                                  |
| `git add .`                   | Stage all changed files                                            |
| `git commit -m "message"`     | Save changes with a message                                       |
| `git log`                     | Show commit history                                               |
| `git log --oneline --graph`   | Compact graphical log (great for quick view)                      |
| `git diff`                    | See differences between changes                                   |

---

### 🧠 Branching & Merging

| Command                                  | What It Does                                                   |
| ---------------------------------------- | -------------------------------------------------------------- |
| `git branch`                             | List all local branches                                        |
| `git branch <name>`                      | Create a new branch                                            |
| `git checkout <name>`                    | Switch to a branch                                             |
| `git checkout -b <name>`                 | Create and switch to new branch                                |
| `git merge <branch>`                     | Merge given branch into current branch                         |
| `git branch -d <name>`                   | Delete a branch (only if merged)                               |
| `git branch -D <name>`                   | Force delete branch (even if not merged)                       |
| `git rebase <branch>`                    | Reapply commits from current branch onto target branch         |
| `git cherry-pick <commit>`               | Apply a specific commit from another branch                    |

---

### 🔁 Remote Repositories

| Command                                      | What It Does                                          |
| ------------------------------------------- | ----------------------------------------------------- |
| `git remote add origin <url>`               | Connect local repo to a remote URL                   |
| `git remote -v`                              | Show current remote URLs                             |
| `git push origin <branch>`                  | Push branch to remote                                |
| `git push --set-upstream origin <branch>`   | Set upstream (link local to remote branch)           |
| `git pull`                                   | Pull latest changes and merge                        |
| `git fetch`                                  | Fetch updates without merging                        |
| `git fetch --all`                            | Fetch all branches and updates                       |

---

### 🧹 Undo & Cleanup

| Command                              | What It Does                                                        |
| ----------------------------------- | ------------------------------------------------------------------- |
| `git reset --soft HEAD~1`           | Undo last commit, keep changes staged                               |
| `git reset --mixed HEAD~1`          | Undo last commit, unstage changes                                   |
| `git reset --hard HEAD~1`           | Completely undo last commit and discard changes                     |
| `git revert <commit>`               | Create a new commit to reverse a specific commit (non-destructive)  |
| `git clean -fd`                     | Delete untracked files and folders                                  |
| `git checkout -- <file>`            | Discard local changes to a file                                     |
| `git restore <file>`                | (Newer syntax) Restore file to last commit state                    |

---

### 📦 Stash & Patch

| Command                 | What It Does                                          |
| ---------------------- | ----------------------------------------------------- |
| `git stash`            | Save uncommitted changes temporarily                  |
| `git stash list`       | List saved stashes                                   |
| `git stash apply`      | Apply latest stash (without deleting it)             |
| `git stash pop`        | Apply and delete stash                               |
| `git stash drop`       | Delete a stash manually                              |
| `git format-patch`     | Create patch file from commits                       |

---

### 👀 Inspection & History

| Command                            | What It Does                                              |
| ---------------------------------- | --------------------------------------------------------- |
| `git show <commit>`               | Show details of a commit                                  |
| `git diff <commit1> <commit2>`    | Compare two commits                                       |
| `git blame <file>`                | Show who last modified each line of a file                |
| `git reflog`                      | Show all HEAD changes (including deleted branches)        |
| `git log --stat`                  | Show files changed with each commit                       |
| `git shortlog -sne`               | Summary of commits by contributors                       |

---

### ⚙️ Configuration & Setup

| Command                                     | What It Does                                          |
| ------------------------------------------ | ----------------------------------------------------- |
| `git config --list`                        | Show all Git config                                   |
| `git config --global user.name "Name"`     | Set global username                                   |
| `git config --global user.email "Email"`   | Set global email                                      |
| `git config credential.helper store`       | Save credentials (not secure – for local/dev only)    |

---

### 🧩 Advanced (Used in Teams / DevSecOps)

| Command                                           | What It Does                                               |
| ------------------------------------------------ | ---------------------------------------------------------- |
| `git worktree add ../new-folder <branch>`        | Use multiple working trees for different branches          |
| `git filter-branch --force ...`                  | Remove files from Git history (e.g., secrets)              |
| `git bisect`                                     | Find commit that introduced a bug                          |
| `git submodule add <repo>`                       | Add repo as a submodule                                    |
| `git tag <name>`                                 | Tag a specific commit (e.g., v1.0.0)                        |
| `git archive -o out.zip HEAD`                    | Export current branch as zip archive                       |

---

### 🧠 Git Interview Tips

| Question / Concept                              | Explanation Hint |
| ----------------------------------------------- | ---------------- |
| `git merge vs rebase`                           | Rebase rewrites history, merge creates new commit |
| `git reset vs revert`                           | Reset removes, revert undoes via new commit       |
| `stash use case`                                | Switch context without committing                 |
| `detached HEAD`                                 | HEAD not pointing to a branch                     |
| `.gitignore vs .gitkeep`                        | Ignore files vs keep empty folders                |
| `how to undo pushed commit safely?`             | `git revert`, not `reset --hard`                 |
| `tracking branch`                               | Local branch linked to remote (upstream)          |
