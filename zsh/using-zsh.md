# Using ZSH

## Autocd and cd shorthand
* `cd` built in command
* `setopt autocd` to just type the dir to go to

## Directory stack 
* `pushd <dir>` and `popd` to pop it off
* `dirs` to display the stack

## Find files
* `find <path> -name "pwd"
* ignore `2>/dev/null` to get rid of `permission denied`
* `-size 5M`for big files

## Whence
* Similar to when, but if it is a builtin which will show differnt output. `whence -v` for verbose

## Autocompletion
* Hit tab after typing, and keep hitting by tab
* `setopt completeinword` to be able to go back and get autocomplet
* `setopt correct` to turn on spell check for commands

