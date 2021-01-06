# Frequently used commands

Tool commands frequently used in the course + added some...

## General
| Command | Description |
| --- | --- |
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

## Git
| Command | Description |
| --- | --- |
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

## ssh

| Command | Description |
| --- | --- |
| `ssh-keygen` | Creates a new private/public key pair. |
| `ssh <machinename>` | Establishes a remote ssh session to the given machine name. Machine name can be host name in `.ssh/config` or an  IP address. |
| `ssh -T git@github.com` | Validate connection to GitHub [ssh setup, deploy keys](https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/connecting-to-github-with-ssh) |

## az
| Command | Description |
| --- | --- |
| `az login` | Login to Azure |
| `az account show` | Show details about currently logged-in user. |

## vi
# Command Mode:
When vi starts up, it is in Command Mode. This mode is where vi interprets any characters we type as commands and thus does not display them in the window. This mode allows us to move through a file, and to delete, copy, or paste a piece of text.
To enter into Command Mode from any other mode, it requires pressing the [Esc] key. If we press [Esc] when we are already in Command Mode, then vi will beep or flash the screen.
# Insert mode:
This mode enables you to insert text into the file. Everything that’s typed in this mode is interpreted as input and finally, it is put in the file. The vi always starts in command mode. To enter text, you must be in insert mode. To come in insert mode you simply type i. To get out of insert mode, press the Esc key, which will put you back into command mode.
# Last Line Mode (Escape Mode):
Line Mode is invoked by typing a colon [:], while vi is in Command Mode. The cursor will jump to the last line of the screen and vi will wait for a command. This mode enables you to perform tasks such as saving files, executing commands.

# Moving within a File (Navigation):
To move around within a file without affecting text must be in command mode (press Esc twice). Here are some of the commands can be used to move around one character at a time.
| Command | Description |
| --- | --- |
| `k` | Moves the cursor up one line. |
| `j` | Moves the cursor down one line. |
| `h` | Moves the cursor to the left one character position. |
| `l` | Moves the cursor to the right one character position. |
| `0 or |` | Positions cursor at beginning of line. |
| `$` | Positions cursor at end of line. |
| `W` | Positions cursor to the next word. |
| `B` | Positions cursor to previous word. |
| `(` | Positions cursor to beginning of current sentence. |
| `)` | Positions cursor to beginning of next sentence. |
| `H` | Move to top of screen. |
| `nH` | Moves to nth line from the top of the screen. |
| `M` | Move to middle of screen. |
| `L` | Move to bottom of screen. |
| `nL` | Moves to nth line from the bottom of the screen. |
| `colon along with x` | Colon followed by a number would position the cursor on line number represented by x. |

# Control Commands (Scrolling):
There are following useful commands which can used along with Control Key:
| Command | Description |
| --- | --- |
| `CTRL+d` | Move forward 1/2 screen. |
| `CTRL+f` | Move forward one full screen. |
| `CTRL+u` | Move backward 1/2 screen. |
| `CTRL+b` | Move backward one full screen. |
| `CTRL+e` | Moves screen up one line. |
| `CTRL+y` | Moves screen down one line. |
| `CTRL+u` | Moves screen up 1/2 page. |
| `CTRL+d` | Moves screen down 1/2 page. |
| `CTRL+b` | Moves screen up one page. |
| `CTRL+f` | Moves screen down one page. |
| `CTRL+I` | Redraws screen. |

# Editing and inserting in Files (Entering and Replacing Text):
To edit the file, we need to be in the insert mode. There are many ways to enter insert mode from the command mode.
| Command | Description |
| --- | --- |
| `i` | Inserts text before current cursor location. |
| `I` | Inserts text at beginning of current line. |
| `a` | Inserts text after current cursor location. |
| `A` | Inserts text at end of current line. |
| `o` | Creates a new line for text entry below cursor location. |
| `O` | Creates a new line for text entry above cursor location. |
| `r` | Replace single character under the cursor with the next character typed. |
| `R` | Replaces text from the cursor to right. |
| `s` | Replaces single character under the cursor with any number of characters. |
| `S` | Replaces entire line. |

# Deleting Characters:
Here is the list of important commands which can be used to delete characters and lines in an opened file.
| Command | Description |
| --- | --- |
| `X` | Uppercase: Deletes the character before the cursor location. |
| `x` | Lowercase : Deletes the character at the cursor location. |
| `Dw` | Deletes from the current cursor location to the next word. |
| `d^` | Deletes from current cursor position to the beginning of the line. |
| `d$` | Deletes from current cursor position to the end of the line. |
| `Dd` | Deletes the line the cursor is on. |

# Copy and Past Commands:
Copy lines or words from one place and paste them on another place by using the following commands.
| Command | Description |
| --- | --- |
| `Yy` | Copies the current line. |
| `9yy` | Yank current line and 9 lines below. |
| `p` | Puts the copied text after the cursor. |
| `P` | Puts the yanked text before the cursor. |

# Save and Exit Commands of the ex Mode:
Need to press [Esc] key followed by the colon (:) before typing the following commands:
| Command | Description |
| --- | --- |
| `q` | Quit |
| `q!` | Quit without saving changes i.e. discard changes. |
| `r` | Read data from file called fileName. |
| `wq` | Write and quit (save and exit). |
| `w filename` | Write to file called fileName (save as). |
| `w! filename` | Overwrite to file called fileName (save as forcefully). |
| `!cmd` | Runs shell commands and returns to Command mode. |