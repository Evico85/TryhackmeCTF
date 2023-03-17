Source.doc
----------------

name : Eviyatar Cohen

Date : 10.10.2022

IP=
-----------------------------------------

Nmap Results:
==============
nmap -sC -sV 10.10.223.30 
Starting Nmap 7.92 ( https://nmap.org ) at 2022-10-10 05:18 EDT
Nmap scan report for 10.10.223.30
Host is up (0.087s latency).
Not shown: 998 closed tcp ports (conn-refused)
PORT      STATE SERVICE  VERSION
22/tcp    open  ssh      OpenSSH 7.6p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 b7:4c:d0:bd:e2:7b:1b:15:72:27:64:56:29:15:ea:23 (RSA)
|   256 b7:85:23:11:4f:44:fa:22:00:8e:40:77:5e:cf:28:7c (ECDSA)
|_  256 a9:fe:4b:82:bf:89:34:59:36:5b:ec:da:c2:d3:95:ce (ED25519)
10000/tcp open  ssl/http MiniServ 1.890 (Webmin httpd)
|_http-title: Site doesn't have a title (text/html; Charset=iso-8859-1).
|_http-trane-info: Problem with XML parsing of /evox/about
| ssl-cert: Subject: commonName=*/organizationName=Webmin Webserver on source
| Not valid before: 2020-06-26T04:42:03
|_Not valid after:  2025-06-25T04:42:03
|_ssl-date: TLS randomness does not represent time
|_http-server-header: MiniServ/1.890
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 48.44 seconds

==================================================================

Using Webmin_Backdoor Exploit in metasploit gave me root access to the mechine (Found In AttackerKB):
-----------------------------------------

Flags!!
===========

User Flag : THM{SUPPLY_CHAIN_COMPROMISE}

Root Flag : THM{UPDATE_YOUR_INSTALL}
