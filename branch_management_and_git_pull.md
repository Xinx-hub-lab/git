# Git Pull & Branch Management

## Push Local Changes

### 1. Check Git Status
```bash
git status
```

### 2. 

git push -u origin main

## Reset SSH Key (Optional)

If asked for users name and password, update the repository URL by SSH key.

### 1. Check Git Status
```bash
git status
```

### 2. Reset SSH Key

```bash
git remote set-url origin git@github.com:<your-username>/<your-repo-name>.git
```



## Rename and Delete Branch

### 1. Check Local and Remote Branches
```bash


## check local branches
git branch

## check remote branches
git branch -r
```


https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax

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
