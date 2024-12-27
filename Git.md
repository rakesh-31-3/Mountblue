------Git---------
Git: git is a tool that tracks the changes in the code over time.
Github: github is a website where you host all of your git repositories.Being online ,it makes easy to work with groups and other people and organize your projects.
What is git?
Git is a **distributed version control** system that tracks changes in files and enables collaboration among developers. It’s a popular tool for software development, used by over 90% of professional developers.
Git Featues:
1.Distributed: Each developer has a local copy of the entire project history, known as a “repository” (or “repo”). This allows them to work offline and synchronize changes later.
2.Version control: Git tracks changes to files, allowing you to recall specific versions or iterations of your project.
3.Branching and merging: Developers can create separate branches to work on features or fixes, and then merge their changes with the main branch (e.g., “master”).
4.Concurrency: Multiple developers can work on different parts of the project simultaneously, without conflicts.
5.Attributable changes: Each commit (change) is attributed to a specific developer, making it easy to track who made changes and when.
6.Reverting: You can easily revert to a previous version of the project if needed.

1.Repository: A repository commonly refered as repo and it's a collection of a source code.A repository has commits to the project or set of a commits to the.
2.Commit: A commit logs the change or series of changes in the repo(source code).A commit has a unique SHA1 hash which is used to keep track of files changed in the past. A series of commits comprises the Git history.
3.Branches: A branch is essentially a unique set of code changes with a unique name. Each repository can have one or more branches. The main branch — the branch where all the changes eventually get merged into - is called the master or main. This is the official working version of your project and the one that you will see when you visit the project repository at github.com/yourname/projectname.

1.Version Controll System:
1.Centralized: in the Centralized system all the members are connected with Centralized server to get the leatest copy of the code. so if the server get into offline then we can't able to access it we need to wait untill it's get onlined.
2.Distributed: in the Distributed system every team member have the copy of the project on their machine.so they can able to work separetly and able to merge into the signle file using the git,mercurial

Git Commands:
1.clone: Bring a repository that is hosted somewhere like github into a folder on your local machine.
Example: git clone url
2.add: track your files and changes in Git.
Example: git add fileName
git add . -> add all the files of the current direcotory
3.commit: save your files in Git.
4.push: Upload git commits to a remote repo,like github.
5.pull: Download the changes from remote repo to your local machine,the opposite of push
6.Creating the new branch:
git branch 'branchname'
Switch to the new branch:
git checkout 'branchname'
Alternatively, you can create and switch to the new branch in one step using:
git checkout -b 'branchname' 7. git reflog: used to display all the commit's that we done

SSH Keys:
SSH keys provide a more secure and convenient way to authenticate and manage remote connections compared to traditional password-based authentication.
Steps to Generate SSH Keys:

1. ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
   -t rsa: Specifies the key type (rsa is widely used).
   -b 4096: Sets the key length to 4096 bits for better security.
   -C "your_email@example.com": Adds a label to your key, typically your email address.
   2.Specify a File to Save the Key: You will be prompted to specify the file where the key should be saved.
   Press Enter to save the key in the default location (~/.ssh/id_rsa).
   3.Set a Passphrase (Optional): You’ll be asked to enter a passphrase to secure the private key.
   You can leave it empty by pressing Enter, but adding a passphrase provides an additional layer of security.pbcopy
   Copy SSH Key:
   use xclip to copy ssh key.
   xclip -sel clip < ~/.ssh/id_rsa.pub
   Add SSH key to GitHub:
   Go to github settings > SSH and GPG Keys > add new ssh key > Generate

Configure your Git environment to use SSH and test the connection:

1.  Test the SSH Connection: You need to confirm that your local machine can successfully connect to GitHub using the SSH key.
    ssh -T git@github.com
    or
    ssh -T git@gitlab.com
    Output: Hi username! You've successfully authenticated, but GitHub does not provide shell access.
    2.Add the SSH Key to the SSH Agent: The SSH agent manages your private keys, so you don’t have to enter the passphrase repeatedly.
    eval "$(ssh-agent -s)"
    2.1 Add Your SSH Key:
    ssh-add ~/.ssh/id_rsa
    2.2 Verify the Key is Added:
    ssh-add -l
    3.Update Your Git Remote URL to Use SSH:
    git remote set-url origin git@github.com:username/repository.git
    for Git Lab: https://docs.gitlab.com/ee/user/ssh.html#generate-an-ssh-key-pair

