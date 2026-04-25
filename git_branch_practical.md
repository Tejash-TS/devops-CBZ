
# Git Branch Practical Guide (Beginner Friendly)

## Introduction to Git Branch

Git Branching is one of the most powerful features of Git. A **branch** allows developers to work on different features or fixes without affecting the main project.

In real software development, multiple developers work on the same project simultaneously. Branching helps keep work organized and safe.

### Example

- `main` → Stable production code
- `feature-login` → Developing login feature
- `bug-fix` → Fixing bugs

Each developer works on their own branch and later merges the changes into the main branch.

---

# Objective

In this practical you will learn:

- How to create a branch
- How to switch between branches
- How to make changes in a branch
- How to merge branches
- How to delete a branch

---

# Prerequisites

- Git installed on your system
- Terminal / Command Prompt
- Basic knowledge of Git

Check git installation:

```bash
git --version
```

Expected Output:

```
git version 2.x.x
```

---

# Practical: Git Branch Step-by-Step

## Step 1 — Create Project Directory

Command:

```bash
mkdir git-branch-practical
cd git-branch-practical
```

Explanation:

- `mkdir` creates a new directory
- `cd` moves into the directory

Expected Output:

(No output)

---

## Step 2 — Initialize Git Repository

Command:

```bash
git init
```

Explanation:

Initializes an empty Git repository.

Expected Output:

```
Initialized empty Git repository in .../git-branch-practical/.git/
```

---

## Step 3 — Create a File

Command:

```bash
echo "Welcome to Git Branch Practical" > project.txt
```

Explanation:

Creates a file named `project.txt` with initial content.

---

## Step 4 — Check Git Status

Command:

```bash
git status
```

Explanation:

Shows current repository state.

Expected Output:

```
On branch main

Untracked files:
  project.txt
```

---

## Step 5 — Add File to Staging Area

Command:

```bash
git add project.txt
```

Explanation:

Moves file from working directory to staging area.

---

## Step 6 — Commit Changes

Command:

```bash
git commit -m "Initial Commit"
```

Explanation:

Saves changes permanently in Git history.

Expected Output:

```
[main (root-commit) abc123] Initial Commit
1 file changed, 1 insertion(+)
```

---

## Step 7 — Check Current Branch

Command:

```bash
git branch
```

Expected Output:

```
* main/master
```

Explanation:

`*` indicates the current active branch.

---

## Step 8 — Create New Branch

Command:

```bash
git branch feature-login
```

Explanation:

Creates a new branch called `feature-login`.

---

## Step 9 — List Branches

Command:

```bash
git branch
```

Expected Output:

```
feature-login
* main
```

---

## Step 10 — Switch to New Branch

Command:

```bash
git checkout feature-login
```

Expected Output:

```
Switched to branch 'feature-login'
```

Explanation:

Moves working directory to the `feature-login` branch.

---

## Step 11 — Modify File in Branch

Command:

```bash
echo "Login Feature Added" >> project.txt
```

Explanation:

Adds a new line to the file.

---

## Step 12 — View File Content

Command:

```bash
cat project.txt
```

Expected Output:

```
Welcome to Git Branch Practical
Login Feature Added
```

---

## Step 13 — Commit Changes in Branch

Command:

```bash
git add project.txt
git commit -m "Added login feature"
```

Expected Output:

```
[feature-login 98abc1] Added login feature
1 file changed, 1 insertion(+)
```

---

## Step 14 — Switch Back to Main Branch

Command:

```bash
git checkout main
```

Expected Output:

```
Switched to branch 'main'
```

---

## Step 15 — Check File Again

Command:

```bash
cat project.txt
```

Expected Output:

```
Welcome to Git Branch Practical
```

Explanation:

Changes from `feature-login` are not yet in the main branch.

---

## Step 16 — Merge Branch into Main

Command:

```bash
git merge feature-login
```

Explanation:

Combines changes from `feature-login` into `main`.

Expected Output:

```
Updating abc123..98abc1
Fast-forward
 project.txt | 1 +
```

---

## Step 17 — Verify File After Merge

Command:

```bash
cat project.txt
```

Expected Output:

```
Welcome to Git Branch Practical
Login Feature Added
```

---

## Step 18 — Delete Branch

Command:

```bash
git branch -d feature-login
```

Expected Output:

```
Deleted branch feature-login
```

---

## Step 19 — Verify Remaining Branches

Command:

```bash
git branch
```

Expected Output:

```
* main
```

---

# Important Git Branch Commands

| Command | Purpose |
|-------|--------|
| git branch | List branches |
| git branch branch-name | Create branch |
| git checkout branch-name | Switch branch |
| git checkout -b branch-name | Create and switch |
| git merge branch-name | Merge branch |
| git branch -d branch-name | Delete branch |

---

# Real World Branch Workflow

Example structure used in companies:

```
main
│
├── feature-login
├── feature-payment
├── bug-fix
└── ui-update
```

Developers create branches for each feature and merge them after testing.

---

# Conclusion

Git branching allows safe and parallel development. It is used in almost every software project and is a core skill for developers and DevOps engineers.

