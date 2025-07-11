# 🎯 Common Git Interview Questions (with Simple Answers & Examples)

### A beginner-friendly and interview-ready cheat sheet covering most frequently asked Git questions in DevOps, SRE, and software development interviews.

---

### 🔄 1. What is the difference between `git pull` and `git fetch`?

| Command                             | What It Does                                                            |
| ----------------------------------- | ----------------------------------------------------------------------- |
| `git fetch`                         | Downloads changes from remote but **does not merge** into your branch   | 
| `git pull`                          | Downloads and **automatically merges** changes into your current branch |


🧠 **Tip:** Use `fetch` when you want to review changes before merging.

```bash
# Typical use
git fetch origin
# Then you can inspect and merge

# Quick merge (pull)
git pull origin main
```

---

### 📦 2. What is `git stash` and when to use it?

> `git stash` temporarily saves your uncommitted changes and cleans your working directory.

Use it when:

- You want to switch branches quickly **without committing** your work
- Need to work on urgent bug fix or pull latest code safely

```bash
git stash            # Stash current changes
git switch featureX  # Move to another branch

git stash list       # See saved stashes
git stash apply      # Reapply last stash
```

---

### 🔁 3. What is `rebase`? How is it different from `merge`?

| Action   | Description                                                             |
| -------- | ----------------------------------------------------------------------- |
| `merge`  | Combines branches and creates a **new merge commit**                    |
| `rebase` | Moves your branch on top of another to make a **linear commit history** |

```bash
# Rebase example
git checkout feature
git rebase main
```

🧠 Rebase is cleaner, but **avoid rebasing shared branches**.

---

### 🚨 4. What happens in `git reset` vs `git revert`?

| Command      | What It Does                                                         |
| ------------ | -------------------------------------------------------------------- |
| `git reset`  | Moves the pointer backward (and may change history — **DANGEROUS**)  |
| `git revert` | Creates a **new commit** that undoes the effect of a previous commit |

🧠 Use `revert` when you've **already pushed** a commit to remote and want to undo it safely.

```bash
git revert <commit-id>   # Safe undo
```

---

### ⚔️ 5. How to resolve merge conflicts?

1. Run: `git pull` or `git merge`
2. Git will show conflict markers like `<<<<<<<` in your code
3. Manually fix the conflict
4. Then:

```bash
git add .
git commit -m "Resolved merge conflict"
```

✅ Use VS Code or other GUI to resolve easily.

---

### 🧠 6. Explain `HEAD` in Git

> `HEAD` is the pointer to the **current branch or commit** you're working on.

```bash
git show HEAD   # Show current commit
```

Think of it as the 'current snapshot'.

---

### 🚫 7. What is Detached HEAD state?

> When `HEAD` points directly to a commit instead of a branch.

This happens when you checkout a specific commit:

```bash
git checkout abc123  # Detached HEAD
```

You can browse, test, or build from this state, but commits won't be saved unless you create a branch:

```bash
git switch -c new-branch
```

---

### 🍒 8. What is the use of `git cherry-pick`?

> `git cherry-pick` applies a **specific commit** from one branch to another.

```bash
git cherry-pick <commit-id>
```

Useful for applying hotfixes or specific changes without merging entire branch.

---

### 🌿 9. Difference between Tracking Branch vs Local Branch

| Branch Type     | Description                                         |
| --------------- | --------------------------------------------------- |
| Local Branch    | Exists only on your machine                         |
| Tracking Branch | Linked to a branch on the remote (e.g. origin/main) |

You set tracking when you do:

```bash
git push -u origin main  # 'main' now tracks 'origin/main'
```

---

### 🔍 10. How does Git work internally? (Trees, Blobs, SHAs)

- Git stores everything as **objects**: blobs (file content), trees (directories), commits (history)
- Each object has a unique **SHA-1 hash**
- Snapshots not diffs: Git saves entire state of repo in each commit

```bash
.git/objects/   # Actual data storage
.git/index      # Staging area (index)
```

---

### 🗃️ 11. What is the `.git` directory?

> It’s the **heart of a Git repo**. It stores metadata, commits, history, config, branches, etc.

When you run `git init`, this folder is created.

```bash
ls .git/   # Shows refs, objects, logs, config, etc.
```

---

### 📤 12. Difference between Fork and Clone

| Action   | Fork                                                 | Clone                                |
| -------- | ---------------------------------------------------- | ------------------------------------ |
| Purpose  | Makes a copy under **your GitHub account**           | Copies repo to your **local system** |
| Used For | Open source contribution, making independent changes | Local development                    |

```bash
git clone https://github.com/user/repo.git
```

---

### ⚙️ 13. What is GitOps? (From DevOps POV)

> GitOps is a DevOps practice where **Git is the single source of truth** for infrastructure and application delivery.

✅ Used with Kubernetes, Terraform, ArgoCD, FluxCD, etc.

Benefits:

- Version-controlled deployments
- Auditable, repeatable changes
- Easier rollback and automation

---

### 📝 14. How to undo a pushed commit safely?

```bash
git revert <commit-id>  # Safest way to undo
```

Avoid `git reset` if commit is already pushed.

---

### 📁 `.gitignore vs .gitkeep`

| File         | Purpose                                                            |
| ------------ | ------------------------------------------------------------------ |
| `.gitignore` | Tells Git which files/folders to skip                              |
| `.gitkeep`   | Dummy file to keep empty folders (Git doesn’t track empty folders) |

---

### 🎓 Summary Tips for Interviews:

- Practice conflict resolution and branch workflows
- Be clear on how Git works behind the scenes
- Know `merge`, `rebase`, `revert`, `reset`, `stash` and `cherry-pick`
- Understand `.git`, `HEAD`, and GitOps concept for DevOps roles

---

**🧠 Bookmark this for interview revision and daily Git refresh!**

