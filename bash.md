# Basic commands for bash


## Commands
|command|description|example|
|-------|-----------|-------|
|alias|Create an alias for a command|alias lm='ls -al'|
|awk 'cond1{action1} cond2{action2} ...' file|Use AWK to extract and report data|last -n 5 \| awk '{print $1 "\t" $3}'|
|col [-bfhpx] [-l num]|Filter out reverse line feeds|man cat \| col -f > test.txt|
|case|Match several values against one variable|case $1 in<br/>&nbsp;&nbsp;"one")<br/>&nbsp;&nbsp;&nbsp;&nbsp;echo "Your choice is ONE"<br/>&nbsp;&nbsp;&nbsp;&nbsp;;;<br/>&nbsp;&nbsp;"two")<br/>&nbsp;&nbsp;&nbsp;&nbsp;echo "Your choice is TWO"<br/>&nbsp;&nbsp;&nbsp;&nbsp;;;<br/>&nbsp;&nbsp;"three")<br/>&nbsp;&nbsp;&nbsp;&nbsp;echo "Your choice is THREE"<br/>&nbsp;&nbsp;&nbsp;&nbsp;;;<br/>&nbsp;&nbsp;\*)<br/>&nbsp;&nbsp;&nbsp;&nbsp;echo "Invalid"<br/>&nbsp;&nbsp;&nbsp;&nbsp;;;<br/>esac|
|cut|Fetch a specific portion of the data|cut -d ':' -f 3,5 test.txt|
|declare [-aixr] variable|Declare a variable|declare -i sum|
|diff [-bBi] from-file to-file|Show the differences between two files|diff /etc/rc3.d/ /etc/rc5.d/|
|echo|Print the value of a variable|echo $PATH|
|env|List all environment variables|env|
|expand [-t] file|Tab to space|expand -t 6 test.txt|
|export|Pass variables or functions to child processes|export VAR|
|for [var] in [conditions] do [action] done<br/>for (( cond; bound; step )) do [action] done|For loop|filelist=$(ls $dir)<br/>for filename in $filelist<br/>do<br/>&nbsp;&nbsp;echo "Found $dir/$filename"<br/>done<br/><br/>s=0<br/>for (( i=1; i<=10; i=i+1 ))<br/>do<br/>&nbsp;&nbsp;s=$(($s+$i))<br/>done|
|function|Define a function|function printit(){<br/>&nbsp;&nbsp;echo "Your choice is $1"<br/>}|
|grep [-acinv] [--color=auto] 'char' filename|Search plain-text data sets for lines that match a RegEx|grep -in 'text' test.txt|
|history [n] [-acrw]|List the command history|history 3|
|if ...; then ... fi|If condition|if [ "$0" == "Y" ]; then<br/>&nbsp;&nbsp;echo "Continuing"<br/>elif [ "$0" == "N" ]; then<br/>&nbsp;&nbsp;echo "Exiting"<br/>else<br/>&nbsp;&nbsp;echo "Cancelling"<br/>fi|
|join [-ti12] file1 file2|Join lines of two files on a common field|join -t ':' /etc/passwd /etc/shadow|
|paste [-d] file1 file2|Join lines of two files on a common field|paste /etc/passwd /etc/shadow|
|patch [option] patchfile|Update text files according to instructions contained in a patch file|diff -Naur passwd.old passwd.new > passwd.patch<br/>patch -p0 < passwd.patch|
|pr [option] file|Format a file to make it look better when printed|pr /etc/man.config|
|read [-pt] var|Read the value of a variable from input|read VAR|
|sh [-nvx] file|Run, check, debug a script|sh -x scripts.sh|
|shift [n]|Move the command line arguments to one position left|shift 3|
|split [-bl] file prefix|Divide a file into multiple files|split -b 300k /etc/test.txt test|
|sort [-fbMnrtuk] [file or stdin]|Sort input|sort -t ':' -k 3 test.txt|
|source|Load a file into the current shell|source ~/.bashrc|
|tee [-a] file|Write the input to both standard output and a file|ls -l \home \| tee ~/testfile \| more|
|test [option] filename|Evaluate conditional expressions|test -e /test.txt && echo "exist" || echo "Not exist"|
|tr [-ds] pattern|Replace or remove specific characters|last \| tr '[a-z]' '[A-Z]'
|type|Show the type of a command|type ls|
|ulimit [-SHacdfltu] [quota]|Set/view the resource limit|ulimit -a|
|unalias|Remove an alias|unalias lm|
|uniq [-ic]|Output unique line of text|uniq -c test.txt|
|unset|Clear a local environment variable|unset $VAR|
|wc [-lwm]|Count the number of words|cat /etc/man.config \| wc |
|while [condition] do [action] done|While loop|while [ "$yn" != "yes" -a "$yn" != "YES" ]<br/>do<br/>&nbsp;&nbsp;read -p "Please input yes/YES to stop this program: " yn<br/>done|
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
