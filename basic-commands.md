# Git & GitHub: Basic Commands

A practical quick reference for the Git commands you will use most often
when working with GitHub repositories.

> **Git** is a version-control system that tracks changes in your
> files.\
> **GitHub** is a platform for hosting Git repositories and
> collaborating with others.

------------------------------------------------------------------------

## 1. Configure Git

Set the name and email that will appear in your commits:

``` bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

Check your configuration:

``` bash
git config --global --list
```
------------------------------------------------------------------------

## 2. Start Working with a Repository

### Clone an existing GitHub repository

``` bash
git clone https://github.com/username/repository.git
```

This downloads the repository and creates a local copy.

### Initialize a repository

Use this when you already have a project folder and want to start
tracking it with Git:

``` bash
git init
```

### Check the repository status

``` bash
git status
```

Shows which files are modified, staged, or untracked.
