Retro.doc
--------------

Nmae : Eviyatar Cohen

Date : 8.10.2022

IP= 10.10.131.101
-------------------------------------

Nmap Results:
==============
nmap -sC -sV -Pn 10.10.131.101 
Starting Nmap 7.92 ( https://nmap.org ) at 2022-10-08 03:24 EDT
Nmap scan report for 10.10.131.101
Host is up (0.089s latency).
Not shown: 998 filtered tcp ports (no-response)
PORT     STATE SERVICE       VERSION
80/tcp   open  http          Microsoft IIS httpd 10.0
| http-methods: 
|_  Potentially risky methods: TRACE
|_http-title: IIS Windows Server
|_http-server-header: Microsoft-IIS/10.0
3389/tcp open  ms-wbt-server Microsoft Terminal Services
| rdp-ntlm-info: 
|   Target_Name: RETROWEB
|   NetBIOS_Domain_Name: RETROWEB
|   NetBIOS_Computer_Name: RETROWEB
|   DNS_Domain_Name: RetroWeb
|   DNS_Computer_Name: RetroWeb
|   Product_Version: 10.0.14393
|_  System_Time: 2022-10-08T07:24:27+00:00
| ssl-cert: Subject: commonName=RetroWeb
| Not valid before: 2022-10-07T07:23:02
|_Not valid after:  2023-04-08T07:23:02
|_ssl-date: 2022-10-08T07:24:28+00:00; 0s from scanner time.
Service Info: OS: Windows; CPE: cpe:/o:microsoft:windows

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 17.19 seconds
==================================================================

GoBuster Results:
====================
gobuster dir -u http://10.10.131.101/retro -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
===============================================================
Gobuster v3.1.0
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     http://10.10.131.101/retro
[+] Method:                  GET
[+] Threads:                 10
[+] Wordlist:                /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
[+] Negative Status codes:   404
[+] User Agent:              gobuster/3.1.0
[+] Timeout:                 10s
===============================================================
2022/10/08 03:41:22 Starting gobuster in directory enumeration mode
===============================================================
/wp-content           (Status: 301) [Size: 161] [--> http://10.10.131.101/retro/wp-content/]
/wp-includes          (Status: 301) [Size: 162] [--> http://10.10.131.101/retro/wp-includes/]
/wp-admin             (Status: 301) [Size: 159] [--> http://10.10.131.101/retro/wp-admin/]   
Progress: 66253 / 220561 (30.04%)                                                           ^C
[!] Keyboard interrupt detected, terminating.
                                                                                             
===============================================================
2022/10/08 03:52:07 Finished
===============================================================
==================================================================

Credentials Found!!
====================
Wade:parzival

after login with those credentials to the windows mechine using xfreerdp i found the User Flag:
==================================================================

Flags!!
==========

User Flag : 3b99fbdc6d430bfb51c72c651a261927

To Find The Root Flag i Used CVE-2017-0213 and upload the file to the mechine to get Root Terminal!!

Root Flag : 7958b569565d7bd88d10c6f22d1c4063
