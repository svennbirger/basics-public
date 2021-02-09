# Frequently used commands

| Command | Description |
| --- | --- |
|   |
| **GENERAL** |
| `CTRL+C` | Cancel / abort a command, hitting CTRL+C will cancel that command. |
| `cat` | Output file to screen, all in one go. Ex.: cat .ssh/id_rsa.pub. |
| `cd ..` | Change directory upwards. Mind the space! |
| `cd -` | Navigate to the previous directory (or back). Mind the space! |
| `cd /` | Navigate back to **root**. Mind the space! |
| `cp` | Copy file or folder. Ex.: cp old-filename.ext new-filename.ext |
| `ls` | List directory (also use dir) CANNOT use parmameter as -l, -la etc. in powershell <br/>`ls -l` = List directory as structured as table. ONLY IN BASH! <br/>`ls -la` = -a also list hidden files. ONLY IN BASH! |
| `pwd` | Print Working Directory. Returns the path to a local folder on your computer's disk. |
| `rm` | Remove file or folder. Ex.: rm path/to/file.ext or rm -r path/to/folder |
| `mv` | Move file or folder. Ex.: mv old-filename.ext new-filename.ext |
| `mkdir` | Make direktory / folder. Ex.: mkdir new-folder |
| `history` | Lists commands used in current session. |
|   |
| **GIT** |
| `sudo dnf install git-all` | Installing Git on Linux. Not to be used on Windows. See [Git Install](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)|
| `git status` | Shows your local git status (current branch, changed files, etc) |
| `git clone <URL>` | Clone a repository from URL <br/>Example:  `git clone https://github.com/username/reponame.git`|
| `git pull` | Updates local branch with remote changes |
| `git add <filepath>` | Stages the specified files for commit. <br/>Common: `git add .`  or `git add --all` = adds all local files to the stage. |
| `git commit` | Creates a new commit from the staged changes. Common: <br/>`git commit -a`  = stage and commit changes to all tracked files. <br/>`git commit -m "Comment text"` = With comment. <br/>`git commit -a -m "Comment text"` = stage and commit changes to all tracked files, with comment.|
| `git push` | Pushes the current local branch to remote branch (e.g. GitHub). <br/> Common: `git push -u origin master` = push to master and track master branch from origin.|
| `git push --set-upstream origin <branchname>` | Use this command if `git push` returns "fatal, The current branch editbranch has no upstream branch." |
| `git fetch` | Updates local repository with remote changes. Does not update branches. |
| `git switch -c <branchname>` | Creates a new branch and switches to it. <br/> Alternative: `git checkout -b <branchname>` |
| `git switch <branchname>` | Switch to the given branch. <br/> Alternative:  `git checkout <branchname>` |
| `git branch --list` | List current local branches |
| `git merge <branchname>` | Merges changes from the given branch into current. |
| `git branch -d <branchname>` | Delete a branch on your local filesystem. <br/> Force delete: `git branch -D <branchname>` |
| `git push origin :<branchname_to_be_deleted>` | Delete a remote branch (on GitHub). |
| `git reset --hard origin/<branchname_to_keep>` | Reset branch. NB! All previous commited localy will be deleted! |
|   |
| **Bash** |
| `${string:position:length}` | Extract $length of characters substring from $string starting from $position. <br/>E.x removing first and last character: `<br/>string="12345" <br/>echo ${string:1:-1} <br/>234` |
| `${string##substring}` | Remove the $substring match from front of $string. <br/>E.x Keep text after the dot (mind the star): `<br/>string="front.back" <br/>echo ${string##*.} <br/>back` |
| `${string%%substring}` | Remove the $substring match from back of $string. <br/>E.x Keep text before the dot (mind the star): `<br/>string="front.back" <br/>echo ${string%%.*} <br/>front` |
| **ssh** |
| `ssh-keygen` | Creates a new private/public key pair. |
| `ssh <machinename>` | Establishes a remote ssh session to the given machine name. Machine name can be host name in `.ssh/config` or an  IP address. |
| `ssh -T git@github.com` | Validate connection to GitHub [ssh setup, deploy keys](https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/connecting-to-github-with-ssh) |
|   |
| **az** |
| `az login` | Login to Azure |
| `az account show` | Show details about currently logged-in user. |
| `az account show --query user.name` | List active user. |
| `az ad sp credential reset --name <principal name>`| Reset credetials of Service Provider (SP). |
| `az account set --subscription <subscription_name>`| Set a subscription to be the current active subscription. |
| `az account list --output table`| List available subscriptions (as table: Name, CloudName, SubscriptionId, State, IsDefault|


## Git branches, create and manage (Listed as needed).
This example shows a case where we need to edit a repository and want to use another (new) branch to do the edits within.
| #   | Command   | Description |
| --- | --- | --- |
| 01 | `git pull` | Before creating a new branch, pull the changes from upstream. Your local master needs to be up to date. |
| 02 | `git switch -c <new_local_branch>` | Creates a branch on your local machine and switch to this branch. |
| 03 | `git push origin <new_local_branch>` | Push the new branch to github. (Make new local branch available on GitHub). <br/> Use `git branch -a` to list all the branches created, if needed. (Both localy and from GitHub). |
| 04 | *Edit files ->* | Edit the files  / do your work in the new local branch and go to next step. |
| 05 | `git commit -a -m "Comment text"` | Stage and commit changes to all tracked files, with comment. |
| 06 | `git push --set-upstream origin <new_local_branch>` | Sets the upstream and pushes the current (edited) *local_branch* to *remote_branch* on GitHub.|
| 07 | `git switch <master_local_branch>` | Switch to the origin master branch. |
| 08 | `git merge <new_local_branch>` | Merges changes from the given branch (*branchname*) into current selected (master) branch. |
| 09 | `git push` | Pushes the current local branch to remote branch (e.g. GitHub).
| 10 | `git branch -d <new_local_branch>` | Delete a branch on your local filesystem. <br/> Force delete: `git branch -D <branchname>` |
| 11 | `git push origin :<new_remote_branch>` | Delete the new external branch (on GitHub) that is no longer needed. |


## Various examples simplified ##

**Clone repository**
>git clone https://github.com/equinor/plantdocs.omnia.git

**Create a branch**
>git branch mybranch

**CheckOut branch**
>git checkout mybranch

**Set-upstream remote repository**
>git push --set-upstream origin mybranch

**Go to folder**
>cd docs/how-to/

**Add the following markdown page you have updated to Stage**
>git add frequently-used-commands.md

**Commit localy, describe the change**
>git commit -a

**Example Message, Commit localy, describe the change**
>git commit -m "create new markdown page"

**Push changes to remote repository**
>git push
