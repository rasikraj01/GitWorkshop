# GitWorkshop


## Resources : 

- Documentation : [Git Docs](https://git-scm.com/docs)
- Book **PRO GIT** : [Pro Git](https://git-scm.com/book/en/v2)
- Git Notes for Professionals : [Download Link](https://goalkicker.com/GitBook/GitNotesForProfessionals.pdf)
- Cheatsheet : [Pdf](https://jan-krueger.net/wordpress/wp-content/uploads/2007/09/git-cheat-sheet.pdf)
- Markdown Guide : [Link](https://guides.github.com/features/mastering-markdown/)


## CheatSheet

Setup
-----------

See where Git is located:
`which git`

Get the version of Git:
`git --version`

Create an alias (shortcut) for `git status`:
`git config --global alias.st status`


General
-----------

Initialize Git: `git init`

Get everything ready to commit: `git add .`

Get custom file ready to commit: `git add index.html`

Commit changes:
`git commit -m "Message"`

Add and commit in one step:
`git commit -am "Message"`

Remove files from Git:
`git rm index.html`

Update all changes:
`git add -u`

Remove file but do not track anymore:
`git rm --cached index.html`

Move or rename files:
`git mv index.html dir/index_new.html`

Undo modifications (restore files from latest commited version):
`git checkout -- index.html`

Restore file from a custom commit (in current branch):
`git checkout <commit_hash_id> -- index.html`


Reset
-----------

Go back to commit:
`git revert <comit_hash_id>`

Soft reset (move HEAD only; neither staging nor working dir is changed):
`git reset --soft <comit_hash_id>`

Undo latest commit: `git reset --soft HEAD~ `

Mixed reset (move HEAD and change staging to match repo; does not affect working dir):
`git reset --mixed <comit_hash_id>`

Hard reset (move HEAD and change staging dir and working dir to match repo):
`git reset --hard <comit_hash_id>`


Log
-----------

Show commits:
`git log`

Show oneline-summary of commits:
`git log --oneline`

Show oneline-summary of commits with full SHA-1:
`git log --format=oneline`

Show oneline-summary of the last three commits:
`git log --oneline -3`

Show only custom commits:
`git log --author="Sven"`
`git log --grep="Message"`
`git log --until=2013-01-01`
`git log --since=2013-01-01`

Show only custom data of commit:
`git log --format=short`
`git log --format=full`
`git log --format=fuller`
`git log --format=email`
`git log --format=raw`

Show changes:
`git log -p`

Show every commit since special commit for custom file only:
`git log 6eb715d.. index.html`

Show changes of every commit since special commit for custom file only:
`git log -p 6eb715d.. index.html`

Show stats and summary of commits:
`git log --stat --summary`

Show history of commits as graph:
`git log --graph`

Show history of commits as graph-summary:
`git log --oneline --graph --all --decorate`


Branch
-----------

Show branches:
`git branch`

Create branch:
`git branch <branch_name>`

Change to branch:
`git checkout <branch_name>`

Create and change to new branch:
`git checkout -b <branch_name>`

Rename branch:
`git branch -m <branch_name> <new_branch_name>` or:
`git branch --move <branch_name> <new_branch_name>`

Show all completely merged branches with current branch:
`git branch --merged`

Delete merged branch (only possible if not HEAD):
`git branch -d <branch_name>` or:
`git branch --delete <branch_name>`

Delete not merged branch:
`git branch -D <name_of_branch_to_delete>`


Merge
-----------

True merge (fast forward):
`git merge <branch_name>`

Merge to master (only if fast forward):
`git merge --ff-only <branch_name>`

Merge to master (force a new commit):
`git merge --no-ff <branch_name>`

Stop merge (in case of conflicts):
`git merge --abort`

Merge only one specific commit:
`git cherry-pick <commit_hash_id>`

Rebase:
`git checkout <branch_name>` » `git rebase master`
or:
`git merge master <branch_name>`
(The rebase moves all of the commits in `master` onto the tip of `<branch_name>`.)

Cancel rebase:
`git rebase --abort`

Squash multiple commits into one:
`git rebase -i HEAD~3`


Collaborate
-----------

Show remote:
`git remote`

Show remote details:
`git remote -v`

Add remote upstream from GitHub project:
`git remote add upstream https://github.com/user/project.git`

Add remote upstream from existing empty project on server:
`git remote add upstream ssh://root@123.123.123.123/path/to/repository/.git`

Fetch:
`git fetch upstream`

Fetch a custom branch:
`git fetch upstream <branch_name>:local_<branch_name>`

Merge fetched commits:
`git merge upstream/master`

Remove origin:
`git remote rm origin`

Show remote branches:
`git branch -r`

Show all branches:
`git branch -a`

Create and checkout branch from a remote branch:
`git checkout -b local_<branch_name> upstream/remote_<branch_name>`

Compare:
`git diff origin/master..master`

Push (set default with `-u`):
`git push -u origin master`

Push:
`git push origin master`

Force-Push:
`git push origin master --force

Pull:
`git pull`

Pull specific branch:
`git pull origin <branch_name>`

Fetch a pull request on GitHub by its ID and create a new branch:
`git fetch upstream pull/ID/head:new-pr-branch`

Clone to localhost:
`git clone https://github.com/user/project.git` or:
`git clone ssh://user@domain.com/~/dir/.git`

Clone to localhost folder:
`git clone https://github.com/user/project.git ~/dir/folder`

Clone specific branch to localhost:
`git clone -b <branch_name> https://github.com/user/project.git`

Delete remote branch (push nothing):
`git push origin :<branch_name>` or:
`git push origin --delete <branch_name>`




Compare
-----------

Compare modified files:
`git diff`

Compare modified files and highlight changes only:
`git diff --color-words index.html`

Compare modified files within the staging area:
`git diff --staged`

Compare branches:
`git diff master..branchname`

Compare branches like above:
`git diff --color-words master..branchname^`

Compare commits:
`git diff 6eb715d`
`git diff 6eb715d..HEAD`
`git diff 6eb715d..537a09f`

Compare commits of file:
`git diff 6eb715d index.html`
`git diff 6eb715d..537a09f index.html`


Stash
-----------

Put in stash:
`git stash save "Message"`

Show stash:
`git stash list`

Show stash stats:
`git stash show stash@{0}`

Show stash changes:
`git stash show -p stash@{0}`

Use custom stash item and drop it:
`git stash pop stash@{0}`

Use custom stash item and do not drop it:
`git stash apply stash@{0}`

Delete custom stash item:
`git stash drop stash@{0}`

Delete complete stash:
`git stash clear`
