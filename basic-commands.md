# Git & GitHub: Basic Commands

A practical quick reference for the Git commands you will use most often
when working with GitHub repositories.

> **Git** is a version-control system that tracks changes in your
> files.\
> **GitHub** is a platform for hosting Git repositories and
> collaborating with others.



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



## 3. Stage and Commit Changes

### Stage a specific file

``` bash
git add filename
```

### Stage all changes in the current directory

``` bash
git add .
```

### Unstage a file

``` bash
git restore --staged filename
```

This removes the file from the staging area but keeps your changes.

### Commit staged changes

``` bash
git commit -m "Describe your changes"
```

A commit saves a snapshot of the staged changes.

### Stage and commit tracked changes in one step

``` bash
git commit -am "Describe your changes"
```

This does **not** include new, untracked files. Use `git add` for those.  

## 4. Connect to GitHub

### View configured remote repositories

``` bash
git remote -v
```

### Add a GitHub remote

``` bash
git remote add origin https://github.com/username/repository.git
```

`origin` is the conventional name for the main remote repository.

### Change the remote URL

``` bash
git remote set-url origin https://github.com/username/repository.git
```

## 5. Push and Pull Changes

### Push a branch to GitHub

``` bash
git push origin main
```

### Push and set the upstream branch

For the first push of a new local branch:

``` bash
git push -u origin branch-name
```

After setting the upstream, you can usually use:

``` bash
git push
```

### Download and integrate remote changes

``` bash
git pull
```

Or specify the remote and branch:

``` bash
git pull origin main
```

### Download remote updates without integrating them

``` bash
git fetch
```

`fetch` updates your remote-tracking information but does not merge the
changes into your current branch.  

## 6. A Typical Daily Workflow

For a project you have already cloned:

``` bash
# 1. Check your current branch and working tree
git status

# 2. Get the latest changes
git pull

# 3. Create a branch for your task
git switch -c feature/your-feature

# 4. Make changes, then stage them
git add .

# 5. Commit your changes
git commit -m "Add your feature"

# 6. Push the branch to GitHub
git push -u origin feature/your-feature

# 7. Open a Pull Request on GitHub
```

For a simple project where you work directly on `main`, the shorter
workflow is:

``` bash
git pull
git add .
git commit -m "Describe your changes"
git push
```
