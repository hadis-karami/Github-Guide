# Git and GitHub Collaboration Guide

A practical guide to collaborating with other developers using Git and
GitHub.

## 1. Git vs. GitHub

-   **Git** is a version-control system. It tracks changes, records
    project history, and lets developers work on separate branches.
-   **GitHub** is an online platform for hosting Git repositories and
    coordinating teamwork through pull requests, code reviews, issues,
    permissions, and project boards.

Git manages the project's history; GitHub helps the team share the
project and coordinate its work.

## 2. How collaboration works

A common team workflow is:

1.  A team creates a shared repository on GitHub.
2.  Each developer clones it to their computer.
3.  Before starting a task, each developer updates their local `main`
    branch.
4.  Each developer creates a separate branch for their task.
5.  They edit files and save their work in commits.
6.  They push their branches to GitHub.
7.  They open Pull Requests (PRs) to propose merging their changes into
    `main`.
8.  Teammates review the changes and request updates or approve them.
9.  An authorized person merges the approved PR.
10. Everyone updates their local `main` branch.

The key idea is that developers work independently on branches and
integrate their work through pull requests.  

## 3. Important concepts

### Repository

A repository (repo) contains project files and their Git history.

-   **Local repository:** the copy on your computer.
-   **Remote repository:** a shared copy hosted on GitHub.

### Commit

A commit is a saved snapshot of your changes. A good commit represents
one logical unit of work.

``` bash
git add .
git commit -m "Add login form validation"
```

### Branch

A branch is an independent line of development. It allows you to work on
a feature without changing `main` immediately.

Examples:

-   `feature/user-login`
-   `feature/profile-page`
-   `bugfix/navbar-overflow`
-   `docs/update-readme`

### Remote

A remote is a named reference to another repository. The default remote
is commonly called `origin`.

``` bash
git remote -v
```

### Pull Request

A Pull Request (PR) is a GitHub proposal to merge one branch into
another. It provides a place to review code, discuss changes, request
improvements, and approve work.

### Merge conflict

A merge conflict occurs when Git cannot automatically combine changes,
often because two developers edited the same lines.