# Basic commands for Linux

## Help
|command|description|
|-------|-----------|
|info \<program\>|Show documentation|info nslookup|
|man \<program\>|Show documentation|man nslookup|

## Compression & Backup
|command|description|Example|
|-------|-----------|-------|
|tar [-j\|-z] [ctxv] -f \<output name\> file\|dir|Compress/decompress|tar -zcv -f /root/etc.tar.gz /root/etc|
|dump [-Suvj] [-level] [-f file] file\|dir|Create a backup file|dump -0u -f /root/boot.dump /root/boot|
|restore [-tCir] [-f dumpfile] [-h]|Restore a backup file|restore -r -f /root/boot.dump|

## File and Directory Management
|command|description|Example|
|-------|-----------|-------|
|cd \<dir\>|Change directory|<ul><li>cd /var/</li><li>cd ~home</li></ul>|
|chattr [+-=][ASacdistu] \<dir\|file\>|Change the attributes of a dir/file|chattr +i test.txt|
|chgrp [-r] \<group\> \<dir\|file\>|Change dir/file group|chgrp test test.txt|
|chown [-r] [user[:group]] \<dir\|file\>|Change dir/file ownership|chown testuser:test test.txt|
|chmod [u\|g\|o\|a][+\|-\|=][r\|w\|x] \<dir\|file\>|Change dir/file permissions|<ul><li>chmod u=rwx,go=rx test.txt</li><li>chmod a+w test.txt</li></ul>|
|chmod xyz \<dir/file\>|Change dir/file permissions using numbers (4 for read, 2 for write, 1 for execute, 0 for none)|chmod 755 test.txt|
|cp [-adfilprsu] \<source>\> \<target\>|Copy dir/file||
|find [PATH] [-name\|size\|user\|] [action]|Find files and directories and perform subsequent operations on them|<ul><li>find / -name test.txt</li><li>find /usr/bin /usr/sbin -perm /7000 -exec ls -l {} \\;</li></ul>|
|ln -s \<source\> \<target\>|Create a symbolic link||
|locate [-ilSr] \<file\|pattern\>|Search for a file in the locate database|locate test.txt|
|ls [-aAdfFhilnrRSt]|List all directories and files||
|lsattr [-adR] \<dir\|file\>|List the attributes of a dir/file||
|mkdir [-m\|p] \<dir\>|Make directory|<ul><li>mkdir -p test1/test2/test3</li><li>mkdir -m 744 test</li></ul>|
|mv [-fiu] \<source\> \<target\>|Remove dir/file||
|passwd|Change password||
|pwd|Print working directory||
|rm [-fir] \<dir\|file\>|Remove dir/file||
|rmdir [-p] \<dir\>|Remove empty directory|<ul><li>rmdir test</li><li>rmdir -p test1/test2/test3</li></ul>|
|touch [-acdmt] \<file\>|Create an empty file or modify timestamps of a file||
|umask [-S] [mask]|Show and modify default permission for new files|umask 002|
|whereis [-bmsu] \<dir\|file\>|Locate the binary, source, and manual page files for a command|whereis python|
|which [-a] \<program\>|Locate the executable file in the path environment variable|which python|

## File Content
|command|description|Example|
|-------|-----------|-------|
|cat [-AbEnTv] \<file\>|Print file content|cat -n test|
|file \<file\>|Report file type|file test.txt|
|head [-n number] \<file\>|Print top n lines||
|less \<file\>|View file with paging (up/down)||
|more \<file\>|View file with paging (only down)||
|nl [-bnw] \<file\>|Print and number file content||
|tac \<file\>|Pring file content bottom up||
|tail [-n number] \<file\>|Print bottom n lines||

## File System
|command|description|Example|
|-------|-----------|-------|
|blkid [device]|Print block identifier||
|df [-ahikHTm] [dir\|file]|Display the amount of disk space available on the file system||
|du [-ahskm] [dir\|file]|Estimate file space usage||
|dumpe2fs [-bfhixV] device|Print the super block and blocks group information|dumpe2fs /dev/vda5|
|fdisk [device]|MBR partition table editor||
|gdisk [device]|Interactive GUID partition table (GPT) editor||
|ln [-sf] \<original filename\> \<link name\>]|Create links between files||
|lsblk [-dfimpt] [device]|List block devices||
|mkfs.xfs [-b bsize] [-d parms] [-i parms] [-l parms] [-L label] [-f] [-r parms] [device]|Format a block storage device with a specific file system||
|mknod device [b\|c\|p] [Major] [Minor]|Create a special file|mknod /dev/vda10 b 252 10|
|mount [-fnrsvw] [-t fstype] [-o options] device dir|Mount a storage device|mount /dev/sr0 /data/usb|
|umount [-fn] device\|dir|Unmount a storage device|umount /data/usb|
|xfs_admin [-lu] [-L label] [-U uuid] device|Modify UUID or label name of a xfs formatted device||
|xfs_repair [-fnd] [device]|Repair xfs filesystems||

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
