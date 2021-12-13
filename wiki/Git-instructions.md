# Git instructions

We would like to keep the history of the OpenSuspect repository nice. To do this, I'll start with the basics of how to clone the repository, then I'll talk about making pull requests.

To clone the repository, you should first fork it to your own user, through github. You will also need [git lfs](https://github.com/git-lfs/git-lfs) installed. Once you have that, then clone the repository to your machine with the clone button on github. If the image files are just one line of text, and cannot be read by godot, then you go not have git lfs installed properly.

In order to push your changes, run some of these commands:
```bash
# This will add any files you list that should be staged. Make sure you don't stage anything that shouldn't be commited to git. This includes builds of the game, things like .DS_Store, or other temporary files.
git add <filenames>
# This will show you what files you have staged
git status
# Once you are happy with that, commit your changes
# The commit message should be a short (one sentence) summary of what you did
git commit -m "Commit message"
# After you have committed your changes, push them to github
git push

# If you get an error message saying no permission, then you did not clone a fork of the repository. You can fork the repository, and then set the url of your local repository to the newly forked one using this command
git remote set-url origin <url>
# If you get an error message telling you to run this command, then run it and try again
git push --set-upstream origin master
```

Once you have done that, make a pull request on github. The administrators of the opensuspect project will handle everything else.

In order to pull changes made on the official repository to your own repository, run these commands:
```bash
# This will create a new branch called opensuspect-main
git checkout -b opensuspect-main
# To look at your current branch
git branch
# You then want to fetch the new changes from the official repository (Make sure to run this while the opensuspect-main branch is selected!)
git fetch https://github.com/opensuspect/opensuspect.git
# Or, if you are using ssh
git fetch git@github.com:opensuspect/opensuspect.git
# Once you have done that, switch back to the main branch
git checkout main
# Then you should update your local branch with the official one
git merge opensuspect-main
# This is where all the problems happen.
# If it says there are conflicts, then you need to fix them, and good luck.
# If it says there are uncommitted changes, then you need to first make a commit of your changes before running git merge
# If everything worked, then you can push these to github
git push
```

For admins of the opensuspect repository, you should run very similar commands to the one above. Except you should be creating a branch for each other person's code, and you should be running `git pull` with the url of their repository.

Git understands all of this, and as soon as you push, it will recognize that you have merged the pull request, and it will close it for you.
