Using Git
===============

Useful websites
-----------

Interactive Beginners Tutorial: http://try.github.io/

Git book: https://git-scm.com/book/en/v2


Reminder
-----------

Press `minus + shift + s` and `return` to chop/fold long lines!

Show folder content: `ls -la`

Setup
-----------

See where Git is located:
`which git`

Get the version of Git:
`git --version`

Initial setup:
`git config --global user.name "Name"`
`git config --global user.email email@email.com`
`git config --global core.editor subl` or `nano` 
`git config --list`


Help
-----------

Help:
`git help <verb>`
`git <verb> help`


General
-----------

Initialize Git:
`git init`

Initialize a bare repo for sharing/remote:
`git init --bare`

Get everything ready to commit:
`git add .`

Interactive commit:
`git add --patch`
`git add --interactive`

Get custom file ready to commit:
`git add index.html`

Commit changes:
`git commit -m "Message"`

Add and commit in one step:
`git commit -am "Message"`

Verbose commit message:
`git commit -v`

Remove files from Git:
`git rm index.html`

Remove a previously tracked file:
`git rm --cached log.out`

Update all changes to tracked files:
`git add -u`

Remove file but do not track anymore:
`git rm --cached index.html`

Move or rename files:
`git mv index.html dir/index_new.html`

Undo modifications (restore files from latest commited version):
`git checkout -- index.html`

Restore file from a custom commit (in current branch):
`git checkout 6eb715d -- index.html`


Reset
-----------

Go back to commit:
`git revert 073791e7dd71b90daa853b2c5acc2c925f02dbc6`

Undo latest commit: `git reset --soft HEAD~ `

Hard reset (move HEAD and change staging dir and working dir to match repo):
`git reset --hard 073791e7dd71b90daa853b2c5acc2c925f02dbc6`

Update & Delete
-----------

Unstage (undo adds):
`git reset HEAD index.html`

Commit to most recent commit:
`git commit --amend -m "Message"`

Update most recent commit message:
`git commit --amend -m "New Message"`

Log
-----------

Show commits:
`git log`

Show oneline-summary of commits:
`git log --oneline`

Show history of commits as graph:
`git log --graph`

Show history of commits as graph-summary:
`git log --oneline --graph --all --decorate`


Branch
-----------

Show branches:
`git branch`

Create branch:
`git branch branchname`

Change to branch:
`git checkout branchname`

Create and change to new branch:
`git checkout -b branchname`

Rename branch:
`git branch -m branchname new_branchname` or:
`git branch --move branchname new_branchname`

Show all completely merged branches with current branch:
`git branch --merged`

Delete merged branch (only possible if not HEAD):
`git branch -d branchname` or:
`git branch --delete branchname`

Delete not merged branch:
`git branch -D branch_to_delete`


Merge
-----------

True merge (fast forward):
`git merge branchname`

Merge to master (only if fast forward):
`git merge --ff-only branchname`

Merge to master (e a new commit):
`git merge --no-ff branchname`

Stop merge (in case of conflicts):
`git merge --abort`


Stash
-----------

Put in stash:
`git stash save "Message"`

Show stash:
`git stash list`


Gitignore & Gitkeep
-----------

About: https://help.github.com/articles/ignoring-files

Useful templates: https://github.com/github/gitignore

Add or edit gitignore: 
`nano .gitignore`

Track empty dir: 
`touch dir/.gitkeep`

Compare
-----------

Compare modified files (working copy and staging area):
`git diff`

Compare modified files and highlight changes only:
`git diff --color-words index.html`

Compare between staging area and latest commit:
`git diff --staged`

Compare branches:
`git diff master..branchname`

Compare commits:
`git diff 6eb715d` - Working directory and specific commit
`git diff 6eb715d..HEAD` - Specific commit and latest commit
`git diff 6eb715d..537a09f` - Between commits

Compare commits of file:
`git diff 6eb715d index.html`
`git diff 6eb715d..537a09f index.html`


Releases & Version Tags
-----------

Show all released versions:
`git tag`

Create release version with comment:
`git tag -a v1.0.0 -m 'Message'`

Checkout a specific release version:
`git checkout v1.0.0`


Collaborate
-----------

Show remote:
`git remote`

Show remote details:
`git remote -v`

Add remote origin from GitHub project:
`git remote add origin https://github.com/user/project.git`

Add remote origin from existing empty project on server:
`git remote add origin ssh://root@123.123.123.123/path/to/repository/.git`

Remove origin:
`git remote rm origin`

Show remote branches:
`git branch -r`

Show all branches:
`git branch -a`

Compare:
`git diff origin/master..master`

Push (set default with `-u`):
`git push -u origin master`

Push to default:
`git push origin master`

Fetch:
`git fetch origin`

Pull:
`git pull`

Pull specific branch:
`git pull origin branchname`

Merge fetched commits:
`git merge origin/master`

Clone to localhost:
`git clone https://github.com/user/project.git` or:
`git clone ssh://user@domain.com/~/dir/.git`

Clone to localhost folder:
`git clone https://github.com/user/project.git ~/dir/folder`

Clone to current folder:
`git clone //server/share .`

Clone specific branch to localhost:
`git clone -b branchname https://github.com/user/project.git`

Delete remote branch (push nothing):
`git push origin :branchname` or:
`git push origin --delete branchname`


Git Ignore
---------------
To add Icon\r:

`vim .gitignore`
Go to a new line: `Icon`
Add CRLF: `Ctrl-v` `Enter` `Ctrl-v` `Enter`
Write and exit: `Esc` `:wq`
