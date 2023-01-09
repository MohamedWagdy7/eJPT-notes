# eJPT-notes
## 1. Introduction
## 2. Networking


## 9. Information Gathering
### Open source inteligence
1. using **LinkedIn**
2. using **CrunchBase**
3. **whois** database. use it on linux by `whois` cmd.
4. navigate the website of the target.
5. guess the the email pattern:
   1. name.surname@company.com
   2. surname.name@company.com
   3. [first letter of the name]surname@company.com , You can try to:
      - Collect a reasonable number of employee data (name/surname)
      - Try to construct a few possible email formats and apply them to each name/surname pair
      - Try to send an email that does not alert potential victims (e.g., do not put a „phishing test” in subject, but choose something tricky like try to pretend it is just an advertisement)
### subdomain enumration
#### Passive enumration (without interact the target):
1. site: company.com in the search
2. dnsdumpster.com , Bing , Virustotal
3. sublist3r ( be aware when using it )
## 10. Footprinting and Scanning
### Mapping network
1. Get all hosts.
2. ping sweep
   - fping
   - nmap
3. os fingerprint (nmap online and p0f offline)
4. port scanning (nmap - masscan)
## 11. vulnerability assessment
1. OpenVAS
2. nessus
## 12. Web Apps attacks
### manually fingerprint
#### banner grabbing
1. netcat(http)
2. openssl(https)
3. httprint (more detailed)
