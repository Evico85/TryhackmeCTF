Library.doc
--------------

name : Eviyatar Cohen

Date : 18.10.2022

IP= 10.10.192.255
-----------------------------------

Nmap Results:
==============
nmap -sC -sV 10.10.192.255  
Starting Nmap 7.92 ( https://nmap.org ) at 2022-10-18 04:55 EDT
Nmap scan report for 10.10.192.255
Host is up (0.086s latency).
Not shown: 998 closed tcp ports (conn-refused)
PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 7.2p2 Ubuntu 4ubuntu2.8 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 c4:2f:c3:47:67:06:32:04:ef:92:91:8e:05:87:d5:dc (RSA)
|   256 68:92:13:ec:94:79:dc:bb:77:02:da:99:bf:b6:9d:b0 (ECDSA)
|_  256 43:e8:24:fc:d8:b8:d3:aa:c2:48:08:97:51:dc:5b:7d (ED25519)
80/tcp open  http    Apache httpd 2.4.18 ((Ubuntu))
| http-robots.txt: 1 disallowed entry 
|_/
|_http-title: Welcome to  Blog - Library Machine
|_http-server-header: Apache/2.4.18 (Ubuntu)
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 13.62 seconds

----------------------------------------------------------------

Potential Username:
====================
meliodas:iloveyou1

Trying Hydra to get ssh password..
------------------------------------

After i login into ssh with meliodas i found her user flag!!
===============================================================
6d488cbb3f111d135722c33cb635f4ec

then i saw python allowed without password so i created zipfile.py file and entered my GTFOBin script to get root shell!!
==============================================================

Root Flag : e8c8c6c256c35515d1d344ee0488c617