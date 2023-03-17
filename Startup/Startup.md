Startup.doc
==============

name : Eviyatar Cohen

Date : 1/10/2022

IP = 10.10.134.253

----------------------------------------------------

Nmap Results:
===============
nmap -sC -sV 10.10.134.253
Starting Nmap 7.92 ( https://nmap.org ) at 2022-10-01 10:18 EDT
Nmap scan report for 10.10.134.253
Host is up (0.081s latency).
Not shown: 997 closed tcp ports (conn-refused)
PORT   STATE SERVICE VERSION
21/tcp open  ftp     vsftpd 3.0.3
| ftp-anon: Anonymous FTP login allowed (FTP code 230)
| drwxrwxrwx    2 65534    65534        4096 Nov 12  2020 ftp [NSE: writeable]
| -rw-r--r--    1 0        0          251631 Nov 12  2020 important.jpg
|_-rw-r--r--    1 0        0             208 Nov 12  2020 notice.txt
| ftp-syst: 
|   STAT: 
| FTP server status:
|      Connected to 10.18.26.95
|      Logged in as ftp
|      TYPE: ASCII
|      No session bandwidth limit
|      Session timeout in seconds is 300
|      Control connection is plain text
|      Data connections will be plain text
|      At session startup, client count was 4
|      vsFTPd 3.0.3 - secure, fast, stable
|_End of status
22/tcp open  ssh     OpenSSH 7.2p2 Ubuntu 4ubuntu2.10 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 b9:a6:0b:84:1d:22:01:a4:01:30:48:43:61:2b:ab:94 (RSA)
|   256 ec:13:25:8c:18:20:36:e6:ce:91:0e:16:26:eb:a2:be (ECDSA)
|_  256 a2:ff:2a:72:81:aa:a2:9f:55:a4:dc:92:23:e6:b4:3f (ED25519)
80/tcp open  http    Apache httpd 2.4.18 ((Ubuntu))
|_http-title: Maintenance
|_http-server-header: Apache/2.4.18 (Ubuntu)
Service Info: OSs: Unix, Linux; CPE: cpe:/o:linux:linux_kernel

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 16.24 seconds

Potential Users:
==================
vagrant
lennie:c4ntg3t3n0ughsp1c3

UseFull Paths:
==============
/home/vagrant
/usr/share/gcc-5
/usr/share/doc/openssh-client/examples/sshd_config                                               
AuthorizedKeysFile      .ssh/authorized_keys
Subsystem       sftp    /usr/lib/openssh/sftp-server
passwd file: /etc/pam.d/passwd                                                                   
passwd file: /etc/passwd

inside the shell i Found a pcap file in incidents and there found password for lennie:
---------------------------------------------------
lennie:c4ntg3t3n0ughsp1c3

After it i looked in the print.sh script and changed it to give me root shell
-------------------------------------------------------------------------------

Flags Found!!
=================

User Flag : THM{03ce3d619b80ccbfb3b7fc81e46c0e79}

Root Flag : THM{f963aaa6a430f210222158ae15c3d76d}




