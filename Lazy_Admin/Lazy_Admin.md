Lazy_Admin.doc
========================

Nmap Results:
========================
nmap -sC -sV 10.10.176.55 
Starting Nmap 7.92 ( https://nmap.org ) at 2022-09-18 12:52 EDT
Nmap scan report for 10.10.176.55
Host is up (0.085s latency).
Not shown: 998 closed tcp ports (conn-refused)
PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 7.2p2 Ubuntu 4ubuntu2.8 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 49:7c:f7:41:10:43:73:da:2c:e6:38:95:86:f8:e0:f0 (RSA)
|   256 2f:d7:c4:4c:e8:1b:5a:90:44:df:c0:63:8c:72:ae:55 (ECDSA)
|_  256 61:84:62:27:c6:c3:29:17:dd:27:45:9e:29:cb:90:5e (ED25519)
80/tcp open  http    Apache httpd 2.4.18 ((Ubuntu))
|_http-title: Apache2 Ubuntu Default Page: It works
|_http-server-header: Apache/2.4.18 (Ubuntu)
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 14.77 seconds

Gobuster Results:
============================
gobuster dir -u http://10.10.176.55/content/ -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
===============================================================
Gobuster v3.1.0
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     http://10.10.176.55/content/
[+] Method:                  GET
[+] Threads:                 10
[+] Wordlist:                /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
[+] Negative Status codes:   404
[+] User Agent:              gobuster/3.1.0
[+] Timeout:                 10s
===============================================================
2022/09/18 13:04:31 Starting gobuster in directory enumeration mode
===============================================================
/images               (Status: 301) [Size: 321] [--> http://10.10.176.55/content/images/]
/js                   (Status: 301) [Size: 317] [--> http://10.10.176.55/content/js/]    
/inc                  (Status: 301) [Size: 318] [--> http://10.10.176.55/content/inc/]   
/as                   (Status: 301) [Size: 317] [--> http://10.10.176.55/content/as/]    
/_themes              (Status: 301) [Size: 322] [--> http://10.10.176.55/content/_themes/]
/attachment           (Status: 301) [Size: 325] [--> http://10.10.176.55/content/attachment/]
Progress: 117828 / 220561 (53.42%)                                                          ^C
[!] Keyboard interrupt detected, terminating.
                                                                                             
===============================================================
2022/09/18 13:22:36 Finished
===============================================================

Found inside the mysql file a username and password for website:
====================================================================
manager:Password123

After Login Into the Website i Use PHP revese shell for the web and got a Shell
=================================================================================

Found Flags!
============
User Flag: THM{63e5bce9271952aad1113b6f1ac28a07}

Root Flag: THM{6637f41d0177b6f37cb20d775124699f}









