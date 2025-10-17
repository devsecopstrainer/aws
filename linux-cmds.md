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


 - head my-file.txt ===> shows top 10 lines	
 - tail my-file.txt ===> shows bottom 10 lines
 - 
 - head -n 20 my-file.txt   ===> shows top 20 lines
 - tail -n 20 my-file.txt   ===> shows bottom 20 lines
 - 
 - head -n -3 my-file.txt   ===> skips last 3 lines and shows the content 
 - tail -n +3 my-file.txt   ===> reads from line number 3 lines and shows the content
 - 
 - tail -f my-file.txt ===> Shows last 10 lines, and file will be in open mode to show newly added contents.
 - tail -5f my-file.txt ===> Shows last 5 lines, and file will be in open mode to show newly added contents.
 - 
 - grep - Global Regular Expression Print
 - 
 - grep "Linux" file2   ==> Searches for the content "Linux" inside file2 ==> case sensitive
 - grep -i "linux" file2   ==> Searches for the content "linux" inside file2 ==> ignore case sensitive
 - grep -i "linux" *   ==> Searches for the content "linux" inside the directory
 - grep -in "linux" file2  ==> Searches for the content "linux" inside file2, shows the line number
 - grep -irn "python" * ==> searches the content inside the folder and the subfolder
 - 
 - sed ==> stream editor
 - sed "s/python/Java/" file3  ==> Shows the preview, how the content will look like after replacing python with Java in file3
 - sed -i "s/python/Java/" file3   ==> Replaces python with Java in file3
 - sed -i "2,4 s/Java/PHP/" file3  > Does the replacement in a particular range
 - sed -i "2 s/easy/difficult/" file3   > Does the replacement in a particular line
 - sed -i "3d" file3   > Deletes a particular line in a file
 - sed -i "2,4d" file3 > Deletes a range of lines in a file
 - 
 - man --> manual, 
 - 	ex: man cd
 - 		man touch
 - 
 - find - to search for the file
 - 
 - 	find *.txt --> lists all text files on the current location
 - 
 - 	sudo find /home -type f   ====> lists all files under /home location	
 - 	sudo find /home -type f -empty  ====> lists all empty files under /home location
 - 
 - 	sudo find /home -type d   ====> lists all directories under /home location
 - 	sudo find /home -type d -empty  ====> lists all empty directories under /home location
 - 
 - hostname
 - hostnamectl - more information about the VM
 - ifconfig
 - netstat -tulpn --> to check all ports running on the system
 - wget --> Download files from internet.
 - history
 - ping google.com ==> to check if connectivity to the particular website is there or not.
 - yum ==> to install/remove softwares
 - 
 - yum list java*
 - sudo yum install java-22-amazon-corretto.x86_64 -y
 - sudo yum remove java* -y
 

   
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


## User and Group Creation

