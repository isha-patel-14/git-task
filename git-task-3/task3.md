# Focused on Repository Management, Commits, Branching, and Merging

# ** Part-1: Creating and Cloning Repositories **

# <ins> Task 1 :  Create a Local Git Repository </ins>
## 1. Create a new project folder :
```bash
mkdir MyProject
cd MyProject
```
> ### <ins> Solution: </ins>
 `mkdir folder_name` -> it is used to make new folder in current directory.

>`cd folder_name` -> it is used move into the folder

## 2. Initialize it as a Git repository :
```bash
git init
```
> ### <ins> Solution: </ins>
git init is used to initializes a new git repository in the current directory .

>it creates a hidden .git folder that tracks version control data .

## 3. Verify the repository status :
```bash
git status
```
> ### <ins> Solution: </ins>
 it is used to check the status of the current working directory and staging area .

> it provides information about the untracked files ,changes not staged for commit, changes to be committed .

<br></br>

# <ins> Task 2 : Clone a Remote Repository </ins>
## 1. Clone a GitHub repository :
```bash
git clone https://github.com/username/repo.git
```
> ### <ins> Solution: </ins>
it is used create a local copy of a remote repository from GitHub to the local machine .

## 2. Verify the cloned repository structure :
```bash
cd repo
ls -a
```
> ### <ins> Solution: </ins>
`cd repo` -> changes the current working directory to repository .

> `ls -a ` -> lists all files in the current directory, including hidden files .

<br></br>
<hr></hr>
<br></br>

# ** Part-2: Understanding Commits and Commit Messages **
# <ins> Task 3 : Commit Changes Locally </ins>
## 1. Create a new file and add content :
```bash
echo "Welcome to Git" > README.md
```
> ### <ins> Solution: </ins>
this creates a new file in the current repository with some content .

## 2. Stage the file :
```bash
git add README.md
```
> ### <ins> Solution: </ins>
it is use to add the file named README.md / changes to the staging area .

<br></br>

# <ins> Task 4 : Write Effective Commit Messages </ins>
## 1. Create a detailed commit message :
```bash
git commit -m "Added initial version of README.md with project overview"
```
> ### <ins> Solution: </ins>
it is used to give a commit to the changes made which describe the changes done .

