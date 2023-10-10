# Git Commands

## commit

changes done in your local repository. its like a check point. at that point you can return back to your code if something goes wrong. it should be manually done. if bug contains in the new update. you can comit back to older comitment. in that comit it stores bunch of different information like who did the change and when and at where. when you are done the local changes and push the code to remote repository (remote storage) it will make chages and it is a put comit. then the codes will be meregd. when we code if we need to update our code after others have already done the chages to local repository then what you do is you pull the data to your local repository. That is the pull commit. then the codes will be meregd.

------------------------------ GITHUB ----------------------------------------

## The Branches

1. Master Branches
2. Normal Bracnches

Master branches - 

### Main code of the software. Its like a time line and each commitment done to it shows the past and present changes in the time line.

### Braches

Normally when we are working on a new features we don not work on the same brach and we brach of from the master brach and do the chages seperately. if we need the updates upto now on the braches we can pull them back fromthe main brach so that we can have currently updated brach with new features that you are working on without having in the main brach. Well if its a complex programm, you can brach off from different locations also.

---------------------------- Common linux codes -----------------------------

`cd` : change directory
`mkdir` : make directory

-------------------------- Start up a new git repository --------------------

`git init` - ( මුලපිරීම - act or take charge before others do ) Use to convert any folder to a git repository. After that all the files and folders inside it will be traked by the git. what that means is, you can run any git command inside it. but only if we initializ ehte git repository by typing 'git commit'.

staging area - this is where we temeperory add or remove files which are gonna be  commited.

`git add index.php` - this command will add the index.php to the next git commit event.

then to check what we did we type git status.

`git status` - eg :-

```
PS D:\laragon\www\git> git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   index.html
```

what above shows is that now that file tracked by git and that file is now ready to be commited. Normally we do not allways commit. but we do when we have chaged to created files or some progress is done.

`git commit -m "added index.html"` - ( කැප කරනවා - pledge or bind (a person or an organization) to a certain course or policy ) here adding the message is a must and without it the command will be aborted. In the message what you have to type is you have to enter what you are acctually doing. ( You can not leave the message empty. But you can type anything inside. )
```
PS D:\laragon\www\git> git commit -m "added index.html"
[master (root-commit) 03e17d0] added index.html
 1 file changed, 15 insertions(+)
 create mode 100644 index.html
```
if we check the status again it shows,

```
PS D:\laragon\www\git> git status
On branch master
nothing to commit, working tree clean
```

so that means all the files inside the folder are inserted to the git repository.Then if mak e a change to the files inside and check the status it will show as below.

```
PS D:\laragon\www\git> git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   index.html

no changes added to commit (use "git add" and/or "git commit -a")
```

--------------------------------------

Methods of adding files - here instead of file name by typing the directory we can add all the files inside.

`git add .` or `git add ./` will add all the files and folders inside the ./ folder to git commit

--------------------------------------

Creating a new branch - `git checkout -b new-branch-name`

lets say if we are going to create the footer to my website then start a new brach so that the chages would not harm my main branch. here '-b' stands for branch.

``````
PS D:\laragon\www\git> git checkout -b footer
Switched to a new branch 'footer'


But the branch is still empty and we need to add the files and folders to it. Therefore,

```
PS D:\laragon\www\git> git commit -m "first commit on branch footer"
On branch footer
nothing to commit, working tree clean
```

so after changes if we need to switch to the master branch. then type,

```
PS D:\laragon\www\git> git checkout master
Switched to branch 'master'
```

if we need to switch back to footer branch then type,

```
PS D:\laragon\www\git> git checkout footer
Switched to branch 'footer'
```

