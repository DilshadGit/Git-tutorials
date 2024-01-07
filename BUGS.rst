dilux_app$ git pull
remote: Enumerating objects: 72, done.
remote: Counting objects: 100% (71/71), done.
remote: Compressing objects: 100% (39/39), done.
remote: Total 55 (delta 18), reused 52 (delta 15), pack-reused 0
Unpacking objects: 100% (55/55), 2.54 MiB | 1.03 MiB/s, done.
From github.com:DilshadGit/Shkar
   59f17d7..cdbd8da  3-dev-v1               -> origin/3-dev-v1
 * [new branch]      4-create-app-tutorials -> origin/4-create-app-tutorials
   010740f..cdbd8da  main                   -> origin/main
hint: You have divergent branches and need to specify how to reconcile them.
hint: You can do so by running one of the following commands sometime before
hint: your next pull:
hint: 
hint:   git config pull.rebase false  # merge (the default strategy)
hint:   git config pull.rebase true   # rebase
hint:   git config pull.ff only       # fast-forward only
hint: 
hint: You can replace "git config" with "git config --global" to set a default
hint: preference for all repositories. You can also pass --rebase, --no-rebase,
hint: or --ff-only on the command line to override the configured default per
hint: invocation.

# SOLUTION:ls
git config --global pull.rebase true

# Next:
dilux_app$ git pull
warning: Cannot merge binary files: dilux_app/djangodb.sqlite3 (HEAD vs. e828698 (update db.))
Auto-merging dilux_app/djangodb.sqlite3
CONFLICT (content): Merge conflict in dilux_app/djangodb.sqlite3
error: could not apply e828698... update db.
hint: Resolve all conflicts manually, mark them as resolved with
hint: "git add/rm <conflicted_files>", then run "git rebase --continue".
hint: You can instead skip this commit: run "git rebase --skip".
hint: To abort and get back to the state before "git rebase", run "git rebase --abort".
Could not apply e828698... update db.

# Next: git rebase --skip
 -  git status (Must display clean)
 
