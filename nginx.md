## Setup NGINX On Ubuntu

 - apt update --> permission denied

 - sudo apt update --> taken root access and check for upgradables
	 - Hit - Checks for the update
	 - Get - Retrieves the version details and stores in local cache
	 - Ign - Ignore

 - apt list --upgradable  --> List of softwares to be upgraded

 - sudo apt upgrade -y   -> Upgrades to the latest version

 - sudo apt install nginx -y

 - systemctl status nginx 
 - sudo systemctl start nginx 
 - sudo systemctl stop nginx 
 - sudo systemctl restart nginx 
