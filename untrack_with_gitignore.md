
https://www.freecodecamp.org/news/gitignore-file-how-to-ignore-files-and-folders-in-git/

.DS_Store is a hidden file created by the macOS operating system in each folder to store custom attributes of the folder, such as the position of icons, the choice of a background image, and other view settings. The .DS_Store file helps macOS remember how you like to view and organize your files in that folder. It is hidden by default, but would appear when uploading to the cloud and Github. It would be unwise to upload them as well since team members would use another system like windows. The following are steps for removing .DS_Store.

How to Clean Up .DS_Store Files in a Git Repository
1. Create/Update .gitignore
echo ".DS_Store" >> .gitignore
git add .gitignore
git commit -m "Add .DS_Store to .gitignore"

2. Remove Existing .DS_Store Files
find . -name .DS_Store -print0 | xargs -0 git rm --ignore-unmatch
git commit -m "Remove .DS_Store files"
git push origin main  # or your current branch name

3. Set Up Global Ignore (Optional)
git config --global core.excludesfile ~/.gitignore_global
echo ".DS_Store" >> ~/.gitignore_global



git rm -r --cached dataset/