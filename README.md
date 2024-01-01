# Start with Git!

## Tutorials:
https://videotutorials.notion.site/Introduction-to-Git-ac396a0697704709a12b6a0e545db049#e0920693bebe4ffd94e973d60bd3f6b4
https://videotutorials.notion.site/Introduction-to-GitHub-202af6f64bbd4299b15f238dcd09d2a7

## Commands:

### 1. Create a new folder and direct
### 2. Initialize
```bash
git init
```
### 3. Confirm initialization
Look for `.git`
```bash
ls -a
```
### 4. Add files / create files
Use `touch file.html` creating command for trial.
```bash
git add .
git add file.py file2.py
```
### 5. Commit 
We can commit for multiple times, note that `m` stands for the word `message`.
```bash
git commit -m "Your commit message"
```
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
```bash
git branch branch1
git checkout branch1
git checkout -b branch1
```
### 8. Delete branch
```bash
git branch -d branch1
```
### 9. Merge branch
```bash
git merge branch1
```


git remote add origin https://github.com/Xinx-hub-lab/ml_homework_backup.git
