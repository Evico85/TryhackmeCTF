Blue Mechine :

------------------------

$IP = 10.10.129.185

---------------------------

# Tasks :

#1 How many ports are open with a port number under 1000?

------
3
------

#2  What is this machine vulnerable to? 

-----------
ms17-010
-----------

#3 

Find the exploitation code we will run against the machine. What is the full path of the code? 

-----
exploit/windows/smb/ms17_010_eternalblue
-----

#4 

Show options and set the one required value. What is the name of this value? 

-----
RHOSTS
-----

#5 Research online how to convert a shell to meterpreter shell in metasploit. What is the name of the post module we will use?

-----
post/multi/manage/shell_to_meterpreter
-----

#6 

Select this (use MODULE_PATH). Show options, what option are we required to change?

------------
SESSION
------------

#7 What is the name of the non-default user? 

-----
jon
-----

#8 Copy this password hash to a file and research how to crack it. What is the cracked password?

----------
alqfna22
----------

#Flags :

flag1 = flag{access_the_machine}

flag2 = flag{sam_database_elevated_access}

flag3 = flag{admin_documents_can_be_valuable}









