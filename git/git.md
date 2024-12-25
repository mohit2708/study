|  No.  | Questions                                                                       |
| :---: | ------------------------------------------------------------------------------- |
|       | [if found ssl error?](#ssl-error)                                               |
|       | [Check Configure and set the Configure](#check-configure-and-set-the-configure) |
|       | [Initialize Git](#initialize-git)                                               |
|       | [Clone the project](#clone-the-project)                                         |
|       | [git status](#git-status)                                                       |
|       | [Git Adding New Files](#git-adding-new-files)                                   |
|       | [Removing Files from the Staging Area](#removing-files-from-the-staging-area)   |


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

## Git configuration

### Check Configure and set the Configure.
* To check set or not
```git
git config user.name
git config user.email
```

* Set the name:
```git
git config --global user.name "mohit-saxena"
```
* Set the email:
```git
git config --global user.email "demo@gamil.com"
```
* check and Set origin
```git
git remote -v
PS D:\gitOcean> git remote add origin https://git.chetu.com/ChetuInc/OceansideBeachService-HOTT.git
PS D:\gitOcean> git remote -v
origin  https://git.chetu.com/ChetuInc/OceansideBeachService-HOTT.git (fetch)
origin  https://git.chetu.com/ChetuInc/OceansideBeachService-HOTT.git (push)
```
* Check all config
```git
git config -list
```

## Starting a project

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

##

### git status
* To check the status for file upload 
* red files are Untracked files: i.e abhi add nahi hui hai hai.
* green files are tracked file i.e add ho chuki hai
```git
git status
```

### Git Adding New Files
```git
git add filename1.html filename2.html   # Add particular file   
(OR) git add .                          # all Files added
(OR) git add --all                      # all Files added
(OR) git add -A                         # all Files added
git add *.java                          # Add Files by Wildcard
```

### Removing Files from the Staging Area
```git
git rm file_name.txt
(OR)
git restore file_name.txt
```

### Create new file
```git
touch newfile.txt
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
git branch --list
(OR)
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

#### Delete Branch
```git
git branch -d <branch name>  
(OR)
git branch -D <branch name>

# Delete a Remote Branch
git push origin -delete <branch name>
```


### show the all file of the folder
```git
ls
# all file - show hidden file also
ls -a
```


### Commit History
* Display the most recent commits and the status of the head:
```git
$ git log

Type q to exit this screen. Type h to get help.
```
* Display the output as one commit per line:
```sql
git log --oneline
```
* Displays the files that have been modified:
```git
$ git log -stat
```
* Display the modified files with location:
```git
$ git log -p
```
### What is git-blame?
* Annotates each line in a file with information about the last commit that modified the line.
* This information includes the commit hash, the author, the date of the change, and optionally, the line number. By using git-blame.
* We can track the origin of each line of code, making it easier to understand the history and context of changes.
```git
git blame <file-name>
```


### Push Command
```git
git push -u origin master
```