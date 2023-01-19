# clone repository from server or github and changed the name of the repo
 - git clone git@github.com:DilshadGit/newrepo.git git-training

	Cloning into 'git-traning'...
	remote: Enumerating objects: 4, done.
	remote: Counting objects: 100% (4/4), done.
	remote: Compressing objects: 100% (3/3), done.
	remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
	Receiving objects: 100% (4/4), done.
 - ls 
   % ls
    Django32		GitHub		Docker  	Git-tutorials		Python		git-traning

 # 
 - git-traning % git remote -v 
   origin	git@github.com:DilshadGit/newrepo.git (fetch)
   origin	git@github.com:DilshadGit/newrepo.git (push)
 # check the branch
 - git branch
 * main

# Change branch and create new branch
 - git branch branchname
 * move to the new branch
 - git checkout branchname
 * Or we can use switch new branch
 - git switch a-branch
   Switched to branch 'a-branch'
 - git branch         
 * a-branch
   b-branch
   main

 NOTICE: * a-branch mean we are in the current branch!

 # Create new file in a-branch
 - touch python.txt
 - git add python.txt
 - git commit -m 'create python file'

 # Now we change back to main branch
 - git checkout main
 - ls 
 - git branch         
   a-branch
   b-branch
 * main
 # We are in main branch check if the python.txt file there!
 - ls
	README.md

 * The python.txt not exist in main branch but we can merged to main branch without pushing 
   to stage

 - git merge a-branch
   Updating ed0d88a..7b3a1f4
   Fast-forward
   python.txt | 0
   1 file changed, 0 insertions(+), 0 deletions(-)
   create mode 100644 python.tx

 NOTICE: What is means Fast-forward
 It means when we made one or more commit in a-branch and back to main branch but othing
 has been done in main branch it is easy to merge the a-branch to main while nothing been
 changed in main branch.

 - ls 
  README.md	python.txt
- git branch
  a-branch
  b-branch
* main
 
 # If we go back to a-branch the python.txt file still there
 - git checkout a-branch
 - ls 
   README.md	python.txt
 
 # move back to main branch and delete a-branch using
 - git branch -d a-branch
   Deleted branch a-branch (was 7b3a1f4).

 * this will deleted a-branch localy but after commit push to stage we have to use another
   command to delete the a-branch in stage 

 - git branch --delete a-branch (This is only if already pushed to staged)

 # There is another way to create new branch and move to the new branch at the same time using:
 - git checkout -b b-branch
	Switched to a new branch 'b-branch'
 * check the branch
 - git branch              
 * b-branch
   main
 - git checkout main
 * we merged a-branch to main and need to commit the main branch
 - git commit -m 'merged the python.txt from a-branch and deleted a-branch.'
	[main 1c3eb72] merged the python.txt from a-branch and deleted a-branch.
	@DilMac git-traning % git push
	Enumerating objects: 6, done.
	Counting objects: 100% (6/6), done.
	Delta compression using up to 8 threads
	Compressing objects: 100% (4/4), done.
	Writing objects: 100% (4/4), 540 bytes | 540.00 KiB/s, done.
	Total 4 (delta 1), reused 0 (delta 0), pack-reused 0
	remote: Resolving deltas: 100% (1/1), done.
	To github.com:DilshadGit/newrepo.git
	7b3a1f4..1c3eb72  main -> main
