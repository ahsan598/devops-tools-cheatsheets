# -------------------------------------------
# 🌱 1. Git Basics – Daily Use
# -------------------------------------------

### Initialize a repo
git init

# Clone a repo
git clone <repo-url>

# Check status of files
git status

# Add files to staging
git add <file>              # single file
git add .                   # all changes

# Commit changes
git commit -m "Your message"

# View commit history
git log                     # full history
git log --oneline --graph   # clean view

# Create a branch
git branch <branch-name>

# Switch to a branch
git checkout <branch-name>

# Create and switch to a branch
git checkout -b <branch-name>

# Merge branch into current branch
git merge <branch-name>

# Delete a branch
git branch -d <branch-name>         # safe delete (merged)
git branch -D <branch-name>         # force delete (even if unmerged)

# Push changes to remote
git push origin <branch-name>

# Pull latest changes
git pull

# Add remote origin
git remote add origin <url>

# View current remotes
git remote -v

# Rename a branch
git branch -m <new-name>

# -------------------------------------------
# 🧠 2. Intermediate – Corporate/Team Usage
# -------------------------------------------

# Track a new remote branch
git checkout -b <branch> origin/<branch>

# Set upstream for push/pull
git push --set-upstream origin <branch>

# Fetch all branches without merging
git fetch --all

# Stash uncommitted changes
git stash
git stash pop       # apply and remove from stash
git stash list      # show stashed items

# Revert a commit (non-destructive)
git revert <commit-id>

# Reset to a commit (destructive)
git reset --hard <commit-id>

# Show changes between commits
git diff <commit1> <commit2>

# Undo last commit (keep changes staged)
git reset --soft HEAD~1

# Undo last commit (unstage changes)
git reset HEAD~1

# -------------------------------------------
# 🚀 3. Advanced / Pro Git (Used in DevSecOps, Teams)
# -------------------------------------------

# View who changed what and when (blame)
git blame <file>

# Clean untracked files
git clean -fd

# Squash commits during rebase
git rebase -i HEAD~3      # interactive rebase last 3 commits

# Amend last commit (change message or add file)
git commit --amend

# Cherry-pick a commit from another branch
git cherry-pick <commit-id>

# Remove sensitive file from history
git filter-branch --force --index-filter \
"git rm --cached --ignore-unmatch <file>" \
--prune-empty --tag-name-filter cat -- --all

# Worktree – multiple branches in same repo
git worktree add ../feature-b feature-branch

# Restore deleted file
git checkout HEAD -- <file>

# -------------------------------------------
# 💡 4. Pro Tips (Good to Know)
# -------------------------------------------

# Save credentials (local use only)
git config --global credential.helper store

# View config
git config --list

# Change commit message after push (force push required – use with care)
git commit --amend
git push --force

# Create a patch file (useful for code reviews)
git format-patch -1 <commit-id>

# Revert pushed commit (via new commit)
git revert <commit-id>

# See all branches (local and remote)
git branch -a

# List files changed in a commit
git show --name-only <commit-id>

# Find deleted branches
git reflog
