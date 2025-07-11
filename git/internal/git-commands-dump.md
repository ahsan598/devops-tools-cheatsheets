
# 🛠️ Git Commands - Internal Dump (Draft)

> ⚠️ This is a raw dump of Git commands collected from various sources. Use it as a personal reference. Not meant for public display as-is.

---

## 📦 Create a New Repository

```bash
echo "# Git-commands" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin <remote-url>
git push -u origin main
```

## 🔄 Push Existing Repo to Remote

```bash
git remote add origin <remote-url>
git branch -M main
git push -u origin main
```

---

## 🔧 Common Commands (with Short Notes)

```bash
git init                          # Create new repo
git diff                          # Show changes not yet staged
git status                        # Show file states
git add .                         # Stage all files
git add <file>                    # Stage specific file
git commit                        # Commit staged changes
git commit -a                     # Commit tracked files directly
git commit --amend                # Modify last commit
git branch <name>                 # Create new branch
git checkout <branch>            # Switch branch
git branch -d <branch>           # Delete a branch
git branch -a                    # Show all branches (local + remote)
git clone -b <branch> <url>      # Clone specific branch
git fetch                        # Get latest changes
git pull <remote> <branch>       # Pull + merge from remote
git push <remote> <branch>       # Push to remote
git merge <branch>               # Merge into current branch
git rebase <branch>              # Reapply commits over another branch
git revert <commit>              # Undo commit via new commit
git clean -f -d                  # Remove untracked files & folders
git show <branch>:<file>         # View file from another branch
git remote -v                    # List remotes
git remote show origin           # Detailed remote info
git remote get-url origin        # Get current origin URL
git remote set-url origin <url>  # Set new origin URL
git rm <file>                    # Remove file from repo
git reset HEAD <file>            # Unstage file
git restore                      # Undo local changes
git log                          # Show commit history
```

---

## 🧪 Useful Categories (Just Command Names)

### Core:
```bash
git init, git clone, git add, git commit, git status, git diff, git checkout, git reset, git log, git show, git tag, git push, git pull
```

### Branching:
```bash
git branch, git checkout -b, git merge, git rebase, git cherry-pick
```

### Stashing:
```bash
git stash, git stash pop, git stash list, git stash apply, git stash drop
```

### Remotes:
```bash
git remote, git remote add, git remote remove, git fetch, git pull, git push
```

### Configuration:
```bash
git config, git config --global alias.<alias> <cmd>
```

### Plumbing (Internals):
```bash
git cat-file, git ls-files, git rev-parse, git hash-object, git show-ref, git update-ref
```

### Porcelain (Everyday Use):
```bash
git blame, git bisect, git grep, git reflog, git reset, git revert, git mv, git tag -d
```

### Additional:
```bash
git fsck, git gc, git archive, git describe, git format-patch, git push --tags, git pull --rebase, git log --stat
```

---

## ✅ Notes

- Avoid using `git reset --hard` on shared branches.
- Use `git reflog` to recover lost commits.
- Use `git bisect` to find bugs.
- Prefer `git pull --rebase` for linear history.

