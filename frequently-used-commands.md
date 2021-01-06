# Frequently used commands

Tool commands frequently used in the course + added some...

| Command | Description |
| --- | --- |
|   |
| **GENERAL** |
| `CTRL+C` | Cancel / abort a command, hitting CTRL+C will cancel that command. |
| `cat` | Output file to screen, all in one go. Ex.: cat .ssh/id_rsa.pub. |
| `cd ..` | Change directory upwards. Mind the space! |
| `cp` | Copy file or folder. Ex.: cp old-filename.ext new-filename.ext |
| `ls` | List directory (also use dir) CANNOT use parmameter as -l, -la etc. in powershell |
| `ls -l` | List directory as structured as table. ONLY IN BASH! |
| `ls -la` | List directory as structured as table. -a also list hidden files. ONLY IN BASH! |
| `pwd` | Print Working Directory. Returns the path to a local folder on your computer's disk. |
| `rm` | Remove file or folder. Ex.: rm path/to/file.ext or rm -r path/to/folder |
| `mv` | Move file or folder. Ex.: mv old-filename.ext new-filename.ext |
| `mkdir` | Make direktory / folder. Ex.: mkdir new-folder |
| `history` | Lists commands used in current session. |
|   |
| **GIT** |
| `git status` | Shows your local git status (current branch, changed files, etc) |
| `git clone <URL>` | Clone a repository from URL <br/>Example:  `git clone https://github.com/username/reponame.git`|
| `git pull` | Updates local branch with remote changes |
| `git add <filepath>` | Stages the specified files for commit. <br /> Common: `git add .`  or `git add --all` = adds all local files to the stage. |
| `git commit` | Creates a new commit from the staged changes. <br/> Common: `git commit -a`  = all modified files commited. `git commit -m "Initial commit"` = With comment|
| `git push` | Pushes the current branch to remote [(e.g. GitHub). <br/> Common: `git push -u origin main` = push to main and track main branch from origin.|
| `git fetch` | Updates local repository with remote changes. Does not update branches. |
| `git switch -c <branch>` | Creates a new branch and switches to it. |
| `git switch <branch>` | Switch to the given branch. |
| `git branch --list` | List current local branches |
| `git merge <branch>` | Merges changes from the given branch into current. |
|   |
| **ssh** |
| `ssh-keygen` | Creates a new private/public key pair. |
| `ssh <machinename>` | Establishes a remote ssh session to the given machine name. Machine name can be host name in `.ssh/config` or an  IP address. |
| `ssh -T git@github.com` | Validate connection to GitHub [ssh setup, deploy keys](https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/connecting-to-github-with-ssh) |
|   |
| **az** |
| `az login` | Login to Azure |
| `az account show` | Show details about currently logged-in user. |
