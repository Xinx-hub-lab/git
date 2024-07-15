# Start with Git!
This README serves as a concise and **quick introductory tutorial for Git and GitHub** for **personal use**. All content is based on tutorials authored by *Colt Steele* on Youtube and the corresponding notes. Please refer to links in Tutorials section for more detailed guidance on Git.

## Tutorials:
1. [Introduction to Git](https://videotutorials.notion.site/Introduction-to-Git-ac396a0697704709a12b6a0e545db049#e0920693bebe4ffd94e973d60bd3f6b4)
2. [Introduction to GitHub](https://videotutorials.notion.site/Introduction-to-GitHub-202af6f64bbd4299b15f238dcd09d2a7)
3. [Learn Git In 15 Minutes](https://www.youtube.com/watch?v=USjZcfj8yxE)
4. [Learn Github in 20 Minutes](https://www.youtube.com/watch?v=nhNq2kIvi9s)

## Initializations

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
We can commit for multiple times, note that `-m` stands for the word `message`.
```bash
git commit -m "Your commit message"
```

## Push to GitHub
### 1. Initial commit to local repository
Repeat **Initializations** from step 1 to 5 to make initial commit to the local repository.
### 2. Create new GitHub repository
Create a repository on GitHub. Add README if needed. If it is not included in the new repository then Step 5 is not needed.
### 3. Clone with SSH key
```bash
git remote add origin git@github.com:<your-username>/<your-repo-name>.git
```
### 4. Confirm Cloning
Output would be 
`origin	git@github.com:<your-username>/<your-repo-name>.git (fetch)`
`origin	ggit@github.com:<your-username>/<your-repo-name>.git (push)`

```bash
git remote -v
```
### 5. Pull README 
```bash
git config pull.rebase true
git pull origin main
```
### 6. Rename Branch master as main
Check for existing branch by `git branch`, output would show only one branch `*master`.
Then rename master to main.

```bash
git branch
git branch -m master main
```
### 7. Push files to GitHub repository
```bash
git push -u origin main
```
