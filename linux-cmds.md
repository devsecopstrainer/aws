## Basic Linux Commands

 - pwd - present working directory
 - ls - list of files
 - ls -l - list of files - describe
 - ls -al - list of files - describe + hidden files
 - cd - change directory to home location
 - cd .. - one step back to prev directory
 - touch - to create a file

   
## Folder structure:
 - [ec2-user@ip-192-168-1-205 /]$ ls -l
 - total 32
 - lrwxrwxrwx.   1 root root     7 Jan 30  2023 bin -> usr/bin  ----> Contains the binaries - Ex: ls, cp, ...
 - dr-xr-xr-x.   5 root root 16384 Aug 13 21:08 boot ---------------> Files present for booting the OS
 - drwxr-xr-x.  14 root root  3060 Sep 10 02:46 dev ----------------> To store device files, to interact between h/w and s/w
 - drwxr-xr-x.  76 root root 16384 Sep 10 02:46 etc ----------------> Editable Text Configuration, contains configuration files.
 - drwxr-xr-x.   3 root root    22 Sep 10 02:46 home ---------------> Every non-root user has a personal directory under home.
 - lrwxrwxrwx.   1 root root     7 Jan 30  2023 lib -> usr/lib -----> Contains shared libraries.
 - lrwxrwxrwx.   1 root root     9 Jan 30  2023 lib64 -> usr/lib64 -> For 64 bit OS.
 - drwxr-xr-x.   2 root root     6 Aug 13 21:06 local --------------> Used by some s/w to store your preferences.
 - drwxr-xr-x.   2 root root     6 Jan 30  2023 media --------------> autometically mounted partitions.
 - drwxr-xr-x.   2 root root     6 Jan 30  2023 mnt ----------------> manually mounted file system.
 - drwxr-xr-x.   3 root root    17 Aug 13 21:08 opt ----------------> Optional addon applications
 - dr-xr-xr-x. 159 root root     0 Sep 10 02:46 proc ---------------> Process information
 - dr-xr-x---.   3 root root   103 Aug 13 21:08 root ---------------> Root user directory
 - drwxr-xr-x.  28 root root   840 Sep 10 02:46 run ----------------> To store volatile run time data
 - lrwxrwxrwx.   1 root root     8 Jan 30  2023 sbin -> usr/sbin ---> System binaries
 - drwxr-xr-x.   2 root root     6 Jan 30  2023 srv ----------------> Server specific files
 - dr-xr-xr-x.  13 root root     0 Sep 10 02:46 sys ----------------> System files
 - drwxrwxrwt.  11 root root   220 Sep 10 02:53 tmp ----------------> Temporary files
 - drwxr-xr-x.  12 root root   144 Aug 13 21:07 usr ----------------> User programs
 - drwxr-xr-x.  19 root root   266 Sep 10 02:46 var ----------------> Variable files ( Log files )
 - [ec2-user@ip-192-168-1-205 /]$


## User Data Section

 #!/bin/bash
 echo "-------- executing shell script - pass 1 --------"
 yum install nginx -y
 echo "-------- executing shell script - pass 2 --------"




