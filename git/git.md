Git:-
* git is a **version control system.** It was created by **Linus Torvalds** in 2005, and has been **maintained** by **Junio Hamano** since then.
* git helps you keep track of code changes.
* git is used to collaborate on code.
* Who made changes.
* Syntx:
```git
git --version
```


### ssl error
* when we got the ssl error
```git
git config --global http.sslVerify false
```

### Initialize Git
```git
git init 
```

### Clone the project
* Download the project by defalut in master branch
* hum defalut branch ko change bhi kar sakte hai.
```git
git clone https://url.git
# move to folder
cd folder_name
```
* When we download the project for particular branch
```git
git clone -b branch_name remote_repo_url
```

### Check Configure and set the Configure.
* To check set or not
```git
git config user.name
git config user.email
```
* Set the name and email 
```git
git config --global user.name "mohit-saxena"
git config --global user.email "demo@gamil.com"
```

### git status
* To check the status for file upload 
* red files are Untracked files:
```git
git status
```

### Git Adding New Files
```git
git add filename1.html filename2.html
(OR) git add .
(OR) git add --all
(OR) git add -A
```

### Git Commit
```git
git commit -m "initial commit"
```

### Git Commit Log
```git
git log
```

### Branch
#### Show current branch name
```git
git branch

Output:
* master
```

#### Show All branch name
```git
git branch -r

Output:-
origin/HEAD -> origin/master
origin/MyLaravelProject
origin/code
origin/copy
```
```git
git branch -a

Output:-
* master
remotes/origin/HEAD -> origin/master
remotes/origin/MyLaravelProject
remotes/origin/code
remotes/origin/copy
```

#### create branch and move to checkout
```git
git checkout hello-world-images
```

### show the all file of the folder
```git
ls
# all file - show hidden file also
ls -a
```






```
PS D:\gitOcean> git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        README.md

nothing added to commit but untracked files present (use "git add" to track)
PS D:\gitOcean> git add .
PS D:\gitOcean> git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   README.md

PS D:\gitOcean> git config user.name
PS D:\gitOcean> git config --global user.name "MohitS4"
PS D:\gitOcean> git config --global user.email "Mohits4@chetu.com"
PS D:\gitOcean> git config --global user.email "mohits4@chetu.com"
PS D:\gitOcean> git config user.name
MohitS4
PS D:\gitOcean> git config user.email
mohits4@chetu.com
PS D:\gitOcean> git commit -m "initial commit"
[master (root-commit) 1ae3be1] initial commit
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 README.md
PS D:\gitOcean> git astatus
git: 'astatus' is not a git command. See 'git --help'.

The most similar command is
        status
PS D:\gitOcean> git status
On branch master
nothing to commit, working tree clean
PS D:\gitOcean> git remote -v
PS D:\gitOcean> git remote add origin https://git.chetu.com/ChetuInc/OceansideBeachService-HOTT.git
PS D:\gitOcean> git remote -v
origin  https://git.chetu.com/ChetuInc/OceansideBeachService-HOTT.git (fetch)
origin  https://git.chetu.com/ChetuInc/OceansideBeachService-HOTT.git (push)
PS D:\gitOcean> git push -u origin master
warning: ----------------- SECURITY WARNING ----------------
warning: | TLS certificate verification has been disabled! |
warning: ---------------------------------------------------
warning: HTTPS connections may not be secure. See https://aka.ms/gcm/tlsverify for more information.
warning: ----------------- SECURITY WARNING ----------------
warning: | TLS certificate verification has been disabled! |
warning: ---------------------------------------------------
warning: HTTPS connections may not be secure. See https://aka.ms/gcm/tlsverify for more information.
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 210 bytes | 210.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To https://git.chetu.com/ChetuInc/OceansideBeachService-HOTT.git
 * [new branch]      master -> master
branch 'master' set up to track 'origin/master'.
PS D:\gitOcean> 
```