- In Linux, we have 3 types of users:
	1. super user --> root --> home dir location = /root
	2. normal user --> ec2-user --> home dir location = /home/ec2-user
	3. system user Ex: ftp --> home dir location = /var/ftp

 - When we create a user, following things happen by default:
	1. A home directory will be created --> under /home
	2. An entry in /etc/passwd
	3. Unique UID and GID will be given to the user.

 - cat /etc/passwd ==> This file contains all user details
 - cat /etc/group  ==> This file contains all group details


 - Create user in Linux: 
	useradd <user-name>
	 - Ex: useradd aws-user
	 - Ex: useradd -c "For Testing Team" sit-user
	 - In /etc/passwd file:
		- aws-user:x:1001:1001::/home/aws-user:/bin/bash
		- sit-user:x:1003:1003:For Testing Team:/home/sit-user:/bin/bash
		
		aws-user = user name
		x = password
		1001 = user id
		1001 = group id
		For Testing Team = Comment
		/home/aws-user = Default Home Directory
		/bin/bash = Shell

 - [root@ip-192-168-1-222 home]# id aws-user
 - uid=1001(aws-user) gid=1001(aws-user) groups=1001(aws-user)


 - Customize the home directory for newly created user:
	 - useradd -m -d /home/sit -c "Fot Testing Team" test-user

 - Delete a user:
	1. userdel <user_name>
	 - It performs following activities:
		 - It will delete the user, 
		 - removes the entry from passwd file, 
		 - deletes the group which got created during user creation.
		 - NB - If the group will be attached to other users, then it won't get deleted.

	 - userdel -f <user_name>
		- performs above activities mentioned in #1 
		- force delete even if the user is logged in
		
	 - userdel -r <user_name>
		- performs above activities mentioned in #1
		- Removes the home directory
	
	 - userdel -rf <user_name>
		- performs above activities mentioned in #1 
		- force delete even if the user is logged in
		- Removes the home directory

 - Create Group:
	groupadd <group_name>

 - Delete Group:
	groupdel <group_name>

 - Add user to a Group:
	usermod -G <group_name> <user_name>


 - To check all users: cat /etc/passwd
 - To check all groups: cat /etc/group
 - To check the user details: id <user_name>
 - To create a user and add it to an existing group: useradd -g <group_name> <user_name>
 - Add existing user to existing group: usermod -G <group_name> <user_name>  ==> It will allow  add user to only one second group.
 - Add existing user to existing group: usermod -a -G <group_name> <user_name>
 - Remove a user from a group: gpasswd -d <user_name> <group_name>
 - Change the default group of a user: usermod -g <existing_another_group_name> <user_name>
 - Remove all secondary/supplementary groups from username, leaving them as a member of only their primary group.
	 - usermod -G "" <user_name>

## Absolute Path and Relative Path:
 - Absolute Path = Starts from the root directory (indicated by a forward slash /) and provides the full, unambiguous location of a file or directory.
 - Relative path = specifies the location of a file or directory in relation to your current working directory, making it shorter and more convenient for local navigation but dependent on your current location to be valid. 

## Soft Link and Hard Link:
 - Soft Link = A soft link is a special type of file that contains a path to another file or directory. It acts as a pointer or a shortcut to the target.
	 - ln -s <src_file_name> <shortcut_name>

 - Hard Link = Backup, it's another name for the same file.
	 - ln <src_file_name> <backup_file_name>


## Change Hostname
 - hostnamectl set-hostname <new_host_name>

##  Set Password for a User
 - passwd <user_name>

## Login to VM by:
	1. Key Based (Public Key + Private Key)
	2. Password Based (By default disabled)

## Enable Password Based authentication:
	- sudo su
	- groupadd devops
	- useradd -g devops devops-user
	- id devops-user
	- passwd devops-user
	- sudo vi /etc/ssh/sshd_config
		- do the change:
			- PasswordAuthentication yes
		- Save and exit.
	
## systemctl commands:
	- status
	- start
	- stop
	- restart
	- reload
	- enable

	- sudo systemctl reload sshd

## Login through password
	- ssh devops-user@3.109.157.209

## Archiving files and directories
	- gzip:	gzip <file_name>
		- To create a compressed file (zip file)
		- File size gets reduced
		- Actual file gets converted to zip file with extension gz
		- Actual file gets deleted, zip file gets created

	- gunzip: gunzip <file_name>
		- Unzip a file
		- zip file gets deleted, Actual file gets created
	
	- zip:
		- To create a compressed file (zip file)
		- zip <zip_file_name_to_be_created> <existing_file_name>
		- Actual file will be there and one zip file gets created

	- tar: works on directories
		tar -cvf <zip_file_name_to_be_created> <existing_dir_name>
		c - create
		v - verbous
		f - file
	
	- untar:
		tar -xvf <existing_tar_file_name>
		x - extract
	
	- tar -xzvf <existing_tar_zip_file_name>

