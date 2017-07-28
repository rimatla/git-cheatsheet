# How to remove a dir ex:(.idea or node_modules) from existing github repo.
### git rm -r --cached .idea

# Sync your local repo to a RE-NAMED repo on github
### git remote set-url origin https://github.com/rimatla/repo_name.git

# Write text with "code syntax" on README.md
### See ex: `myCode.js`.

# Hyperlinks
## [CakePHP](http://www.cakephp.org) - The rapid development PHP framework

# Permanently Delete a repo
## rm -rf .git

# Force a push to master branch
## git push -f -u origin master  

# Add a new dir project to an existing (previously created) repo
## git remote add origin https://github.com/username/repo_name.git


# Rollback a github repository to a specific commit
## git reset --hard 'your_commit_id'
## git push -f -u origin master  


# Create and/or remove files
### echo '.idea' >> .gitignore
### git rm -r --cached .idea
### git add .gitignore
### git commit -m 'your msg'
### git push

# Undo a git init
## If you just inited it, you can just delete it:
### rm -rf .git
