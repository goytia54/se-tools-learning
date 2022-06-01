# Zsh Found foundations

## Install
* Can install via the package manager for the linux distro you use, default shell for mac

## Config
* Can start up with `zsh` to generate new file wizards

## Using zsh as the primary shell
* Need to know where it is located, `which zsh`
* `chsh` command to change shell and follow prompt or `chsh <path> <user>` -s 
* Can use `usermod -s /usr/bin/zsh user`
* Can change path for all users

## Environment and Options
* Many enviroment variables to customize the variables, `SHEll` for example
* `PATH` is important as the shell looks for thigns to run
* `setopt` or `unsetop` to set or unset options
* `setopt verbose` to enable it and `unsetopt verbose` to unset it

## Aliases and reserverd words
* Aliases make short versions for the longer commands, `command ls` will just run the regular ls

### Reserved keywords
* if, else, then for example

## Functions
* `$1` gets us into using the first argument

## Built ins and commands
* `builtin <cmd>` and `command <cmd>` to see built ins

## Finding Help
* `man zsh`