So after the chages are done if you need to add the chages, what you can to is merge the branches. Lets say if you are now in the footer branch and need to add the chages in master branch to footer. ( But the changes in footer won't be added to the master branch. FOr that you need to switch to master branch and then merge with footer. )

after creating the program. If we need to connect the local repository to a remote one. type in,

`git remote add origin https://github.com/Kenura-R-Gunarathna/learn-github.git`

What it does is it add the above git url and refer that url with the name 'origin'. So when we need to push or pull changes inbetwenn local and remote repositories we need to adress the remote repository by its name => 'origin' ( You can't change the name and it is default. And also when linking the remote repository it is important to consider the branch you are in. becuse the the branch you are in will be connected to the remote repository. You can add any amount remotes you want.)

------------------ to push the git local repository type in,

`git push -u origin master`

structure code : /* git push -u ~remote name~ ~branch name~ */

here this will push aal your commits upto now to remote repository 'origin', from local branch 'master'.

'-u' stands for 'remember these settings'. So that next time we only need to type in 'git push' and it will automatically remember the remaining parts. ( we can type the code without -u also. )

`
PS D:\laragon\www\git> git push -u origin master
Enumerating objects: 22, done.
Counting objects: 100% (22/22), done.
Delta compression using up to 8 threads
Compressing objects: 100% (18/18), done.
Writing objects: 100% (22/22), 2.12 KiB | 722.00 KiB/s, done.
Total 22 (delta 6), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (6/6), done.
To https://github.com/Kenura-R-Gunarathna/learn-github.git
 * [new branch]      master -> master
branch 'master' set up to track 'origin/master'.
`

now our project is in the remote repository and open for any one in private/public.

----------------- to pull the changes from remote repository type,

`git pull origin master`

code structure : /* git pull ~remote name~ ~branch name~ */

```
PS D:\laragon\www\git> git pull origin master
remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), 733 bytes | 3.00 KiB/s, done.
From https://github.com/Kenura-R-Gunarathna/learn-github
 * branch            master     -> FETCH_HEAD
   531d049..add3650  master     -> origin/master
Updating 531d049..add3650
Fast-forward
 README.md | 4 +++-
 1 file changed, 3 insertions(+), 1 deletion(-)
 ```

boom, now everything is done.

----------------- conflicts in git repository

```
PS D:\laragon\www\git> git merge footer
Auto-merging index.html
CONFLICT (content): Merge conflict in index.html
Automatic merge failed; fix conflicts and then commit the result.
PS D:\laragon\www\git> git commit -m "all the chages in index.html are added"
[master 8d3df10] all the chages in index.html are added
```

this happens when in both sides if we change the codes in the same line. Then git won't be able to identify the changes and will throw an error. Then you have to manually change the code according to what you want to see. then as normally,

```
git add .
git commit -m "changes"
git push
```

then the merge conflict will be resolved and pushed to remote repository.

--------------- Pushing more than one branch

as normally switch to your branch. the type,

`git push origin footer`

code structure : /* git push ~remote name~ ~branch name~ */

```
PS D:\laragon\www\git> git push origin footer
Total 0 (delta 0), reused 0 (delta 0), pack-reused 0
remote:
remote: Create a pull request for 'footer' on GitHub by visiting:
remote:      https://github.com/Kenura-R-Gunarathna/learn-github/pull/new/foote
remote:
To https://github.com/Kenura-R-Gunarathna/learn-github.git
 * [new branch]      footer -> footer
 ```

--------------------------- List All Branches

NOTE: The current local branch will be marked with an asterisk (*).

To see local branches, run this command: `git branch`
To see remote branches, run this command: `git branch -r`
To see all local and remote branches, run this command: `git branch -a`

--------------------------- Delete Branches

To delete a remote branch, run this command: `git push origin --delete my-branch-name`
To delete a local branch, run either of these commands: 
	`git branch -d my-branch-name`
	`git branch -D my-branch-name`

NOTE: The -d option only deletes the branch if it has already been merged. The -D option is a shortcut for --delete --force, which deletes the branch irrespective of its merged status.

--------------- Change github remote repository config details ---------------

Here type in the code, 

```
git config --blobal user.name "Tim" // Change/Setup your name
git config --blobal user.email "kenura@krag.lk" // Change/Setup your email
```


--------------------------- Git commands -----------------------------

⌨ Common GitHub Commands ⌨

To create a new repository locally: `git init`

To add files to staging area: `git add .` OR `git add ~filename~`

To check status of staging area: `git status`

To commit new changes: `git commit -m "commit message"`

To create a new branch: `git checkout -b ~branch name~`

To switch between branches: `git checkout ~branch name~`

To merge branches together: `git merge ~branch name~`

To add a remote repository: `git remote add ~remote name~ ~https://yourremoteurl~`

To pull changes from a remote repository: `git pull ~remote name~ ~branch name~`

To push changes to a remote repository: `git push ~remote name~ ~branch name~`

@Thank you, Kenura R.Gunarathna