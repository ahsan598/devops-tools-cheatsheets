### ✅ Basic Git Commands

| Command                        | What It Does                                                     |
| ----------------------------- | ------------------------------------------------------------------|
| `git init`                    | Initialize a new Git repository                                   |
| `git clone <repo-url>`        | Clone a remote repository to local                                |
| `git status`                  | Show changes (staged/unstaged/untracked)                          |
| `git add <file>`              | Stage a specific file for commit                                  |
| `git add .`                   | Stage all changed files                                           |
| `git commit -m "message"`     | Save changes with a message                                       |
| `git log`                     | Show commit history                                               |
| `git log --oneline --graph`   | Compact graphical log (great for quick view)                      |
| `git diff`                    | See differences between changes                                   |



> ⚠️ **Warning:** Avoid committing sensitive info (e.g., `.env`, secrets) — use `.gitignore`.

---

### 🧠 Branching & Merging

| Command                                  | What It Does                                               |
| ---------------------------------------- | -----------------------------------------------------------|
| `git branch`                             | List all local branches                                    |
| `git branch <name>`                      | Create a new branch                                        |
| `git checkout <name>`                    | Switch to a branch                                         |
| `git checkout -b <name>`                 | Create and switch to new branch                            |
| `git switch -c <name>`                   | Modern alternative to checkout                             |
| `git merge <branch>`                     | Merge given branch into current branch                     |
| `git merge --no-ff <branch>`             | Forces a merge commit, useful for clear history in teams.  |
| `git branch -d <name>`                   | Delete a branch (only if merged)                           |
| `git branch -D <name>`                   | Force delete branch (even if not merged)                   |
| `git rebase <branch>`                    | Reapply commits from current branch onto target branch     |
| `git cherry-pick <commit>`               | Apply a specific commit from another branch                |


---

### 🔁 Remote Repositories

| Command                                     | What It Does                                         |
| ------------------------------------------- | -----------------------------------------------------|
| `git remote add origin <url>`               | Connect local repo to a remote URL                   |
| `git remote -v`                             | Show current remote URLs                             |
| `git push origin <branch>`                  | Push branch to remote                                |
| `git push --set-upstream origin <branch>`   | Set upstream (link local to remote branch)           |
| `git pull`                                  | Pull latest changes and merge                        |
| `git fetch`                                 | Fetch updates without merging                        |
| `git fetch --all`                           | Fetch all branches and updates                       |
| `git push origin --delete <branch>`         | To delete remote branch                              |
| `git remote prune origin`                   | Cleanup stale branches                               |



> ⚠️ **Warning:** Don't force push (`--force`) unless you're 100% sure — it rewrites remote history.

---

### 🧹 Undo & Cleanup

| Command                             | What It Does                                                 |
| ----------------------------------- | -------------------------------------------------------------|
| `git reset <file>`                  | Unstage a staged file                                        |
| `git restore --staged <file>`       | Also unstages                                                |
| `git reset --soft HEAD~1`           | Undo last commit, keep changes staged                        |
| `git reset --mixed HEAD~1`          | Undo last commit, unstage changes                            |
| `git reset --hard HEAD~1`           | Completely undo last commit and discard changes              |
| `git revert <commit>`               | Create a new commit to reverse a specific commit (non-destructive) |
| `git revert -m 1 <merge-commit-sha>`| Use this when you want to undo a merge without rewriting history.  |
| `git clean -fd`                     | Delete untracked files and folders                           |
| `git checkout -- <file>`            | Discard local changes to a file                              |
| `git restore <file>`                | (Newer syntax) Restore file to last commit state             |



> ⚠️ **Warning:** `git reset --hard` is **dangerous**. Always warn that it discards local changes **permanently**.

---

### 📦 Stash & Patch

| Command                    | What It Does                                         |
| -------------------------- | -----------------------------------------------------|
| `git stash`                | Save uncommitted changes temporarily                 |
| `git stash save "message"` | For clarity when using multiple stashes              |
| `git stash  branch <name>` | Create and switch to a branch from stash             |
| `git stash list`           | List saved stashes                                   |
| `git stash apply`          | Apply latest stash (without deleting it)             |
| `git stash pop`            | Apply and delete stash                               |
| `git stash drop`           | Delete a stash manually                              |
| `git format-patch`         | Create patch file from commits                       |



> 💡 **Tip:** Use `git stash` to temporarily save changes and switch context.

---

### 👀 Inspection & History

