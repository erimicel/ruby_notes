## GIT Guide

### Find difference lines numbers changes between branches
git diff --stat <commit-ish> <commit-ish>

https://pawelgrzybek.com/multiple-ssh-keys-for-multiple-bitbucket-github-accounts/

git checkout -b backup-branch
git rebase main
git rebase -i main # squash commits similiar
git push -f

git reflog
git reset --hard HEAD@{2} (or commit number)
git reset —hard origin/staging

git rm --cached -r .
git reset --hard

### Multiple branch remove:
git branch --merged | egrep -v "(^\*|master|main|staging)" | xargs git branch -d

* git branch - to list out all local branches
* git branch -r - to list all remote branches
* git branch -a - to list both local and remote branches
* git branch --merged - to list all the branches that have been merged
* git branch --no-merged - to list all branches not merged

git log --pretty=format:'"%h","%an","%aD","%s",' --shortstat --no-merges | paste - - - > log.csv

### GIT: GET COMMITS BY USER
git log --date=iso --pretty=format:'%h','%an','%ad','%s' --author='Name Surname' > ~/Desktop/log.csv
