# Branching

## What is a branch?

A branch is a temporary copy of the project. We can work on it without breaking the main version (`main`).

## Create a new branch

This command creates a new branch and switches to it:

```bash
git checkout -b branch-name
```

## List all branches

This shows all branches. The current branch has a `*` next to it:

```bash
git branch
```

## Switch to another branch

```bash
git checkout main
```

## Delete a branch

After the work is merged into `main`, we can delete the branch:

```bash
git branch -d branch-name
```

## Why don't we work directly on main?

- `main` is the official and working version of the project. It should not break.
- If everyone works on `main`, our changes get mixed up.
- With separate branches, teammates can review the changes before they go into `main`.