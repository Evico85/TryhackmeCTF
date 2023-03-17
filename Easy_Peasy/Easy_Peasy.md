Easy_Peasy.doc
------------------

name: Eviyatar Cohen

Date : 19.10.2022

IP=
---------------------------------------------

Nmap Results:
===============
nmap -p- -T4 -A 10.10.233.205
Starting Nmap 7.92 ( https://nmap.org ) at 2022-10-19 03:14 EDT
Nmap scan report for 10.10.233.205
Host is up (0.091s latency).
Not shown: 65532 closed tcp ports (conn-refused)
PORT      STATE SERVICE VERSION
80/tcp    open  http    nginx 1.16.1
| http-robots.txt: 1 disallowed entry 
|_/
|_http-title: Welcome to nginx!
|_http-server-header: nginx/1.16.1
6498/tcp  open  ssh     OpenSSH 7.6p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 30:4a:2b:22:ac:d9:56:09:f2:da:12:20:57:f4:6c:d4 (RSA)
|   256 bf:86:c9:c7:b7:ef:8c:8b:b9:94:ae:01:88:c0:85:4d (ECDSA)
|_  256 a1:72:ef:6c:81:29:13:ef:5a:6c:24:03:4c:fe:3d:0b (ED25519)
65524/tcp open  http    Apache httpd 2.4.43 ((Ubuntu))
| http-robots.txt: 1 disallowed entry 
|_/
|_http-title: Apache2 Debian Default Page: It works
|_http-server-header: Apache/2.4.43 (Ubuntu)
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 109.85 seconds

----------------------------------------------------------------

Potential Creds:
==================
ba....:ObsJmP173N2X6dOrAgEAL0Vu :(Decode To -/n0th1ng3ls3m4tt3r)

----------------------------------------------------------------

Robots.txt
============
User-Agent:*
Disallow:/
Robots Not Allowed
User-Agent:a18672860d0510e5ab6699730763b250 :(flag{1m_s3c0nd_fl4g})
Allow:/
This Flag Can Enter But Only This Flag No More Exceptions

---------------------------------------------------------------

Another Hash To Crack in /n0th1ng3ls3m4tt3r :
===============================================
940d71e8655ac41efb5f8ab850668505b86dd64186a66e57d1483e7f5fe6fd81

Using John i Got This Password:
=================================
mypasswordforthatjob

----------------------------------------------------------------

After Running GoBuster i Found /hidden Directory and then i run it again with this directory and found /whatever and inside was this hash:
==============================================================
ZmxhZ3tmMXJzN19mbDRnfQ== : flag{f1rs7_fl4g}

----------------------------------------------------------------

Using the password mypasswordforthatjob with steghide on the binary jpg image i found secrettext.txt file that has inside Crdentials:
=============================================================
username:boring
password:iconvertedmypasswordtobinary

Login SSH To Connect:
-----------------------
Found User.txt : synt{a0jvgf33zfa0ez4y}

Convert it To Rot and Got Flag!!
=================================
flag{n0wits33msn0rm4l}

after it i Used The Script that i have premossions to it to give myself a netcat shell with root by inject command to the script that run in crontab:
==============================================================

Root Flag:flag{63a9f0ea7bb98050796b649e85481845}

----------------------------------------------------------------