# Metasploit-for-reconnaissance
# Metasploit
Metasploit for reconnaissance in pentesting

# AIM:

To get introduced to Metasploit Framework and to  perform reconnaissance  in pentesting .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

# PROGRAM: 
Find out the ip address of the attackers system.

##  OUTPUT:
![image](https://github.com/Yogabharathi3/Metasploit-for-reconnaissance/assets/118899387/330b59b8-4801-4d70-91d9-24201eec1c1a)
Invoke msfconsole:

## OUTPUT:
![image](https://github.com/Yogabharathi3/Metasploit-for-reconnaissance/assets/118899387/ff5f2ca6-4728-41c0-8eb4-7db813e1eb82)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

![image](https://github.com/Yogabharathi3/Metasploit-for-reconnaissance/assets/118899387/99283143-503b-45f1-89b5-f74875bd274e)

Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000
## OUTPUT:
![image](https://github.com/Yogabharathi3/Metasploit-for-reconnaissance/assets/118899387/a4d31860-beb4-480a-9121-f8adca61a9b5)

step4: use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24

# OUTPUT:
![image](https://github.com/Yogabharathi3/Metasploit-for-reconnaissance/assets/118899387/1118180a-78c9-43a1-ac95-40def45a2ebe)

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l
# OUTPUT:
![image](https://github.com/Yogabharathi3/Metasploit-for-reconnaissance/assets/118899387/cde7c8a2-9f1c-4bea-8d1b-6e1f77b6c69c)

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

![image](https://github.com/Yogabharathi3/Metasploit-for-reconnaissance/assets/118899387/88c2069d-88ca-4785-978a-aae514786595)

The info command provides information regarding a module or platform.
# OUTPUT:
![image](https://github.com/Yogabharathi3/Metasploit-for-reconnaissance/assets/118899387/fd030f4b-09c9-42af-b0df-0dcab68bdb2f)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init

# MYSQL ENUMERATION:
```
            Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port.
```
db_nmap -sV -sC -p 3306 <metasploitable_ip_address>
# OUTPUT:
![image](https://github.com/Yogabharathi3/Metasploit-for-reconnaissance/assets/118899387/a3011417-761e-40f7-b986-c3bbf2f23dc9)

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql

![image](https://github.com/Yogabharathi3/Metasploit-for-reconnaissance/assets/118899387/a3737f8b-5f41-4ee1-abac-3d2b7cf49c44)

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version

![image](https://github.com/Yogabharathi3/Metasploit-for-reconnaissance/assets/118899387/64d169a3-2316-410f-8285-9df384aeb2d4)
Use the set rhosts command to set the parameter and run the module, as follows:
![image](https://github.com/Yogabharathi3/Metasploit-for-reconnaissance/assets/118899387/abc2901e-1976-4989-862f-cab1ca5bfdeb)

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.

![image](https://github.com/Yogabharathi3/Metasploit-for-reconnaissance/assets/118899387/5ce74fce-b4a4-4428-9242-d487da3ef64b)

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true

![image](https://github.com/Yogabharathi3/Metasploit-for-reconnaissance/assets/118899387/da7aa2dd-cc96-4fff-b5b7-db8853e6eb27)

## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