| Command                            | What It Does                                             |
| ---------------------------------- | ---------------------------------------------------------|
| `git show <commit>`               | Show details of a commit                                  |
| `git diff <commit1> <commit2>`    | Compare two commits                                       |
| `git blame <file>`                | Show who last modified each line of a file                |
| `git reflog`                      | Show all HEAD changes (including deleted branches)        |
| `git log --stat`                  | Show files changed with each commit                       |
| `git shortlog -sne`               | Summary of commits by contributors                        |
| `git log -p`                      | Show commit diffs inline                                  |
| `git diff --staged`               | Show staged vs last commit                                |
| `git log --oneline --graph --all` | Use  to visualize complete commit tree                    |


---

### ⚙️ Configuration & Setup

| Command                                    | What It Does                                          |
| ------------------------------------------ | ----------------------------------------------------- |
| `git config --list`                        | Show all Git config                                   |
| `git config --global user.name "Name"`     | Set global username                                   |
| `git config --global user.email "Email"`   | Set global email                                      |
| `git config credential.helper store`       | Save credentials (not secure – for local/dev only)    |
| `git config core.autocrlf input`           | Prevent Windows vs Linux line ending issues           |
| `git config alias.<name>`                  | Custom command aliases                                |
| `git config --global init.defaultBranch main`| Set default branch name to main when initializing new repositories |


> Ex: Custom command aliases example
> ```sh
> git config --global alias.lg "log --oneline --graph --all"
> ```


> 💡 **Tip:** Use `git config --global init.defaultBranch main` to avoid defaulting to `master`.


---

### 🧩 Advanced (Used in Teams / DevSecOps)

| Command                                          | What It Does                                     |
| ------------------------------------------------ | -------------------------------------------------|
| `git worktree add ../new-folder <branch>`        | Use multiple working trees for different branches     |
| `git filter-branch --force ...`                  | Remove files from Git history (e.g., secrets)         |
| `git bisect`                                     | Find commit that introduced a bug                     |
| `git submodule add <repo>`                       | Add repo as a submodule                               |
| `git tag <name>`                                 | Tag a specific commit (e.g., v1.0.0)                  |
| `git archive -o out.zip HEAD`                    | Export current branch as zip archive                  |



> 💡 **Tip:** `git bisect` is a power move in debugging. Definitely worth mastering.

---

🧩 Advanced / DevSecOps + GitOps Essentials

| Command                               | What It Does / Short Description                                |
| ------------------------------------- | ----------------------------------------------------------------|
| `git sparse-checkout init` + `set`    | Checkout only specific folders from a large repo (great for monorepos) |
| `git fsck`                            | Check repo for corruption and dangling commits                  |
| `git gc`                              | Clean up unnecessary files and optimize the local repository    |
| `git revert HEAD~2..HEAD`             | Revert a **range** of commits (last 2 commits in this example)  |
| `git rebase -i HEAD~3`                | Interactive rebase: squash, reorder, or edit last 3 commits     |
| `git worktree add ../folder <branch>` | Create a new working directory tied to a different branch (parallel workspace) |
| `git archive -o release.zip HEAD`     | Export current repo content as a `.zip` file (useful for releases/artifacts) |
| `git log --graph --all --decorate`    | Visualize entire repo history (useful in teams and large repos) |


> 💡 **Tip:** Use `git worktree` to work on multiple branches without switching.

> ⚠️ **Warning:** Commands like `git filter-branch` and `git rebase -i` rewrite history — use them only on local or private branches.

---

🔧 GitOps & CI/CD Relevance (Bonus for DevOps Interviews)

| Concept / Command              | Use Case / Why It’s Useful                                           |
| ------------------------------ | ---------------------------------------------------------------------|
| GitOps                         | Git as the **single source of truth** for infrastructure (IaC) and deployments |
| `git tag <v1.0.0>`             | Mark a commit for a release; used in CI/CD pipelines                 |
| `git push origin --tags`       | Push all tags to remote (so CI/CD can trigger from them)             |
| `git checkout <tag>`           | Checkout a specific release state                                    |
| `git diff <commit1> <commit2>` | Compare environments or code before/after deployment                 |


---

### 🧠 Git Interview Tips

| Question / Concept                              | Explanation Hint                                  |
| ----------------------------------------------- | --------------------------------------------------|
| `git merge vs rebase`                           | Rebase rewrites history, merge creates new commit |
| `git reset vs revert`                           | Reset removes, revert undoes via new commit       |
| `stash use case`                                | Switch context without committing                 |
| `detached HEAD`                                 | HEAD not pointing to a branch                     |
| `.gitignore vs .gitkeep`                        | Ignore files vs keep empty folders                |
| `how to undo pushed commit safely?`             | `git revert`, not `reset --hard`                  |
| `tracking branch`                               | Local branch linked to remote (upstream)          |



> 📝 **Note:** "`Rebase` rewrites history and should not be used on shared branches unless you know what you're doing."