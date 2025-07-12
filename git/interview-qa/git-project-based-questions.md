# 🚀 Git Real-World Project Scenarios (DevOps, CI/CD, GitOps)


### 🔸 1. What branching strategy do you follow in your project?

**Answer:**\
We follow `Git Flow` or `Trunk Based Development`.

- `main` or `master`: always production-ready.
- `develop`: integration branch for features.
- `feature/*`: for feature-specific work.
- `hotfix/*`: for critical fixes on production.
- `release/*`: for preparing a release.

---

### 🔸 2. How do you handle a hotfix in Git?

**Answer:**

```bash
# Checkout from main
git checkout -b hotfix/issue-123 main

# Fix the code, commit, test
git commit -am "fix: urgent patch for issue-123"

# Merge to main and develop
git checkout main
git merge hotfix/issue-123

git checkout develop
git merge hotfix/issue-123
```

---

### 🔸 3. How do you manage code review using Pull Requests?

**Answer:**

- We raise PRs from `feature/*` to `develop`.
- Enforce approvals using GitHub/GitLab rules.
- Ensure PR includes tests, ticket ID, and meaningful description.
- Merge strategy: `Squash + Merge` or `Rebase`.

---

### 🔸 4. CI/CD pipeline failed due to a bad Git commit. What do you do?

**Answer:**

- Use `git revert` to undo the bad commit without history rewrite:

```bash
git revert <bad-commit-hash>
git push
```

- This creates a safe rollback commit that fixes the pipeline.

---

### 🔸 5. How do you sync your feature branch with the latest develop changes?

**Answer:**

```bash
git checkout feature/login
git fetch origin
git rebase origin/develop
```

Or if rebase not allowed:

```bash
git merge origin/develop
```

---

### 🔸 6. How do you handle conflicts during rebase?

**Answer:**

- Git stops at the conflict.
- Fix the file(s), then:

```bash
git add <file>
git rebase --continue
```

- Repeat till done. Use `git rebase --abort` to cancel.

---

### 🔸 7. You want to test someone else's PR locally. How?

**Answer:**

```bash
git fetch origin pull/ID/head:pr-branch
git checkout pr-branch
```

---

### 🔸 8. How do you roll back a release in Git?

**Answer:**

- Find the last good tag or commit on `main`:

```bash
git checkout main
git revert <bad-commit-range>
git push
```

---

### 🔸 9. How does Git help in GitOps or Infra-as-Code?

**Answer:**

- Git is the **single source of truth**.
- Changes to infra (Terraform/YAML) are made via PR.
- CI/CD pipeline reads Git state and applies it via `terraform apply` or `kubectl apply`.

---

### 🔸 10. How do you clean stale branches?

**Answer:**

```bash
git fetch --prune
git branch -r | grep 'origin/' | while read remote; do
  echo $remote
done
```

Or manually delete merged branches:

```bash
git branch --merged develop
git branch -d old-feature
```

---

### 🔸 11. How can we manage security on GitHub branches? What are the approaches?**

**A:**
- **Branch protection rules**: Prevent force pushes, require PR reviews, enforce status checks before merging.
- **Code owners**: Automatically request reviews from designated teams.
- **Signed commits**: Enforce commit signature verification.
- **Secrets scanning**: GitHub scans for secrets in code to avoid leaks.
- **Least privilege**: Give minimum access via Teams/Repo permissions.

---


### 🔸 12. How many branching strategies are there and how can we manage multiple developers working on them?**

**A:**
- **Main strategies**:
  - `Git Flow`: `main`, `develop`, `feature/*`, `release/*`, `hotfix/*`
  - `GitHub Flow`: Only `main` + `feature branches` + PR
  - `Trunk-based Development`: Everyone commits to `main` frequently
- **Best Practices**:
  - Use pull requests with reviews.
  - Regularly rebase/sync with the base branch.
  - Feature flags for incomplete code.
  - CI/CD pipelines for validation.