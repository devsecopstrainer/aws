## Linux Architecture:
	User -> Shell -> Kernel -> hardware

## Script:
	- Set of commands / instructions mentioned in a file for execution.
	- To automate our routine work.

## Shell Scripting:
	- It is used to execute set of Linux commands mentioned in a script file.
	- Extension .sh

	- Check the available shells in the machine: cat /etc/shells
	/bin/sh
	/bin/bash
	/usr/bin/sh
	/usr/bin/bash
	/bin/csh
	/bin/tcsh
	/usr/bin/csh
	/usr/bin/tcsh

	- Check the default shell: echo $SHELL
		/bin/bash
	
	#! ==> shebang

	#!/bin/bash
	
1. hello-world.sh

#!/bin/bash
echo "Hello World"

2. Comment Line in shell script:
	comment-line.sh
	
#!/bin/bash

#echo "Single Line Comment will start with #"

echo "Single Line Comment" # test abc

<< abc

comment line 1
comment line 2
comment line 3
comment line 4

abc

3. sleep example:
	sleep-ex.sh

#!/bin/bash
echo "Hello World"
sleep 5s
echo "Welcome Back"



