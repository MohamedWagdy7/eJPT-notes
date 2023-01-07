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