## 2. Commit multiple files with one message :
```bash
touch file1.txt file2.txt
git add .
git commit -m "Added two new files for feature setup"
```
> ### <ins> Solution: </ins>
`touch` -> creates empty files named `file1.txt` and `file2.txt` in the current directory (if they don't already exist) .

> ` add . ` -> add all the files to the staging area .

> `commit -m `-> it is used to give a commit to the changes made which describe the changes done .

> here both the files will have the same commit .

<br></br>
<hr></hr>
<br></br>

# ** Part-3: Viewing Commit History with git log **
# <ins> Task 5 : View Detailed Commit History </ins>
## 1. View full commit logs :
```bash
git log
```
> ### <ins> Solution: </ins>
it is use to see/check the commit history .

## 2. View commit history in a compact format :
```bash
git log --oneline
```
> ### <ins> Solution: </ins>
`git log` -> displays the commit history .

>`--oneline` -> formats the output to show each commit on a single line, displaying only the commit hash and commit message .

<br></br>

# <ins> Task 6 : Customize Log Outputs </ins>
## 1. View logs with a graphical representation :
```bash
git log --oneline --graph --decorate
```
> ### <ins> Solution: </ins>
 this command provides a concise, visual representation of your commit history in git .

> `--oneline` -> displays each commit on a single line, showing only the abbreviated commit hash and the commit message .

> `--graph` -> shows a text-based visual representation of the branch structure, with lines connecting the commits to depict how branches diverged or merged .

> `--decorate` -> adds references to the commit hashes for any branch, tag, or other Git references to help identify the positions of branches and tags . 

## 2. Filter logs for a specific file :
```bash
git log README.md
```
> ### <ins> Solution: </ins>
it shows the commit history for a specific file (README.md) .

<br></br>
<hr></hr>
<br></br>

# ** Part-4: Understanding Branching and Merging **
# <ins> Task 7 : Understanding Branching </ins>
## 1. List all branches :
```bash
git branch
```
> ### <ins> Solution: </ins>
it is used to display all the branches in the repository .

## 2. Create a new branch :
```bash
git branch feature-branch
```
> ### <ins> Solution: </ins>
it creates a new branch without switching to it .

## 3. Switch to the new branch :
```bash
git checkout feature-branch
```
> ### <ins> Solution: </ins>
it switch to the branch named feature-branch .

## Alternative Command :
```bash
git checkout -b feature-branch
```

> ### <ins> Solution: </ins>
it creates a new branch and also switch to it in a single command .

<br></br>
<hr></hr>
<br></br>

# ** Part-5: Creating and Working with Branches **
# <ins> Task 8 : Make Changes in a Branch </ins>
## 1. Add content to a file in the new branch :
```bash
echo "Feature in progress" > feature.txt
git add feature.txt
git commit -m "Added feature.txt in feature-branch"
```
> ### <ins> Solution: </ins>
 `echo` -> it will create a new file .

>`add` -> it will add the new file to the git .

>`commit -m` -> it will commit the changes .

# <ins> Task 9 : Merging Branches </ins>
## 1. Switch back to the `main` branch :
```bash
git checkout main
```
> ### <ins> Solution: </ins>
it switch to the `main` branch .

## 2. Merge the `feature-branch` into `main` :
```bash
git merge feature-branch 
```
> ### <ins> Solution: </ins>
it combines the changes from `feature-branch` branch into `main` branch .

<br></br>
<hr></hr>
<br></br>

# ** Part-6: Resolving Merge Conflicts **
# <ins> Task 10 : Simulate a Merge Conflict </ins>
## 1. Modify the same line in a file on two branches :
```bash
echo "Main branch content" > conflict.txt
git add conflict.txt
git commit -m "Added conflict.txt in main branch"
```
> ### <ins> Solution: </ins>
 `echo` -> it will create a new file .

>`add` -> it will add the new file to the git .

>`commit -m` -> it will commit the changes .

## 2. Switch to the other branch and make conflicting changes :
```bash
git checkout feature-branch
echo "Feature branch content" > conflict.txt
git add conflict.txt
git commit -m "Modified conflict.txt in feature-branch"
```
> ### <ins> Solution: </ins>
`checkout` -> switch to the branch assigned .

> `echo` -> it will create a new file .

>`add` -> it will add the new file to the git .

>`commit -m` -> it will commit the changes .

## 3. Merge `feature-branch` into `main` :
```bash
git checkout main
git merge feature-branch 
```
> ### <ins> Solution: </ins>
`checkout` -> switch to the branch main .

> `merge` -> it combines the changes from `feature-branch` branch into `main` branch .

## 4. Resolve the conflict by editing the file and choosing the correct version :
* ## Open `conflict.txt` and decide which changes to keep .
* ## Stage the resolved file :
    ```bash
    git add conflict.txt
    ```
    > ### <ins> Solution: </ins>
    it adds the file to the repository .
* ## Commit the merge :
    ```bash
    git commit -m "Resolved conflict in conflict.txt"
    ```
    > ### <ins> Solution: </ins>
    it commits the changes made .

<br></br>
<hr></hr>
<br></br>

# ** Part-7: Deleting and Renaming Branches **
# <ins> Task 11 : Delete a Branch </ins>
## 1. Delete a local branch :
```bash
git branch -d feature-branch
```
> ### <ins> Solution: </ins>
it is used to delete a branch only if it has been fully merged .

## 2. Force-delete a branch :
```bash
git branch -D feature-branch
```
> ### <ins> Solution: </ins>
it is used to delete a branch only if it has not been merged .

<br></br>

# <ins> Task 12 : Rename a Branch </ins>
## 1. Rename the current branch :
```bash
git branch -m new-branch-name
```
> ### <ins> Solution: </ins>
it is use to rename current branch .

## 2. Rename another branch (not checked out) :
```bash
git branch -m old-branch-name new-branch-name
```
> ### <ins> Solution: </ins>
it is use to rename any other branch which is not checked out .

<br></br>
<hr></hr>
<br></br>

# ** Consolidated Flow Summary **

1. Start by creating and cloning repositories.
2. Learn to commit changes effectively with clear messages.
3. Explore commit history using various `git log` commands.
4. Understand branching and practice creating, switching, and merging branches.
5. Dive into resolving merge conflicts.
6. End by managing branches through deletion and renaming.
