ignite.doc
--------------------

Nmap Results:
--------------------
nmap -sC -sV 10.10.39.209                
Starting Nmap 7.92 ( https://nmap.org ) at 2022-09-16 10:53 EDT
Nmap scan report for 10.10.39.209
Host is up (0.090s latency).
Not shown: 999 closed tcp ports (conn-refused)
PORT   STATE SERVICE VERSION
80/tcp open  http    Apache httpd 2.4.18 ((Ubuntu))
|_http-title: Welcome to FUEL CMS
| http-robots.txt: 1 disallowed entry 
|_/fuel/
|_http-server-header: Apache/2.4.18 (Ubuntu)

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 28.10 seconds

Gobuster Results:
--------------------
gobuster dir -u http://10.10.39.209 -w /usr/share/wordlists/dirb/big.txt
===============================================================
Gobuster v3.1.0
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     http://10.10.39.209
[+] Method:                  GET
[+] Threads:                 10
[+] Wordlist:                /usr/share/wordlists/dirb/big.txt
[+] Negative Status codes:   404
[+] User Agent:              gobuster/3.1.0
[+] Timeout:                 10s
===============================================================
2022/09/16 10:54:48 Starting gobuster in directory enumeration mode
===============================================================
/!res                 (Status: 400) [Size: 1134]
/!                    (Status: 400) [Size: 1134]
/!images              (Status: 400) [Size: 1134]
/!textove_diskuse     (Status: 400) [Size: 1134]
/!ut                  (Status: 400) [Size: 1134]
/!backup              (Status: 400) [Size: 1134]
/!_archives           (Status: 400) [Size: 1134]
/!_images             (Status: 400) [Size: 1134]
/.htaccess            (Status: 403) [Size: 296] 
/.htpasswd            (Status: 403) [Size: 296] 
/0                    (Status: 200) [Size: 16595]
/@                    (Status: 400) [Size: 1134] 
/]                    (Status: 400) [Size: 1134] 
/[                    (Status: 400) [Size: 1134] 
/asdfjkl;             (Status: 400) [Size: 1134] 
/assets               (Status: 301) [Size: 313] [--> http://10.10.39.209/assets/]
/fixed!               (Status: 400) [Size: 1134]                                 
/home                 (Status: 200) [Size: 16595]                                
/index                (Status: 200) [Size: 16595]                                
/lost+found           (Status: 400) [Size: 1134]                                 
/offline              (Status: 200) [Size: 70]                                   
/plain]               (Status: 400) [Size: 1134]                                 
/quote]               (Status: 400) [Size: 1134]                                 
/robots.txt           (Status: 200) [Size: 30]                                   
/server-status        (Status: 403) [Size: 300]                                  
/sitemap_xml          (Status: 200) [Size: 398]                                  
                                                                                 
===============================================================
2022/09/16 11:00:20 Finished
===============================================================


==============================================
Site is Vunrablue To CVE-2018-16763 !!
==============================================


Used Fuel-1.4.1-RCE-Updated To get a Shell
-------------------------------------------------

Flags Found!!
====================
User Flag : 6470e394cbf6dab6a91682cc8585059b

Root Flag : b9bbcb33e11b80be759c4e844862482d

Root Password was at This path:
---------------------------------------
/var/www/html/fuel/application/config/database.php

