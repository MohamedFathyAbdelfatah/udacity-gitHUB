

### Github and git in Udacity ####

how can you be so sure about the **pain** and _result_.


how to compare old and new file by command prompt:
In windows: FC old.js new.js
In Linux/Mac: diff -u old.js new.js        || -u means unified format

+ the line starting with '+' means line was added in `new.js`

> A good rule of thumb is to make _one commit per logical change_.

+ Find a  [concept map from the course](https://www.udacity.com/wiki/ud775/concept-map?nocache)


### Linux Commands ###

#### Git ###
`git log`  [-stat]                                  # to see git commit logs [with statistics]  
`git log --oneline`    # see log with 'short commit id' and 'message'  
`git log --graph --oneline <branchname1> <branchname2>` # see graphcially commit logs with its history in simple line.  
`git diff` [-u] <oldfile.js> <newfile.js>        # to see the difference between the old and new commits. [-u: unified fomrat]  
                                                # you can type first **4 or more characters** of commit ID  
`git checkout <commitID>`                       # to go back to the old **temporary** version/commit , not equal to SVN checkout  
`git clone <httpAddress.git>`                   # clone and download files/commit history and everything from repository  
`git init`  
`git add`  
`git status`  
**staging area**   
**working directory**  
[git commit message guide](http://udacity.github.io/git-styleguide/)   
[git training cheatsheet :concepts](https://github.com/github/training-kit/blob/master/downloads/github-git-concepts_BETA.md)  

`git diff`   #compare working directory vs staging area  
`git diff --staged` #compare staged area with respository  
`git reset --hard`  #to remove any changes in working directory and staging area and get all files from repsoitory. **Careful**: this is irrversible command.  
`git branch  [-a]'     # see available branches , [-a] shows hidden branches with orgin/remoteMastersinceLastPullPush
`git branch '<branchname>'` # create a branch with <branchname>  
`git checkout -b <branchname>` # create a branchname and checkout to it.  
`git branch -d <branchname>` # delete the label of branch, only do this after the merge process  
`git checkout <branchname>` # switch to branchname.  

`git remote` #check remote repositories  
`git remote add <remoteNametobeCalledInThisLocal> <remoteRepoUrl>`   # add and give name to remote repository.  
`git remote -v' # see verbose remote repositories.  
`git push/pull <remote_repo_name[usally origin]> <branch_name_to_push>` #pull or pull branch to remote repo.  
                                # on `git pull <origin> <master>`, if both local and remote are out of sync, it will fetch and merge!  
`git fetch <remoteRepoName_usually_origin>` #update local <origin/master> from repo like Github.  





`pwd`  # print working directory  
`ls`  # list the files in this directory  
`ls -a` ## show all files including hidden files  

`rm [-r] <folder/filename>`   ## remove directory/folder/file [-r: recursive to its subfiles, used to clean direcotry]   
`mv <sourcefilepath> <destinationfilepath/name>`    ## move files from folder to folder with given name. Note source file will be moved and renamed.    


### merge conflict ###
If you get a merge conflict then the file will have what conflicts shown in the file.
```
<<<<<<< HEAD   
code in heads
|||||||| share common ansestors
code in common anseteros means code in shared parents 
=======
code in masters
>>>>>>> masters
```
+ have to remove those HEAD and other comments
+ figure out which thing should be in the final files[merge repo]
+ after modified conflicts, add on stage then commit with commit message.
+ merge will be complete after _resolving the conflict_.


### Fast - forward Merge ###
a<-x <- b

Fast forward merge happens, if b is merged with a, when `a` can be reached by b. `git pull` update local HEAD and merge the difference in branch.  
in the case of fast-forward merge it doesn't create another commit for merge, since they share the same ancestor.

**Note**: github will create another commit if done from the browser.


### Pull Request ###
think of this as, user is requesting to pull his/her change to 'main branch/master'. 

### Behavior of `git checkout` ###
Checking out an earlier commit will change the state of at least one file.

This is sometimes true. Git doesn't allow you to save a new commit if no files have been updated, so you might think this is always true. However, it's possible to do the following:

Save a commit (call this commit 1).
Update some files and save another commit (call this commit 2).
Change all the files back to their state during commit 1, then save again (call this commit 3).
This sometimes happens if commit 2 contained a bug, and it's important to fix the bug quickly. The easiest thing to do might be to remove all the changes introduced by commit 2 to fix the bug, then figure out how to safely reintroduce the changes later.

At this point, commit 3 is the latest commit, so if you checkout commit 1, none of the files will be changed. 


Checking out an earlier commit will change the state of more than one file.

Checking out an earlier commit will change the state of every file in the repository.

Both of these are sometimes true. Since each commit tracks the state of all files in the repository, it is possible that checking out an earlier commit will change the state of multiple files, or even all the files in the repository. However, it is possible to save a new commit after changing only one file, so it is possible only one file will change. 


After checking out a commit, the state of all the files in the repository will be from the same point in time.

This is always true. A commit saves a snapshot of all files in the repository at the time the commit was made, so checking out an earlier commit will result in all the files being reverted to their state at the time the commit was made. That is, the files will be in a consistent state.