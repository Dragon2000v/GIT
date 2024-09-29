# Comprehensive Git and SSH Guide

This guide covers essential Git commands and SSH setup for version control and remote repository management.

## Git Configuration

### Setting Up Your Identity

```bash
git config --global user.name 'UserName'
git config --global user.email 'temp@gmail.com'
```

### Viewing Your Git Configuration

```bash
git config --list
```

## SSH Key Generation and Management

### Generate SSH Key

```bash
ssh-keygen -t rsa -b 4096 -C "temp@gmail.com"
```

### Start SSH Agent

```bash
eval "$(ssh-agent -s)"
```

### Add SSH Key

For Windows:

```bash
ssh-add ~/.ssh/id_rsa
```

For Mac:

```bash
ssh-add --apple-use-keychain ~/.ssh/id_rsa
```

### View SSH Public Key

```bash
cat ~/.ssh/id_rsa.pub
```

## Remote Repository Management

### Connect Local to Remote Repository

```bash
git remote add origin git@github.com:UserName/my-notes.git
```

### Check Remote Repository Connection

```bash
git remote -v
```

### Update Remote Repository URL

```bash
git remote set-url origin git@github.com:UserName/my-notes.git
```

## Basic Git Operations

### Check Repository Status

```bash
git status
```

### Add Files to Tracking

```bash
git add file.js  # Add specific file
git add *.txt    # Add all .txt files
git add .        # Add all files
git add -A       # Add all changes
```

### Rename Files

```bash
git mv name.js newName.js
```

### Remove Files from Version Control

```bash
git rm --cached my-password.txt  # Remove from Git but keep locally
git reset my-passwords.txt       # Unstage file
```

### Reset to Last Commit

```bash
git reset
```

### Commit Changes

```bash
git commit -m "add a new task"
git commit --amend -m 'new text'  # Amend last commit
```

### View Commit History

```bash
git log
git log -n 2
git log --since=2.weeks
git log --author='UserName'
```

## Stash Management

```bash
git stash
git stash save 'my-comment'
git stash list
git stash pop
git stash apply stash@{56f4530}
git stash drop stash@{56d4530}
git stash clear
```

## Pushing Changes

```bash
git push
git push -u origin main
```

## Branch Management

### Rename Default Branch

```bash
git branch -M main
```

### List Branches

```bash
git branch -a   # All branches
git branch      # Local branches
git branch -r   # Remote branches
```

### Create and Switch Branches

```bash
git switch -c page-header
git switch branch_name
```

### Fetch and Pull Changes

```bash
git fetch
git pull origin footer
```

### Merge Branches

```bash
git switch main
git pull origin main
git merge page-header
git push origin main
```

### Delete Branches

```bash
git branch -d page-header         # Delete merged branch
git branch -D page-header         # Force delete unmerged branch
git push origin --delete footer   # Delete remote branch
```

Remember to use these commands carefully, especially those that delete or modify branches and commits.
