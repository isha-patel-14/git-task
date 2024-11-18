# Focused on Advanced Git Operations

# ** Part-1: Understanding and Using git stash **

# <ins> Task 1 :  Save Changes Temporarily with git stash </ins>
## 1. Make changes to a file without committing :
```bash
echo "Temporary changes" >> temp-file.txt
```
> ### <ins> Solution: </ins>
this will make a new file if does not exist and append some content to it .

## 2. View the status of changes :
```bash
git status
```
> ### <ins> Solution: </ins>
 it is used to check the status of the current working directory and staging area .

> it provides information about the untracked files ,changes not staged for commit, changes to be committed .

## 3. Stash the changes :
```bash
git stash
```
> ### <ins> Solution: </ins>
temporarily saves your uncommitted changes (both staged and unstaged) and cleans your working directory .

> This command saves changes to a stash and restores the working directory to the last commit state.

## 4. View the stashed changes :
```bash
git stash list
```
> ### <ins> Solution: </ins>
it is used to display a list of all the stashes you have saved in your repository .

<br></br>

# <ins> Task 2 :  Apply and Drop Stashed Changes </ins>
## 1. Apply the most recent stash :
```bash
git stash apply
```
> ### <ins> Solution: </ins>
it is used to reapply the most recent stash entry to your working directory .

> it does not remove the stash from the stash list, so you can reuse it later if needed .

## 2. Drop the most recent stash after applying it :
```bash
git stash drop
```
> ### <ins> Solution: </ins>
it removes a specific stash entry from the stash list . it is used when you no longer need a particular stash after applying or reviewing it .

> If no stash is specified, `git stash drop` removes the most recent stash .

## 3. Alternatively, to apply a specific stash :
```bash
git stash apply stash@{1}
```
> ### <ins> Solution: </ins>
it  is used to apply a specific stash from the stash list .

> `git stash apply` -> applies the changes saved in a specific stash to your working directory . this does not remove the stash from the list of stashes .

> `stash@{1}` -> refers to the second-most recent stash in the stash list . stashes are indexed starting from stash@{0} .

<br></br>

# <ins> Task 3 :  Stash Untracked Files </ins>
## 1. Stash changes, including untracked files :
```bash
git stash -u
```
> ### <ins> Solution: </ins>
it is used to stash both tracked and untracked files in your git working directory .

> `-u ( or --include-untracked )` -> in addition to stashing tracked changes, this flag also stashes untracked files .

## 2. Apply stashed changes including untracked files :
```bash
git stash apply
```
> ### <ins> Solution: </ins>
it is used to reapply the changes saved in the most recent stash or a specific stash without removing it from the stash list .

<br></br>
<hr></hr>
<br></br>

# ** Part-2: Rewriting History with git rebase **
# <ins> Task 4 : Rebase Commits to a New Base </ins>
## 1. Rebase the current branch onto main :
```bash
git rebase main
```
> ### <ins> Solution: </ins>
`git rebase main` is used to rebase the current branch onto the main branch .

> `git rebase` -> rebase command allows you to take all the changes (commits) from your current branch and apply them on top of another branch .

> `main` -> name of branch you want to rebase onto .

## 2. Resolve any conflicts that may arise during rebase, and continue :
```bash
git rebase --continue
```
> ### <ins> Solution: </ins>
it  is used during a rebase operation to resume the process after you've resolved any merge conflicts .

<br></br>

# <ins> Task 5 :  Canceling a Rebase </ins>
## 1. If a rebase goes wrong, abort it :
```bash
git rebase --abort
```
> ### <ins> Solution: </ins>
it is used to abort the rebase process and return your repository to the state it was in before you started the rebase .

<br></br>
<hr></hr>
<br></br>

# ** Part-3: Interactive Rebase (`git rebase -i`) **
# <ins> Task 6 : Use Interactive Rebase to Modify Commit History </ins>
## 1. View the last few commits :
```bash
git log --oneline
```
> ### <ins> Solution: </ins>
`git log` -> displays the commit history .

>`--oneline` -> formats the output to show each commit on a single line, displaying only the commit hash and commit message .

## 2. Start an interactive rebase for the last 3 commits :
```bash
git rebase -i HEAD~3
```
> ### <ins> Solution: </ins>
this command starts an interactive rebase for the last three commits in the current branch .

>it allows to edit, reorder, squash, or drop commits in a clean and controlled way.

