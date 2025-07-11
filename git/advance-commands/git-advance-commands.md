# 🔴 Advanced Commands

### This is an advanced Git reference. These commands are rarely used in daily workflows but are useful for scripting, automation, or working with Git internals.

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
| `git clone --mirror`                             | Clone the entire repo including all refs; used for backup/migration  |


> 💡 **Tip:** `git bisect` is a power move in debugging. Definitely worth mastering.

---

### 🧩 Advanced / DevSecOps + GitOps Essentials

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

### 🔧 GitOps & CI/CD Relevance (Bonus for DevOps Interviews)

| Concept / Command              | Use Case / Why It’s Useful                                           |
| ------------------------------ | ---------------------------------------------------------------------|
| GitOps                         | Git as the **single source of truth** for infrastructure (IaC) and deployments |
| `git tag <v1.0.0>`             | Mark a commit for a release; used in CI/CD pipelines                 |
| `git push origin --tags`       | Push all tags to remote (so CI/CD can trigger from them)             |
| `git checkout <tag>`           | Checkout a specific release state                                    |
| `git tag -d <tag>`             | Useful for deleting remote tags.                                     |
| `git push origin :refs/tags/<tag>`| Useful for deleting remote tags.                                  |
| `git diff <commit1> <commit2>` | Compare environments or code before/after deployment                 |


---


### Plumbing:

| Command                            | Explanation                                                                |
|------------------------------------|----------------------------------------------------------------------------|
| `git cat-file`                     | Show type, size, and content of Git objects                                |
| `git checkout-index`               | Restore files from index to working directory                              |
| `git commit-tree`                  | Create commit object manually (used internally or in scripting)            |
| `git diff-tree`                    | Show differences between two trees (commits)                               |
| `git for-each-ref`                 | Iterate over refs with custom format output                                |
| `git hash-object`                  | Hash a file and optionally write to Git database                           |
| `git ls-files`                     | Show all tracked files in index                                            |
| `git ls-remote`                    | List references in a remote repository                                     |
| `git merge-tree`                   | Show what a merge would look like                                          |
| `git read-tree`                    | Load tree into the staging area                                            |
| `git rev-parse`                    | Convert ref/branch/tag into SHA or parse arguments                         |
| `git show-branch`                  | Show branches and their commits                                            |
| `git show-ref`                     | List all references                                                        |
| `git symbolic-ref`                 | Read or modify symbolic refs like HEAD                                     |
| `git tag --list`                   | List all tags                                                              |
| `git update-ref`                   | Update ref files directly                                                  |

---

### Porcelain:

| Command                            | Explanation                                                                |
|------------------------------------|----------------------------------------------------------------------------|
| `git blame`                        | Show who changed each line of a file and when                              |
| `git bisect`                       | Binary search to find commit that introduced a bug                         |
| `git checkout`                     | Switch branches or restore files                                           |
| `git commit`                       | Commit staged changes                                                      |
| `git diff`                         | Show file changes                                                          |
| `git fetch`                        | Download objects and refs from remote                                      |
| `git grep`                         | Search working directory or history for lines matching a pattern           |
| `git log`                          | View commit history                                                        |
| `git merge`                        | Combine another branch into current one                                    |
| `git push`                         | Upload local commits to remote                                             |
| `git rebase`                       | Reapply commits on another base commit                                     |
| `git reset`                        | Reset index and/or working tree                                            |
| `git show`                         | Display objects like commits, tags, or files                               |
| `git tag`                          | Create or list tags                                                        |


### Alias:
| `git config --global alias.*`      | Create short aliases for Git commands                                      |


### Hook:
| `git config --local core.hooksPath`| Set custom path for Git hooks                                              |


---

### Additional

| Command                            | Explanation                                                                |
|------------------------------------|----------------------------------------------------------------------------|
| `git annex`                        | Manage large files outside the Git repository                              |
| `git am`                           | Apply patches from emails                                                  |
| `git cherry-pick --upstream`       | Apply commit from another branch (with upstream awareness)                 |
| `git describe`                     | Name a commit using closest tag and number of commits                      |
| `git format-patch`                 | Create patch files from commits                                            |
| `git fsck`                         | Verify connectivity and validity of Git objects                            |
| `git gc`                           | Cleanup unnecessary files to optimize repository                           |
| `git help`                         | Show help manual                                                           |
| `git log --merges`                 | Show only merge commits                                                    |
| `git log --oneline`                | Show compact one-line-per-commit log                                       |
| `git log --pretty=`                | Customize log formatting                                                   |
| `git log --short-commit`           | (Alias style) Show brief commit hash + message                             |
| `git log --stat`                   | Show changes (insertions/deletions) per commit                             |
| `git log --topo-order`             | Topologically ordered log                                                  |
| `git merge-ours`                   | Use ‘ours’ strategy to resolve conflicts                                   |
| `git merge-recursive`              | Merge strategy used for merging multiple branches                          |
| `git merge-subtree`                | Merge external repositories as subtrees                                    |
| `git mergetool`                    | Open configured merge tool                                                 |
| `git mktag`                        | Create tag object manually                                                 |
| `git mv`                           | Rename or move a file                                                      |
| `git patch-id`                     | Generate stable patch ID                                                   |
| `git p4`                           | Work with Perforce repositories                                            |
| `git prune`                        | Remove unreachable objects                                                 |
| `git pull --rebase`                | Pull and rebase instead of merge                                           |
| `git push --mirror`                | Push all refs and tags; makes exact mirror of local repo                   |
| `git push --tags`                  | Push all local tags                                                        |
| `git reflog`                       | Show branch/reference history (incl. deleted)                              |
| `git replace`                      | Replace Git objects                                                        |
| `git reset --hard`                 | Reset everything to last commit (⚠️ destructive)                           |
| `git reset --mixed`                | Reset index and unstage, but keep working dir changes                      |
| `git revert`                       | Safely undo commits using new commit                                       |
| `git rm`                           | Remove file from working dir and index                                     |
| `git show-ref --heads`             | List branch refs                                                           |
| `git show-ref --tags`              | List tag refs                                                              |
| `git stash save`                   | Save current changes to stash                                              |
| `git subtree`                      | Include sub-projects in a single repository                                |
| `git tag --delete`                 | Delete a tag                                                               |
| `git tag --force`                  | Force creation or overwrite tag                                            |
| `git tag --sign`                   | Create GPG-signed tag                                                      |
| `git tag -f`                       | Force (overwrite) tag                                                      |
| `git tag -l`                       | List tags matching pattern                                                 |
| `git tag --verify`                 | Verify GPG signature on a tag                                              |
| `git unpack-file`                  | Extract blob from Git database                                             |
| `git update-index`                 | Add/modify index directly                                                  |
| `git verify-pack`                  | Verify contents of pack files                                              |
| `git worktree`                     | Manage multiple working directories for branches                           |
