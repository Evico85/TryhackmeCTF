Skynet.doc
======================

name : Eviyatar Cohen
Date : 21/9/2022

IP = 10.10.114.49
------------------------------------------------------------

#Tasks:
===================

> What is Miles password for his emails?
-------------
cyborg007haloterminator
-------------

> What is the hidden directory?
--------------
/45kra24zxs28v3yd
--------------


Nmap Results:
==================
nmap -sC -sV 10.10.114.49
Starting Nmap 7.92 ( https://nmap.org ) at 2022-09-21 06:14 EDT
Nmap scan report for 10.10.114.49
Host is up (0.085s latency).
Not shown: 994 closed tcp ports (conn-refused)
PORT    STATE SERVICE     VERSION
22/tcp  open  ssh         OpenSSH 7.2p2 Ubuntu 4ubuntu2.8 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 99:23:31:bb:b1:e9:43:b7:56:94:4c:b9:e8:21:46:c5 (RSA)
|   256 57:c0:75:02:71:2d:19:31:83:db:e4:fe:67:96:68:cf (ECDSA)
|_  256 46:fa:4e:fc:10:a5:4f:57:57:d0:6d:54:f6:c3:4d:fe (ED25519)
80/tcp  open  http        Apache httpd 2.4.18 ((Ubuntu))
|_http-title: Skynet
|_http-server-header: Apache/2.4.18 (Ubuntu)
110/tcp open  pop3        Dovecot pop3d
|_pop3-capabilities: RESP-CODES TOP UIDL AUTH-RESP-CODE SASL PIPELINING CAPA
139/tcp open  netbios-ssn Samba smbd 3.X - 4.X (workgroup: WORKGROUP)
143/tcp open  imap        Dovecot imapd
|_imap-capabilities: more LOGINDISABLEDA0001 OK LITERAL+ IDLE post-login LOGIN-REFERRALS SASL-IR IMAP4rev1 ID capabilities listed Pre-login ENABLE have
|_sslv2: ERROR: Script execution failed (use -d to debug)
445/tcp open  netbios-ssn Samba smbd 4.3.11-Ubuntu (workgroup: WORKGROUP)
Service Info: Host: SKYNET; OS: Linux; CPE: cpe:/o:linux:linux_kernel

Host script results:
|_clock-skew: mean: 1h40m00s, deviation: 2h53m12s, median: 0s
| smb2-security-mode: 
|   3.1.1: 
|_    Message signing enabled but not required
| smb-security-mode: 
|   account_used: guest
|   authentication_level: user
|   challenge_response: supported
|_  message_signing: disabled (dangerous, but default)
|_nbstat: NetBIOS name: SKYNET, NetBIOS user: <unknown>, NetBIOS MAC: <unknown> (unknown)
| smb-os-discovery: 
|   OS: Windows 6.1 (Samba 4.3.11-Ubuntu)
|   Computer name: skynet
|   NetBIOS computer name: SKYNET\x00
|   Domain name: \x00
|   FQDN: skynet
|_  System time: 2022-09-21T05:14:52-05:00
| smb2-time: 
|   date: 2022-09-21T10:14:52
|_  start_date: N/A

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 24.98 seconds


SMB Shares :
===============
Sharename       Type      Comment
---------       ----      -------
print$          Disk      Printer Drivers
anonymous       Disk      Skynet Anonymous Share
milesdyson      Disk      Miles Dyson Personal Share
IPC$            IPC       IPC Service (skynet server (Samba, Ubuntu))

-------------------------------------------------------------------
inside logs there was three log files: log1.txt log2.txt log3.txt
-------------------------------------------------------------------

log1.txt was hold a list of passwords (I think..) :
----------------------------------------------------
#cyborg007haloterminator# <---------- (password for emails..)
terminator22596
terminator219
terminator20
terminator1989
terminator1988
terminator168
terminator16
terminator143
terminator13
terminator123!@#
terminator1056
terminator101
terminator10
terminator02
terminator00
roboterminator
pongterminator
manasturcaluterminator
exterminator95
exterminator200
dterminator
djxterminator
dexterminator
determinator
cyborg007haloterminator
avsterminator
alonsoterminator
Walterminator
79terminator6
1996terminator
-----------------------------------------------------------

Gobuster Results:
======================
gobuster dir -u http://10.10.114.49 -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
===============================================================
Gobuster v3.1.0
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     http://10.10.114.49
[+] Method:                  GET
[+] Threads:                 10
[+] Wordlist:                /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
[+] Negative Status codes:   404
[+] User Agent:              gobuster/3.1.0
[+] Timeout:                 10s
===============================================================
2022/09/21 06:24:05 Starting gobuster in directory enumeration mode
===============================================================
/admin                (Status: 301) [Size: 312] [--> http://10.10.114.49/admin/]
/css                  (Status: 301) [Size: 310] [--> http://10.10.114.49/css/]  
/js                   (Status: 301) [Size: 309] [--> http://10.10.114.49/js/]   
/config               (Status: 301) [Size: 313] [--> http://10.10.114.49/config/]
/ai                   (Status: 301) [Size: 309] [--> http://10.10.114.49/ai/]    
/squirrelmail         (Status: 301) [Size: 319] [--> http://10.10.114.49/squirrelmail/]
Progress: 58627 / 220561 (26.58%)                                                     ^C
[!] Keyboard interrupt detected, terminating.
                                                                                       
===============================================================
2022/09/21 06:33:21 Finished
===============================================================


inside the email of milesdyson i found his SMB password :
===========================================================
)s{A&2Z=F^n_E.B`

and there was the hidden directoy : /45kra24zxs28v3yd
------------------------------------------------------


Gobuster Results on /45kra24zxs28v3yd :
========================================
gobuster dir -u http://10.10.114.49/45kra24zxs28v3yd -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
===============================================================
Gobuster v3.1.0
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     http://10.10.114.49/45kra24zxs28v3yd
[+] Method:                  GET
[+] Threads:                 10
[+] Wordlist:                /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
[+] Negative Status codes:   404
[+] User Agent:              gobuster/3.1.0
[+] Timeout:                 10s
===============================================================
2022/09/21 07:02:14 Starting gobuster in directory enumeration mode
===============================================================
/administrator        (Status: 301) [Size: 337] [--> http://10.10.114.49/45kra24zxs28v3yd/administrator/]
Progress: 5720 / 220561 (2.59%)                                                                  Progress: 5780 / 220561 (2.62%)                                                                  Progress: 5836 / 220561 (2.65%)                                                                  Progress: 5887 / 220561 (2.67%)                                                                  Progress: 5937 / 220561 (2.69%)                                                                         ^C
[!] Keyboard interrupt detected, terminating.
                                                                                                         
===============================================================
2022/09/21 07:03:12 Finished
===============================================================
                                                                  
After I found the administrator webpage i found LFI that let me enter a php reverse shell using python HTTP server and nc listner and gor a shell !!

==================
User Flag Found!
==================
7ce5c2109a40f958099283600a9ae807

==========================================
After Using CVE-2021-4034 Found Root Flag!
==========================================
3f0372db24753accc7179a282cd6a949

