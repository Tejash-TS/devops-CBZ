# Git & GitHub Practical Guide (Branching, Remote Operations & GitHub Basics)

## Objective

Learn and practice the following Git and GitHub concepts with **clear
explanations and practical examples**.

Topics Covered:

### Git Branching

-   git branch
-   Types of branches
-   git checkout
-   git diff
-   git merge

### Remote Repository Commands

-   git clone
-   git pull
-   git push

### Repository Setup Commands

-   git init
-   git config
-   git remote

### GitHub Basics

-   GitHub Dashboard
-   Public vs Private Repository
-   Searching Public Repositories

------------------------------------------------------------------------

# PART 1 --- Git Branching

## What is a Branch?

A branch in Git is an **independent line of development**.\
Developers create branches to work on new features without affecting the
main project.

Example:

    main branch
       |
       |---feature-login
       |
       |---feature-payment

------------------------------------------------------------------------

# git branch

## Command

    git branch

## Explanation

Shows all branches in the repository.

Example Output

    * main
    feature-login

`*` indicates the **current active branch**.

------------------------------------------------------------------------

## Create a Branch

    git branch feature-login

Creates a new branch but **does not switch to it**.

Check again

    git branch

Output

    * main
    feature-login

------------------------------------------------------------------------

# Types of Branches

## 1 Main Branch

-   Primary branch of the project
-   Production-ready code

Example:

    main

------------------------------------------------------------------------

## 2 Feature Branch

Used for developing new features.

Example

    feature-login
    feature-payment

------------------------------------------------------------------------

## 3 Bug Fix Branch

Used for fixing bugs.

Example

    bugfix-navbar
    bugfix-api

------------------------------------------------------------------------

## 4 Release Branch

Prepared for deployment.

Example

    release-v1.0

------------------------------------------------------------------------

## 5 Hotfix Branch

Urgent fixes applied directly to production.

Example

    hotfix-payment

------------------------------------------------------------------------

# git checkout

## Command

    git checkout branch-name

Example

    git checkout feature-login

## Explanation

Switches from one branch to another.

Example Output

    Switched to branch 'feature-login'

------------------------------------------------------------------------

## Create and Switch Branch

    git checkout -b feature-payment

This command:

1 Creates branch\
2 Switches to branch

------------------------------------------------------------------------

# git diff

## Command

    git diff

## Explanation

Shows the **difference between file changes**.

Example Scenario

Modify a file

    echo "New update" >> app.txt

Run

    git diff

Example Output

    + New update

This shows the newly added line.

------------------------------------------------------------------------

# git merge

## Command

    git merge branch-name

Example

    git checkout main
    git merge feature-login

## Explanation

Combines changes from one branch into another.

Workflow Example

    Create branch → Work on feature → Merge to main

Example Output

    Updating a1b2c3d..d4e5f6g
    Fast-forward

------------------------------------------------------------------------

# PART 2 --- Remote Repository Commands

Remote repository = repository hosted on GitHub.

------------------------------------------------------------------------

# git clone

## Command

    git clone repository-url

Example

    git clone https://github.com/user/project.git

## Explanation

Downloads the **entire repository** from GitHub to local machine.

Example Output

    Cloning into 'project'...

------------------------------------------------------------------------

# git pull

## Command

    git pull origin main

## Explanation

Fetches **latest updates from remote repository** and merges them into
local branch.

Example Workflow

    Developer A pushes code
    Developer B runs git pull
    Local repo gets updated

------------------------------------------------------------------------

# git push

## Command

    git push origin main

## Explanation

Uploads local commits to GitHub repository.

Example Workflow

    Edit files
    git add .
    git commit -m "updated project"
    git push origin main

------------------------------------------------------------------------

# PART 3 --- Repository Setup Commands

------------------------------------------------------------------------

# git init

## Command

    git init

## Explanation

Creates a **new local Git repository**.

Creates hidden folder

    .git

------------------------------------------------------------------------

# git config

Used to configure Git user information.

## Set Username

    git config --global user.name "Your Name"

## Set Email

    git config --global user.email "your@email.com"

Check configuration

    git config --list

Example Output

    user.name=John
    user.email=john@email.com

------------------------------------------------------------------------

# git remote

Used to connect local repository with GitHub repository.

## Check Remote

    git remote -v

Example Output

    origin https://github.com/user/project.git

------------------------------------------------------------------------

## Add Remote

    git remote add origin https://github.com/user/project.git

------------------------------------------------------------------------

# PART 4 --- GitHub Dashboard

GitHub Dashboard is the **main interface of GitHub after login**.

You can:

-   Create repositories
-   View your repositories
-   Manage pull requests
-   View commits
-   Track issues
-   Collaborate with developers

Main Sections:

    Repositories
    Pull Requests
    Issues
    Actions
    Projects

------------------------------------------------------------------------

# Public vs Private Repository

  Feature         Public Repository
  --------------- -------------------
  Visibility      Anyone can see
  Collaboration   Open community
  Use Case        Open source
  Security        Less restricted

Example:

Public Repo → open source project\
Private Repo → company backend code

------------------------------------------------------------------------

# How to Search Public Repositories

Steps:

1 Go to GitHub homepage

2 Use the search bar

Example Search

    terraform aws

3 Press Enter

4 Select **Repositories** tab

You will see:

-   Repository name
-   Description
-   Stars
-   Programming language

Example Result

    terraform-aws-modules
    aws-terraform-examples

------------------------------------------------------------------------

# Complete Practical Workflow Example

    mkdir git-demo
    cd git-demo

    git init

    git config --global user.name "Student"
    git config --global user.email "student@email.com"

    touch app.txt
    echo "Hello Git" > app.txt

    git add .
    git commit -m "first commit"

    git branch feature-login

    git checkout feature-login

    echo "login feature code" >> app.txt

    git add .
    git commit -m "added login feature"

    git checkout main

    git merge feature-login

------------------------------------------------------------------------

# Final Git Architecture

    Local Repository
          |
          | git push
          ↓
    GitHub Repository
          |
          | git pull
          ↓
    Local Repository

------------------------------------------------------------------------

# Practical Completed

You successfully learned:

-   Git branching
-   Git remote commands
-   Repository setup
-   GitHub dashboard basics
