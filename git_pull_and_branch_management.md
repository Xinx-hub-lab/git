# Git Pull & Branch Management

## Pull Remote Changes

### 1. Check Git Status
Check the state of the local changes. This command will not show changes from the remote repository.
```bash
git status
```

### 2. Pull Remote Changes
Pull remote changes to ensure your local repository is up to date. Attempting to push (`git push origin main`) without pulling can lead to errors if there are remote changes.
```bash
git pull origin main
```
### 3. Create a Merge Commit
If both the local and remote repositories have changes, Git may default to a merge strategy, potentially leading to a merge conflict. 

Configure Git to use the merge strategy by default:
```bash
git config pull.rebase false
```
This is only needed once. Return to Step 2 to pull the remote changes. 

This updates your local repository with remote files but does not yet push your local changes to the remote repository.

### 4. Commit Changes
If a merge commit is necessary, Git will prompt you to create a commit message:
- Press `i` to switch to Insert mode
- Type the commit message
- Press `ESC` to exit Insert mode and return to Command mode
- Type `:wq` (write and quit) and press `Enter` to save commit message and exit Vim

## Push Local Changes

### 1. Add Files, Commit, and Push
```bash
git add .
git commit -m "Your commit message"
git push origin main
```

### 2. Handle Errors
If pushing fails, it may be due to the remote having updates that your local branch does not have. If this occurs:

- First, pull the remote changes as described in steps 2 and 3.
- After resolving any conflicts and successfully pulling, attempt to push again.


## Reset SSH Key (Optional)

If asked for users name and password, update the repository URL by SSH key.

### 2. Reset SSH Key

```bash
git remote set-url origin git@github.com:<your-username>/<your-repo-name>.git
```



## Rename and Delete Branch (Optional)

### 1. Check Local and Remote Branches
```bash


## check local branches
git branch

## check remote branches
git branch -r
```


## Other Commands
### 6. Check history
Note that `log` stands for `log book` / 航海日志
```bash
git log
git history
```
### 7. Create and switch branches
The first command is for creating a new branch;
The second with the word `checkout` means switch to `branch1`;
The third does both.
Note that `-b` stands for the word `branch`.
```bash
git branch branch1
git checkout branch1
git checkout -b branch1
```
### 8. Delete branch
Note that `-d` stands for the word `delete`.
```bash
git branch -d branch1
```
### 9. Merge branch
```bash
git merge branch1
```
