# Git Cheatsheet – DevSecOps Friendly

This folder contains a simple reference to commonly used **Git** commands, useful for:
- Daily Development
- Learning Basics
- Interview Preparation

### 📂 Directory Contains:

- `git-commands`: All necessary basic Git commands
- `interview-questions`: Frequently asked GIT questions
- `repo-setup-handling`: Helps you create your first repo locally or remotely
- `gitignore-guide`: Helps you understand how and why to use a `.gitignore` file in a project.


Use this for quick recall before interviews or while working with Git in real-world CI/CD pipelines.

---

<!-- ## 💡 Tips & Warnings

> 💡 **Tip:** Master Git concepts like **rebase, cherry-pick, stash, and reset** for DevOps and DevSecOps interviews.

> ⚠️ **Warning:** Avoid committing sensitive info (e.g., `.env`, secrets) — use [`.gitignore`](gitignore-guide.md).

> ⚠️ **Warning:** Don't force push (`--force`) unless you're 100% sure — it rewrites remote history.

> ⚠️ **Warning:** `git reset --hard` is **dangerous**. Always warn that it discards local changes **permanently**.

> 💡 **Tip:** Use `git stash` to temporarily save changes and switch context.

> 💡 **Tip:** Use `git config --global init.defaultBranch main` to avoid defaulting to `master`.

> 💡 **Tip:** `git bisect` is a power move in debugging. Definitely worth mastering.

> 💡 **Tip:** Use `git worktree` to work on multiple branches without switching.

> ⚠️ **Warning:** Commands like `git filter-branch` and `git rebase -i` rewrite history — use them only on local or private branches.

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


> 📝 **Note:** "`Rebase` rewrites history and should not be used on shared branches unless you know what you're doing." -->