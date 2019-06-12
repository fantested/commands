# Basic commands for Linux

## File
|command|description|
|-------|-----------|
|ln -s \<source\> \<target\>|Create a symbolic link|

## Permissions
|command|description|
|-------|-----------|
|chown [user[:group]] \<file\>|Change file ownership|
|chmod [u\|g\|o\|a][+\|-\|=][r\|w\|x] \<file\>|Change file permissions|

## Debugging
|command|description|Example|
|-------|-----------|-------|
|strace|Print out system calls|<ul><li>strace ls .</li><li>strace -p 1234</li></ul>|
|ltrace|Print out library calls|<ul><li>ltrace ls .</li><li>ltrace -p 1234</li></ul>|

## Networking
|command|description|Example|
|-------|-----------|-------|
|ifconfig|IP addresses and network interfaces||
|netstat|Network connections|<ul><li>netstat -nt - list TCP connections</li><li>netstat -ntl - list TCP ports that are listening for new connections</li><li>netstat -nr - routing table</li><li>netstat -tulpn - show all open ports</li></ul>|
|traceroute|Trace the internet route to a host|traceroute www.abc.com|

## Processes
|command|description|Example|
|-------|-----------|-------|
|top|most active processes||
|ps|running processes|ps -aux - show all processes|
|pidof \<process name\>|Process ID of a single running process|pidof ps|
|\proc\\<pid or self\>|Directory of a process|ls \proc\self|
|lsof|Information about the files, processes, and network connections|<ul><li>lsof /lib/x86_64-linux-gnu/libc.so.6 - List instances of programs using the C standard library</li><li>lsof -p 1234 – List open files for the process with process ID = 1234</li><li>lsof -i tcp:80 – List uses of TCP port 80 (http)</li><ul>|
|kill \<pid\>|Kill a process|kill 123|
|pkill \<pattern\>|Kill a process whose name matches the given pattern|pkill pyth|
|killall \<process name\>|Kill a process|kill python|

## Power
|command|description|Example|
|-------|-----------|-------|
|halt|Cease all CPU function||
|poweroff|Shut down the system||
|reboot|Shut down the system and commence a warm boot||
|shutdown [time] [message]|Schedule a shutdown|shutdown +10 "Upgrade"|