## 3. Modify the commits by changing pick to one of the following :
* ###  `squash` (combine commits)
* ###  `reword` (edit commit message)
* ###  `edit` (edit commit content)
* ###  `drop` (remove commit)

## 4. Example of squashing two commits :
* ### Change the second commit from pick to squash and save .
* ### Git will combine the commit messages for the squashed commit .

<br></br>

# <ins> Task 7 :  Complete Interactive Rebase </ins>
1. ### After modifying the commits, save and close the editor .
2. ### Resolve any conflicts if prompted, then continue the rebase :
    ```bash
    git rebase --continue
    ```
    > ### <ins> Solution: </ins>
    it is used to continue a rebase operation after resolving conflicts that occurred during the rebase process .

<br></br>
<hr></hr>
<br></br>

# ** Part-4: Cherry-Picking Commits (`git cherry-pick`) **
# <ins> Task 8 : Pick a Specific Commit </ins>
## 1. View the commit history to find the commit hash you want to cherry-pick :
```bash
git log --oneline
```
> ### <ins> Solution: </ins>
`git log` -> displays the commit history .

>`--oneline` -> formats the output to show each commit on a single line, displaying only the commit hash and commit message .

## 2. Cherry-pick a specific commit by its hash :
```bash
git cherry-pick <commit-hash>
```
> ### <ins> Solution: </ins>
the command is used to apply the changes introduced by a specific commit from one branch to another branch .

> it creates a new commit on the current branch that duplicates the changes from the referenced commit .

## 3. Resolve conflicts if any, then commit the changes :
```bash
git add .
git cherry-pick --continue
```
> ### <ins> Solution: </ins>
`git add .` -> add all the files and changes to staging area .

>`git cherry-pick --continue` -> is used to continue a cherry-pick operation after resolving conflicts during the process of cherry-picking a commit .

<br></br>
<hr></hr>
<br></br>

# ** Part-5: Tagging Commits (`git tag`) **
# <ins> Task 9 : Tag a Commit </ins>
## 1. Tag the current commit with a version number :
```bash
git tag -a v1.0 -m "Initial release"
```
> ### <ins> Solution: </ins>
`tag` -> creates a tag in git . tags are used to mark specific points in the commit history, often for releases or important milestones .

> ` -a v1.0 ` -> Specifies the tag name (v1.0) 

> `-a` flag indicates that this is an annotated tag, which includes metadata like the tagger's name, email, and a message .

> `-m "Initial release" ` -> provides a message describing the tag .
this message is stored with the tag and can be viewed later .

## 2. List all tags :
```bash
git tag
```
> ### <ins> Solution: </ins>
it is used to create, list, and manage tags in a Git repository . 

> tags are typically used to mark specific points in the history of a repository, such as release points .

<br></br>

# <ins> Task 10 :  Tag a Specific Commit </ins>
## 1. Tag a specific commit by its hash :
```bash
git tag -a v1.1 <commit-hash> -m "Bug fix"
```
> ### <ins> Solution: </ins>
`git tag -a` -> this creates an annotated tag.

> `v1.1` -> this is the name of the tag you are creating. in this case, it is v1.1.

> `<commit-hash>` -> this is the commit hash you want to tag .  replace `<commit-hash>` with the actual hash (e.g., abc1234).

> `-m "Bug fix"` -> this specifies a message that describes the tag. in this case, the message is "Bug fix".

<br></br>

# <ins> Task 11 :  Push Tags to Remote </ins>
## 1. Push a specific tag to the remote repository :
```bash
git push origin v1.0
```
> ### <ins> Solution: </ins>
it  is used to push the tag `v1.0` to the remote repository .

## 2. Push all tags to the remote repository :
```bash
git push --tags
```
> ### <ins> Solution: </ins>
it is used to push all local tags in your git repository to the remote repository .

<br></br>
<hr></hr>
<br></br>

# ** Part-6: Working with Remote Repositories **
# <ins> Task 12 : Add a Remote Repository </ins>
## 1. Add a remote repository URL to the project :
```bash
git remote add origin https://github.com/username/repo.git
```
> ### <ins> Solution: </ins>
it is used to add a remote repository to your local Git repository .

# <ins> Task 13 : Fetch Changes from Remote </ins>
## 1. Fetch changes from the remote repository without merging them :
```bash
git fetch origin
```
> ### <ins> Solution: </ins>
it is used to update your local repository with the latest changes from the remote repository, without merging them into your working branch .

