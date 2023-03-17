Mind_Games.doc
---------------------

Name : Eviyatar Cohen

Date : 26/9/2022

IP = 
--------------------------------------------

#Nmap Results:
=================
nmap -sC -sV 10.10.112.247
Starting Nmap 7.92 ( https://nmap.org ) at 2022-09-26 10:34 EDT
Nmap scan report for 10.10.112.247
Host is up (0.095s latency).
Not shown: 998 closed tcp ports (conn-refused)
PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 7.6p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 24:4f:06:26:0e:d3:7c:b8:18:42:40:12:7a:9e:3b:71 (RSA)
|   256 5c:2b:3c:56:fd:60:2f:f7:28:34:47:55:d6:f8:8d:c1 (ECDSA)
|_  256 da:16:8b:14:aa:58:0e:e1:74:85:6f:af:bf:6b:8d:58 (ED25519)
80/tcp open  http    Golang net/http server (Go-IPFS json-rpc or InfluxDB API)
|_http-title: Mindgames.
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 83.41 seconds


Using BrainFuck Python3 Script to Get Revrse Shell!!

User.txt : thm{411f7d38247ff441ce4e134b459b6268}

After it i created c File for running before server script and got root shell!!

Root.txt : thm{1974a617cc84c5b51411c283544ee254}