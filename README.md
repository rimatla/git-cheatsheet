### How to remove a dir ex:(.idea or node_modules) from existing github repo.
`git rm -r --cached .idea`

### Sync your local repo to a RE-NAMED repo on github
`git remote set-url origin https://github.com/rimatla/repo_name.git`

### Write text with "code syntax" on README.md
#### See ex: `myCode.js`.

### Hyperlinks
`[CakePHP](http://www.cakephp.org) - The rapid development PHP framework`

### Clone repo from a specific commit ie: first commit 
`git clone --depth=1 https://github.com/angular/angular-seed.git <your-project-name>`

### Images
![alt text](app.png?raw=true "app image")

### Stage and commit 
`git commit -a -m 'message'`

### Delete file from repo
`git rm file_name`

### Permanently Delete a repo, caution with `rf`
`rm -rf .git`

### Force a push to master branch
`git push -f -u origin master`

### Add a new dir project to an existing (previously created) repo
`git remote add origin https://github.com/username/repo_name.git`


### Rollback a github repository to a specific commit
`git reset --hard 'your_commit_id'`
`git push -f -u origin master `


### Create and/or remove files
`echo '.idea' >> .gitignore`,
`git rm -r --cached .idea`,
`git add .gitignore`,
`git commit -m 'your msg'`,
`git push`

### Undo a git init
#### If you just inited it, you can just delete it:
`rm -rf .git`

### List Remote Branches
`git branch ls-remote`
`git branch -a`

### Fetch Newly Created Branches
`git fetch`

### List Current Branch
`git branch`

### Checkout a Branch
`git checkout branch_name`

### See changes before commit
`git diff`
#### hit enter
#### q ends it

### Undo commit
`git reset HEAD~`

### Find what remote url owns a given repo
`git remote show origin`


### Remote rejected (shallow update not allowed) ERROR
#### This means that you have to unshallow your repository. To do so you will need to add your old remote again.
`git remote add old <path-to-old-remote>`

#### After that we use git fetch to fetch the remaining history from the old remote
`git fetch --unshallow old`

#### Log History
`$ git log`

#### Fixes typos on last commit messages 
`$ git commit --amend -m 'new message'`

## VIM
#### To save: type  `:wq`, then press enter
#### To quit: type  `:q!`, then press enter

### Discard Changes to file
`git checkout -- file_name`

### Unstage a added file
`git reset HEAD file_name`

### To see commit graph
`git log --all --decorate --oneline  --graph`

### print file on cli
`cat file_name`

### create new dir and file at the same time
`mkdir name && touch name/file.js`

### remove a file
`rm file_name`

### remove a dir
`rm -r dir_name`

### to move files
`mv file_name path`