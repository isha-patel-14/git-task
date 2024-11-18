# ** Part-1: Introduction to version control and git **

# <ins> Task 1 : Install and config git </ins>
## 1. Configure Git with your username and email :
```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```
> ### <ins> Solution: </ins>
>git config is used to configure git settings, such as username, email .

>Using `--global` applies the settings globally for all repositories.

## 2. View your Git configuration :
```bash
git config --list
```
> ### <ins> Solution: </ins>
>displays a list of all the git configuration settings currently in effect .

>it includes global, system, and local configurations, showing details like username, email, and other preferences .  

<br></br>

# <ins>Task 2 : Initialize a Repository</ins>
## 1. Create a new project folder and navigate to it :
```bash
mkdir MyProject
cd MyProject
```
> ### <ins> Solution: </ins>
>`mkdir folder_name` -> it is used to make new folder in current directory.

>`cd folder_name` -> it is used move into the folder

## 2. Initialize it as a Git repository :
```bash
git init
```
> ### <ins> Solution: </ins>
>git init is used to initializes a new git repository in the current directory .

>it creates a hidden .git folder that tracks version control data .

<br></br>

# <ins>Task 3 : Create a File and Make Multiple Commits</ins>
## 1. Create a new file and add content :
```bash
echo "my first project" > README.md
```
> ### <ins> Solution: </ins>
>this is used to make a new file named README.md in the current directory with the text entered in the double quotes .

> `>` -> redirects the output to a file .

## 2. Stage the file :
```bash
git add README.md
```
> ### <ins> Solution: </ins>
>this is use to add a particular file to the git .

## 3. Commit the file :
```bash
git commit -m "initial commit"
```
> ### <ins> Solution: </ins>
>this is used to save the changes to the local repository .

> it is used with the `-m` flag to provide a commit message that describes the changes you are committing .
> commit message is written in `" "` .

## 4. Make changes to the file :
```bash
echo "added a description" >> README.md
```
> ### <ins> Solution: </ins>
>this is used to append the text "added a description" to the README.md file in your repository .

> if the file does nnot exist , the file will be created .

## 5. Stage and commit the changes :
```bash
git add README.md
git commit -m "updated README.md with a description"
```
> ### <ins> Solution: </ins>
>this is used to add updated file to the staging area with the commit message about what changes have been done.

<br></br>

# <ins> Task 4 : Check Status and Log </ins>
## 1. Check the repository’s current status :
```bash
git status
```
> ### <ins> Solution: </ins>
>it is used to check the status of the current working directory and staging area .

> it provides information about the untracked files ,changes not staged for commit, changes to be committed .


## 2. View commit history in detail :
```bash
git log --oneline --graph --decorate
```
> ### <ins> Solution: </ins>
>this command provides a concise, visual representation of your commit history in git .

> `--oneline` -> displays each commit on a single line, showing only the abbreviated commit hash and the commit message .

> `--graph` -> shows a text-based visual representation of the branch structure, with lines connecting the commits to depict how branches diverged or merged .

> `--decorate` -> adds references to the commit hashes for any branch, tag, or other Git references to help identify the positions of branches and tags . 

<br></br>

# <ins> Task 5 : Create and Clone a Repository </ins>
## 1.Create a repository on GitHub (eg.: example-repo)
## 2.Clone it locally :
```bash
git clone http://codinggita.com/example-repo
```
> ### <ins> Solution: </ins>
>it is used to create a local copy of a remote git repository .

> it will download all the files, history, and branches from a remote repository and set up a local version on your machine .

<br></br>

# <ins> Task 6 : Understanding the Git Workflow </ins>
* ## Example Workflow :
   1. ### Make changes to a file in the working directory :
   ```bash
   echo "Workflow example" > workflow.md
   ```
   2. ### Stage the file :
   ```bash
   git add workflow.md
   ```
   3. ### Commit the file to the repository :
   ```bash
   git commit -m "added workflow example"
   ```

> ### <ins> Solution: </ins>
>this workflow will first make a file with some content and then it will be added to the staging area with a commit message describing about the work/changes done .

<br></br>
<hr></hr>
<br></br>

# ** Part-2: Working with Repositories **

