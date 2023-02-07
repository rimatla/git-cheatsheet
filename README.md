# • Add Origin

### - Sync your local repo to a RE-NAMED repo on github

`git remote set-url origin https://github.com/rimatla/repo_name.git`

### - Add a new dir project to an existing (previously created) repo

`git remote add origin https://github.com/username/repo_name.git`

### - Find what remote url owns a given repo

`git remote show origin`

# • README

### - Hyperlinks

`[CakePHP](http://www.cakephp.org) - The rapid development PHP framework`

### - Images

`![alt text](app.png?raw=true "app image")`

### - Write text with "code syntax" on README.md

#### See ex: `myCode.js`.

# • CLONE

### - Clone repo from a specific commit ie: first commit

`git clone --depth=1 https://github.com/angular/angular-seed.git <your-project-name>`

# • COMMITS

### - Stage and commit

`git commit -a -m 'message'`

### - Fixes typos on last commit messages

`$ git commit --amend -m 'new message'`

### - Undo commit (with files already commited to remote)
`git reset --soft HEAD^`
or
`git reset HEAD~`

### - Rollback a github repository to a specific commit

`git reset --hard 'your_commit_id'`
`git push -f -u origin master`

### - See all unpushed commits or commits that are not in another branch

`git cherry -v`

### - Compare against another (upstream) branch like:

`git cherry -v origin/somebranch`

## - SQUASH Commits

- `git rebase -i HEAD~N`
- On VIM: `CW, esc, .` (this will change the desired word and period will repeat the previous actions)
- Pass the desired flag **before each commit message**
- You may need to use `-f` when pushing if your rebased branch was previously pushed before

## - if there are only two commits you want to merge, and they are the "most recent two"

`git reset --soft "HEAD^"`
`git commit --amend`

### - Amend Most Recent Commit Message

`git commit --amend`

# • DELETE

### - Delete file from repo

`git rm file_name`

### - Permanently Delete a repo, caution with `rf`

`rm -rf .git`

### - How to remove a dir ex: `.idea or node_modules` from existing github repo.

`git rm -r --cached .idea`

### - How to remove already commited .DS_STORE

`find . -name .DS_Store -print0 | xargs -0 git rm -f --ignore-unmatch`

### - Create and/or remove files

```
echo '.idea' >> .gitignore,
git rm -r --cached .idea,
git add .gitignore,
git commit -m 'your msg',
git push
```

# • Discard

### - Dicard ALL changes

`git checkout .`

### - Discard Staged and Working Directories changes

`git reset --hard`

### - Discard everything including newly created files

- To see what's been removed `git clean -nfd`
- To delete `git clean -fd`

### - Undo a git init

#### If you just inited it, you can just delete it:

`rm -rf .git`

# • PUSH

### - Force a push to master branch

`git push -f -u origin master`

# • BRANCHES

### - Create and checkout branch

`git checkout -b <branch-name>`

### - Delete a branch

`git branch -d <branch-name>`

### - Delete remote branch

`git push origin --delete branch-name`

### - Rename a branch

`git branch -m <new_name>`

### - Create a branch

`git branch <branch-name>`

### - Checkout a Branch

`git checkout <branch_name>`

### - List Remote Branches

`git branch ls-remote`
`git branch -a`

### - Fetch Newly Created Branches

`git fetch`

### - List Current Branch

`git branch`

# • LOG

### - To see log and commits on a branch graph

`git log --all --decorate --oneline --graph`

### - One Line Log

`git log --oneline`

### - Log History

```
git log
git log <filename>
```

# • DIFF

### - See changes before commit

`git diff`

#### hit enter

#### q ends it

### - See differance between master and local branch before merging

`git diff master ..branch-name`

# • Case Sensitive File Renamed

### - Tell remote origin to compute a renamed file locally

`git mv -f OldFileNameCase newfilenamecase`

# • VIM

#### - To type/insert: type `i`

#### - When finished editing the file, click the `esc` key

#### - To save: type `:wq`, then press enter

#### - To quit: type `:q!`, then press enter

#### - To change word: type `cw`

#### - To delete type `dd`

#### - To undo type `u`

# • Linux Commands

### - print file on cli

`cat file_name`

### - create new dir and file at the same time

`mkdir name && touch name/file.js`

### - remove a file

`rm file_name`

### - remove a dir

`rm -r dir_name`

### - to move files

`mv file_name path`

### - Toggle between directories

`cd -`

### - Clean terminal window

- `ctr l`
- `cmd k`
- `ctr u`

### - Bring Cursor Back to begining of line

`ctr a`

### - Bring Cursor back by one word

`ctr e`

### - Delete the word immediately before, or to the left of, the cursor.

`ctl w`

### - Move cursor to the next word on the line

`esc f`

### - Move cursor to the next word on the line

`esc b`

### - Remove all node modules (monorepo)

`rm -rf packages/*/node_modules`

# • Merge and/or Discard

### - Discard Changes to file

`git checkout -- file_name`

### - Discard Changes to all files

`git checkout -- .`

