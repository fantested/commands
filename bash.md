# Basic commands for bash


## Commands
|command|description|example|
|-------|-----------|-------|
|alias|Create an alias for a command|alias lm='ls -al'|
|col [-bfhpx] [-l num]|Filter out reverse line feeds|man cat \| col -f > test.txt|
|cut|Fetch a specific portion of the data|cut -d ':' -f 3,5 test.txt|
|declare [-aixr] variable|Declare a variable|declare -i sum|
|echo|Print the value of a variable|echo $PATH|
|env|List all environment variables|env|
|expand [-t] file|Tab to space|expand -t 6 test.txt|
|export|Pass variables or functions to child processes|export VAR|
|grep [-acinv] [--color=auto] 'char' filename|Search plain-text data sets for lines that match a RegEx|grep -in 'text' test.txt|
|history [n] [-acrw]|List the command history|history 3|
|join [-ti12] file1 file2|Join lines of two files on a common field|join -t ':' /etc/passwd /etc/shadow|
|paste [-d] file1 file2|Join lines of two files on a common field|paste /etc/passwd /etc/shadow|
|read [-pt] var|Read the value of a variable from input|read VAR|
|split [-bl] file prefix|Divide a file into multiple files|split -b 300k /etc/test.txt test|
|sort [-fbMnrtuk] [file or stdin]|Sort input|sort -t ':' -k 3 test.txt|
|source|Load a file into the current shell|source ~/.bashrc|
|tee [-a] file|Write the input to both standard output and a file|ls -l \home \| tee ~/testfile \| more|
|tr [-ds] pattern|Replace or remove specific characters|last \| tr '[a-z]' '[A-Z]'
|type|Show the type of a command|type ls|
|ulimit [-SHacdfltu] [quota]|Set/view the resource limit|ulimit -a|
|unalias|Remove an alias|unalias lm|
|uniq [-ic]|Output unique line of text|uniq -c test.txt|
|unset|Clear a local environment variable|unset $VAR|
|wc [-lwm]|Count the number of words|cat /etc/man.config \| wc |
|xargs [-0epn] command|Build and execute commands from standard input|find /path -type f -print | xargs rm|


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
|![n\|pattern\|!]|Run a command in the history|!3|
|>|Write standard output to|ls > output.txt|
|>>|Append standard output to|ls >> output.txt|
|2>|Write standard error to|ls > output.txt 2> error.txt|
|2>>|Write standard error to|ls 2>> output.txt|
|&>|Write standard output and error to|ls &> output.txt|
|<|Write standard input to|cat > output.txt < ~/.bashrc|
|<<|Append standard input to|cat > output.txt << ~/.bashrc|
|;|Execute commands sequentially|sync;sync;shutdown|
|&&|Execute the second command only if the first command succeeds|ls /test && touch /test/test.txt|
|\|\||Skip the second command if the first command succeeds|ls /test \|\| mkdir /test|
|\||Pipe standard output from the first command into the second command|ls -al /etc \| less|
