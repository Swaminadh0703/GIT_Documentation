GIT AND GITHUB TUTORIAL

Centralized Version Control System: A Central Version control system is a model where all code and its history are stored in single central repository. Each developer needs to connect to that server to commit, update or view changes. It’s simple to set up and manage but creates a single point of failure and requires constant network connectivity. 
Eg: SVN, CVS, and Perforce.

Distributed Version Control System: A Distributed version control system is a type of version control system where each developer will have a complete copy of the project codebase along with its history enabling offline work, faster operations, and flexible operations without relying on single central server.
Eg: Git, Bazaar etc.

GIT
Git is a distributed version control system (VCS) used to track changes in source code during software development. It helps developers collaborate, manage different versions of code, and roll back to previous states if needed.

Core Things in GIT
Repository: It is storage space where your project files and their history will keep.
Two types: 
1.Local Repository --> Project copy in our local machine
2.Remote Repository --> Version of the project hosted in remote server usually platforms like GitHub,
 Gitlab and bitbucket etc.
Commits: It’s like a snapshot of the project within specified point of timeline. Each commit has specific unique identifier(hash) and a message that describes the changes made allowing you to track and review the history of your project.
Branch: A Git branch is a separate workspace used to make changes without affecting the main project.
Common types:
1.Main Branch --> The stable version of the project, usually production-ready.
2.Feature Branch --> Used for developing the new features and for bug fixes.
Merging: It is the process of integrating the changes from one branch to another. It allows you to combine the work done in two different branches and resolve any conflict issues that arise.
Cloning: Creating a local copy from remote repository in local machine.
Pull: Fetching the updates from the remote repository and integrates them into your local repository.
Push: Sends the local changes to the remote repository making it available to the others.

Git Repository Structure
Working Directory: Local directory where you write the code and make changes to it.
Staging Area: This is the area where you keep your code before committing it. This is used for code review by other team members.
Local Repository: Repository where you commit changes to your project before pushing them to the central repository of the GitHub. This corresponds to the .git folder in our directory.
Central Repository: Main project on central server, a copy of which every developer has as a local repo.


GITHUB
It is a web-based platform that built around GIT enables version control, collaboration and project management for software development teams. It hosts GIT repositories.


USEFUL GIT COMMANDS
1.Configuration & Setup: It is good practice to set up and configure your environment before writing any single code.
 
git --version  #shows the installed version of git
git config --global user.name "Name”  #set your identity for all the commits
git config --global user.email "mail" #sets your email address
git config --global color.ui true #enables helpful color highlighting in the terminal
git config --list  #shows all the configured settings
git init #initialize new empty git repo in current folder
git clone <url> #download the existing repos from the remote server 
git clone -b <branch-name> <repository-url> #clones the specified branch into your local repository instead of the default branch

2.The Core Workflow Commands (Modify --> Stage --> Commit)

git status #shows which files are modified, staged and untracked
git add <file> #adds a specific file to the staging area
git add . #adds all changed files to the staging area
git add -p #Allows us to stage parts of the file interactively
git rm <file> #deletes the file both from working directory and the index
git rm --cached <file> #removes the file from git tracking but keeps it in your local disk
git commit -m “message” #records the snapshot with the message
git commit -am “message” #shortcuts git add . and git commit in one command
git commit --amend #modifies the last commit

3.Branching & Merging

git branch #lists all branches locally
git branch <name> #creates a new branch
git checkout <name> #switches to the specified branch
git switch <name> #alternative to the checkout
git checkout -b <name> #creates a new branch and switches to it immediately
git branch -d <name> #deletes a branch(prevents deleting unmerged work)
git branch -D <name> #Force delete. Deletes a branch even if it has unmerged changes.

git merge <branch> #merges specified branch into current branch
git merge --abort #Stops the merge process if conflicts occur and you want to give up.
git rebase <branch> #Reapplies commits on top of another base tip (linear history).

4.Remote Syncing 

git remote -v #Lists all remote repositories linked to your local account
git remote add origin <url> #Connects local repo to a remote server
git remote remove <name> #Removes the remote connection
git fetch #Downloads the changes from the remote but does not update your code
git pull #Downloads changes and immediately merges them (Fetch + Merge)
git push -u origin <branch> #Uploads your commits to the remote branch
git push --tags #Pushes specific version tags to the remote
git push --force #Overwrites remote history with your local history


5.Inspection and Comparison

git log #Shows the full commit history
git log --oneline #Condensed history (one line per commit)
git log --graph #Shows a text-based graph of branching history
git diff #Shows differences between working directory and staging area
git diff --staged #Shows differences between staging area and the last commit
git blame <file> #Shows who modified each line of a file and when
git show <commit-id> #Shows the specific changes (metadata + diff) of a commit

6.Undo and fix

git reset --soft HEAD~1 #Undoes the last commit but keeps changes in the Staging Area
git reset HEAD~1 #Undoes the last commit and moves changes to the Working Dir
git reset --hard HEAD~1 #Undoes the last commit and deletes all changes
git restore <file> #Discards local changes to a specific file
git revert <commit-id> #Creates a new commit that is the exact opposite of the specified commit






















