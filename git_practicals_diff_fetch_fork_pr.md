
# Git Practical Guide – diff, fetch, fork, and pull request

This lab manual contains **separate practical exercises** for:

1. Git Diff
2. Git Fetch
3. Fork (GitHub)
4. Pull Request (GitHub)

Each section contains:
- Introduction / theory
- Step‑by‑step commands
- Explanation
- Expected output

------------------------------------------------------------

# 1. Git Diff Practical

## Introduction

`git diff` is used to **compare changes between files, commits, branches, or working directory**.

It helps developers see:
- what code changed
- what lines were added or removed
- differences before committing.

## Practical Steps

### Step 1 — Create Project

Command

```
mkdir git-diff-practical
cd git-diff-practical
git init
```

Explanation

Creates project folder and initializes Git repository.

Expected Output

```
Initialized empty Git repository
```

---

### Step 2 — Create File

Command

```
echo "Hello Git" > file.txt
```

---

### Step 3 — Add and Commit

Command

```
git add file.txt
git commit -m "Initial commit"
```

Expected Output

```
1 file changed, 1 insertion(+)
```

---

### Step 4 — Modify File

Command

```
echo "Learning Git Diff" >> file.txt
```

---

### Step 5 — Run Git Diff

Command

```
git diff
```

Explanation

Shows **difference between working directory and last commit**.

Expected Output

```
+ Learning Git Diff
```

`+` means line added.

---

### Step 6 — Stage File and Compare

Command

```
git add file.txt
git diff --staged
```

Explanation

Shows difference between **staging area and last commit**.

------------------------------------------------------------

# 2. Git Fetch Practical

## Introduction

`git fetch` downloads **latest changes from remote repository** but **does not merge them**.

Difference:

| Command | Function |
|------|------|
git fetch | download changes only |
git pull | download + merge |

## Practical Steps

### Step 1 — Clone Repository

Command

```
git clone https://github.com/example/repo.git
```

Explanation

Copies remote repository to local machine.

---

### Step 2 — Check Remote

Command

```
git remote -v
```

Expected Output

```
origin https://github.com/example/repo.git
```

---

### Step 3 — Fetch Latest Changes

Command

```
git fetch origin
```

Explanation

Downloads updates from GitHub but **does not change local files**.

Expected Output

```
From https://github.com/example/repo
 * branch main -> origin/main
```

---

### Step 4 — Compare Local and Remote

Command

```
git diff main origin/main
```

Explanation

Shows difference between local branch and remote branch.

------------------------------------------------------------

# 3. Fork Practical (GitHub)

## Introduction

Forking means **creating a copy of someone else's repository into your GitHub account**.

Used in **open source contributions**.

Example:

Original Repo → Fork → Modify → Pull Request

## Practical Steps

### Step 1 — Open GitHub Repository

Example

```
https://github.com/example/project
```

---

### Step 2 — Click Fork

At top right click:

```
Fork
```

GitHub creates:

```
https://github.com/your-username/project
```

---

### Step 3 — Clone Forked Repo

Command

```
git clone https://github.com/your-username/project.git
```

---

### Step 4 — Make Changes

Example

```
echo "New feature added" >> feature.txt
```

---

### Step 5 — Commit Changes

Command

```
git add .
git commit -m "Added new feature"
```

---

### Step 6 — Push Changes

Command

```
git push origin main
```

Your fork repository is now updated.

------------------------------------------------------------

# 4. Pull Request Practical

## Introduction

A **Pull Request (PR)** is used to **request merging your changes into another repository**.

Workflow:

```
Fork Repo
↓
Clone Fork
↓
Create Branch
↓
Push Changes
↓
Create Pull Request
```

## Practical Steps

### Step 1 — Create New Branch

Command

```
git checkout -b feature-update
```

---

### Step 2 — Make Changes

Example

```
echo "Improved documentation" >> README.md
```

---

### Step 3 — Commit Changes

Command

```
git add .
git commit -m "Improved documentation"
```

---

### Step 4 — Push Branch

Command

```
git push origin feature-update
```

Expected Output

```
remote:
Create a pull request for 'feature-update'
```

---

### Step 5 — Create Pull Request

Steps in GitHub:

1. Open repository
2. Click **Pull Requests**
3. Click **New Pull Request**
4. Compare branches
5. Click **Create Pull Request**

---

### Step 6 — Maintainer Reviews Code

Maintainer can:

- Review code
- Add comments
- Approve changes
- Merge pull request

------------------------------------------------------------

# Real Industry Workflow

```
Main Repository
      │
      ├── Fork
      │      │
      │      ├── Clone
      │      ├── Create Branch
      │      ├── Commit Changes
      │      └── Push
      │
      └── Pull Request → Review → Merge
```

------------------------------------------------------------

# Conclusion

These commands are essential in real DevOps and development workflow.

Important concepts:

- `git diff` → compare changes
- `git fetch` → download remote updates
- `fork` → copy repository to your account
- `pull request` → request code merge

Mastering these commands helps in **team collaboration and open‑source contribution**.
