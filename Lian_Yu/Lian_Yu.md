Lian_Yu.doc
==============================
nmap Results :
--------------------
nmap -sC -sV 10.10.113.72               
Starting Nmap 7.92 ( https://nmap.org ) at 2022-09-14 09:05 EDT
Nmap scan report for 10.10.113.72
Host is up (0.10s latency).
Not shown: 996 closed tcp ports (conn-refused)
PORT    STATE SERVICE VERSION
21/tcp  open  ftp     vsftpd 3.0.2
22/tcp  open  ssh     OpenSSH 6.7p1 Debian 5+deb8u8 (protocol 2.0)
| ssh-hostkey: 
|   1024 56:50:bd:11:ef:d4:ac:56:32:c3:ee:73:3e:de:87:f4 (DSA)
|   2048 39:6f:3a:9c:b6:2d:ad:0c:d8:6d:be:77:13:07:25:d6 (RSA)
|   256 a6:69:96:d7:6d:61:27:96:7e:bb:9f:83:60:1b:52:12 (ECDSA)
|_  256 3f:43:76:75:a8:5a:a6:cd:33:b0:66:42:04:91:fe:a0 (ED25519)
80/tcp  open  http    Apache httpd
|_http-title: Purgatory
|_http-server-header: Apache
111/tcp open  rpcbind 2-4 (RPC #100000)
| rpcinfo: 
|   program version    port/proto  service
|   100000  2,3,4        111/tcp   rpcbind
|   100000  2,3,4        111/udp   rpcbind
|   100000  3,4          111/tcp6  rpcbind
|   100000  3,4          111/udp6  rpcbind
|   100024  1          35153/tcp   status
|   100024  1          35395/tcp6  status
|   100024  1          55855/udp6  status
|_  100024  1          60968/udp   status
Service Info: OSs: Unix, Linux; CPE: cpe:/o:linux:linux_kernel


GoBuster Results:
---------------------------
gobuster dir -u http://10.10.113.72 -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
===============================================================
Gobuster v3.1.0
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     http://10.10.113.72
[+] Method:                  GET
[+] Threads:                 10
[+] Wordlist:                /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
[+] Negative Status codes:   404
[+] User Agent:              gobuster/3.1.0
[+] Timeout:                 10s
===============================================================
2022/09/14 09:07:34 Starting gobuster in directory enumeration mode
===============================================================
/island               (Status: 301) [Size: 235] [--> http://10.10.113.72/island/]
Progress: 18401 / 220561 (8.34%)                                                ^C
[!] Keyboard interrupt detected, terminating.
                                                                                 
===============================================================
2022/09/14 09:10:31 Finished
===============================================================

Gobuster Results (2):
-----------------------------
gobuster dir -u http://10.10.113.72/island -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
===============================================================
Gobuster v3.1.0
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     http://10.10.113.72/island
[+] Method:                  GET
[+] Threads:                 10
[+] Wordlist:                /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
[+] Negative Status codes:   404
[+] User Agent:              gobuster/3.1.0
[+] Timeout:                 10s
===============================================================
2022/09/14 09:11:13 Starting gobuster in directory enumeration mode
===============================================================
/2100                 (Status: 301) [Size: 240] [--> http://10.10.113.72/island/2100/]
Progress: 9982 / 220561 (4.53%)                                                      ^C
[!] Keyboard interrupt detected, terminating.
                                                                                      
===============================================================
2022/09/14 09:12:49 Finished
===============================================================

Gobuster Results (3):
-----------------------------
gobuster dir -u http://10.10.113.72/island/2100 -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -x .ticket 
===============================================================
Gobuster v3.1.0
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     http://10.10.113.72/island/2100
[+] Method:                  GET
[+] Threads:                 10
[+] Wordlist:                /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
[+] Negative Status codes:   404
[+] User Agent:              gobuster/3.1.0
[+] Extensions:              ticket
[+] Timeout:                 10s
===============================================================
2022/09/14 09:32:59 Starting gobuster in directory enumeration mode
===============================================================
/green_arrow.ticket   (Status: 200) [Size: 71]
Progress: 30526 / 441122 (6.92%)  

Directories Found!:
-----------------------------
/island
/2100
/green_arrow.ticket

FTP Password Found and User (Apperently...)
-----------------------------
vigilante:!#th3h00d
slade:M3tahuman

Code For Lian_Yu :  vigilante
---------------------------------


Flags!!!:
----------------------------------
User Flag : THM{P30P7E_K33P_53CRET5__C0MPUT3R5_D0N'T}

Root Flag : THM{MY_W0RD_I5_MY_B0ND_IF_I_ACC3PT_YOUR_CONTRACT_THEN_IT_WILL_BE_COMPL3TED_OR_I'LL_BE_D34D}