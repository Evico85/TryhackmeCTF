The_Blob_Blog.doc
------------------------

name : Eviyatar Cohen

Date : 12.10.2022

IP=10.10.142.188
-------------------------------------

Nmap Results:
==============
nmap -sC -sV 10.10.142.188
Starting Nmap 7.92 ( https://nmap.org ) at 2022-10-12 10:51 EDT
Nmap scan report for 10.10.142.188
Host is up (0.087s latency).
Not shown: 998 filtered tcp ports (no-response)
PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 6.6.1p1 Ubuntu 2ubuntu2.13 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   1024 e7:28:a6:33:66:4e:99:9e:8e:ad:2f:1b:49:ec:3e:e8 (DSA)
|   2048 86:fc:ed:ce:46:63:4d:fd:ca:74:b6:50:46:ac:33:0f (RSA)
|   256 e0:cc:05:0a:1b:8f:5e:a8:83:7d:c3:d2:b3:cf:91:ca (ECDSA)
|_  256 80:e3:45:b2:55:e2:11:31:ef:b1:fe:39:a8:90:65:c5 (ED25519)
80/tcp open  http    Apache httpd 2.4.7 ((Ubuntu))
|_http-title: Apache2 Ubuntu Default Page: It works
|_http-server-header: Apache/2.4.7 (Ubuntu)
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 18.21 seconds

------------------------------------------------------------------

Found Strage String and convert it fron base 64 and got this:
----------------------------------------------------------------
+[--->++<]>+.+++[->++++<]>.---.+++++++++.-[->+++++<]>-.++++[->++<]>+.-[->++++<]>.--[->++++<]>-.-[->+++<]>-.--[--->+<]>--.+[---->+<]>+++.[->+++<]>+.-[->+++<]>.-[--->++<]>+.--.-----.[->+++<]>.------------.+[----->+<]>.--[--->+<]>.-[---->+<]>++.++[->+++<]>.++++++++++++.---------.----.+++++++++.----------.--[--->+<]>---.+[---->+<]>+++.[->+++<]>+.+++++++++++++.----------.-[--->+<]>-.++++[->++<]>+.-[->++++<]>.--[->++++<]>-.--------.++++++.---------.--------.-[--->+<]>-.[->+++<]>+.+++++++++++.+++++++++++.-[->+++<]>-.+[--->+<]>+++.------.+[---->+<]>+++.-[--->++<]>+.+++.+.------------.++++++++.-[++>---<]>+.+++++[->+++<]>.-.-[->+++++<]>-.++[-->+++<]>.[--->++<]>--.+++++[->+++<]>.---------.[--->+<]>--.+++++[->+++<]>.++++++.---.[-->+++++<]>+++.+[----->+<]>+.---------.++++.--.+.------.+++++++++++++.+++.+.+[---->+<]>+++.+[->+++<]>+.+++++++++++..+++.+.+[++>---<]>.++[--->++<]>..[->++<]>+.[--->+<]>+.+++++++++++.-[->+++<]>-.+[--->+<]>+++.------.+[---->+<]>+++.-[--->++<]>--.+++++++.++++++.--.++++[->+++<]>.[--->+<]>----.+[---->+<]>+++.[-->+++<]>+.-----.------------.---[->++++<]>.------------.---.+++++++++.-[->+++++<]>-.++[-->+++<]>.-------.------------.---[->++++<]>.------------.---.+++++++++.-[->+++++<]>-.-----[->++<]>-.--[--->++<]>-.

------------------------------------------------------------------

After Convert BrainFuck Again Got this string:
-------------------------------------------------
When I was a kid, my friends and I would always knock on 3 of our neighbors doors.  Always houses 1, then 3, then 5!

==================================================================
 
Also Found This in the Page Source:
====================================
Dang it Bob, why do you always forget your password?
I'll encode for you here so nobody else can figure out what it is: 
HcfP8J54AK4

Potential User:
=================
Bob:cUpC4k3s (The Password Decoded From base 58) (Also Found Another Password : p@55w0rd)

(Also Didnt Work On SSH)
------------------------------------------------------------------

GoBuster Results:
==================
Didnt Found Anything..

used knock tool to knock on 1 3 5 and after it used nmap again..
-----------------------------------------------------------------

Nmap Results (2):
====================
nmap -p- -T4 10.10.142.188
Starting Nmap 7.92 ( https://nmap.org ) at 2022-10-12 11:29 EDT
Warning: 10.10.142.188 giving up on port because retransmission cap hit (6).
Stats: 0:10:25 elapsed; 0 hosts completed (1 up), 1 undergoing Connect Scan
Connect Scan Timing: About 97.82% done; ETC: 11:40 (0:00:14 remaining)
Nmap scan report for 10.10.142.188
Host is up (0.081s latency).
Not shown: 65528 closed tcp ports (conn-refused)
PORT      STATE    SERVICE
21/tcp    open     ftp
22/tcp    open     ssh
80/tcp    open     http
445/tcp   open     microsoft-ds
5355/tcp  filtered llmnr
8080/tcp  open     http-proxy
37295/tcp filtered unknown

Nmap done: 1 IP address (1 host up) scanned in 653.55 seconds

------------------------------------------------------------------

in the Ftp Port i Used the Password cUpC4k3s To Enter:
-------------------------------------------------------
inside was a cool.jped with file inside him so i used Steghide to extract the file and it needed a password so i used p@55w0rd

Content Of The file:
======================
zcv:p1fd3v3amT@55n0pr (bob:d1ff3r3ntP@55w0rd) (Decoded Using Vigenere)
/bobs_safe_for_stuff

Try go the that directory and found this:
==========================================
Remember this next time bob, you need it to get into the blog! I'm taking this down tomorrow, so write it down!
- youmayenter (Key For Vigenere Decode)

After Go To blog Directory That Was On Port 8080 I used Bash one liner to get Reverse Shell and Found There User id_rsa

Try Login with SSH but didnt work... :(
=========================================

I Found The File blogFeedback and play with it until i found the code 6 5 4 3 2 1 that gave me shell to bobloblaw!!
==============================================================

Flags!!
========

User Flag: THM{C0NGR4t$_g3++ing_this_fur}
 
Root Flag: THM{G00D_J0B_G3++1NG+H3R3!}

To Find Root Flag I modified the .c file to give me revrse shell to root and there i found the root.txt file.
