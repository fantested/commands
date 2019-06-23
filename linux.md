# Basic commands for Linux

## Help
|command|description|
|-------|-----------|
|info \<program\>|Show documentation|info nslookup|

## File System
|command|description|Example|
|-------|-----------|-------|
|cd \<dir\>|Change directory|<ul><li>cd /var/</li><li>cd ~home</li></ul>|
|chgrp [-r] \<group\> \<dir/file\>|Change dir/file group|chgrp test test.txt|
|chown [-r] [user[:group]] \<dir/file\>|Change dir/file ownership|chown testuser:test test.txt|
|chmod [u\|g\|o\|a][+\|-\|=][r\|w\|x] \<dir/file\>|Change dir/file permissions|<ul><li>chmod u=rwx,go=rx test.txt</li><li>chmod a+w test.txt</li></ul>|
|chmod xyz \<dir/file\>|Change dir/file permissions using numbers (4 for read, 2 for write, 1 for execute, 0 for none)|chmod 755 test.txt|
|cp [-adfilprsu] \<source>\> \<target\>|Copy dir/file||
|ln -s \<source\> \<target\>|Create a symbolic link||
|ls [-aAdfFhilnrRSt]|List all directories and files||
|mkdir [-m\|p] \<dir\>|Make directory|<ul><li>mkdir -p test1/test2/test3</li><li>mkdir -m 744 test</li></ul>|
|mv [-fiu] \<source\> \<target\>|Remove dir/file||
|pwd|Print working directory||
|rm [-fir] \<dir/file\>|Remove dir/file||
|rmdir [-p] \<dir\>|Remove empty directory|<ul><li>rmdir test</li><li>rmdir -p test1/test2/test3</li></ul>|

## View
|command|description|Example|
|-------|-----------|-------|
|cat [-AbEnTv] \<file\>|Print file content|cat -n test|
|more \<file\>|View file with paging||
|nl [-bnw] \<file\>|Print and number file content||
|tac \<file\>|Pring file content bottom up||

## Debugging
|command|description|Example|
|-------|-----------|-------|
|echo \<variable\>|Show|echo $PATH|
|gdb|GNU debugger||
|ltrace|Print out library calls|<ul><li>ltrace ls .</li><li>ltrace -p 1234</li></ul>|
|objdump \<file\>|Display information of object files|objdump -x -D wc|
|strace|Print out system calls|<ul><li>strace ls .</li><li>strace -p 1234</li></ul>|

## Networking
|command|description|Example|
|-------|-----------|-------|
|ifconfig|IP addresses and network interfaces||
|netstat|Network connections|<ul><li>netstat -nt - list TCP connections</li><li>netstat -ntl - list TCP ports that are listening for new connections</li><li>netstat -nr - routing table</li><li>netstat -tulpn - show all open ports</li></ul>|
|nslookup|DNS loopup|nslookup -q=any abc.com|
|traceroute|Trace the internet route to a host|traceroute www.abc.com|

## Processes
|command|description|Example|
|-------|-----------|-------|
|\proc\\<pid or self\>|Directory of a process|ls \proc\self|
|lsof|Information about the files, processes, and network connections|<ul><li>lsof /lib/x86_64-linux-gnu/libc.so.6 - List instances of programs using the C standard library</li><li>lsof -p 1234 – List open files for the process with process ID = 1234</li><li>lsof -i tcp:80 – List uses of TCP port 80 (http)</li><ul>|
|kill \<pid\>|Kill a process|kill 123|
|killall \<process name\>|Kill a process|kill python|
|pidof \<process name\>|Process ID of a single running process|pidof ps|
|pkill \<pattern\>|Kill a process whose name matches the given pattern|pkill pyth|
|ps|running processes|ps -aux - show all processes|
|top|most active processes||

## Power
|command|description|Example|
|-------|-----------|-------|
|halt|Cease all CPU function||
|poweroff|Shut down the system||
|reboot|Shut down the system and commence a warm boot||
|shutdown [time] [message]|Schedule a shutdown|shutdown +10 "Upgrade"|
