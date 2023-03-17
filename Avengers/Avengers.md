Avengers.doc
----------------

name : Eviyatar Cohen

Date : 6.10.2022

IP= 10.10.213.47

--------------------------------------

Nmap Results:
==============
nmap -p- -T4 10.10.213.47
Starting Nmap 7.92 ( https://nmap.org ) at 2022-10-06 02:46 EDT
Stats: 0:05:26 elapsed; 0 hosts completed (1 up), 1 undergoing Connect Scan
Connect Scan Timing: About 91.05% done; ETC: 02:52 (0:00:32 remaining)
Nmap scan report for 10.10.213.47
Host is up (0.083s latency).
Not shown: 65533 closed tcp ports (conn-refused)
PORT   STATE SERVICE
21/tcp open  ftp
22/tcp open  ssh

Nmap done: 1 IP address (1 host up) scanned in 366.97 seconds

==================================================================

GoBuster Results:
====================
gobuster dir -u http://10.10.213.47 -w /usr/share/wordlists/dirbuster/directory-list-lowercase-2.3-medium.txt
===============================================================
Gobuster v3.1.0
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     http://10.10.213.47
[+] Method:                  GET
[+] Threads:                 10
[+] Wordlist:                /usr/share/wordlists/dirbuster/directory-list-lowercase-2.3-medium.txt
[+] Negative Status codes:   404
[+] User Agent:              gobuster/3.1.0
[+] Timeout:                 10s
===============================================================
2022/10/06 03:06:05 Starting gobuster in directory enumeration mode
===============================================================
/home                 (Status: 302) [Size: 23] [--> /]
/img                  (Status: 301) [Size: 173] [--> /img/]
/assets               (Status: 301) [Size: 179] [--> /assets/]
/portal               (Status: 200) [Size: 1409]              
/css                  (Status: 301) [Size: 173] [--> /css/]   
/js                   (Status: 301) [Size: 171] [--> /js/]    
/logout               (Status: 302) [Size: 29] [--> /portal]  
Progress: 6518 / 207644 (3.14%) 