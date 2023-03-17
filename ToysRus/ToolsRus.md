ToolsRus.doc
------------------

name : Eviyatar Cohen

Date : 3.10.2022

IP = 10.10.107.236

----------------------------------

Nmap Results:
=================
nmap -sC -sV 10.10.107.236
Starting Nmap 7.92 ( https://nmap.org ) at 2022-10-03 02:48 EDT
Nmap scan report for 10.10.107.236
Host is up (0.085s latency).
Not shown: 998 closed tcp ports (conn-refused)
PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 7.2p2 Ubuntu 4ubuntu2.8 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 ac:bc:91:93:52:4e:b2:90:7b:7f:99:68:e2:a6:f0:c0 (RSA)
|   256 81:74:32:73:5a:32:22:33:cb:6a:5e:6c:2b:3a:71:92 (ECDSA)
|_  256 c7:71:3b:76:04:f4:20:3d:ae:e5:74:79:b0:96:92:06 (ED25519)
80/tcp open  http    Apache httpd 2.4.18 ((Ubuntu))
|_http-title: Site doesn't have a title (text/html).
|_http-server-header: Apache/2.4.18 (Ubuntu)
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 20.41 seconds
------------------------------------------------------------------

GoBuster Results:
==================
gobuster dir -u http://10.10.107.236 -w /usr/share/wordlists/dirbuster/directory-list-lowercase-2.3-medium.txt
===============================================================
Gobuster v3.1.0
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     http://10.10.107.236
[+] Method:                  GET
[+] Threads:                 10
[+] Wordlist:                /usr/share/wordlists/dirbuster/directory-list-lowercase-2.3-medium.txt
[+] Negative Status codes:   404
[+] User Agent:              gobuster/3.1.0
[+] Timeout:                 10s
===============================================================
2022/10/03 02:49:33 Starting gobuster in directory enumeration mode
===============================================================
/guidelines           (Status: 301) [Size: 319] [--> http://10.10.107.236/guidelines/]
/protected            (Status: 401) [Size: 460]                                       
/server-status        (Status: 403) [Size: 301]                                       
Progress: 131716 / 207644 (63.43%)                                                   ^C
[!] Keyboard interrupt detected, terminating.
                                                                                      
===============================================================
2022/10/03 03:08:43 Finished
===============================================================

-----------------------------------------------------------------
Potential Users:
==================
bob:bubbles

Using Hydra To Get Password..
---------------------------------

Nmap Second Scan:
=====================
nmap -p- -T4 10.10.107.236
Starting Nmap 7.92 ( https://nmap.org ) at 2022-10-03 03:10 EDT
Nmap scan report for 10.10.107.236
Host is up (0.082s latency).
Not shown: 65531 closed tcp ports (conn-refused)
PORT     STATE SERVICE
22/tcp   open  ssh
80/tcp   open  http
1234/tcp open  hotline
8009/tcp open  ajp13

-----------------------------------------------------------------

Used exploit/multi/http/tomcat_mgr_upload and set options to get root shell
==================================================================

root.txt : ff1fc4a81affcc7688cf89ae7dc6e0e1

