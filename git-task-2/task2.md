# ** Part-1: Git Basics **

# <ins> Task 1 : Install and configure git </ins>
## 1. Install git from `git-scm.com` .
## 2. Configure your global Git settings :
```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```
> ### <ins> Solution: </ins>
>git config is used to configure git settings, such as username, email .

 >Using `--global` applies the settings globally for all repositories.

 ## 3. Verify the configuration :
```bash
git config --list
```
> ### <ins> Solution: </ins>
>displays a list of all the git configuration settings currently in effect .

>it includes global, system, and local configurations, showing details like username, email, and other preferences . 

<br></br>

# <ins>Task 2 : Initialize a Repository</ins>
## 1. Create a directory and initialize it as a Git repository :
```bash
mkdir MyProject
cd MyProject
git init
```
> ### <ins> Solution: </ins>
 >`mkdir folder_name` -> it is used to make new folder in current directory.

 > `cd folder_name ` -> it is used to move into that folder .

 > `init` -> it is used to initialize the git repository .

<br></br>
<hr></hr>
<br></br>

# ** Part-2: Basic Workflow **
# <ins> Task 3 : Creating and Commiting Files </ins>
## 1. Create a file :
```bash
echo "Hello Git" > file1.txt
```

> ### <ins> Solution: </ins>
>it is used to make a new file with some content written in double quotes .

## 2. Stage and commit the file :
```bash
git add file1.txt
git commit -m "Initial commit: Added file1.txt"
```

> ### <ins> Solution: </ins>
>`add` -> it is use to add file to the git repository .

> `commit -m` -> it is used to commit the changes done .

<br></br>

# <ins>Task 4 : Viewing Changes</ins>
## 1. Modify the file :
```bash
echo "Git is awesome!" >> file1.txt
```
> ### <ins> Solution: </ins>
>it is used to update the pre-existing file .

## 2. Check file status and differences :
```bash
git status
git diff
```
> ### <ins> Solution: </ins>
>`status` ->  it is used to check the status of the current working directory and staging area .
it provides information about the untracked files ,changes not staged for commit, changes to be committed .

> `diff` -> is used to view the differences between repository states, like the working directory, staging area, or commits . it is useful for reviewing changes before committing .

<br></br>

# <ins>Task 5 : Undoing Changes</ins>
## 1. Unstage a staged file :
```bash
git reset file1.txt
```
> ### <ins> Solution: </ins>
>it is used to unstage changes to `file1.txt` that were added to the staging area, without affecting the working directory .

## 2.Discard uncommitted changes :
```bash
git checkout -- file1.txt
```
> ### <ins> Solution: </ins>
>it  is used to discard all local changes made to `file1.txt` , restoring it to the state of the last commit .

<br></br>
<hr></hr>
<br></br>

# ** Part-3: Branching and Merging **
# <ins> Task 6 : Branch Management </ins>
## 1. Create a branch and switch to it :
```bash
git checkout -b feature-branch
```

> ### <ins> Solution: </ins>
>it is used to create a new branch and switch to it directly .

## 2. List branches :
```bash
git branch
```

> ### <ins> Solution: </ins>
>it is used to manage and view branches in a Git repository . 

> it allow us to work on different versions of your project simultaneously .

## 3. Rename a branch :
```bash
git branch -m feature-branch feature-enhanced
```
> ### <ins> Solution: </ins>
>it is used to change the name of a branch created already .

<br></br>

# <ins>Task 7 : Merging Branches</ins>
## 1. Merge `feature-enhanced` into `main` :
```bash
git checkout main
git merge feature-enhanced
```
> ### <ins> Solution: </ins>
>`checkout` -> used to switch the branch .

> `merge` -> used to merge different branches .

<br></br>

# <ins>Task 8 : Handling Merge Conflicts</ins>
## 1. Create two conflicting branches and resolve a conflict manually :
```bash
git merge <branch-name>
```
> ### <ins> Solution: </ins>
> `merge` -> used to merge different branches .

## 2. Use :
```bash
git add <resolved-file>
git commit
```
> ### <ins> Solution: </ins>
> `add` -> used to add the file to the git repository .

 > `commit` -> used to commit the changes done .

<br></br>
<hr></hr>
<br></br>

# ** Part-4: Remote Repositories **
# <ins> Task 9 : Remote Setup </ins>
## 1. Add a remote repository :
```bash
git remote add origin https://github.com/your-username/repo.git
```

> ### <ins> Solution: </ins>
>it is used to link your local Git repository to a remote repository hosted on a platform like GitHub .

## 2. Verify the remote :
```bash
git remote -v
```
> ### <ins> Solution: </ins>
>displays the remote repositories associated with your local Git repository and their URLs .

<br></br>

# <ins>Task 10 : Push and Pull</ins>
## 1. Push changes to the remote repository :
```bash
git push -u origin main
```
> ### <ins> Solution: </ins>
>it is use to push the changes made to the remote repository .

## 2. Pull changes from the remote :
```bash
git pull origin main
```
> ### <ins> Solution: </ins>
>it is use to pull the changes from the remote repository to the local .

<br></br>

# <ins>Task 11 : Cloning a Repository</ins>
## 1. Clone a remote repository :
```bash
git clone https://github.com/your-username/repo.git
```
> ### <ins> Solution: </ins>
>it is used create a local copy of a remote repository from GitHub to the local machine .