### - Unstage a added file

`git reset HEAD file_name`

### - Fast Forward Merge

```
git checkout master
git merge branch-name
```

### - Certify what branches were merged

`git branch --merged`

### - 3-way Merge

`git merge branch-name`

# • Merge Conflicts

### - Abort a merge during a merge conflict situation

`git merge --abort`

### - Checkout a commit directly, not through a branch, results in a detached HEAD state

`git checkout (commit-hash)`

## - Merging changes from a remote branch

### - Make sure you have the latest data from upstream

`git fetch upstream`

### - Create and switch to a new branch based on master to explore the conflict

`git checkout -b explore-conflict upstream/master`

### - Now try merging the unmergeable-branch into it

`git merge upstream/unmergeable-branch`

### - Fix Conflits, then:

`git add file-name`,
`git commit -m "fixed conflict"`

ps: Create new branches when resolving conflicts

- Branches are cheap and disposable.
- Rather than risk messing up the branch you’ve been working on, create a new one specially for the purpose of discovering what sort of conflicts arise, and to give you a place to work on resolving them without disturbing your work so far.

# • STASH

#### - Save changes for later use:

`git stash`

#### - See list of stashed changes:

`git stash list`

#### - See all edits done on previous stashes points:

`git stash list -p`

#### - To show files changed in the last stash:

`git stash show`

#### - To view the content of the most recent stash:

`git stash show -p`

#### - To view the content of an arbitrary stash:

`git stash show -p stash@{1}`

#### - Apply stashed changes (applies the most recent one)

`git stash apply`

#### - Apply a specific stashed change

```
git stash list
git stash apply <label-name>
```

#### - Discard a stash

`git stash pop`

#### - Add message w/ stash

`git stash save "message"`

#### - To clear all of stashes at once:

`git stash clear`

# • PULL

### - Pull all changes

`git pull --all`

# Origin

### - Incorporate origin master changes

```
git checkout master
git fetch
git merge origin/master
```

# Upstream

### - Incorporate upstream master changes

```
git checkout master
git fetch upstream
git merge upstream/master
```

PS: Note that here instead of **git fetch** followed by **git merge**, you could have run **git pull**. The pull operation does two things: it fetches updates from your GitHub fork (origin), AND merges them. However, be warned that occasionally git pull won’t always work in the way you expect, and doing things the explicit way helps make what you are doing **clearer**. git fetch followed by git merge is generally the **safer** option.

# • Workflow

`fork > clone > branch > edit > stage > commit > push > pull request > merge`

## ps:

### - When you ready to push, do it from your local branch

`push origin <local-branch>`

### - Send pull request `from` your local branch

### - Keeping master ‘clean’

You could of course have **merged** your new **branch** into your **master** branch, and sent me a **pull request from that**. But, once again, it’s a good policy to **keep** **your master branch**, on GitHub too, **clean** of changes you make, and only to pull things into it from **upstream**.

In fact the same thing goes for other branches on my upstream that you want to work with. Keeping them clean isn’t strictly necessary, but it’s nice to know that you’ll always be able to pull changes from upstream without having to tidy up merge conflicts.

# • Obscure Errors

##### - Remote rejected (shallow update not allowed) ERROR

##### - This means that you have to unshallow your repository. To do so you will need to add your old remote again.

`git remote add old <path-to-old-remote>`

#### - After that we use git fetch to fetch the remaining history from the old remote

`git fetch --unshallow old`

# • Alias Examples

```
alias gs='git status '
alias ga='git add '
alias gb='git branch '
alias gc='git commit'
alias gd='git diff'
alias go='git checkout '
alias gk='gitk --all&'
alias gx='gitx --all'
```

# • Work flow

`git branch`
`git checkout master`

#### Once on master and ready to pull updates, use the following:

`git fetch`
`git merge origin/master`

#### Now that I am all up to date with the remote repo, I'll create a branch

`git checkout -b branch-name`
`git branch`

#### Edit and commit

`git commit -am 'my message in present tense'`

#### Push local branch

`git push origin branch-name`

#### Tracking remote branches

`git branch -r`

#### To keep my local repo 100% in sync with deleted remote branches, I make use of this command:

The -p or --prune flag, after fetching, will remove any remote-tracking branches which no longer exist.
`git fetch -p`

#### Pull request - Once the reviewer has approved the editors updates...

`git checkout my-feature-branch`
`git pull origin branch-name`

#### Make sure that the feature branch is up to date with master, while in the feature branch, execrate the following:

`git pull origin master`

#### Now that I know that the feature branch is up to date with the remote repo and that it has the latest code from master, I can now merge these branches

`git checkout master`
`git pull origin master`
`git merge --no-ff my-feature-branch`

Notice the --no-ff flag in the merge command. This flag keeps the repo branching history from flattening out. If I were to look at the history of this branch, using GitX for example, when using the --no-ff flag, I will see the appropriate bump illustrating the history of the feature branch. This is helpful information. If I didn't use this flag, then Git will move the commit pointer forward.

