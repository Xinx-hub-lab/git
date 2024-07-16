
# Ignore Files and Folders in GIT with .gitignore

By adding `.gitignore`, we can tell GIT to ignore and not track files and folders. The content is based on [Tutorial by Dionysia Lemonaki](https://www.freecodecamp.org/news/gitignore-file-how-to-ignore-files-and-folders-in-git/).


## Basic Workflow
### 1. Create .gitignore

Navigate to the local repository root folder and type the following:
```bash
touch .gitignore
```

### 2. Confirm the Creation
```bash
ls -a
```

### 3. Modify .gitignore
Open and edit the text file `.gitignore` with `nano`.
```bash
nano .gitignore
```
Add the following lines based on your needs:
```bash
## 1. ignore project.txt in root directory
/project.txt

## 2. ignore any project.txt in any folder in root
project.txt

## 3. ignore project.txt in the output folder in the root directory
/output/project.txt  ## OR
output/project.txt

## 4. ignore the folder and all contents within, include a slash
dataset/

## 5. ignore all md files
*.md

# 6. ignores all .md files BUT NOT README.md file
.md
!README.md

# NOTE THAT THIS CANNOT WORK: ignore folder dataset and all its contents but not one file
dataset/
!dataset/test.csv
```

### 4. Save Changes


- Press `Ctrl + O` (the letter O, not zero) to initiate saving the file
- Press `Enter` to confirm and save the changes to the `.gitignore` file
- Press `Ctrl + X` to exit

### 5. Push
```bash
git add .gitignore
git commit -m "Update .gitignore"
git push origin main
```

## Untrack Files and Add to .gitignore

The previous section workflow does not work for files and folders that has been already tracked by Git.

### 1. Create and Edit .gitignore
Follow step 1-4 from the previous section if .gitignore has not been created and editted.

### 2. Remove the Files/Folders from the Tracking Index

`-r` stands for 'recursively', meaning recursively remove every file within the specified directory. 

Use the first command when you want to untrack individual files or when you are certain a directory is empty. Use the second one when you no longer want to track the directory and all its contents within.

```bash
## for files
git rm --cached project.txt

## for folders
git rm -r --cached dataset/
```

### 3. Push the Changes
Follow step 5 from the previous section to add, commit and push the changes in `.gitignore`.


## Example: Clean Up .DS_Store in a Git Repository

`.DS_Store` is a hidden file created by the macOS operating system in each folder to store custom attributes of the folder, such as the position of icons, the choice of a background image, and other view settings. The `.DS_Store` file helps macOS remember how you like to view and organize your files in that folder. 

It is hidden by default, but would appear when uploading to the cloud and Github. The following are steps for removing .DS_Store.

The following steps can also solve the problem if `.DS_Store` has already been tracked by Git.

### 1. Create and Update .gitignore

```bash
echo ".DS_Store" >> .gitignore
git add .gitignore
git commit -m "Add .DS_Store to .gitignore"
```

### 2. Remove Existing .DS_Store Files
```bash
find . -name .DS_Store -print0 | xargs -0 git rm --ignore-unmatch
git commit -m "Remove .DS_Store files"
git push origin main
```

### Additional: Set Up Global Ignore (Optional)
```bash
git config --global core.excludesfile ~/.gitignore_global
echo ".DS_Store" >> ~/.gitignore_global
```