## Undo Changes

## 1.Committed the Wrong Message

### Fix the last commit message:

```bash
git commit --amend -m "Correct message"
```

## 2.Skipped a File in the Last Commit

### Add the missed file and update the commit

```bash
git add <file>
git commit --amend --no-edit
```

## 3. Accidentally Committed on Master

### Reset the commit on the master branch

```bash
git reset HEAD~ --soft
```

### This will undo the last commit but keep the changes in your working directory. You can now switch branches:

```bash
git checkout <branch-name>
git add .
git commit -m "Commit message"
```

## 4. Accidentally Committed to the Wrong Branch

### Move the commit to the correct branch:

```bash
git checkout -b <correct-branch>
```

### This creates a new branch from the current state. If you need the commit removed from the original branch:

```bash
git checkout <wrong-branch>
git reset HEAD~ --soft
git stash
```

### Now you can apply the stash on the correct branch:

````bash
git checkout <correct-branch>
git stash pop
```
## 5. Want to Undo the Last 5 Commits
### Remove the last 5 commits while keeping changes
```bash
git revert HEAD~5 --sort
```
### Remove the last 5 commits and discard changes
```bash
git revert HEAD~5 --hard
```
## 6. Want to Undo Changes to a File
### Undo unstaged changes to a file
```bash
git checkout --<file>
```
### undo staged changes to a file
``bash
git reset <file>
git checkout --<file>
```
### Undo changes to a file from the last commit
```bash
git checkout HEAD --<file>
```
# Git Cheat Sheet

## 1. Basic Commands

### Initialize a Repository:

