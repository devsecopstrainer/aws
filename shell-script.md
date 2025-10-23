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

 - #!/bin/bash
   echo "Hello World"

2. Comment Line in shell script:
	 - comment-line.sh
	
 - #!/bin/bash
 - #echo "Single Line Comment will start with #"
 - echo "Single Line Comment" # test abc
 - << abc
 - comment line 1
 - comment line 2
 - comment line 3
 - comment line 4
 - abc

3. sleep example:
	sleep-ex.sh

#!/bin/bash
 - echo "Hello World"
 - sleep 5s
 - echo "Welcome Back"


## Variables:
	- Storage location that has a name.
	- Name value pair.
	- 2 types:
		- Environment variables
			- see all environment variables => printenv
		- User defined variables
			- It can contain letters (A-Z a-z), numbers (0-9), underscore (_)
			- Can start with letters or underscore, but cannot start with numbers.
			- Special characters or symbols not allowed.
			- Dynamically typed.
			
			

## Steps:

		Create the file : touch script_var_ex.sh
		Provide Permission: chmod 755 script_var_ex.sh
		Edit the file: vi script_var_ex.sh
		Execute the script: sh script_var_ex.sh

 - Example: script_var_ex.sh
   
		#!/bin/bash
		MY_VAR_1="Test Data"
		MY_VAR_2=20
		MY_VAR_3=10.23
		echo $MY_VAR_1
		echo "value of variable 2 = $MY_VAR_2"
		echo $MY_VAR_3
		
## Assign command output to a variable:

		#!/bin/bash
		name=$(hostname)
		echo "host name is : $name"


## Command Line Arguments:

		Ex: 
		#!/bin/bash
		echo $0
		echo $1
		echo $2
		echo $3

 - Execute as: sh script_var_ex.sh test data ok
 - Output:
		script_var_ex.sh
		test
		data
		ok

## Ex: Print all the command line variables:

		#!/bin/bash
		echo $*

## Read input from user:

		#!/bin/bash
		echo "Enter your Name: "
		read name
		echo "You have entered: $name"

## Silent the input: (-s)
 - Ex1:

		#!/bin/bash

		echo "Enter User Name: "
		read u_name

		echo "Enter Password: "
		read -s u_pass

		echo "User name is : $u_name"
		echo "Password is : $u_pass"

 - Ex2:

		#!/bin/bash

		read -p "Enter User Name: " u_name
		read -sp "Enter Password: " u_pass

		echo ""
		echo "User name is : $u_name"
		echo "Password is : $u_pass"

		output:
		Enter User Name: test
		Enter Password:
		User name is : test
		Password is : 123


## Arithmetic Operations

			+ : add 
			- : subtract 
			* : multiply 
			/ : divide
			% : reminder 

### Ex

			#!/bin/bash
			num1=20
			num2=10
			#echo $num1+$num2			# 20+10
			#echo $(num1+num2)			# num1+num2: command not found
			echo $((num1+num2))			# 30
			echo $(expr $num1 % $num2)	# 9



## Conditional Statements
 - if, then, elif, else, fi

### Ex:
			#!/bin/bash
			num1=20
			if [ $num1 -eq 20 ]; then
				echo "Value is 20"
				echo "Inside if block"
			fi


### Ex:

			#!/bin/bash

			str1="Welcome"
			str2="Hello"

			# Check if two strings are equal or not
			if [ $str1 == $str2 ]; then
				echo "Strings are equal"
			else
				echo "Strings are not equal"
			fi


### Ex:

			#!/bin/bash

			num1=20

			if [ $num1 -eq 20 ]; then
				echo "equal to 20"
			elif [ $num1 -gt 20 ]; then
				echo "greater than 20"
			else
				echo "Less than 20"
			fi


## Number Comparison:

			-eq -> equals   --> Returns true if both the values are equal
			-ne -> not equal -> Returns true if both the values are not equal
			-lt -> less than
			-le -> less than or equal to
			-gt -> greater than
			-ge -> greater than or equal to


## String Comparison:

### Ex:

			#!/bin/bash

			str1="Welcome"
			str2="Hello"
			str3="Hello"
			str4=""

			# Check if length of string is zero or not
			if [ -z $str4 ]; then
				echo "String length is zero"
			fi

			# Check if two strings are equal or not
			if [ $str2 == $str3 ]; then
				echo "Strings are equal"
			fi

			# Check if two strings are equal or not
			if [ $str1 != $str3 ]; then
				echo "Strings are not equal"
			fi



## case statement in shell script

			#!/bin/bash

			read -p "Enter the name of day: " day

			case $day in

				"sun")
					echo "You have entered Sunday"
					echo "Sunday is Holiday"
					;;

				"mon")
					echo "You have entered Monday"
					echo "Monday is Working Day"
					;;

				*)
					echo "You have entered Invalid Day"
					echo "Please try again..."
					;;
			esac


## case statement with Semicolon Operator ;


			#!/bin/bash

			read -p "Enter the name of day: " day

			case $day in

				"sun")
					echo "You have entered Sunday"; echo "Sunday is Holiday";
					;;

				"mon")
					echo "You have entered Monday"; echo "Monday is Working Day";
					;;

				*)
					echo "You have entered Invalid Day"; echo "Please try again...";
					;;
			esac


## Logical And Operator &&

			#!/bin/bash

			str1="Hello"
			str2="Hello"
			str3="Hello"

			if [[ $str1 == $str2 && $str1 == $str3 ]]; then
				echo "all are equal"
			else
				echo "all are different"
			fi


## Logical Or Operator || 

			#!/bin/bash

			str1="Hello"
			str2="Welcome"
			str3="Welcome"

			if [[ $str1 == $str2 || $str2 == $str3 ]]; then
				echo "all are equal"
			else
				echo "all are different"
			fi

## Function - No arg function:

			#!/bin/bash

			function test() {
				echo "Function call starts here"
				echo "test function call"
				echo "Function call ends here"
			}

			test


## Pass parameter to the function:

			#!/bin/bash

			function test() {
				echo "Function call starts here"
				echo $1
				echo $2
				echo $3
			}

			test abc def ghi jkl mno

### Another Ex:

			#!/bin/bash

			function test() {
				echo "Function call starts here"
				echo $1
				echo $2
				echo $3
				str1="Hello"
				str2="Welcome"
				str3="Welcome"
				if [[ $str1 == $str2 || $str2 == $str3 ]]; then
					echo "all are equal"
				else
					echo "all are different"
				fi
			}

			test abc def ghi


## for Loop - Ex-1

			#!/bin/bash

			# print numbrs from 1 to 10 using for loop

			for (( i=1; i<=10; i++ )); do
				echo $i
			done

## for Loop - Ex-2

			#!/bin/bash

			days="sun mon tue wed thu fri sat"
			for day in $days; do
				echo $day
			done




while loop: Ex-1

			#!/bin/bash
			i=1
			while [[ $i -le 10 ]]; do
					echo $i
					let i++
			done

while loop: Ex-2

			#!/bin/bash
			i=10
			while [[ $i -ge 1 ]]; do
				echo $i
				let i--
			done

