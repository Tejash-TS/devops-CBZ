# Git Local Repository Practical Guide

## Objective

Learn and practice basic Git commands on a **local repository**: - git
init - git add - git commit - git status - git log - git restore - git
revert

This guide is designed for **100% practical classroom or lab usage**.

------------------------------------------------------------------------

# 1. Install Git (Check)

First check if Git is installed.

``` bash
git --version
```

Expected Output Example:

    git version 2.43.0

If not installed, download from: https://git-scm.com

------------------------------------------------------------------------

# 2. Create Project Folder

``` bash
mkdir git-practical
cd git-practical
```

This will be our **working project directory**.

------------------------------------------------------------------------

# 3. git init

## Command

``` bash
git init
```

## Explanation

-   Initializes a **new Git repository**
-   Creates a hidden `.git` folder
-   Git starts tracking the project

## Expected Output

    Initialized empty Git repository in .../git-practical/.git/

## Verify

    ls -a

You should see

    .git

------------------------------------------------------------------------

# 4. Create a File

    touch index.html

Add some content:

    echo "<h1>Hello Git</h1>" > index.html

------------------------------------------------------------------------

# 5. git status

## Command

    git status

## Explanation

Shows: - modified files - untracked files - staged files

## Example Output

    Untracked files:
    index.html

Meaning Git sees the file but **is not tracking it yet**.

------------------------------------------------------------------------

# 6. git add

## Command

    git add index.html

OR

    git add .

## Explanation

Moves files to **Staging Area**.

Git workflow:

    Working Directory → Staging Area → Repository

Check status again:

    git status

Output:

    Changes to be committed:
    new file: index.html

------------------------------------------------------------------------

# 7. git commit

## Command

    git commit -m "Initial commit - added index.html"

## Explanation

-   Saves the staged files into Git history
-   Each commit has a unique ID

## Example Output

    [main (root-commit) a1b2c3d] Initial commit
    1 file changed, 1 insertion(+)

------------------------------------------------------------------------

# 8. Modify File

Edit the file again:

    echo "<p>Welcome to Git Practical</p>" >> index.html

Check status

    git status

Output

    modified: index.html

------------------------------------------------------------------------

# 9. git log

## Command

    git log

## Explanation

Shows **commit history**.

Example:

    commit a1b2c3d4
    Author: User
    Date:

    Initial commit

Short version

    git log --oneline

Example:

    a1b2c3d Initial commit

------------------------------------------------------------------------

# 10. git restore

## Command

    git restore index.html

## Explanation

-   Discards **local changes**
-   Restores file from last commit

Example Scenario:

1 Modify file 2 Run restore

File returns to previous version.

------------------------------------------------------------------------

# 11. git revert

## Command

    git revert <commit-id>

Example:

    git revert a1b2c3d

## Explanation

-   Creates a **new commit**
-   Undoes changes from a previous commit
-   Safe for shared history

Example Output

    [main 9f8e7d6] Revert "Initial commit"

------------------------------------------------------------------------

# 12. Complete Workflow Example

    mkdir git-practical
    cd git-practical

    git init

    touch file1.txt
    echo "Hello Git" > file1.txt

    git status

    git add file1.txt

    git commit -m "Added file1"

    git log

    echo "New line" >> file1.txt

    git status

    git restore file1.txt

------------------------------------------------------------------------

# Final Git Workflow Diagram

    Working Directory
           ↓
       git add
           ↓
       Staging Area
           ↓
       git commit
           ↓
       Git Repository

------------------------------------------------------------------------

# Commands Summary

  Command       Purpose
  ------------- -----------------------
  git init      Initialize repository
  git status    Check repo state
  git add       Add files to staging
  git commit    Save snapshot
  git log       View commit history
  git restore   Discard file changes
  git revert    Undo a commit safely

------------------------------------------------------------------------

# Practical Completed

You successfully practiced **Git Local Repository Commands**.
