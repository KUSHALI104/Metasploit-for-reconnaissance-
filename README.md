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

## EXECUTION STEPS AND ITS OUTPUT:

Find out the ip address of the attackers system

## OUTPUT:

![image](https://github.com/user-attachments/assets/1bbfd4c2-e511-4774-8219-e9bdd8d694f6)

Invoke msfconsole:

![image](https://github.com/user-attachments/assets/649f11ae-05e2-43c1-9377-2954d2cf84b1)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

![image](https://github.com/user-attachments/assets/5c522352-e297-496a-a07c-24a4cb4ee743)

## Port Scanning:
Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000

### OUTPUT:

![image](https://github.com/user-attachments/assets/ed717f00-aec2-4686-90b4-993f25b7f790)

step4:

use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24

## OUTPUT:

![image](https://github.com/user-attachments/assets/43c561b4-3dee-4bb9-b2dc-d0e39b1eecc9)

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l

## OUTPUT:

![image](https://github.com/user-attachments/assets/fc9fdfb6-3408-43ad-8291-914acc72f82a)

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

The info command provides information regarding a module or platform,

## OUTPUT

![image](https://github.com/user-attachments/assets/a286e65e-2605-478c-8e9b-525f5aac4b9b)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init

## MYSQL ENUMERATION
Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>

![image](https://github.com/user-attachments/assets/dd695837-88ec-424c-84bd-f11345fb071c)

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql

![image](https://github.com/user-attachments/assets/a1fd1007-432d-4fa9-bc5a-b7256df89e48)

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version

![image](https://github.com/user-attachments/assets/61d8e2d1-135c-44fd-9177-b80a386709fe)

Use the set rhosts command to set the parameter and run the module, as follows:

![image](https://github.com/user-attachments/assets/59aad2d4-d186-4f34-914e-07787dadef6d)

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.

![image](https://github.com/user-attachments/assets/125964d1-9920-4747-b63d-cbb382d4416e)

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true

![image](https://github.com/user-attachments/assets/b834d553-04d7-4d9f-b599-be9e94d7cbfb)


## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
