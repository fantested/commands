# Basic commands for bash


## Commands
|command|description|example|
|-------|-----------|-------|
|alias|Create an alias for a command|alias lm='ls -al'|
|declare [-aixr] variable|Declare a variable|declare -i sum|
|echo|Print the value of a variable|echo $PATH|
|env|List all environment variables|env|
|export|Pass variables or functions to child processes|export VAR|
|read [-pt] var|Read the value of a variable from input|read VAR|
|type|Show the type of a command|type ls|
|ulimit [-SHacdfltu] [quota]|Set/view the resource limit|ulimit -a|
|unset|Clear a local environment variable|unset $VAR|


## Symbols
|Symbol|description|example|
|-------|-----------|-------|
|$VAR or ${VAR}|Return the value of variable VAR||
|$()|Execute the command within the parentheses in a sub-shell|$(echo foo)|
|$$|pid of the current shell||
|\/|Replace the first instance of the first string with the second one|echo ${path/sbin/SBIN}|
|\/\/|Replace all instances of the first string with the second one|echo ${path//sbin/SBIN}|
|\#|Replace the shortest match from left to righ|echo \$\{path\#\/\*root\/bin\:\}|
|\#\#|Replace the longest match from left to right|echo \$\{path\#\#\/\*\}|
|\%|Replace the shortest match from right to left|echo \$\{path\%\:\*bin\}|
|\%\%|Replace the longest match from right to left|echo \$\{path\%\%\:\*bin\}|
|-|Assign default value to var if str is undefined|var=${str-newvar}|
|-|Assign default value to var if str is undefined or an empty string|var=${str:-newvar}|
