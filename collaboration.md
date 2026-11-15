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

## 4. Two common collaboration models

### Shared repository

The repository owner invites teammates as collaborators. Each teammate
can push their own branches to the same repository, depending on their
permissions.

This is common for small teams, university projects, and company teams.

### Fork and Pull Request

A contributor creates a **fork**, which is their own GitHub copy of the
original repository. They push changes to their fork and open a PR
against the original project.

This is common in open-source projects where contributors do not have
direct write access.  

## 5. Set up a shared repository

One team member creates a repository:

1.  Sign in to GitHub.
2.  Select **New repository**.
3.  Choose a name and visibility.
4.  Optionally initialize it with a README and `.gitignore`.
5.  Create the repository.
6.  Open **Settings → Collaborators** (menu wording may vary).
7.  Invite teammates by their GitHub usernames.

Each teammate accepts the invitation and clones the repository:

``` bash
git clone https://github.com/OWNER/REPOSITORY.git
cd REPOSITORY
```

Check the remote:

``` bash
git remote -v
```

## 6. Keeping your branch up to date

Other teammates may merge changes into `main` while you work. Bring
those changes into your feature branch periodically.

First, fetch the latest remote information:

``` bash
git fetch origin
```

### Option A: Merge main into your branch

``` bash
git switch feature/user-registration
git merge origin/main
```

This preserves the branch history and may create a merge commit.

### Option B: Rebase your branch onto main

``` bash
git switch feature/user-registration
git rebase origin/main
```

Rebase replays your commits on top of the latest `main`, creating a more
linear history.

**Important:** Do not rebase a branch that other people are actively
using unless your team has agreed on it. Rebase changes commit history.
If you have already pushed the branch, updating it after a rebase may
require:

``` bash
git push --force-with-lease
```

Use this only when you understand the consequences and have coordinated
with teammates. Avoid plain `git push --force`, which can overwrite
remote work.  

## 7. Writing a good Pull Request

A useful PR explains:

-   **What changed?** Describe the implementation.
-   **Why was it needed?** Explain the requirement or link an issue.
-   **How was it tested?** List tests or manual checks.
-   **Are there risks?** Mention anything reviewers should inspect
    carefully.

Example PR description:

``` markdown
## Summary
- Add user registration form
- Validate email and password fields
- Display validation messages

## Testing
- Tested valid registration
- Tested invalid email
- Tested empty required fields

## Related issue
Closes #12
```

Before opening a PR, check that:

-   Your branch is based on an up-to-date `main`.
-   The change has a focused purpose.
-   You have tested the relevant functionality.
-   You have not committed passwords, API keys, or other secrets.
-   Documentation is updated when necessary.
-   The PR description explains the change.

## 8. Code reviews

A code review is a teammate's examination of proposed changes before
they are merged.

Reviewers should consider:

-   **Correctness:** Does the code do what it should?
-   **Readability:** Can another developer understand it?
-   **Maintainability:** Will it be easy to change later?
-   **Security:** Are there unsafe operations or exposed secrets?
-   **Testing:** Are important cases covered?
-   **Scope:** Does the PR contain only changes related to its task?

Good review etiquette:

-   Discuss the code, not the person.
-   Explain why a change is needed.
-   Ask questions when uncertain.
-   Keep comments specific and constructive.
-   The author should respond to feedback and push updates to the same
    branch.

On GitHub, reviewers can comment, approve, or request changes.

## 9. Example: a team of three developers

Imagine three people are building a university project:

-   Developer A: user authentication.
-   Developer B: dashboard interface.
-   Developer C: database integration.

They start from the same `main` branch, but each creates a separate
branch:

``` text
main
├── feature/authentication
├── feature/dashboard
└── feature/database
```

Each developer commits and pushes their work independently. They open
PRs, review one another's changes, resolve conflicts if needed, and
merge approved work into `main`.

After the PRs are merged, everyone updates their local `main`:

``` bash
git switch main
git pull origin main
```

They now have the latest integrated version of the project.

## 10. Key takeaways

1.  Use Git to track changes and GitHub to coordinate collaboration.
2.  Keep `main` stable; do your work on task-specific branches.
3.  Fetch or pull regularly so your branch does not drift too far
    behind.
4.  Commit small, meaningful changes.
5.  Push your branch and open a PR instead of directly changing `main`.
6.  Review teammates' code respectfully and carefully.
7.  Resolve conflicts by understanding both changes.
8.  Never commit secrets.
9.  Agree on branch names, commit messages, and review rules as a team.
