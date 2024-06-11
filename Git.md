# Git setup and configuration

## Installation

1. Download and install latest version of git
2. Type `git --version` to check if your version is the latest

## Initialize

1. Go to root folder of where you want to start your snapshot
2. Type `git init` to initialize git into that folder
3. Type `ls -a` to view all files and folders, including hidden ones. You should be able to see `.git` folder if successfully initialized

## End of line

1. On windows new lines are appended with \r\n, on linux it is only \n
2. On windows, type `git config --global core.autocrlf true`. This will remove the carriage return(CR), `\n` when checking in code to the repo. Then when checking out code, it will auto add the CR.
3. On Mac, type `git config --global core.autocrlf input`. This will ensure that any input from mac should not consist of CR if it was accidentally added.

## Integration with vscode

1. In vscode, open command palette, type in `shell code`. Select `Shell command: Install 'code' command in PATH`. This will allow you to open vscode from cli by typing `code`
2. In cli, type `git config --global core.editor "code --wait"`. This will setup vscode to open as the default editor when using the `-e` arugument. The `--wait` flag will cause the terminal to wait until the file is closed before returning to terminal input.
3. You can now edit using vscode by typing `git config --global -e`

## Diff tool using vscode

1. Type `git config --global diff.tool vscode` to set vscode as the diff tool
2. Type `git config --global difftool.vscode.cmd "code --wait --diff $LOCAL $REMOTE"` to set vscode to check the difference between local and remote. After entering this command, go to the global config to make sure the $LOCAL and $REMOTE are properly set. At this time of writing, it doesn't seem to set it properly.
3. You can now use git difftool by typing `git difftool`

## Global user name and email

1. Type `git config --global user.name "[name]"`, and `git config --global user.email [email]` to set up your name and email globally.

## Local user name and email

1. Type `git config --local user.name "[name]"` and `git config --local user.email [email]` to set up your name and email for that local repo.
