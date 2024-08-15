# Basic Git commands 
1> git pull --> to pull latest changes from the main branch in remote repo.
2> git push--> to push the changes into the remote repo.
3> git fetch ---> to check the latest changes in the remote repo.

### difference between git fetch and git pull: 
git pull check the latest changes and also pull the latest changes in my system and git fetch only check the latest changes in remote repo.

## to set origin: 
git origin originName 

## to create branch:
git branch branchName

## switch to another branch 
git checkout branchName 

## switch and create branch 
git checkout -b branchName 

## switch and create branch in latest version of git 
git switch -c branchName 

## push the local branch to remote repo 
git push -u origin branchName // u flag is basically for upstream. 

## to list all the branches 
git branch ---> to list all the branches locally. 
git branch -r ---> to list all the branches in remote repo. 
git branch -a --> to list all the branches in local and remote. 

## to delete the branch
git branch -d branchName --> to delete branch locally. 
git branch -D branchName ---> to delete branch forcefully in local. 
git push origin --delete branchName. 

## status 
git status ---> tells about current branch , and about the stagging area. 

## fetch commands :
git fetch originName 
git fetch --all --> to fetch all changes from remote. 
git fetch --tags --> to fetch the details from particular tags. 
git fetch --prune --> if branch is delete from remote repo then to delete it from local repo. 

## pull command 
git pull is combination of two commands git fetch+ git merge. 
By default git pull perform merge , but explicitly you will tell to perform rebase git pull --rebase 
<br/>
git pull <remote-name> --> If want to pull from specific remote but not from default remote. 
git pull <remote-name> <branch-name>
<br/>
pull and discard local changes: git reset ~Hard and git pull <remote-name> <branch-name> 
<br/>

## init 
git init --> It is used to create the git repository in current directry. 
To link local git repo to remote github repo : 
git remote add origin <remote-repo-url> 

## add command 
git add fileName --> to add file from local directory to stagging area. 
git add . --> to add all the files in current directory to stagging area .
git add -A --> to add all the files  stagging area irrespective of directory. 
git add -u --> to add midified or new files but not deleted files. 
git add '.*txt' --> to add specific file type to stagging area. 
git add -p --> to add changes interactively in stagging area , you have an option to check which patch of changes you want to add in stagging area. 

## commit command 
git commit -m " message " 
<br/>
git commit -m " message1" -m  " message2 " --> multiline commits. 
git commit --> then editor open you have to write message there. 
git commit --amend --> to change the last commit messages and add files (it will open editor). 
git commit -a -m "message" --> to commit all the git tracked files changes. 

## log 
git log ---> to see all the commits. 
git log --oneline --> to see only the headings of commit. 
git log -n number ---> to see limit  number of commits. 
git log file-path --> to see git history of particular file. 
git log -p --> to see commits and changes due to that commit. 
git log --graph ---> to see graphical representation of commits history. 
git log --graph --oneline --all  --> to see branch detail and merge info too.
git log --author="Author Name"  ---> to see particular authors commits. 
git log --grep="keyword"  --> to search the commit according to particular keyword. 
git log --since="YYYY-MM-DD" --until="YYYY-MM-DD"   --> to see the commits in between range. 


## to see hw many commits are your local that are not in main 
git log origin/main..HEAD --oneline

## reset command 
git reset --soft <commit> --> keep remain stagged and working directory changes but point pointer to that reference. 
git reset <commit> ---> keep remain working directory , but un stag stagging area to match that commit. 
git reset --hard <commmit> --> point pointer to that commit and also delete the changes to match that commit. 
git reset --keep <commit>   ---> to non conflict changes keep. 
for eg: git reset --keep HEAD~1
git reset HEAD <file> --> incenditall stag file but want to unstag that file. 

## revert command 
git revert <commit> This command creates a new commit that reverses the changes made in the commit with hash.  
git revert <oldest-commit>..<newest-commit>  --> In range you want to revert changes. 
git checkout <commit> -- <file>  ---> To revert changes in a specific file from a commit.

## to Delete commits from remote repository : 
1> Use reset command : 
<br/>
Step1: git reset --hard Head~1
<br/>
Step2: git push origin branchName --force 
<br/>
2> Use revert command : 
<br/>
Step1: git revert <commit-hash>
<br/>
Step2: git push origin branchName

## stash 
1> git stash ---> to save changes in your local working directory. 
2> git stash push -m "message" --> to save the changes in your working directory with specific message. 
3> To list all stash --> git stash list. 
4> to apply latest stash --> git stash apply.
5> to apply particular indexed stash ---> git stash apply stash@{n}
<br/>
6> git stash pop  --> To apply the most recent stash and then remove it from the stash list.
7> git stash clear --> to remove all stashes. 
8> git stash drop stash@{n}  -> To remove specific stash from list 
9> git stash push -u --> to stash untracked files 
10> git stash push -a ---. to stash ignored files


