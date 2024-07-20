# Merging Local and Remote Changes

## Pull Remote Changes

### 1. Check Git Status
Check the state of the local changes. This command **will not show changes from the remote repository**.
```bash
git status
```

### 2. Pull Remote Changes
Pull remote changes to ensure your local repository is up to date. Attempting to push (`git push origin main`) without pulling can lead to errors if there are remote changes.
```bash
git pull origin main
```
### 3. Create a Merge Commit
Both the local and remote repositories have changes would potentially lead to a merge conflict. We can reconcile the differences by using merge strategy with Configure Git:

```bash
git config pull.rebase false
```
This is only needed once. Return to Step 2 to pull the remote changes. 

This updates your local repository with remote files but **does not yet** push your local changes to the remote repository.

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

If asked for users name and password, update the repository URL by SSH key, since HTTP needs authentication.

```bash
git remote set-url origin git@github.com:<your-username>/<your-repo-name>.git
```

## More about Divergence Management
In the first section, we have showed how to reconcile the differences between local and remote repository. The terminal would ask for preferred method to handle the divergence. There are 3 methods:

### 1. Merge (Default)
Integrates changes from the remote branch into your local branch with a merge commit.
```bash
## Create a merge commit
git pull origin main --no-rebase

## Set as the default behavior, configure it globally
git config --global pull.rebase false
```
### 2. Rebase
Re-applies your local commits **on top of the remote branch**, resulting in a linear history.
```bash
## Reapply local commits on top of the fetched branch
git pull origin main --rebase
## Set as the default behavior
git config --global pull.rebase true
```
### 3. Fast-forward only
Only updates your branch if it can be fast-forwarded. It will fail if there are divergent changes.

```bash
## Updates your branch if it can be fast-forwarded
git pull origin main --ff-only
## Set as the default behavior
git config --global pull.ff only
```



