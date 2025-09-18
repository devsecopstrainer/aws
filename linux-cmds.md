## Basic Linux Commands

 - pwd - present working directory
 - ls - list of files
 - ls -l - list of files - describe
 - ls -al - list of files - describe + hidden files
 - cd - change directory to home location
 - cd .. - one step back to prev directory
 - touch - to create a file


	 - whoami - provides the current user name
	 - 	sudo su - to change the logged in user to root user
	 - 	exit - to ecit from current user to previous user
	 - 	pwd - present working directory
	 - 	/home/ec2-user --> This location is the home directory for ec2-user
	 - 	cd
	 - 		cd ..  - to move one step back
	 - 		cd - change directory - to the home directory of logged in user
	 - 		cd /var/log - to navigate to any other location.
	 - 	cal -> calendar
	 - 	date -> to print the current date and time
	 - 	ls -l -> lists all files and directories
	 - 	ls -al -> To display all files along with hidden files
	 - 	File creation -> touch, vi, cat
	 - 		touch file1.txt file2.txt file3.txt
	 - 		creates multiple files in a single go.
	 - 		Won't change the existing contents of a file if present already.
	 - 		vi --> edit a file
	 - 			if file is not there, it will create a new file and open in edit mode
	 - 		cat
	 - 			cat filename --> Displays the contents of the file from top to bottom
	 - 			tac filename --> Displays the contents of the file from bottom to top
	 - 			cat > filename ===> Existing contents gets removed completely, new contents get added ===> override
		 - 		cat >> filename ===> Append new contents to the existing file.

	 - echo "line 1" > test.txt  ---> Create a file and add contents to it. If file exists, then override the contents.
	 - echo "line 2" >> test.txt ---> Create a file and add contents to it. If file exists, then append the contents.
	 - mkdir folder1 folder2 -------> Create multiple folders / directories
	 - rm file-name -> to delete a file
	 - rmdir directory-name ---> to delete empty dorectory
	 - rm -rf directory-name ---> to delete non-empty dorectory
	 - rm -rf * ----------------> To delete everything inside a directory
	 - cp file1 file2 ---> copy contents from file 1 to file 2
	 - mv file1.txt file4.txt  --> rename file1.txt to file4.txt
	 - cat file2 file3 > file4 --> Copy contents of file2 and file3, paste on file4.
	 - wc file-name
	 - 	output:	x1 x2 x3 file-name
	 - 	x1 - total number of lines
	 - x2 - total number of words
		 - x3 - total number of letters





   
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

  - #!/bin/bash
  - echo "-------- executing shell script - pass 1 --------"
  - yum install nginx -y
  - echo "-------- executing shell script - pass 2 --------"




