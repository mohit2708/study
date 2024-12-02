### Global Credintials

* User name
```git
git config user.name
# Mohit saxena
```

* change your Git username
```git
git config --global user.name "mohit saxena mohit"
```

* user email
```git
git config user.email
# mksaxena27@gmail.com
```
* change your Git email address
```git
git config --global user.email "cscreen@aiteamsuperstars.com"
```
* All List
```git
git config --list

Output:-
credential.helper=osxkeychain
user.name=Christian Screen
user.email=cscreen@aiteamsuperstars.com

core.repositoryformatversion=0
core.filemode=true
core.bare=false
core.logallrefupdates=true
core.ignorecase=true
core.precomposeunicode=true
remote.origin.url=https://github.com/aicglabs/datalakehouse.git
```


++++++++++++++++++++++

Show Branch

* Show current branch name
git branch
* Show all branch
To see all remote branch names, run
git branch -r

To see all local and remote branches, run

git branch -a

Branch details
--------------
* You can see detailed information such as the local or remote branches in use, commit ids, and commit messages by running
* current branch details
git branch -vv
* branch details local and global
git branch -vva


Show the User

git config user.name 
# Mohit Saxena
