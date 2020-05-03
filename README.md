## General Workflow for Git

### Part I: Before start working

`git pull origin master` to get updates from other teammates. The git will automatically resolve merge
conflicts. But there can be situations when some conflicts need to get resolved manually. 

### Part II: Before pushing to remote repo

1. `git add .` to add all modified files to stagging area. 

2. `git commit -m "msg"` to commit the changes.

3. `git push origin master` to push to the master branch on the remote Github repo.

(90% of failures in pushing to master is caused by forgetting to run `git pull origin master` at first).

### Part III (Optional): Create branches for work

Sometimes there are tentative changes that are either incomplete or unstable, making the commit dangerous
to be pushed directly to the master. One potential way to fix this issue is to work locally until the codes are safe for use. Another way is to create branches locally and push them to branches in the Github repo.

1. `git checkout -b XYZ` to create a branch called XYZ.

2. Follow the same `add` and `commit` procedures as Part II.

3. Run `git push origin XYZ` instead of `git push origin master` when pushing to Github.

When a branch is ready to get merged with the master branch, it's recommended (and best practice) to send
out a `pull request` for other teammates to review other than directly performing the merge operation locally.

### Part IV: Using .gitignore file to filter folders/files not to be committed

Due to settings of different editors/languages, our workspace might contain undesirable folder/file generated automatically (e.g. `.vscode` file by vscode). We may not want to commit them together to the Github repo (these files can be useless for other people). The `.gitignore` file helps us solve this issue easily. Please check the `.gitignore` file already created by Star Li as a reference.

`final_proj_data/basketball/*` this line means that we omit all the files (`*`) in the `basketball` folder, so we only want to commit data related to COVID19 dataset. Similarly, `.vscode` on the third line tells git not to consider the .vscode file as part of our workspace.
