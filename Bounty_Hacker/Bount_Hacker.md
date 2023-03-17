Bount_Hacker.doc
-----------------------

Nmap Results:
-------------------------
nmap -sC -sV 10.10.21.125 
Starting Nmap 7.92 ( https://nmap.org ) at 2022-09-16 07:50 EDT
Nmap scan report for 10.10.21.125
Host is up (0.098s latency).
Not shown: 967 filtered tcp ports (no-response), 30 closed tcp ports (conn-refused)
PORT   STATE SERVICE VERSION
21/tcp open  ftp     vsftpd 3.0.3
| ftp-syst: 
|   STAT: 
| FTP server status:
|      Connected to ::ffff:10.18.26.95
|      Logged in as ftp
|      TYPE: ASCII
|      No session bandwidth limit
|      Session timeout in seconds is 300
|      Control connection is plain text
|      Data connections will be plain text
|      At session startup, client count was 3
|      vsFTPd 3.0.3 - secure, fast, stable
|_End of status
| ftp-anon: Anonymous FTP login allowed (FTP code 230)
| -rw-rw-r--    1 ftp      ftp           418 Jun 07  2020 locks.txt
|_-rw-rw-r--    1 ftp      ftp            68 Jun 07  2020 task.txt
22/tcp open  ssh     OpenSSH 7.2p2 Ubuntu 4ubuntu2.8 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 dc:f8:df:a7:a6:00:6d:18:b0:70:2b:a5:aa:a6:14:3e (RSA)
|   256 ec:c0:f2:d9:1e:6f:48:7d:38:9a:e3:bb:08:c4:0c:c9 (ECDSA)
|_  256 a4:1a:15:a5:d4:b1:cf:8f:16:50:3a:7d:d0:d8:13:c2 (ED25519)
80/tcp open  http    Apache httpd 2.4.18 ((Ubuntu))
|_http-title: Site doesn't have a title (text/html).
|_http-server-header: Apache/2.4.18 (Ubuntu)
Service Info: OSs: Unix, Linux; CPE: cpe:/o:linux:linux_kernel

Potential Users:
-----------------------
Ed:No Need
spike:No Need
jet:No Need
Faye:No Need
lin:RedDr4gonSynd1cat3
Edward:No Need
Ein:No Need

FTP Files:
------------------------
locks.txt
task.txt


GoBuster Results:
-------------------------
gobuster dir -u http://10.10.21.125 -w /usr/share/wordlists/dirb/big.txt 
===============================================================
Gobuster v3.1.0
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     http://10.10.21.125
[+] Method:                  GET
[+] Threads:                 10
[+] Wordlist:                /usr/share/wordlists/dirb/big.txt
[+] Negative Status codes:   404
[+] User Agent:              gobuster/3.1.0
[+] Timeout:                 10s
===============================================================
2022/09/16 07:57:51 Starting gobuster in directory enumeration mode
===============================================================
/.htaccess            (Status: 403) [Size: 277]
/.htpasswd            (Status: 403) [Size: 277]
/images               (Status: 301) [Size: 313] [--> http://10.10.21.125/images/]
/server-status        (Status: 403) [Size: 277]                                  
                                                                                 
===============================================================
2022/09/16 08:01:25 Finished
===============================================================

Content of task.txt:
--------------------------                   
1.) Protect Vicious.
2.) Plan for Red Eye pickup on the moon.

-lin
--------------------------

Content of locks.txt:
--------------------------    
rEddrAGON            -
ReDdr4g0nSynd!cat3   -
Dr@gOn$yn9icat3      -
R3DDr46ONSYndIC@Te   -
ReddRA60N            -
R3dDrag0nSynd1c4te   -
dRa6oN5YNDiCATE      -
ReDDR4g0n5ynDIc4te
R3Dr4gOn2044
RedDr4gonSynd1cat3
R3dDRaG0Nsynd1c@T3
Synd1c4teDr@g0n
reddRAg0N
REddRaG0N5yNdIc47e
Dra6oN$yndIC@t3
4L1mi6H71StHeB357
rEDdragOn$ynd1c473
DrAgoN5ynD1cATE
ReDdrag0n$ynd1cate
Dr@gOn$yND1C4Te
RedDr@gonSyn9ic47e
REd$yNdIc47e
dr@goN5YNd1c@73
rEDdrAGOnSyNDiCat3
r3ddr@g0N
ReDSynd1ca7e

Flags Found!
========================
User Flag:THM{CR1M3_SyNd1C4T3}

Root Flag:THM{80UN7Y_h4cK3r}










