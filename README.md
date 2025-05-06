
# Git Practice Repository

This repository is created for practicing Git commands including branching, merging, conflict resolution, and syncing changes across branches.

## 📁 Initial Setup

1. Created a new GitHub repository named `git-practice`.
2. Cloned the repository locally:
   ```bash
   git clone https://github.com/satishvudata98/git-practice.git
   ```
3. Added a simple `hello.py` file:
   ```python
   print("Hello World!")
   ```
   Committed and pushed to the `main` branch.

---

## 🌱 Branching Strategy

### 1. Created a `develop` branch from `main`:
```bash
git checkout -b develop
git push origin develop
```

### 2. Created two feature branches from `develop`:
- `feature/sub-01`
- `feature/sub-02`

```bash
git checkout -b feature/sub-01 develop
git push origin feature/sub-01

git checkout -b feature/sub-02 develop
git push origin feature/sub-02
```

---

## 🧪 Feature Work

### ✅ `feature/sub-01`
- Modified `hello.py`
- Committed and pushed the changes
- Merged into `develop` using CLI:
  ```bash
  git checkout develop
  git merge feature/sub-01
  git push origin develop
  ```

### ✅ `feature/sub-02`
- Modified the same `hello.py`, causing a conflict
- Resolved the merge conflict in favor of `feature/sub-02` changes
- Merged into `develop`:
  ```bash
  git checkout develop
  git merge feature/sub-02
  git push origin develop
  ```

---

## 🔄 Syncing Branches

After merging `feature/sub-02` into `develop`, we switched back to `feature/sub-01`:

```bash
git checkout feature/sub-01
git pull origin develop
```

This ensured that `feature/sub-01` got the latest updates from `develop`, including the resolved `hello.py`.

---

## 🔀 Final Merge

Merged `develop` into `main`:
```bash
git checkout main
git merge develop
git push origin main
```

---

## 🗑️ Cleanup (Optional)

Feature branches can now be deleted:

```bash
# Local
git branch -d feature/sub-01
git branch -d feature/sub-02

# Remote
git push origin --delete feature/sub-01
git push origin --delete feature/sub-02
```

---

## ℹ️ GitHub "Create Pull Request" Note

Even after merging via command line, GitHub may still show the **“Create Pull Request”** button. This is **safe to ignore** if the changes have already been merged and pushed.

---

## ✅ Summary

This exercise covered:

- Creating and pushing branches
- Working with multiple feature branches
- Handling merge conflicts
- Syncing branches with `pull`
- Merging back to `develop` and finally to `main`
