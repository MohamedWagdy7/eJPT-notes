# Malware
**Malware** ,short for **Mal**icious soft**ware**, is any software used to misuse computer systems with the intent to:
1. Cause Denial of Service (DoS)
2. Spy on user activity
3. Get unauthorized control over one or more computer systems
## Malware Classifications according to their behaviour
### 1. Virus
a small piece of code that copy itself from computer to another without authorization of the owner of the infected machine. it usually copy itself in critical places in the harddisk.
### 2. Trojan Horses
a malware came embedded in a harmless file such as document , PDFs and executable files. when the user open that file it became a victim.
the most used trojan horses are the backdoors which give an attacker shell on the victim machine.
### 3. Backdoors
is a malware made by two components: backdoor server(on victim machine) and backdoor client(on your machine) after install and connect to the backdoor sever you will have the full control on the victim machine.
**NetBus** and **subseven** are the most famous oldschool backdoors.
backdoor will be blocked if an administrator configures the network firewall to block connections from the internet to internal machines,then the reverse backdoor is the solution
### 4. Rootkit
is a malware designed to hide itself from users and antivirus programes It lets an attacker maintain privileged access to the victim machine without being noticed.
### 5. Bootkit
are rootkits which circumvent OS protection by executing before the os and get full control over it.
### 6. Adware
is annoying software that shows advertisements to computer users.
### 7. Spyware
is software used to collect information about the machine ( The OS installed,Visited websites, and Passwords)
### 8. Greyware
it can be spyware , adware or both,
### 9. Dialer
software ,installed on smartphones, try to make dial-ups from victims' mobiles and take money. 
### 10. Key-logger
is a software record all keystrokes on victim's machine.
#### Key-logger:
1. records all keystrokes.
2. record the window where the user is tayping.
3. save the records in log file and send it to the attacker server so it subjected to the same restrictions of the backdoor.
#### there are also:
##### 1. Hardware Key-logger
a small device installed between the keyboard and the computer.
##### 2. Rootkit Key-logger
working at the kernel level by taking all OS APIs to the logs file.
The keylogger logs the key pressed and then it calls the original function of the operating system.
### 11. Bots
are small pieces of software that get installed on millions of Internet-connected machines to perform Denial of Service.
These Bots are commanded remotely by a so-called Command and Control server. The C&C server can instruct thousands or even millions of bots to perform a given operation simultaneously.
### 12. Ransomware
software that encrypts a computer or smartphone files with a secret key, then asks the victim for a ransom to give them the content back.
### 13. Data-Stealing Malware
a software built for stealing data. it's tailored for a specifiec environment.
### 14. Worm
spread over the network by exploiting system vulnerabilities.
# Password Attacks
passwords are stored in database in **one way encrypted**( Hash ) form to protect the from internal users.
**Password Cracking** is the proccess of recover password from its hash.
## Password Cracking ways
### 1. Brute Force Attack
is the way of trying each possible password until reach the right one.
it start cycling over lowercase , uppercase , number, then symbols until reach the password
If the password is longer than two characters, then the algorithm moves to three characters long, then four and so on until a valid password
#### brute force tools
##### 1. John the Ripper ( it's so fast because using the mean of parallelization)
--> After attack we stole the password files of Linux machine `/etc/passwd/` and `/etc/shadow/`
this tool need the usernames and the passwords to be in the same file so we need to use unshadow utility `unshadow usernames passwd > crackme`
### 2. Dictionary attacks
try each password in the most common passwords list.
use `-rules` to mangle **john**
you can find repo of most common password by **OWASP** [here](https://github.com/danielmiessler/SecLists/tree/master/Passwords) or use `apt-get install seclists` if you use Linux.
you can reduce the time of cracking passwords by using **Rainbow Tables**.
**ophcrack** is a great tool to do rainbow table on windows devices.
# Buffer overflow
- forcing a piece of software or a routine of the operating system to behave differently from what the author of it design.
- it lead to:
    - rempte code execution
    - Denial of Service
    - Bypass system security
    - previlige escalation
- **Buffer** is an area in the RAM (Stored in the stack) have finite size and reserved for temporary data such as:
    - server banner
    - user input
- if the programmer doesn't limit the buffer,an attacker can take control over program execution flow