# <ins> Task 7 : Branching and Merging </ins>
## 1. Create a new branch for a feature :
```bash
git branch feature-login
git checkout feature-login
```
> ### <ins> Solution: </ins>
>`branch` -> it is used to make a new branch in git repository .

>`checkout` -> it is used to switch the branch to the newly made branch .

### <ins> ** OR USE :** </ins>

```bash
git checkout -b feature-login
```
> ### <ins> Solution: </ins>
>`checkout -b` -> is used to make a new branch in git repository and switch the branch to the newly made branch .

## 2. Add a new file and commit changes :
```bash
echo "login page" > login.html
git add login.html
git commit -m "added login page"
```
> ### <ins> Solution: </ins>
>`echo` -> it will create a new file .

>`add` -> it will add the new file to the git .

>`commit -m` -> it will commit the changes .

## 3. Merge the feature branch into `main` :
```bash
git checkout main
git merge feature-login
```
> ### <ins> Solution: </ins>
>`checkout` -> it will switch the branch to main .

>`merge` -> it will integrate changes from one branch into another .

<br></br>

# <ins> Task 8 : Handling Merge Conflicts </ins>
## 1. Create two Branches :
```bash
git branch branch-A
git branch branch-B
```
> ### <ins> Solution: </ins>
>this will make two different branches , branch-A and branch-B .

## 2. Modify the same line in README.md in both brnaches.
## 3. Merge `branch-A`  into `main` :
```bash
git checkout main
git merge branch-A
```
> ### <ins> Solution: </ins>
>the branch will switch to main and the changes will integrate to main branch .

## 4. Attempt to merge `branch-B`  into `main`(this will cause a conflict) :
```bash
git merge branch-B
```

> ### <ins> Solution: </ins>
>this will cause a conflict beacuse of different data at a single place in the files that are trying to get merged .


 ##  <ins> To resolve the conflict :- </ins>
* Open the conflicted files. Git marks the conflicting areas with conflict markers like this :
```bash
<<<<<<< HEAD
Changes in the main branch
=======
Changes in branch-B
>>>>>>> branch-B
```
* Edit the file(s) to resolve the conflict. Decide which changes to keep or combine them in a way that makes sense for your project .

## 5. Resolve the conflict manually in README.md , then :
```bash
git add READEME.md
git commit -m "resolved merge conflict between branch-A and branch-B "
```
> ### <ins> Solution: </ins>
>this will add the file and commit the changes done .

<br></br>

# <ins> Task 9 : Renaming and Deleting Branches </ins>
## 1. Rename a Branch :
```bash
git branch -m old-branch-name new-branch-name
```
> ### <ins> Solution: </ins>
>it is use to rename a branch .

## 2. Delete a Branch :
```bash
git branch -d feature-login
```
> ### <ins> Solution: </ins>
>it is use to delete a branch .

<br></br>
<hr></hr>
<br></br>

# ** Part-3: Advanced Git Operations **
# <ins> Task 10 : Using Git Stash </ins>
## 1. Make changes to a file but don't commit :
```bash
echo "temporary work" >> temp.md
```
> ### <ins> Solution: </ins>
>it will make a new file name temp.md and have a content "temporary work"

## 2. Stash the chnages :
```bash
git stash
```
> ### <ins> Solution: </ins>
>it is used to temporarily save changes in your working directory that you don't want to commit yet but need to set aside to work on something else

## 3. View stashed changes :
```bash
git stash list
```
> ### <ins> Solution: </ins>
>it is used to display a list of all the stashes you have saved in your repository .

## 4. Apply the stashed changes :
```bash
git stash apply
```
> ### <ins> Solution: </ins>
>it is used to reapply the changes saved in the most recent stash or a specific stash without removing it from the stash list .


## 5. Drop the stash after applying :
```bash
git stash drop
```
> ### <ins> Solution: </ins>
>it is used to delete a specific stash from the stash list .

>This is useful when you no longer need a stash and want to clean up your stash list .

<br></br>

