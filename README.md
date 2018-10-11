# GitWorkshop


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

Stop merge (in case of conflicts):
`git reset --merge` // prior to v1.7.4

Merge only one specific commit: 
`git cherry-pick <commit_hash_id>`

Rebase:
`git checkout branchname` » `git rebase master`
or:
`git merge master branchname`
(The rebase moves all of the commits in `master` onto the tip of `branchname`.)

Cancel rebase:
`git rebase --abort`

Squash multiple commits into one:
`git rebase -i HEAD~3` ([source](https://www.devroom.io/2011/07/05/git-squash-your-latests-commits-into-one/))

