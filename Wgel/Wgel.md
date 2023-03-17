Wgel.doc
----------------------

Nmap Results:
----------------------
nmap -sC -sV 10.10.26.243
Starting Nmap 7.92 ( https://nmap.org ) at 2022-09-17 10:13 EDT
Nmap scan report for 10.10.26.243
Host is up (0.11s latency).
Not shown: 998 closed tcp ports (conn-refused)
PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 7.2p2 Ubuntu 4ubuntu2.8 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 94:96:1b:66:80:1b:76:48:68:2d:14:b5:9a:01:aa:aa (RSA)
|   256 18:f7:10:cc:5f:40:f6:cf:92:f8:69:16:e2:48:f4:38 (ECDSA)
|_  256 b9:0b:97:2e:45:9b:f3:2a:4b:11:c7:83:10:33:e0:ce (ED25519)
80/tcp open  http    Apache httpd 2.4.18 ((Ubuntu))
|_http-server-header: Apache/2.4.18 (Ubuntu)
|_http-title: Apache2 Ubuntu Default Page: It works
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 27.09 seconds


Potential Users:
----------------------
Jessie:
Dave:

Gobuster Results:
----------------------
gobuster dir -u http://10.10.26.243/sitemap/ -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
===============================================================
Gobuster v3.1.0
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     http://10.10.26.243/sitemap/
[+] Method:                  GET
[+] Threads:                 10
[+] Wordlist:                /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
[+] Negative Status codes:   404
[+] User Agent:              gobuster/3.1.0
[+] Timeout:                 10s
===============================================================
2022/09/17 10:25:46 Starting gobuster in directory enumeration mode
===============================================================
/images               (Status: 301) [Size: 321] [--> http://10.10.26.243/sitemap/images/]
/css                  (Status: 301) [Size: 318] [--> http://10.10.26.243/sitemap/css/]   
/js                   (Status: 301) [Size: 317] [--> http://10.10.26.243/sitemap/js/]    
/fonts                (Status: 301) [Size: 320] [--> http://10.10.26.243/sitemap/fonts/] 
/sass                 (Status: 301) [Size: 319] [--> http://10.10.26.243/sitemap/sass/]  
                                                                                         
===============================================================
2022/09/17 11:00:11 Finished
===============================================================

Inside the /.ssh Directory was id_rsa file for ssh with jessie:
---------------------------------------------------------------------

After Login i Found User Flag:
------------------------------
057c67131c3d5e42dd5cd3075b198ff6

Now Need To get Root Flag:
------------------------------
Got The Root Flag by using wget to add a file of a flag to the mechime and take the root flag.

b1b968b37519ad1daa6408188649263d