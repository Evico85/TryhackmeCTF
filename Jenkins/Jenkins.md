Jenkins.doc
==================

name : Eviyatar Cohen

Date : 29/9/2022

IP = 10.10.202.86

------------------------------------------------


Nmap Results:
=================

nmap -sC -sV 10.10.202.86 
Starting Nmap 7.92 ( https://nmap.org ) at 2022-09-29 05:38 EDT
Nmap scan report for 10.10.202.86
Host is up (0.085s latency).
Not shown: 997 filtered tcp ports (no-response)
PORT     STATE SERVICE            VERSION
80/tcp   open  http               Microsoft IIS httpd 7.5
|_http-title: Site doesn't have a title (text/html).
| http-methods: 
|_  Potentially risky methods: TRACE
|_http-server-header: Microsoft-IIS/7.5
3389/tcp open  ssl/ms-wbt-server?
| rdp-ntlm-info: 
|   Target_Name: ALFRED
|   NetBIOS_Domain_Name: ALFRED
|   NetBIOS_Computer_Name: ALFRED
|   DNS_Domain_Name: alfred
|   DNS_Computer_Name: alfred
|   Product_Version: 6.1.7601
|_  System_Time: 2022-09-29T09:39:53+00:00
|_ssl-date: 2022-09-29T09:39:55+00:00; +1s from scanner time.
| ssl-cert: Subject: commonName=alfred
| Not valid before: 2022-09-28T09:35:14
|_Not valid after:  2023-03-30T09:35:14
8080/tcp open  http               Jetty 9.4.z-SNAPSHOT
| http-robots.txt: 1 disallowed entry 
|_/
|_http-title: Site doesn't have a title (text/html;charset=utf-8).
|_http-server-header: Jetty(9.4.z-SNAPSHOT)
Service Info: OS: Windows; CPE: cpe:/o:microsoft:windows

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 102.55 seconds

=================================================================

Log in the website Using Default Admin:Admin
-----------------------------------------------

inside the website go to Manage Jenkins > Script Console and there i upload reverse shell
-------------------------------------------------

=======
Flags:
=======

User.txt : 79007a09481963edf2e1321abd9ae2a0

Root.txt : dff0f748678f280250f25a45b8046b4a




