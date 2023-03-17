Chocolate_Factory.doc
--------------------------

name : Eviyatar Cohen

Date : 10.10.2022

IP= 10.10.171.200
------------------------------------------

Nmap Results:
==============
nmap -sC -sV 10.10.171.200
Starting Nmap 7.92 ( https://nmap.org ) at 2022-10-10 06:09 EDT
Stats: 0:01:47 elapsed; 0 hosts completed (1 up), 1 undergoing Service Scan
Service scan Timing: About 27.27% done; ETC: 06:16 (0:04:27 remaining)
Stats: 0:03:50 elapsed; 0 hosts completed (1 up), 1 undergoing Script Scan
NSE Timing: About 99.27% done; ETC: 06:13 (0:00:00 remaining)
Stats: 0:04:54 elapsed; 0 hosts completed (1 up), 1 undergoing Script Scan
NSE Timing: About 96.74% done; ETC: 06:14 (0:00:01 remaining)
Stats: 0:05:07 elapsed; 0 hosts completed (1 up), 1 undergoing Script Scan
NSE Timing: About 98.91% done; ETC: 06:14 (0:00:00 remaining)
Nmap scan report for 10.10.171.200
Host is up (0.089s latency).
Not shown: 989 closed tcp ports (conn-refused)
PORT    STATE SERVICE    VERSION
21/tcp  open  ftp        vsftpd 3.0.3
| ftp-anon: Anonymous FTP login allowed (FTP code 230)
|_-rw-rw-r--    1 1000     1000       208838 Sep 30  2020 gum_room.jpg
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
|      At session startup, client count was 1
|      vsFTPd 3.0.3 - secure, fast, stable
|_End of status
|_auth-owners: ERROR: Script execution failed (use -d to debug)
22/tcp  open  ssh        OpenSSH 7.6p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
|_auth-owners: ERROR: Script execution failed (use -d to debug)
| ssh-hostkey: 
|   2048 16:31:bb:b5:1f:cc:cc:12:14:8f:f0:d8:33:b0:08:9b (RSA)
|   256 e7:1f:c9:db:3e:aa:44:b6:72:10:3c:ee:db:1d:33:90 (ECDSA)
|_  256 b4:45:02:b6:24:8e:a9:06:5f:6c:79:44:8a:06:55:5e (ED25519)
80/tcp  open  http       Apache httpd 2.4.29 ((Ubuntu))
|_auth-owners: ERROR: Script execution failed (use -d to debug)
|_http-server-header: Apache/2.4.29 (Ubuntu)
|_http-title: Site doesn't have a title (text/html).
100/tcp open  newacct?
|_auth-owners: ERROR: Script execution failed (use -d to debug)
| fingerprint-strings: 
|   HTTPOptions, SSLSessionReq: 
|     "Welcome to chocolate room!! 
|     small hint from Mr.Wonka : Look somewhere else, its not here! ;) 
|_    hope you wont drown Augustus"
106/tcp open  pop3pw?
| fingerprint-strings: 
|   GenericLines, NULL: 
|     "Welcome to chocolate room!! 
|     small hint from Mr.Wonka : Look somewhere else, its not here! ;) 
|_    hope you wont drown Augustus"
|_auth-owners: ERROR: Script execution failed (use -d to debug)
109/tcp open  pop2?
| fingerprint-strings: 
|   GenericLines, NULL: 
|     "Welcome to chocolate room!! 
|     small hint from Mr.Wonka : Look somewhere else, its not here! ;) 
|_    hope you wont drown Augustus"
|_auth-owners: ERROR: Script execution failed (use -d to debug)
110/tcp open  pop3?
|_auth-owners: ERROR: Script execution failed (use -d to debug)
|_tls-alpn: ERROR: Script execution failed (use -d to debug)
|_ssl-cert: ERROR: Script execution failed (use -d to debug)
|_tls-nextprotoneg: ERROR: Script execution failed (use -d to debug)
|_ssl-date: ERROR: Script execution failed (use -d to debug)
| fingerprint-strings: 
|   GenericLines, NULL: 
|     "Welcome to chocolate room!! 
|     small hint from Mr.Wonka : Look somewhere else, its not here! ;) 
|_    hope you wont drown Augustus"
111/tcp open  rpcbind?
| fingerprint-strings: 
|   NULL, RPCCheck: 
|     "Welcome to chocolate room!! 
|     small hint from Mr.Wonka : Look somewhere else, its not here! ;) 
|_    hope you wont drown Augustus"
|_auth-owners: ERROR: Script execution failed (use -d to debug)
113/tcp open  ident?
| fingerprint-strings: 
|   DNSVersionBindReqTCP, FourOhFourRequest, GenericLines, Help, NULL: 
|_    http://localhost/key_rev_key <- You will find the key here!!!
|_auth-owners: ERROR: Script execution failed (use -d to debug)
119/tcp open  nntp?
|     "Welcome to chocolate room!! 
|     small hint from Mr.Wonka : Look somewhere else, its not here! ;) 
|_    hope you wont drown Augustus"
|_sslv2: ERROR: Script execution failed (use -d to debug)
125/tcp open  locus-map?
| fingerprint-strings: 
|   GenericLines, NULL: 
|     "Welcome to chocolate room!! 
|     small hint from Mr.Wonka : Look somewhere else, its not here! ;) 
|_    hope you wont drown Augustus"
|_auth-owners: ERROR: Script execution failed (use -d to debug)

Potential User:
=================
Charlie:cn7824

inside the ftp was a gum_room.jpg file that has embedded data :
---------------------------------------------------------------

i Took The Hash that was there and cracked it to find the Charlie Password.

inside was the User Flag and the Sudo -l was with vi so i Used GTFOBin to get root shell
----------------------------------------------------------------

=========
Flags!!
=========

User Flag : flag{cd5509042371b34e4826e4838b522d2e}

Root Flag : flag{cec59161d338fef787fcb4e296b42124}
