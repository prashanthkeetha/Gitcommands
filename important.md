git is a version control system which store the data and shows the history of perivious data.
Git have
1. Local control system : where the changed that can have multiple copies.
2. Centralized version control system: where the changed data can store in the central repository (it can not have multiple copies).
3. Distributed version control system: In this we have local repository and remote repository.
---
* Git Workflow:
1. Working Directory (or) Tree: serves the record of version where we have the file versions authorized git track.
2. Staging Area: this is tracking the add the files last commit where the HEAD is present.
3. Local Repo: where commits the files by using ( git commit -m "version or file name ")
4. Remote Repo: where we push the added files to remote repository by using (git push and git remote push)
5. stash Area: while working on one repository by stashing we can move into into the another repository ( CMD: Git stash repo name)
Stash Area:-
>> git add .
>> git stash save filename
>> git stash list – To view the stashed files
Play with data in Stash Area
>> Copy + paste = Take a copy from stash area and use it in normally git stash
apply stashID
>> Cut + paste = Move a file from stash and use it normally git stash pop stashID
>> Delete = Remove files from stash Area
>> git stash drop stashID
----
we work on a working tree.
we move the files from working tree to staging area.
from staging area we move the changes into local repo
once we done with the changes we move the changes from local repo to remote repo.
----
to install git first we need to init
# CMD: Git init
to add the file from working directory to staging area
# CMD: Git add .
this command used to add only the modified files
# CMD: git add -u
it uses to add all files from working directory to staging area 
# CMD: git add -A
it uses to commit the code from staging area to local repo.
# CMD: git commit.
to add the origin and remote of the git repository.
# CMD: git remote add origin https://github.com/prashanthkeetha/practice.git
to check that on which remote we are working on 
# CMD: git remote -v
to push into the repository.
# CMD: git push origin <branch name>
to upstream the branch we can use 
# CMD: git push -u origin <branchname>
to push changes in multiple branchs use
# CMD: git push --all 
to see the commit ids after moving into the local repo 
# CMD: git log or git log --oneline.
to see the file in the graph format we can use 
# CMD: git log --graph --online
By using "git rm --cached <file>..." to unstage the file from staging area to local repo
# CMD: "git rm --cached <file>..." to unstage
by using restore, we can move thr change from local repo to staging area.
# CMD: git restore --staged
by using rebase, we can change the branch from one commit to another commit.
# CMD: git rebase -i commit id. HEAD~2
HEAD is a pointer where the latest commit. HEAD refers the latest commit.
To see th logs(or)Commits in the graph we use
# CMD: git log --oneline --graph --all
To remove the Untracked file we use the
# CMD: git clean or git clean -fd <file name>
To change from one branch to another branch we use
By using git clean in the staging area got this fatal error
ERROR:fatal: clean.requireForce defaults to true and neither -i, -n, nor -f given; refusing to clean.
-----
to see number of baranches you have
# CMD: git branch -all
To change the branch
# CMD: git checkout <branch name> 
there is chance we can two Repo at the same time using
# CMD: git remote add other <git repo url>
To see the what type of commit 
# CMD: git cat-file -t <commit id>
To print the values of the commit ( EX : tree,parent,commiter and author )
# CMD: git cat-file -d <commit.id>
1.Parent prefers the previous commit
2.Author and Committer means user and email configured message.
3.Tree is which shows the directory and blob refers the file.
To delete the files in the working tree we use
# CMD: git clean -fd
To move the file from local repo to staging area we use
# CMD: git reset --soft HEAD~give th commit number (ex numaber:git reset --soft HEAD~1or2)
To remove the commit from the local repo we use
# CMD: git reset --hard HEAD~give th commit number (ex numaber:git reset --HEAD HEAD~1or2)

# ERROR
git reset --hard HEAD revision 924e2ee
fatal: Cannot do hard reset with paths.


## Branching
------------
* To add new branch it will to the latest commit of the previous branch, to add the branch 
# CMD: git branch <branch name>
# to chnage the branch <git checkout created branch name>
# we can rename the branch name by using < CMD: git branch -m branchname to change>  -m stands for move or rename.
( {once we have multiple branches and and commits in the branches if we changes the branch and if we do commit it add to previous commit. the branch which we add before will be atteched to commite which it added to the commit there will be  no change.
to change the pervious branch into latest commit we use })
##  Merge
1. Three way merge:
       ## CMD : In this if we have multiple branches with the same file without with the different data in the files there will be conflict in the commit.
                * Merge commit is a special commit, which has two parents    
2. no fast forword merge :
       ## CMD : The merge command is git merge <source-branch> i.e. you should  be in target branch
                    when we do the above commands there will be merge conflicts
3. Rebase :
           It is used to change the position of the branch and rewrite the history
       # CMD: Git rebase <branch-name>
# cherry pick:
-----------
            It is used to chnage the position of the commit form the one branch to another or same branch with the history in the both the barnch
## CMD: git cherrypick <commit id> 

# Multiusers:
-------------
* By using multi user if one user pushes the changes in a branch and other user want to push the changes in the same branch first you need to fallow the steps.
1. You to fetch the changes<git fetch>
2. there is a chance you can the merge the chnages as well  
3. By using git pull we can fetch the changes and merge the changes as well <git pull origin <branch-name>>
* When we pull the changes there will be an extra commit will get created.
4. For not getting created the extra commit in the <git pull> we can use the 
# CMD: git pull origin <branch-name> --rebase.

# THERE IS A COMMANDS THAT WE USE
# CMD: git HEAD^ it is used see the parent of the commit
# CMD: git HEAD~1 it is used to see the 1st commit
# CMD: git HEAD~2 it is used to see the 2nd commit
# CMD: git HEAD^^ it is used to see the grand parent of the commit.
-------------------------------------------------------------------------

there is file that can get ignore the unwanted file are folder
# .gitignore in the file you can mention the files that need to get ignore. 







