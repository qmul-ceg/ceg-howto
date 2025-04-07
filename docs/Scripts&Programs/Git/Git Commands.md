
Substitutions are indicated and described within { } curly brackets. eg `cd {directory/path}` would be `cd C:\Users\wew303\github` or `cd ~/github`.
## Version
- `git -v` to check installed version
## Folders
- `cd {directory/path}` to change directory
	- `cd /` go to root
	- `cd ..` go up 1 directory (Linux)
	- `cd` OR `cd ~ OR cd ~/` go to home directory (Linux)
	- `cd - ` go back to previous directory (Linux)
- `mkdir {repo-name}` to create a new folder with repo name (best with lower case, no spaces and dashes(-) where needed.
Add a `.gitignore` file containing a list of files and folders to exclude from Git (eg system folders and files containing passwords). eg Linux:
```
touch .gitignore
echo '.env' > .gitignore
```
## Create a Local Repo
- `git init -b main` to initialize, in the current folder, a new local git repo with a 'main' branch.
- `git branch -m master main` to rename the 'master' branch to 'main' (see [[#Master / Main Issue]])
- `git status` to check current status of repo
- `git checkout -b {branch-name}` to create a new branch in the repo.
- `git checkout {branch-name}` to go to an existing branch in your repo.
- `git clone {url}` to clone a remote repo (create a synced local copy) in the current folder.
- `git pull` to pull the latest changes from the remote repo into your local.
## Clone a Repo
Navigate to, or make, the parent folder in which you want the repo folder.
- `git clone {remote repo url}` 
URL can be SSH or HTTPS format. SSH is preferable and the *only* option for cloning private repos. Both formats are available in Github online 
	repo web page >> main page -  *<> Code* button
SSH format: `git@github.com:qmul-ceg/eldb2023`
HTTPS format: `https://github.com/LinkedInLearning/learning-python-2896241.git`
## Clone Selected Folders from a Repo
Add repo to local git; use `sparse-checkout` to set particular folders; `pull` repo.
```
git remote add -f origin {remote repo SSH url}
git sparse-checkout set {folder/subfolder}
git pull origin main
```
- `git sparse-checkout add {folder2/subfolder2}` to add additional folders to the checkout
- `git sparse-checkout list` to view folders in the checkout
## Syncing (Pull + Push Commits)
- `git pull` to pull the latest changes from the remote repo into your local.
- `git add .` OR `git add -A` to add all files changed into tracked files to commit.
	- `git add {file}` to add a single file into tracked files
- `git commit -m "{summary}"` to commit the changes made with a summary description.
- `git push -u origin {branch}` to push the changes into the {branch} branch of `origin` - the remote repository. And set this as the default upstream (tracking) for this branch
	- `git push` to push changes using the default upstream

## Master / Main Issue
Git by default uses `master` as the name for the primary branch.  As of late 2020, GitHub has changed from 'master' to instead use `main`.  Both the local Git and Github need to be using the same branch name, preferably `main` in order to sync.
The best way to accomplish this is to change your default Git primary branch name to `main`:
`git config --global init.defaultBranch main`

Alternatively, you can change the primary branch name **after** you make the first commit to the repo. This only for the specific repo and so must be repeated for each new repo.
`git add --move master main`

**Github Desktop** automatically edits the global Git config to `main`.

## Github CLI
Not currently available on QM devices
- `gh repo create` to create a new repo in your GitHub account.
 
# Useful Links
https://medium.com/the-research-nest/the-basics-of-git-for-first-time-users-355486233e7d
[https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository)


