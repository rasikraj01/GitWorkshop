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
