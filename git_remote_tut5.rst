create new branch and push to remote

- git checkout -b remote_tags
- touch git_remote_tut5.rst
- git commit -a -m 'create new file add and commit at the same time'
- git push origin remote_tags

# to check the branch localy 
- git branch

# to check the branch remotely
- git branch -r

# tp-o display all remote branches
- git remote show origin

# Delete remote branch
- git push origin :remote_tags

# OR
- git push --delete origin/remote_tags 

# Delete branch localy this way delete the branch even if the commit not been merged.
- git branch -D remote_tags

# If you use this way you may not able to delete localy because some commit not been merged
- git branch -d remote_tage

# Sometime make some commit and push but the branch is deleted what is happening:
- git push   # (No remote to push to)
 Everything up to date!

 # If you run:
 - git remote show origin
 - master
 - refs/remotes/origin/remote_tags stale (Use: 'git remote prune' to removed branch!)

# Deleted branch resolve:
- git remote prune origin #(Clean up deleted remote branches)

# Heroku only deployee in the branch called master there is no staging branch or production branch
- git branch
 * staging
   master

- git push heroku-staging staging # (staging is branch name!)
# in this case we have to use another way to push to master branch in Heroku
- git push heroku-staging staging:master #(connect staging local branch to remote master branch to deployee )

# Tagging:
# A tag is a reference to a commit (used mostly for releae version)

# List all tags
- git tag
  v0.0.1
  v0.0.2

- git checkout v0.0.1

# add a new tag
- git tag -a v0.0.2 -m 'add new tag'

# To push new tags have to use --tags to push to remote otherwise push local only if you use - git push
- git push --tags