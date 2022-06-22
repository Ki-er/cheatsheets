## Git cheatsheet

### view repo url

`git remote -v`

may show `git@github.com:` url instead if you cloned via ssh

### add a remote

`git remote add <name> <url>`

e.g. `git remote add upstream https:github.com/kieran/reponame`

### change remote url 
`git remote set-url <name> <newurl>`

e.g. `git remote set-url origin https://git.kieranrobson.com/kieran/reponame`

### view information about a remote

`git remote show <name>`

### reset your local git repo to whatever state the remote is

```bash
read -p "Enter branch name: " branchname 
git fetch origin
git checkout $branchname
git reset --hard origin/$branchname
git clean -d --force
```

### add files to a commit without just making a new commit

git add . # or add individual files
git commit --amend --no-edit

### a magic git time machine

git reflog
read -p "Enter index: " index
<br>\# you will see a list of every thing you've
<br>\# done in git, across all branches!
<br>\# each one has an index HEAD@{index}
<br>\# find the one before you broke everything
git reset HEAD@{$index}


some commands taken from <https://dangitgit.com>