```bash
git init
````

Initializes a new Git repository in the current directory. Creates a `.git` folder to track changes.

### Clone a Repository:

```bash
git clone <repository_url>
```

Copies an existing Git repository from a remote location to your local machine.

### Check Repository Status:

```bash
git status
```

Shows the status of your working directory and staging area, such as untracked files and changes.

### View Commit History:

```bash
git log
```

Displays a list of commits in the repository, showing author, date, and commit message.

### Display a Graph of Commits:

```bash
git log --oneline --graph
```

Provides a concise, graphical representation of commit history in one line per commit.

### Add Files to Staging:

```bash
git add <file>
```

Stages the specified file for the next commit.
Add all files:

```bash
git add .
```

Stages all changes in the current directory.

### Commit Changes:

```bash
git commit -m "Commit message"
```

Records changes to the repository with a descriptive message.

## 2. Branching and Merging

### List Branches:

```bash
git branch
```

Lists all local branches in the repository.

### Create a New Branch:

```bash
git branch <branch_name>
```

Creates a new branch off the current branch.

### Switch to a Branch:

```bash
git checkout <branch_name>
```

Switches to the specified branch.

### Create and Switch to a New Branch:

```bash
git checkout -b <branch_name>
```

Creates a new branch and switches to it in one step.

### Merge Branches:

```bash
git merge <branch_name>
```

Combines the specified branch into the current branch.

### Delete a Branch:

```bash
git branch -d <branch_name>
```

Deletes the specified branch.

## 3. Remote Repositories

### Add a Remote Repository:

```bash
git remote add origin <repository_url>
```

Links a local repository to a remote one, often named `origin`.

### View Remote Repositories:

```bash
git remote -v
```

Lists all remote repositories linked to your local repository.

### Fetch Changes from Remote:

```bash
git fetch
```

Downloads updates from the remote repository but does not apply them.

### Pull Changes from Remote:

```bash
git pull
```

Fetches and merges updates from the remote repository into your local branch.

### Push Changes to Remote:

```bash
git push origin <branch_name>
```

Uploads your local branch changes to the corresponding branch on the remote repository.

## 4. Undo Changes

### Undo Changes in Working Directory:

```bash
git checkout -- <file>
```

Reverts the specified file to its last committed state.

### Unstage Changes:

```bash
git reset <file>
```

Removes the specified file from the staging area without deleting its changes.

### Revert a Commit:

```bash
git revert <commit_hash>
```

Creates a new commit that undoes the changes of the specified commit.

### Reset to a Previous Commit:

```bash
git reset --hard <commit_hash>
```

Resets the repository to the specified commit, discarding all changes.

## 5. Stashing

### Stash Changes:

```bash
git stash
```

Saves uncommitted changes in a temporary stack and reverts the working directory to the last commit.

### List Stashes:

```bash
git stash list
```

Displays a list of saved stashes.

### Apply a Stash:

```bash
git stash apply
```

Reapplies the latest stash to the working directory without removing it from the stash list.

### Drop a Stash:

```bash
git stash drop
```

Deletes the latest stash from the stack.

## 6. Tagging

### Create a Tag:

```bash
git tag <tag_name>
```

Creates a lightweight tag to mark a specific commit.

### Push Tags to Remote:

```bash
git push origin --tags
```

Uploads all local tags to the remote repository.

### List Tags:

```bash
git tag
```

Lists all tags in the repository.

## 7. Viewing Changes

### Show Changes:

```bash
git diff
```

Shows the differences between your working directory and the staging area.

### Show Changes Between Commits:

```bash
git diff <commit_hash1> <commit_hash2>
```

Compares changes between two specific commits.

### Show Commit Details:

```bash
git show <commit_hash>
```

Displays detailed information about a specific commit.

## 8. Configuration

### Set Username:

```bash
git config --global user.name "Your Name"
```

Configures your Git username globally across all repositories.

### Set Email:

```bash
git config --global user.email "you@example.com"
```

Sets your Git email address globally.

### View Configuration:

```bash
git config --list
```

Displays your current Git configuration settings.

## 9. Collaboration Tips

### Check for Conflicts:

```bash
git merge <branch_name>
```

Attempts to merge branches and shows conflicts if they exist.

### Resolve Conflicts:

Edit the conflicting files manually, then:

```bash
git add <file>
git commit
```

Marks the conflict as resolved and commits the changes.

## 10. Miscellaneous

### Clean Untracked Files:

```bash
git clean -f
```

Removes all untracked files in the working directory.

### Create an Alias:

```bash
git config --global alias.<alias_name> '<command>'
```

Defines a shortcut for a Git command.
Example:

```bash
git config --global alias.st 'status'
```

## Git Reset:

### git reset is used to undo the changes.it help us to roll back the previous state. it has three main forms.

### 1.git reset --soft [commit]:it moves the head to the specified commit but leaves the changes in the staging area.

### 2.git reset --mixed [commit](defualt):it moves the head to the specified commit and remvoes the changes in the staging area.

### 3.git reset --hard [commit]: it moves the head to the specified commit and remove all changes in the staging area and current working directory.

## Git Revert:

### git revert is also used to undo the changes. but git reset changes the commit history and git revert create a new commit that undoes the changes made by the previous commit.

### git revert [commit]

```bash
git revert aa2b2b4
```

## Git Merge:

### git merge used to integrate the changes from diffrent branches to single branch.

```bash
git merge [branchname]
```

### This command will merge a specified branch into the current branch.

### Fast-Forword Merge: if current branch has no commits since our target branch has created,Git simply moves the pointer forword.this is called fast-forword merge.

### Three-way Merge: if there are changes in the both the branches since the target branch created,then git performs the three way merge.it finds the common base commit and creates the new merge commit that combines the both the changes.

## Git Rebase:

### Git rebase is used to integrate the changes from one branch to anthor

```bash
git rebase [branchname]
```

### it takes the commits from the specified branch and applies the changes on top of the current branch

### Interactive Rebase::

### You can use git rebase -i [base-commit] to enter an interactive mode where you can edit, reorder, or squash commits before they are applied.
