# 🧬 Git Reference Section

### 📖 What is Git?
Git is a distributed version control system used to track changes in source code during software development. It allows teams to collaborate, manage code history, switch between features using branches, and safely deploy changes.

Git is the backbone of platforms like **GitHub, GitLab, Bitbucket**, and widely used in DevOps, CI/CD, and cloud automation workflows.


### 💡 🛠️ How to Install Git

- Linux (Debian/Ubuntu):
  ```sh
  sudo apt update
  sudo apt install git
  ```

- macOS (with Homebrew):
  ```sh
  brew install git
  ```

- Windows:
👉 Download Git from [here](https://git-scm.com/downloads)

---

### 📦 What's in This Cheatsheet?

| File                              | Purpose                                                           |
| --------------------------------- | ----------------------------------------------------------------- |
| `Git/git-commands.md`             | Git CLI commands (basic to intermediate)                          |
| `Git/interview-questions.md`      | Common Git interview questions and real-world scenarios           |
| `Git/gitignore-guide.md`          | How and why to use a `.gitignore` file in a project               |
| `Git/gitkeep-guide.md`            | How and why to use a `.gitkeep` file to track empty folders       |
| `Git/repo-setup-and-remotes.md`   | Configure and manage Git remotes during repo setup or rename      |
| `Git/branch-restructure-guide.md` | Reorganize branches: convert `main` to `feature`, create `master` |


---

### 👤 Who Is This Cheatsheet For?

- DevOps & DevSecOps Engineers  
- Developers working with Git workflows  
- Students preparing for technical interviews  
- Anyone using Git for source control and collaboration

---

### 🚀 Quick Start (Core Workflow)

Clone the repo and switch to this branch:

```sh
git clone https://github.com/ahsan598/devops-tools-cheatsheets.git
cd devops-tools-cheatsheet
git checkout git
```
View Git command reference:
```sh
cat Git/git-commands.md
```

Or open in GitHub → [Git CLI Commands](./git/git-commands.md)

---

### 🧠 Key Concepts
- **Branches:** Work in parallel without conflict
- **Commits:** Track history of changes
- **Remotes:** Sync with GitHub/GitLab repositories
- **Stash & Rebase:** For temporary changes and cleaner history
- **Cherry-pick, Reset, Revert:** Modify or undo commits
- **Worktrees & Submodules:** Multi-branch and repo management


---

### ❓ Frequently Asked Interview Questions
- Difference between `merge` and `rebase`?
- What is a `detached HEAD`?
- How do you undo a pushed commit safely?
- When to use `stash`, and how?
- How does Git track changes in `.gitignore`?


### 📚 Interview Prep
[Common Git Interview Questions](./git/interview-questions.md)

---

### 🛠️ Some Useful Commands

```sh
git clone <repo-url>        # Clone a repo
git status                  # Show changes
git add .                   # Stage all changes
git commit -m "msg"         # Commit with message
git checkout -b <branch>    # Create & switch branch
git push origin <branch>    # Push to remote
git pull                    # Pull latest changes
git stash                   # Save local changes temporarily
git log --oneline --graph   # View compact commit history
```

---

### 📚 Recommended Resources
- 📘 [Official Git Documentation](https://git-scm.com/doc)
- 📖 [Pro Git Book (Free)](https://git-scm.com/book/en/v2)
- 🎥 [Git & GitHub Crash Course (YouTube)](https://www.youtube.com/watch?v=RGOj5yH7evk)
- 🧪 [Learn Git Branching (Interactive Visual Tool)](https://learngitbranching.js.org/)