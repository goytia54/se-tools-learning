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

## Redirection and multios

### Inputs and outputs
* `<:` `>:`
* `setopt noclobber` to not let you redirect and not overwrite but can use `>>` to append

### Piping
* Usually use `|` but also can use `| tee myfile` to

### Multios
* 0 is standard input, 1 is standard output, 2 is standard error
* 2> is standard error while 1> is standoutput

## Command History
* up arrow and down arrow
* ctrl A and crtl E to get to beginning and end of command
* r var=bin to replace values of last command
* `setopt histignorespace` to exclude from command history
* `setopt interactivecomments` to save a command in the history

## History shell variables
* `!!` previous
* `!*` previous arg command
* `$_` for the last command 

## Expansions
### History Expansion 
* `!!` last command
* `!252` for ordered

### Alias Expansion
* take alias and expands

### Process Substitution

### Parameter Expansion
* Stores values, `a=apple`
* `${a}apple` to match

### Command Sub
* `(command)`

### Arithmetic Expansion
* `{1..5}`
* `{1..5}{a..c}` for permutations

### Filename Expansion
* `~`
* `!` for one char
* `c[u,a]t` to match `cat` and `cut`

## zmv
* uses globbing to do mass commands, touch `file_{0..100}`
* `zmv 'file_(*)' 'log_$1'
* only work with name of the files
* `-n` option before you change the file names


