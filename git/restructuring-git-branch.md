# 🚀 Repository Branch Reorganization: From Main to Feature and Master

### 🔧 1. Convert main → feature Branch

```sh
# Rename local branch from main to feature (new-branch)
git branch -m main new-branch

# Push 'new-branch' branch to remote
git push origin new-branch

# Set upstream
git push --set-upstream origin new-branch

# Delete 'main' branch from remote
git push origin --delete main
```

---

### ✳️ 2. Create a Clean master Branch (as homepage)

```sh 
# Create orphan branch (no history)
git checkout --orphan master

# Remove all files from index
git rm -rf .

# Add clean README.md
echo "# DevOps Cheatsheets" > README.md
echo "This repository contains cheatsheets for various DevOps tools." >> README.md
echo "## Branches" >> README.md
echo "- **terraform**: Terraform automation and commands" >> README.md
echo "- **git**: Git commands and tips" >> README.md

# Commit and push
git add README.md
git commit -m "Initial master branch with project overview"
git push origin master
```
---

### ➕ 3. Create More Tool-Specific Branches (Optional)
```sh
git checkout master
git checkout -b git
mkdir Git
# Add README.md
git add Git/
git commit -m "Added Git cheatsheet structure"
git push -u origin git
```

### 🔁 Sync

- Pull Latest Changes
```sh
git fetch
git pull

git pull origin branch-name
```

### 🧹 Delete Branch (Local & Remote)

- Delete local branch:
```sh
git branch -d branch-name     # If merged
git branch -D branch-name     # Force delete
```

- Delete remote branch:
```sh
git push origin --delete branch-name
```
> 🛑 Can't delete remote default branch (like main) until default branch is changed on GitHub UI
Fix: Go to GitHub → Repo → Settings → Branches → Change default → Then delete

---

### ✅ 4. Final Verification
- List Remote Branches
```sh
git ls-remote --heads origin
```

- Remote-Tracking Branches
```sh
git branch -r
git branch -a   [All branches (local + remote)]
```
---

### 🧹 5. Fix: Remove that stale origin/main reference locally
- Run this command to clean up your local remote-tracking branches:
```sh
git remote prune origin
```

- Now Verify:
```sh
git branch -r
```