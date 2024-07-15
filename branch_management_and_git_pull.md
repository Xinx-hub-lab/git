# Git Pull & Branch Management

## Pull Remote Changes

### 1. Check Git Status
`git status` will show local changes, but not remote ones. 
```bash
git status
```

### 2. Pull Remote Changes
You can try pushing first and usually there will be an error. Therefore we need to first pull the remote changes.
```bash
git pull origin main
```
### 3. Create a Merge Commit
An error occured as local and remote repository has both made changes. This makes git pull use the merge strategy by default. It will create a merge commit in your local repository to reconcile any differences between your local branch and the remote branch. This keeps the history of both branches and merges them together.
```bash
git config pull.rebase false
```
Return to Step 2 to pull the remote changes. Note that the remote files has been updated in the local repository, but not the local files to the remote repository.

### 4. 
Press `i` to switch to Insert mode. 

Type your commit message

Press ESC to exit Insert mode and return to Command mode

To save your commit message and exit Vim, type :wq (write and quit) and press Enter.

## Push Local Changes

### 1. Add Files, Commit, and Push
```bash
git add .
git commit -m "Your commit message"
git push origin main
```

### 2. Error occurred?
If Step 1 does not work, try pulling first.


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
