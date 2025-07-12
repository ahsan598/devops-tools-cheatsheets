# 🎯 Common Git Interview Questions


### 🔄 1. What is the difference between `git pull` and `git fetch`?

| Command                  | What It Does                                                            |
| -------------------------| ----------------------------------------------------------------------- |
| `git fetch`              | Downloads changes from remote but **does not merge** into your branch   | 
| `git pull`               | Downloads and **automatically merges** changes into your current branch |


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

## 🔹 1. You made changes in a file but don’t want to commit them now. What will you do?

**Answer:**
Use `git stash` to save the changes temporarily.
```bash
git stash
```
You can reapply it later using:
```bash
git stash apply
```

---

## 🔹 2. You committed to the wrong branch by mistake. How to fix it?

**Answer:**
```bash
# Save the changes in a new branch
git checkout -b correct-branch
# (Your commit is here now)

# Go back and remove commit from wrong branch
git checkout wrong-branch
git reset --hard HEAD~1
```

---

## 🔹 3. You want to undo the last commit but keep the changes in the working directory?

**Answer:**
```bash
git reset --soft HEAD~1
```

---

## 🔹 4. How to resolve a merge conflict?

**Answer:**
- Git will mark conflicting areas with `<<<<<<<`, `=======`, and `>>>>>>>`.
- Open the file, manually fix the conflict.
- After fixing:
```bash
git add <filename>
git commit
```

---

## 🔹 5. Difference between `git pull` and `git fetch`?

**Answer:**
- `git fetch`: downloads changes from remote but doesn’t merge.
- `git pull`: fetches + merges changes automatically.

---

## 🔹 6. You accidentally deleted a branch. Can you recover it?

**Answer:**
```bash
git reflog
# Find the commit hash
git checkout -b branch-name <commit-hash>
```

---

## 🔹 7. How do you check who made changes to a specific line in a file?

**Answer:**
```bash
git blame <filename>
```

---

## 🔹 8. What is detached HEAD? How to come out of it?

**Answer:**
Detached HEAD occurs when you're not on a branch (e.g., checked out a commit directly).  
To fix:
```bash
git checkout main
```

---

## 🔹 9. How to delete a remote branch?

**Answer:**
```bash
git push origin --delete branch-name
```

---

## 🔹 10. How to revert a commit that is already pushed?

**Answer:**
```bash
git revert <commit-hash>
# creates a new commit that undoes changes
```

---

## 🔹 11. How to clone a specific branch only?

**Answer:**
```bash
git clone -b branch-name --single-branch <repo-url>
```

---

## 🔹 12. You want to move only one file from one branch to another. How?

**Answer:**
```bash
git checkout source-branch -- path/to/file
```

---

## 🔹 13. How to see the commit history in a simple format?

**Answer:**
```bash
git log --oneline --graph --all
```

---

## 🔹 14. How do you squash multiple commits into one?

**Answer:**
```bash
git rebase -i HEAD~<number-of-commits>
# Mark commits as "squash" or "s"
```

---

## 🔹 15. What is the difference between `git reset`, `git revert`, and `git checkout`?

**Answer:**

| Command        | Use Case                                 |
|----------------|-------------------------------------------|
| `git reset`    | Move HEAD to previous commit (history rewrite) |
| `git revert`   | Creates a new commit that undoes previous one |
| `git checkout` | Switch branches or restore files          |

---

## 🔹 16. How to track a remote branch locally?

**Answer:**
```bash
git checkout --track origin/branch-name
```

---

## 🔹 17. What’s the difference between `origin/master` and `master`?

**Answer:**
- `master`: local branch.
- `origin/master`: remote-tracking branch (not yet fetched).

---

## 🔹 18. How to push code to a new repo for the first time?

**Answer:**
```bash
git remote add origin <repo-url>
git branch -M main
git push -u origin main
```

---

## 🔹 19. You want to remove a file from Git but not from your system?

**Answer:**
```bash
git rm --cached filename
```

---

## 🔹 20. How to apply only specific stashed changes?

**Answer:**
```bash
git stash show -p stash@{0} | git apply -R
```

---

✅ **Tip:** Always double-check before using `reset --hard` or `force push`.


---


### 🎓 Summary Tips for Interviews:

- Practice conflict resolution and branch workflows
- Be clear on how Git works behind the scenes
- Know `merge`, `rebase`, `revert`, `reset`, `stash` and `cherry-pick`
- Understand `.git`, `HEAD`, and GitOps concept for DevOps roles

