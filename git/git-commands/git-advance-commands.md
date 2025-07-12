# 🔴 Advanced Commands

### This is an advanced Git reference. These commands are rarely used in daily workflows but are useful for scripting, automation, or working with Git internals.

---

### 🧩 Used in Teams / DevSecOps

| Command                                          | What It Does                                     |
| ------------------------------------------------ | -------------------------------------------------|
| `git worktree add ../new-folder <branch>`        | Use multiple working trees for different branches     |
| `git filter-branch --force ...`                  | Remove files from Git history (e.g., secrets)         |
| `git bisect`                                     | Find commit that introduced a bug                     |
| `git submodule add <repo>`                       | Add repo as a submodule                               |
| `git tag <name>`                                 | Tag a specific commit (e.g., v1.0.0)                  |
| `git archive -o out.zip HEAD`                    | Export current branch as zip archive                  |
| `git clone --mirror`                             | Clone the entire repo including all refs; used for backup/migration  |


> 💡 **Tip:** `git bisect` is a power move in debugging. Definitely worth mastering.

---

### 🧩 DevSecOps + GitOps Essentials

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
| `git pull --rebase`                   | Preferred for linear history in teams.                          |


> 💡 **Tip:** Use `git worktree` to work on multiple branches without switching.
>
> ⚠️ **Warning:** Commands like `git filter-branch` and `git rebase -i` rewrite history — use them only on local or private branches.

---

### 🔧 GitOps & CI/CD Relevance

| Concept / Command              | Use Case / Why It’s Useful                                           |
| ------------------------------ | ---------------------------------------------------------------------|
| GitOps                         | Git as the **single source of truth** for infrastructure (IaC) and deployments |
| `git tag <v1.0.0>`             | Mark a commit for a release; used in CI/CD pipelines                 |
| `git push origin --tags`       | Push all tags to remote (so CI/CD can trigger from them)             |
| `git checkout <tag>`           | Checkout a specific release state                                    |
| `git tag -d <tag>`             | Useful for deleting remote tags.                                     |
| `git push origin :refs/tags/<tag>`| Useful for deleting remote tags.                                  |
| `git diff <commit1> <commit2>` | Compare environments or code before/after deployment                 |



### 🔧 Repository Plumbing (Low-level Internal Commands)

| Command           | Explanation                                                     |
| ----------------- | --------------------------------------------------------------- |
| `git cat-file`    | Show type, size, and content of Git objects                     |
| `git commit-tree` | Create commit object manually (used internally or in scripting) |
| `git diff-tree`   | Show differences between two trees (commits)                    |
| `git hash-object` | Hash a file and optionally write to Git database                |
| `git merge-tree`  | Show what a merge would look like                               |
| `git worktree`    | Manage multiple working directories for branches                |
| `git read-tree`   | Load tree into the staging area                                 |
| `git update-ref`  | Update ref files directly                                       |
| `git rev-parse`   | Convert ref/branch/tag into SHA or parse arguments              |
| `git fsck`        | Verify connectivity and validity of Git objects                 |
| `git gc`          | Cleanup unnecessary files to optimize repository                |
| `git prune`       | Remove unreachable objects                                      |
| `git verify-pack` | Verify contents of pack files                                   |



### 🗃️ Index & Working Directory Management

| Command              | Explanation                                   |
| -------------------- | --------------------------------------------- |
| `git checkout-index` | Restore files from index to working directory |
| `git ls-files`       | Show all tracked files in index               |


### 🔗 References & Refs Handling

| Command            | Explanation                                 |
| ------------------ | ------------------------------------------- |
| `git for-each-ref` | Iterate over refs with custom format output |
| `git ls-remote`    | List references in a remote repository      |
| `git show-ref`     | List all references                         |
| `git symbolic-ref` | Read or modify symbolic refs like HEAD      |
| `git show-branch`  | Show branches and their commits             |
| `git show-ref --heads` | List all branch refs |
| `git show-ref --tags`  | List all tag refs    |



### 🌳 Branching, Merging, History – Porcelain Commands

