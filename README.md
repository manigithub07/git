# git



# 1. Initialize a Git repository
mkdir gitlab
cd gitlab
git init
git status

# 2. Create and commit README.md
echo "# My Project" > README.md
git add README.md
git commit -m "Add README file"

# 3. Create and switch to a feature branch
git branch feature
git switch feature
echo "This is a feature" >> README.md
git add README.md
git commit -m "Add feature information"

# 4. Stage a file and view staged changes
echo "Git commands" > commands.txt
git add commands.txt
git status
git diff --staged

# 5. Make two commits and view history
echo "First change" >> commands.txt
git add commands.txt
git commit -m "Add first change"
echo "Second change" >> commands.txt
git add commands.txt
git commit -m "Add second change"
git log --oneline

# 6. Rename the branch to main
git branch -M main
git branch

# 7. Connect local repository to GitHub
git remote add origin https://github.com/USERNAME/REPOSITORY.git
git remote -v

# 8. Push main branch to GitHub
git push -u origin main

# 9. Create, modify and push a dev branch
git switch -c dev
echo "Development work" >> commands.txt
git add commands.txt
git commit -m "Add development work"
git push -u origin dev

# 10. Merge dev into main
git switch main
git merge dev
git push origin main

# 11. Clone a GitHub repository
git clone https://github.com/USERNAME/REPOSITORY.git
cd REPOSITORY
echo "New file" > newfile.txt
git add newfile.txt
git commit -m "Add new file"
git push

# 12. View and change remote URL
git remote -v
git remote set-url origin https://github.com/USERNAME/NEW-REPOSITORY.git
git remote -v

# 13. View uncommitted changes
echo "Some changes" >> README.md
git diff

# 14. Undo the most recent commit while keeping changes
git reset --soft HEAD~1
git status
git log --oneline

# 15. Create and test .gitignore
echo "*.log" > .gitignore
echo "temp/" >> .gitignore
touch error.log
mkdir temp
touch temp/test.txt
git status
