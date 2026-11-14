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

## Push your branch to GitHub

A new branch only exists on your computer. To send it to GitHub, use:

```bash
git push -u origin branch-name
```

The `-u` option is needed only the first time. After that, `git push` is enough.

## From branch to main (Pull Request)

After pushing, go to the repository on GitHub and create a Pull Request. Your teammates review your changes. If they approve, the branch is merged into `main`.

## Full example

Let's say we want to add a new file called `notes.md`.

```bash
git checkout main                 # go to main
git checkout -b add-notes         # create a new branch
# create and edit notes.md, then:
git add notes.md                  # prepare the file
git commit -m "Add notes file"    # save the change
git push -u origin add-notes      # send the branch to GitHub
```

Next, open a Pull Request on GitHub and ask a teammate to review it.

## Common mistakes

- **Working on main by mistake.** Always run `git branch` first to check which branch you are on.
- **Forgetting to commit before switching branches.** Commit your changes first, then run `git checkout`.
- **Creating a new branch from the wrong branch.** Go back to `main` first (`git checkout main`), then create the new branch.