## Process Management Commands
 - Process - When you start a program or application in Linux, it runs as a process.

	- ps -ef ==> List all the processes running
	- ps -ef | grep <process_name> ===> Search for a particular process
	
	- kill -15 <process_id>  ==> safe way of terminating a process
	- kill -9 <process_id>  ===> forcefully terminating a process


## File Permission

 - file ==>  -
 - directory ==> d
 - link ==> l	

 - 4 = r = read
 - 2 = w = write
 - 1 = x = execute
 - 0 = no permission

- rwx(1) rwx(2) rwx(3)

 - rwx(1) = user
 - rwx(2) = primary group
 - rwx(3) = other group


## Change file permission in 2 ways:
 - 	1. symbolic link 	==> u, g, o (+/-/=)
 - 	2. Absolute method  ==> we use numbers
 - 
 - 4 = r = read
 - 2 = w = write
 - 1 = x = execute
 - 0 = no permission
 - 
 - chmod u=rwx,g=rwx,o=rwx file.txt
 - chmod u=rxw,g=rxw,o=rxw file.txt
 - chmod u=rwx,g=rw,o=rw file.txt
 - chmod u=rwx,g=rx,o=w file.txt
 - chmod u=rwx,g-w,o+x file.txt
 - chmod o-x file.txt
 - chmod g+w file.txt
 - chmod ugo= file.txt
 - 
 - 
 - chmod 777 file.txt
 - chmod 700 file.txt
 - chmod 666 file.txt
 - 
 - chmod 777 ec2-user
 - 
 - change ownership of a file: we need sudo access for this.
 - sudo chown aws-user:aws file.txt

## sudoers
 - sudo = super user do
 - 	= Grant admin rights temporarily.
 - 
 - 1. Created a group : aws	=====> groupadd aws
 - 2. Created new user and added to the group : aws-user ==> useradd -g aws aws-user
 - 3. Tried to perform admin activities by this new user aws-user ==> Failed
 - 4. Added aws-user in /etc/sudoers file.
 - 	
 - 	## Allow root to run any commands anywhere =====> Already there
 - 	root    ALL=(ALL)       ALL				   =====> Already there
 - 	aws-user ALL=(ALL) ALL					   =====> We added
 - 
 - 5. Tried to perform admin activities ==> Success 
 - 6. Removed the entry of the user from /etc/sudoers file.
 - 7. Added the group in /etc/sudoers file.
 - 	## Allows people in group wheel to run all commands =====> Already there
 - 	%wheel  ALL=(ALL)       ALL			=====> Already there
 - 	%aws ALL=(ALL) ALL					=====> We added
 - 
 - Key Based Authentication:
 - ========================
 - Public Key
 - Private Key
 - 
 - .ssh ===> 700
 - authorized_keys ==> 600

## Connect 2 Linux Machines using ssh

 - create 2 linux machines:

 - In VM 1:
 - sudo hostnamectl set-hostname vm1

 - 1. create a user as user1===> useradd user1
 - 2. set the password for user1 ===> passwd user1
 - 3. switch to user1
 - 4. do ssh-keygen
 - 5. Copy the public key and paste in authorized_keys under .ssh of VM2

 - In VM 2:
 - sudo hostnamectl set-hostname vm2

 - 1. create a user as user2===> useradd user2
 - 2. set the password for user2 ===> passwd user2
 - 3. switch to user2
 - 4. create a directory as .ssh
 - 5. Create a file as authorized_keys
 - 6. provide appropriate permission to .ssh and authorized_keys
 - 7. paste the public key of user1 in authorized_keys

 - Connect to VM2 from VM1:
	#### 1 ssh <user_name>@<private_ip>   ============> using private IP
	#### 2 ssh -i <private_key> <user_name>@<public_ip> ===> using public key



## tree:
	sudo yum install tree -y


## Additional Commands:
 - free	 ==> ==> memory usage 
 - free -m  ==> memory usage in MB
 - uname -a ==> Check Kernel version
 - du -k =====> Disk usage in KB
 - du -m =====> Disk usage in MB
 - df -m
 - df -k









