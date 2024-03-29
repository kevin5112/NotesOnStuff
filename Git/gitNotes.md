# testing git

# test 2

# git learnings

after messing around with git, I found out that when you run
`git remote add origin git@github.com:kevin5112/<repository name>`
it basically will add the remote repo on github and link it to your local machine.
you add the `origin` because it's an alias so you don't have to type out the whole name

additionally that means you can do
`git push -u git@github.com:kevin5112/<repository name> master`
note here you don't use the alias origin where as you normally would just do
`git push -u origin master`
the `-u` flag just means set-upstream, meaning to set up your local branch to the remote repository so you can push

# Amends

using the command `git commit --amend` will amend the latest commit on your local repository. It will not amend any commits that have already been pushed onto your remote repository.

# Rebase

you can use `git rebase -i HEAD^ (or --root)` to rebase any commits you had on local. For example, if you accidentally created 2 separate commits you can merge them through rebase or vice versa. You can also amend through rebase or remove past commits through rebase.

# --force

using `git push --force` is _VERY DANGEROUS_ and should only be used if developers are certain on using it. It will force override git push through all safety mechanisms. A scary example is if you did a `git rebase -i -root` and removed a commit in your rebase. Then did a `git push --force`. The commit you erased will be completely gone locally and remotely.

# --force-with-lease

`git push --force-with-lease` is an alternative to force that companies will use to atleast have a failsafe for if someone accidentally does a force push. It's like a force push lite.

# reset

there are a few resets with git. `git reset --soft` will soft reset your commit but the files will still be changed and in the staging state.

`git reset` I believe is normalized so it would reset your commit to before staging but will stil have the changes

`git reset --hard` will completely revert your local repo to right after pushing the previous commit. Meaning it'll erase all new changes to the repo.

git reset will only affect local repos and won't affect your remote repos on github
