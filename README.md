# Git cheatsheet

## main concepts
- Git is a Distributed Version Control System: 
keeps records of modifications in a repository via snapshots
- repository is the folder tracked by git
- HEAD is a reference to the latest commit on checkout branch


### philosophy 
- git is always moving forward ( can revert with a new commit )
- each commit stores a full snapshot of the repository
- history only for users not for git
- branches are cheap, use them ubiquitously ( git is designed for collaboration )
- a git development environment consists of 3 sections: 
1. working directory
2. staging area
3. repository

```
  working           staging             local            remote
 directory            area               repo          repository
     |                  |                 |                 |
     |                  |                 |                 |
     | --- git add ---> |                 |                 |
     |                  |                 |                 |
     |                  | - git commit -> |                 |
     |                  |                 |                 |
     |                  |                 |                 |
     | -------- git commit -a ----------> |                 |
     |                  |                 |                 |
     |                  |                 | -- git push --> |
     |                  |                 |                 |
     |                  |                 |                 |
     |                  |                 | <-- git pull -- |              
     |                  |                 |                 |
     | <-------- git checkout ----------- |                 |
     |                  |                 |                 |
```

### cheatsheet

```

### working with repositoryes
# create a git repository
$ git init
# clone a remote repository
$ git clone username@host:/path/to/repository
    
    
### staging area and commits
# add file/folder to the staging area
$ git add <file/folder>
# add all modifications to staging area
$ git add *
# commit 
$ git commit -m "<commit message>"


### working with branches
# create a local branch
$ git branch -b <branch>
# delete a branch
$ git branch -d <branch>
# push branch to remote
$ git push origin <branch>


### dealing with the remote
# get changes from remote
$ git fetch --all --prune
# push changes to remote
$ git push
# push local branch to remote
$ git push --set-upstream origin <branch name>
# pull changes from the remote
$ git pull
# adding a new remote ( advanced users )
$ git remote add origin <server>


### releases
# create a tag
$ git tag <tagname>
# view tags
$ git tag


### logs and status
$ git log --pretty=oneline


### when things go bad
# restore working files
$ git checkout <file/folder> 
# clear all changes from working tree and stage ( use with caution )
$ git reset --hard
# ammend the history
$ git commit --ammend ( use with caution )

### repos within repos ( submodules )
# adding a submodule
$ $ git submodule add <remote_url> <destination_folder>
# updating a submodule within the repo
$ git submodule init --update --recursive

### cleaning repo
$ git clean -fd
``