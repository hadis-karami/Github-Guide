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