<br></br>
<hr></hr>
<br></br>

# ** Part-5: Branching and Merging **
# <ins> Task 12 : Stashing Changes </ins>
## 1. Save uncommitted changes :
```bash
git stash
```
> ### <ins> Solution: </ins>
>temporarily saves your uncommitted changes (both staged and unstaged) and cleans your working directory .

## 2. Apply stashed changes :
```bash
git stash apply
```
> ### <ins> Solution: </ins>
>it is used to reapply the most recent stash entry to your working directory .

> it does not remove the stash from the stash list, so you can reuse it later if needed .

## 3. Drop the stash :
```bash
git stash drop
```
> ### <ins> Solution: </ins>
>it removes a specific stash entry from the stash list . it is used when you no longer need a particular stash after applying or reviewing it .

> If no stash is specified, `git stash drop` removes the most recent stash .

<br></br>

# <ins>Task 13 : Tagging Commits </ins>
## 1. Create and annotate a tag :
```bash
git tag -a v1.0 -m "Version 1.0 release"
```
> ### <ins> Solution: </ins>
>`tag` -> creates a tag in git . tags are used to mark specific points in the commit history, often for releases or important milestones .

> ` -a v1.0 ` -> Specifies the tag name (v1.0) 

> `-a` flag indicates that this is an annotated tag, which includes metadata like the tagger's name, email, and a message .

> `-m "Version 1.0 release" ` -> provides a message describing the tag .
this message is stored with the tag and can be viewed later .

## 2. Push the tag to the remote :
```bash
git push origin v1.0
```
> ### <ins> Solution: </ins>
>it is used to push the branch or tag named `v1.0` to the remote repository named origin .

<br></br>

# <ins>Task 14 : Rewriting Commit History </ins>
## 1. Use interactive rebase to modify commit messages :
```bash
git rebase -i HEAD~3
```
> ### <ins> Solution: </ins>
>this command starts an interactive rebase for the last three commits in the current branch .

>it allows to edit, reorder, squash, or drop commits in a clean and controlled way.

<br></br>

# <ins>Task 15 : Cherry-Picking Commits </ins>
## 1. Apply a specific commit to another branch :
```bash
git cherry-pick <commit-hash>
```
> ### <ins> Solution: </ins>
>the command is used to apply the changes introduced by a specific commit from one branch to another branch .

> it creates a new commit on the current branch that duplicates the changes from the referenced commit .

<br></br>
<hr></hr>
<br></br>

# ** Part-6: Collaboration **
# <ins> Task 16 : Forking and Pull Requests </ins>
## 1. Fork a repository and clone it locally :
```bash
git clone https://github.com/your-username/forked-repo.git
```
> ### <ins> Solution: </ins>
>it is used to copy a forked repository from GitHub to your local machine . this allows you to work on the forked repository locally, make changes, and push updates back to your fork .

## 2. Make changes and push them :
```bash
git checkout -b fix-typo
echo "Typo fixed" >> README.md
git commit -m "Fixed a typo"
git push origin fix-typo
```
> ### <ins> Solutions: </ins>
>`checkout -b` -> creates a new branch and switch to it .

> `echo " " >> file_name ` -> used to update the file content .

> `commit -m` -> used to commit the changes done .

> `push origin` -> use to push the changes to the repository .

## 3. Open a pull request on GitHub .

<br></br>

# <ins> Task 17 : Simulating Team Collaboration </ins>
## 1. Simulate a conflict by having two users modify the same file .
## 2. Practice resolving the conflict as a team .


<br></br>
<hr></hr>
<br></br>

# ** Part-7: Ignoring Files **
# <ins> Task 18 : Using .gitignore </ins>
## 1. Create a `.gitignore` file :
```bash
echo "node_modules/" > .gitignore
git add .gitignore
git commit -m "Added .gitignore"
```
> ### <ins> Solution: </ins>
 >`echo " " > file_name ` -> used to create a new file and add some content into it .

 > `add .` -> it is used to add all the files to the git repository .

 > `commit -m` -> it is used to commit the changes made .

 ## 2. Verify that ignored files are not staged :
```bash
git status
```
> ### <ins> Solution: </ins>
> displays the current state of your git working directory and staging area .
 
<br></br>
<hr></hr>
<br></br>

# ** Part-8: Automation and Cleanup **
# <ins> Task 19 :  Cleaning the Repository </ins>
## 1. Remove untracked files :
```bash
git clean -f
```
> ### <ins> Solution: </ins>
>it is used to delete untracked files from your working directory . 

> this is useful when you want to clean up unnecessary files that git is not tracking .

# <ins> Task 20 :  Aliases and Shortcuts </ins>
## 1. Create an alias for frequently used commands :
```bash
git config --global alias.st status
git config --global alias.cm commit
```
> ### <ins> Solution: </ins>
>`git config` -> Modifies Git's configuration files.

> `--global` -> Applies the configuration globally for all repositories on your system.

> `alias.st` -> Creates a shortcut for the git status command. After this, you can type git st instead of git status.

> `alias.cm` -> Creates a shortcut for the git commit command.After this, you can type git cm instead of git commit.

## 2. Use the alias :
```bash
git st
git cm -m "Message"
```
> ### <ins> Solution: </ins>
>`git st` -> Execute the git status.

> `git cm -m "Message" ` -> Execute the git commit in "message".
 
<br></br>
<hr></hr>
<br></br>
<br></br>