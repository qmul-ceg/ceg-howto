
Substitutions are indicated and described within { } curly brackets. eg `cd {directory/path}` would be `cd C:\Users\wew303\github` or `cd ~/github`.
## Common Commands
- `git -v` to check installed version
- `git init -b main` to initialize, in the current folder, a new local git repo with a 'main' branch.
- `git branch -m master main` to rename the 'master' branch to 'main' (see [[#Master / Main Issue]])
- `git status` to check current status of repo
- `git checkout -b {branch-name}` to create a new branch in the repo.
- `git checkout {branch-name}` to go to an existing branch in your repo.
- `git clone {url}` to clone a remote repo (create a synced local copy) in the current folder.
- `git pull` to pull the latest changes from the remote repo into your local.

## SSH Connection
In order to connect from the local to the Github remote, you will need to ensure your ssh key is in the ssh agent running on the local device. There are various methods for achieving this.  The basic command is
- Linux/Mac: `ssh-add {path/to/your/private/ssh key}`
	- for example: `ssh-add ~/.ssh/ssh_key`
- QMUL Laptops: use Pageant, which is included in the PuTTY install. Information on adding keys: [how to use pageant](https://www.digitalocean.com/community/tutorials/how-to-use-pageant-to-streamline-ssh-key-authentication-with-putty)
See [[Github SSH]] for setting up the SSH connection.

## Github Repo URL
The Github URL is available in both a SSH or HTTPS format. SSH is preferable and the *only* option for cloning private repos. Both formats can be found on the online Github console: 
*repo web page >> main page -  <> Code button*
- SSH format: `git@github.com:qmul-ceg/eldb2023`
- HTTPS format: `https://github.com/LinkedInLearning/learning-python-2896241.git`

## Folders
- `cd {directory/path}` to change directory
	- `cd /` go to root
	- `cd ..` go up 1 directory (Linux)
	- `cd` OR `cd ~ OR cd ~/` go to home directory (Linux)
	- `cd - ` go back to previous directory (Linux)
- `mkdir {repo-name}` to create a new folder with repo name (best with lower case, no spaces and dashes(-) where needed.

## Creating a Repo
There are 3 Options
1) You can create a local repo on your device and then upload it to Github
2) You can copy ('clone') a repo from Github onto your device
3) You can copy just selected folders (sparse-checkout) from a repo on Github
### Create a Local Repo
Navigate to, or make, the parent folder in which you want the repo folder.
Initiate a new local git repo with a 'main' branch.
- `git init -b main` 
### Clone a Repo from Github
Navigate to, or make, the parent folder in which you want the repo folder.
Clone a repo from Github using the remote URL.
- `git clone {remote repo url}` 
### Clone Selected Folders from a Github Repo
Navigate to, or make, the parent folder in which you want the repo folder.
Initiate a new local git repo with a 'main' branch.
Add a link to a Github repo using the remote SSH URL
Enable `sparse-checkout` and define the selected folder(s)
`pull` the remote repo (only for selected folders) to the local git.
```
git init -b main
git remote add origin {SSH repo URL}
git config core.sparseCheckout true
echo "{folder}/" >> .git/info/sparse-checkout
git pull origin main  
```
- `git sparse-checkout add {folder2/subfolder2}` to add additional folders to the checkout
- `git sparse-checkout list` to view folders in the checkout

## Syncing Local + Github Repo (Pull + Push Commits)
### Pull
- `git pull` to pull the latest changes from the remote repo into your local.
### Commit + Push
- `git status` to list changed files
- `git add .` OR `git add -A` to add all files changed into tracked files to commit.
	- OR `git add {file}` to add a single file into tracked files
- `git commit -m "{summary}"` to commit the changes made with a summary description.
- git push
	- for the first push use `git push -u origin main` to push the changes into the *main* branch of *origin* - the remote repository. And set this as the default upstream (tracking) for this branch
	- `git push` to push changes using the default upstream
Example:
```
git pull

## edit a file 

git status
git add .
git commit -m "amended input parameter"
git push
```
## Ignore files and folders
Add a `.gitignore` file containing a list of files and folders to exclude from Git (eg system folders and files containing passwords). eg Linux:
```
touch .gitignore
echo '.env' > .gitignore
```

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