## 2. View fetched branches :
```bash
git branch -r
```
> ### <ins> Solution: </ins>
it  is used to list all remote branches in your Git repository .

<br></br>

# <ins> Task 14 : Pull Changes from Remote </ins>
## 1. Pull the latest changes from the remote repository and merge them into the local branch :
```bash
git pull origin main
```
> ### <ins> Solution: </ins>
is used to update your local `main` branch with the latest changes from the `main` branch on the remote repository (`origin`) .

<br></br>

# <ins> Task 15 : Push Changes to Remote </ins>
## 1. Push local changes to the remote repository :
```bash
git push origin main
```
> ### <ins> Solution: </ins>
it is used to push the commits in your local `main` branch to the `main` branch on the remote repository (referred to as `origin`) .


## 2. Push a new branch to the remote repository :
```bash
git push origin feature-branch
```
> ### <ins> Solution: </ins>
it is used to push the local branch `feature-branch` to the remote repository under the same name (`feature-branch`) .

<br></br>

# <ins> Task 16 : Delete Remote Branch </ins>
## 1. Delete a remote branch :
```bash
git push origin --delete feature-branch
```
> ### <ins> Solution: </ins>
is used to delete the remote branch named `feature-branch` from the remote repository .


<br></br>
<hr></hr>
<br></br>

# ** Part-7: Forking and Contributing to Open-Source Projects **
# <ins> Task 17 : Fork a Repository on GitHub </ins>
## 1. Go to a repository on GitHub and click Fork in the top right corner to create your own copy of the repository.

## 2. Clone the forked repository to your local machine :
```bash
git clone https://github.com/your-username/repo.git
```
> ### <ins> Solution: </ins>
it is used create a local copy of a remote repository from GitHub to the local machine .

<br></br>

# <ins> Task 18 : Make Changes and Commit </ins>
## 1. Create a new branch for your changes :
```bash
git checkout -b fix-typo
```
> ### <ins> Solution: </ins>
it creates a new branch and switch to it .

## 2. Make changes to the code (e.g., fix a typo in `README.md`), stage, and commit them :
```bash
git add README.md
git commit -m "Fixed typo in README.md"
```
> ### <ins> Solution: </ins>
this add README.md file with a commit message to the staging area .

<br></br>

# <ins> Task 19 : Push Changes to Your Fork </ins>
## 1. Push the changes to your remote fork :
```bash
git push origin fix-typo
```
> ### <ins> Solution: </ins>
it is use to push the changes to the repository .

<br></br>

# <ins> Task 20 : Create a Pull Request </ins>
1. ### Go to your forked repository on GitHub, click on Compare & Pull Request.
2. ### Write a description of your changes and submit the pull request to the original repository.

<br></br>

# <ins> Task 21 : Sync Your Fork with the Original Repository </ins>
## 1. Add the original repository as a remote source :
```bash
git remote add upstream https://github.com/original-owner/repo.git
```
> ### <ins> Solution: </ins>
it is used to add a new remote repository named `upstream` to your local git configuration . 

## 2. Fetch changes from the original repository :
```bash
git fetch upstream
```
> ### <ins> Solution: </ins>
it is used to fetch changes from the remote repository named `upstream` without merging them into your local branch . 

## 3. Merge changes from the original repository into your local branch :
```bash
git checkout main
git merge upstream/main
```
> ### <ins> Solution: </ins>
`git checkout main` -> switches to your local main branch.

> `git merge upstream/main` -> merges the changes from the remote-tracking branch `upstream/main` into your local main branch.

## 4. Push the changes to your fork :
```bash
git push origin main
```
> ### <ins> Solution: </ins>
it is used to push the commits in your local `main` branch to the `main` branch on the remote repository (referred to as `origin`) .

<br></br>
<hr></hr>
<br></br>

# ** Consolidated Flow Summary **
1. `Stashing` -> Saving and applying uncommitted changes temporarily.
2. `Rewriting History` -> Using git rebase and interactive rebase to modify and clean up commit history.
3. `Cherry-Picking` -> Selecting specific commits from another branch.
4. `Tagging` -> Labeling commits for versioning.
5. `Working with Remote Repositories` -> Managing remotes, pushing, pulling, and fetching changes.
6. `Forking & Contributing` -> Forking repositories, contributing to open-source projects, and syncing your fork.

<br></br>
<br></br>