#### Now that I have merged the code, the feature branch by definition is obsolete. First, delete the branch from the local repo.

`git branch -d branch-name`

#### Finally...

#### If the feature branch was pushed to the repo, as it should have been per the workflow we described, you will want to delete this from the remote repo as well...

`git push origin --delete my-feature-branch`

#### PS: My branch was rejected?

> AKA: Updates were rejected because the tip of your current branch is behind

This is a special case when working on a team and the branch I am are pushing is out of sync with the remote. To address this, it's simple, pull the latest changes:
`git pull origin branch-name`

# • Greyed out icon on remote GitHub directories

```
git rm --cached <folder_name>
git add .
git commit -m "<your_message>"
git push --all
```

# • SSH

### • How to add SSH keys to your github/gilab
https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent

- List existing ssh keys, if any
`ls -al ~/.ssh`

- Create the key
  `ssh-keygen -t ed25519 -C  "$your_email@foobar.com"`

> To accept the default path just hit Enter on your keyboard

- View the Public Key
  `cat ~/.ssh/id_ed25519.pub`

- Copy Public Key
`pbcopy < ~/.ssh/id_ed25519.pub`

- To see if it worked:
`ssh -T git@github.com`

> Your key will appear – copy the key text starting from ssh-rsa all the way to your username/host.

- Add the Key to Your GitLab/GitHhub Profile

- To avoid entering a passphrase everytime
  `$ ssh-add`

# • Fork

### • How to Fork and PR to main Stream from your Fork

- Fork a repo
- Clone your _forked_ repo
- Check for the remote version `$ git remote -v`
- Add the Main Repo - not yout fork but rather the one you forked - as remote upstream `$ git remote add upstream 'main_repo_url'`
- Pull latest upstream changes `$ git pull upstream master`
- Pull latest upstream changes w/ rebase `$ git pull --rebase upstream master`

# • PR from Fork

- Make changes inside your fork, stage, commit
- Push change: `git push origin my-feature-branch`
- Create a PR from your fork into the main repo

# • GitLens- How to Compare Changes Between Branches

- On VSC >GitLens:Compare Working Tree With...
- Choose desired option

# • Git Config

- Set a Git username: `$ git config --global user.name "Mona Lisa"`
- Confirm that you have set the Git username correctly: `$ git config --global user.name` > Mona Lisa
- Repeat process for `$ git config --global user.email you@example.com`

# • Commit History Trouble Shooting

- `git reset --soft HEAD~1`
- stash your changes
- `git reset --hard HEAD~10`
- Merge Origin Master
- stash apply
- stage, commit and force push your branch

# • node_modules

#### Delete all node_modules recursively

- Print out a list of directories to be deleted:

`find . -name 'node_modules' -type d -prune`

- Delete directories from the current working directory:

`find . -name 'node_modules' -type d -prune -exec rm -rf '{}' +`

- To Delete folders one by one and printing the folder being deleted

`find . -name 'node_modules' -type d -prune -print -exec rm -rf '{}' \;`

# • rsync Data Transfer (External HD)

- sudo rsync -vaE --progress /Volumes/SourceName /Volumes/DestinationName

# • Rename File on Git Remote

`git mv -f OldFileNameCase newfilenamecase`

# • JEST

#### Clear Cache

`yarn jest --clearCache`

# • New Private Remote Repo under new github username

`git remote add origin https://USERNAME:PASSWORD@github.com/USERNAME/REPONAME.git`

# • See remote credentials username, etc

`git config --list`

# Multiple username on github with multiple SSH keys

- Create default key

`ssh-keygen`

- This should create a `id_rsa` and `id_rsa.pub` file

- Grab the contents of the public file
  `cat id_rsa.pub`

- Add SSH key to the github account

- Clone repo from SSH

- Try pushing code back upstream

-Edit: Alternatively create a [EdDSA key](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
- Custom Name 👇
```
ssh-keygen -t ed25519 -f ~/.ssh/ed25519_customname -C "myemail@gmail.com
```

#### Set up a config file

```
#Account1
Host github.com
HostName github.com
IdentityFile ~/.ssh/id_rsa

#Account2
Host github.com-abt
HostName github.com
IdentityFile ~/.ssh/abt_id_rsa
```

- Create a config file inside `.ssh` folder

- Create a new ssh file name

- This time provide a file name `ssh-keygen -f filename_id_rsa`

- Grab the contents of the new public file
  `cat filename_id_rsa.pub`

- Add SSH key to the github account

- Clone repo from SSH

- Add hostname to the ssh clone i.e: `git clone git@github.com-hostname:username/reponame.github.io.git`

- Try pushing code back upstream

#### Edit credentials on .gitconfig

- `git config --global credential.useHttpPath true`

> **Note**
> We might need to add your ssh keys and agent to your (either) .zshrc or .bashrc 
> eval "$(ssh-agent -s)"
> ssh-add --apple-use-keychain ~/.ssh/ed25519_example

- config your repo locally 
`git config user.name newusername`
`git config user.email useremail` 


- push code 
