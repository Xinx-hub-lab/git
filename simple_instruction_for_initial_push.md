# Start with Git!
This README serves as a concise and **quick introductory tutorial for Git and GitHub** for **personal use**. All content is based on tutorials authored by *Colt Steele* on Youtube and the corresponding notes. Please refer to links in Tutorials section for more detailed guidance on Git.

## Tutorials:
1. [Introduction to Git](https://videotutorials.notion.site/Introduction-to-Git-ac396a0697704709a12b6a0e545db049#e0920693bebe4ffd94e973d60bd3f6b4)
2. [Introduction to GitHub](https://videotutorials.notion.site/Introduction-to-GitHub-202af6f64bbd4299b15f238dcd09d2a7)
3. [Learn Git In 15 Minutes](https://www.youtube.com/watch?v=USjZcfj8yxE)
4. [Learn Github in 20 Minutes](https://www.youtube.com/watch?v=nhNq2kIvi9s)

## Initial Setup

### 1. Create a New Folder and Direct
```bash
mkdir my_project
cd my_project
```

### 2. Initialize
```bash
git init
```

### 3. Confirm Initialization
Look for `.git`
```bash
ls -a
```

### 4. Add Files / Create Files
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

### 1. Create New GitHub Repository
Create a repository on GitHub. 

Navigate to GitHub and create a new repository. Include a README if necessary.

### 2. Clone with SSH key
Add the GitHub repository as a remote to the local repository. **Do not use web URL clone**.
```bash
git remote add origin git@github.com:<your-username>/<your-repo-name>.git
```

### 3. Confirm Cloning
```bash
git remote -v
```

You should see:
```bash 
origin	git@github.com:<your-username>/<your-repo-name>.git (fetch)
origin	ggit@github.com:<your-username>/<your-repo-name>.git (push)
```

### 4. Pull README 
If you created a README on GitHub, pull it to the local repository.
```bash
git config pull.rebase true
git pull origin main
```

### 5. Rename Branch Master as Main
If the main branch is named `master`, rename it to `main`.

```bash
git branch
git branch -m master main
```

### 6. Push Files to GitHub Repository
```bash
git push -u origin main
```
