Hacker_Vs_Hacker.doc
--------------------------

name : Eviyatar Cohen

Date : 7.10.2022

IP=10.10.195.43
----------------------------------------

Nmap Results:
===============
nmap -sC -sV 10.10.195.43 
Starting Nmap 7.92 ( https://nmap.org ) at 2022-10-07 08:31 EDT
Nmap scan report for 10.10.195.43
Host is up (0.086s latency).
Not shown: 998 closed tcp ports (conn-refused)
PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 8.2p1 Ubuntu 4ubuntu0.4 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   3072 9f:a6:01:53:92:3a:1d:ba:d7:18:18:5c:0d:8e:92:2c (RSA)
|   256 4b:60:dc:fb:92:a8:6f:fc:74:53:64:c1:8c:bd:de:7c (ECDSA)
|_  256 83:d4:9c:d0:90:36:ce:83:f7:c7:53:30:28:df:c3:d5 (ED25519)
80/tcp open  http    Apache httpd 2.4.41 ((Ubuntu))
|_http-server-header: Apache/2.4.41 (Ubuntu)
|_http-title: RecruitSec: Industry Leading Infosec Recruitment
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 12.23 seconds
==================================================================

in the website i found RCE in the /cvs directory which leads me to upload a shell.pdf.php file that aloows me to get a shell to the website

after it inside i found the first flag:
-----------------------------------------
thm{af7e46b68081d4025c5ce10851430617}

inside lachlan user home folder the bash history was not deleted so i cat the file and found this..
----------------------------------------------------------------
vi /etc/cron.d/persistence
echo -e "dHY5pzmNYoETv7SUaY\nthisistheway123\nthisistheway123" | passwd
ls -sf /dev/null /home/lachlan/.bash_history

The echo was the password for the lachlan user but i couldnt enter the user with ssh so i used the switch -T and it gave me a connection to the user and from there i used the cron job of pkill to create reverse shell to root user via the cron tabs.

==================================================================

Root Flag:
===========
thm{7b708e5224f666d3562647816ee2a1d4}