| Command        | Explanation                                                       |
| -------------- | ----------------------------------------------------------------- |
| `git branch`   | *(implicit in other commands, not listed above but usually here)* |
| `git checkout` | Switch branches or restore files                                  |
| `git commit`   | Commit staged changes                                             |
| `git merge`    | Combine another branch into current one                           |
| `git rebase`   | Reapply commits on another base commit                            |
| `git reset`    | Reset index and/or working tree                                   |
| `git cherry-pick --upstream` | Apply commit from another branch with upstream awareness     |
| `git merge-ours`             | Use ‘ours’ strategy to resolve conflicts                     |
| `git merge-recursive`        | Merge strategy for multiple branches                         |
| `git merge-subtree`          | Merge external repositories as subtrees                      |
| `git mergetool`              | Open configured merge tool                                   |
| `git rebase`                 | Reapply commits on another base commit *(from earlier list)* |



### 🧾 Log Customization & History Exploration

| Command                   | Explanation                                        |
| ------------------------- | -------------------------------------------------- |
| `git log`                 | View commit history                                |
| `git blame`               | Show who changed each line of a file and when      |
| `git show`                | Display objects like commits, tags, or files       |
| `git bisect`              | Binary search to find commit that introduced a bug |
| `git diff`                | Show file changes                                  |
| `git log --oneline`       | Show compact one-line-per-commit log               |
| `git log --stat`          | Show changes per commit                            |
| `git log --merges`        | Show only merge commits                            |
| `git log --pretty=`       | Customize log formatting                           |
| `git log --short-commit`  | Show brief commit hash + message                   |
| `git log --topo-order`    | Show topologically ordered commits                 |
| `git reflog`              | Show reference history including deleted commits   |
| `git describe`            | Name a commit using nearest tag + distance         |



### 🌐 Remote Interactions

| Command         | Explanation                            |
| --------------- | -------------------------------------- |
| `git fetch`     | Download objects and refs from remote  |
| `git push`      | Upload local commits to remote         |
| `git ls-remote` | List references in a remote repository |


### 🔍 Searching

| Command    | Explanation                                                      |
| ---------- | ---------------------------------------------------------------- |
| `git grep` | Search working directory or history for lines matching a pattern |


### 🏷️ Tags Management

| Command                  | Explanation                    |
| ------------------------ | ------------------------------ |
| `git tag`                | Create or list tags            |
| `git tag --list`         | *(from earlier)* List all tags |
| `git tag -l`             | List tags matching pattern     |
| `git tag --delete`       | Delete a tag                   |
| `git tag --force` / `-f` | Force (overwrite) tag          |
| `git tag --sign`         | Create GPG-signed tag          |
| `git tag --verify`       | Verify GPG signature on a tag  |
| `git mktag`              | Create tag object manually     |



### ⚙️ Configuration & Customization (Alias & Hook)

| Command                             | Explanation                           |
| ----------------------------------- | ------------------------------------- |
| `git config --global alias.*`       | Create short aliases for Git commands |
| `git config --local core.hooksPath` | Set custom path for Git hooks         |



### 📤 Push, Pull, & Syncing with Remotes

| Command             | Explanation                               |
| ------------------- | ----------------------------------------- |
| `git push --mirror` | Push all refs and tags; mirror local repo |
| `git push --tags`   | Push all local tags                       |
| `git pull --rebase` | Pull and rebase instead of merge          |


### 📦 Patch & Email Workflow

| Command            | Explanation                     |
| ------------------ | ------------------------------- |
| `git am`           | Apply patches from emails       |
| `git format-patch` | Create patch files from commits |
| `git patch-id`     | Generate stable patch ID        |


### 🧩 Submodules / Subtrees / Large Files

| Command       | Explanation                             |
| ------------- | --------------------------------------- |
| `git annex`   | Manage large files outside the Git repo |
| `git p4`      | Work with Perforce repositories         |
| `git subtree` | Include sub-projects in one repository  |



### 🗂️ Index & File Operations

| Command             | Explanation                                       |
| ------------------- | ------------------------------------------------- |
| `git mv`            | Rename or move a file                             |
| `git rm`            | Remove file from working dir and index            |
| `git update-index`  | Add/modify index directly                         |
| `git unpack-file`   | Extract blob from Git database                    |
| `git replace`       | Replace Git objects                               |
| `git reset --hard`  | Reset everything to last commit (⚠️ destructive)  |
| `git reset --mixed` | Reset index and unstage, keep working dir changes |
| `git revert`        | Safely undo commit by creating a new one          |
| `git stash save`    | Save current working changes to stash             |