# <ins> Task 11 : Rewriting History with Interactive Rebase </ins>
## 1. Create multiple commits :
```bash
echo "Commit 1" > file1.txt && git add file1.txt && git commit -m "Commit 1"
echo "Commit 2" > file2.txt && git add file2.txt && git commit -m "Commit 2"
echo "Commit 3" > file3.txt && git add file3.txt && git commit -m "Commit 3"
```
> ### <ins> Solution: </ins>
>the commands create three new files (`file1.txt`, `file2.txt`, `file3.txt`), add content to them, and commit each one to the git repository with a unique commit message .

## 2. Squash commits into one :
```bash
git rebase -i HEAD~3
```
> ### <ins> Solution: </ins>
>this command starts an interactive rebase for the last three commits in the current branch .

>it allows to edit, reorder, squash, or drop commits in a clean and controlled way.

<br></br>

# <ins> Task 12 : Cherry-Picking Commits </ins>
## 1. Create a new branch :
```bash
git checkout -b cherry-pick-example
```
> ### <ins> Solution: </ins>
>the commands create a new branch and switch to the the branch created .

## 2. Cherry-pick a specific commit from another branch :
```bash
git cherry-pick <commit-hash>
```
> ### <ins> Solution: </ins>
>the command is used to apply the changes introduced by a specific commit from one branch to another branch .

> it creates a new commit on the current branch that duplicates the changes from the referenced commit .

<br></br>

# <ins> Task 13 : Tagging Commits </ins>
## 1. Tag the current commit :
```bash
git tag -a v1.0 -m "Version 1.0 release"
```
> ### <ins> Solution: </ins>
>`tag` -> creates a tag in git . tags are used to mark specific points in the commit history, often for releases or important milestones .

> ` -a v1.0 ` -> Specifies the tag name (v1.0) 

> `-a` flag indicates that this is an annotated tag, which includes metadata like the tagger's name, email, and a message .

> `-m "Version 1.0 release" ` -> provides a message describing the tag .
this message is stored with the tag and can be viewed later .

## 2. Push the tag to the remote repository :
```bash
git push origin v1.0
```
> ### <ins> Solution: </ins>
>it is used to push the branch or tag named `v1.0` to the remote repository named origin .

<br></br>

# <ins> Task 14 : Working with Remote Repositories </ins>
## 1. Add a remote repository :
```bash
git remote add origin <repository-url>
```
> ### <ins> Solution: </ins>
>it is used to add a remote repository to your local Git repository .

## 2. Push your changes to the remote repository :
```bash
git push origin main
```
> ### <ins> Solution: </ins>
>it is used to push the the changes from your local main branch to the main branch on the remote repository named origin .

<br></br>

# <ins> Task 15 : Forking and Contributing </ins>
## 1. Fork a repository on GitHub.
## 2. Clone the fork locally :
```bash
git clone <forked-repo-url>
```
> ### <ins> Solution: </ins>
>it is used to create a local copy of a repository from a remote source.

## 3. Create a new branch, make changes, and push :
```bash
git checkout -b fix-typo
echo "Typo fixed" >> README.md
git add README.md
git commit -m "Fixed a typo"
git push origin fix-typo
```
> ### <ins> Solution: </ins>
>`checkout -b` -> use to make a new branch and switch to it .

> ` echo "content" >> file_name` -> use to make new file and add content in it .

>`add` -> it is use to add a file to git repository .

> `commit -m` -> used to commit the made changes .

> `push origin` -> use to push th changes to the main branch in the git repository .

## 4. Open a pull request on GitHub.

<br></br>
<hr></hr>
<br></br>

# ** Part-4: Additional Practice **
# <ins> Task 16 : Simulate Team Collaboration </ins>
## 1. Create a repository and share it with a friend
## 2.Both make changes to the same file simultaneously
## 3.Practice resolving merge conflicts and pushing changes


# <ins> Task 17 : Git Ignore </ins>
## 1. Create a `.gitignore` file :
```bash
echo "node_modules/" > .gitignore
```
> ### <ins> Solution: </ins>
>it  adds the `node_modules/` directory to a `.gitignore` file, which tells git to ignore the `node_modules` directory in the version control system .


## 2. Add files and ensure ignored files are not staged :
```bash
git add .
```
> ### <ins> Solution: </ins>
>it adds all the files to the git from your local machine .