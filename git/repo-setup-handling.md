# 📁 Repository Setup & Remote Handling

### 🔁 When Repository Name or Remote URL Changes

| 🔧 Command                            | 💬 What It Does                                               |
| ------------------------------------- | ------------------------------------------------------------- |
| `git remote -v`                       | Check current remote URL (origin)                             |
| `git remote set-url origin <new-url>` | Update the remote URL after repo name or host changes         |
| `git remote get-url origin`           | Verify that the remote URL was updated correctly              |
| `git push -u origin <branch>`         | Set upstream again (optional if push fails due to URL change) |


#### Example (after renaming repo on GitHub):
```sh
git remote set-url origin https://github.com/username/new-repo-name.git
```

---

# 📁 Creating a New Git Repository (Local & Remote)

### ✅ Option 1: Create Local → Link to Remote

| Step | Command                                   | Description                                |
| ---- | ----------------------------------------- | ------------------------------------------ |
| 1️⃣  | `git init`                                | Initialize empty Git repo locally          |
| 2️⃣  | `git add .`                               | Stage all current files                    |
| 3️⃣  | `git commit -m "Initial commit"`          | Make first commit                          |
| 4️⃣  | Create repo on GitHub/GitLab (no README!) | Manually (via browser)                     |
| 5️⃣  | `git remote add origin <repo-url>`        | Link local repo to remote                  |
| 6️⃣  | `git branch -M main`                      | Rename default branch to `main` (optional) |
| 7️⃣  | `git push -u origin main`                 | Push local code to remote                  |


### ✅ Option 2: Clone Remote Repo → Work Locally

| Step | Command                        | Description                          |
| ---- | ------------------------------ | ------------------------------------ |
| 1️⃣  | `git clone <repo-url>`         | Clone the remote repo to your system |
| 2️⃣  | `cd <repo-name>`               | Go into the cloned repo folder       |
| 3️⃣  | `git status` / `git add`, etc. | Make changes, commit, and push       |


### 📝 Pro Tip
- Use `git remote rename <old> <new>` if origin name needs to change (rare).
- Use `git remote remove origin` and `add` again if it gets corrupted.


### ❌🗑️ How to Delete the Repo

| Action                    | Command / Steps                           |
| ------------------------- | ----------------------------------------- |
| Delete repo on GitHub     | Go to repo → Settings → Delete repository |
| Delete repo locally       | `rm -rf <repo-folder>`                    |
| Remove remote from local  | `git remote remove origin`                |
| Reconnect to new repo URL | `git remote add origin <new-url>`         |
