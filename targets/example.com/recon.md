Reconnaissance was performed ethically for educational purposes.


# Recon Report: mozilla.com
**Date:** `2025-06-22`

## 1. WHOIS Data
```text
Registrar:  MarkMonitor Inc.
Name Server: NS1-240.AKAM.NET
Name Server: NS4-64.AKAM.NET
Name Server: NS5-65.AKAM.NET
Name Server: NS7-66.AKAM.NET
Registry Expiry Date: 2025-10-17T04:00:00Z
```

## 2.DIG  and Host 
![image](https://github.com/user-attachments/assets/0953ff9d-9445-4a1e-a8a0-0ec8cfcf6835)
```text
The result of command:
infoblox1.private.mdc1.mozilla.com. hostmaster.mozilla.com. 2018044520 180 180 1209600 60
Both dig and host gives same result which is dns lookup (detailed) but for faster access and human understing we use host rather than dig but dig is more powerfull.
```

## 3. theHarvester
![image](https://github.com/user-attachments/assets/653c09b2-42da-4c71-89ae-4a151f4a7cdf)
```text
Result:
[*] Target: mozilla.com 

[*] Searching Duckduckgo. 
                                                                                                                                                            
[*] No IPs found.                                                                                                                                           
                                                                                                                                                            
[*] No emails found.                                                                                                                                        
                                                                                                                                                            
[*] No people found.                                                                                                                                        
                                                                                                                                                            
[*] Hosts found: 2                                                                                                                                          
---------------------                                                                                                                                       
2Fstatic.mozilla.com                                                                                                                                        
static.mozilla.com

theHarvester is a powerfull OSINT (Open Source Intelligence) tool to gather Email , Host , IP.
As it shows above two hosts are found of mozilla which is great step  in the reconnaisance step.
```


## 4. Sublist3r and amass enum
```text
Yes as you see above its not Sublister it's Sublist3r which is subdomain enumeration tool to find the subdomains.
```
![image](https://github.com/user-attachments/assets/0c0f27d9-bd99-46c5-bd31-f85b5fe3e924)
```text
The reuslt ?.. Here:
[-] Total Unique Subdomains Found: 12
www.mozilla.com
qsurvey.mozilla.com
firefox-ci-tc.services.mozilla.com
location.services.mozilla.com
phabricator.services.mozilla.com
push.services.mozilla.com
firefox.settings.services.mozilla.com
shavar.services.mozilla.com
status.services.mozilla.com
stubdownloader.services.mozilla.com
cdn.stubdownloader.services.mozilla.com
tls-observatory.services.mozilla.com

As you see the command gives us the sub-domains we can check for vulnerability which is not that well managed compared to main domains in many organization
```
![image](https://github.com/user-attachments/assets/afed316a-03c9-48d0-931f-6bb9a21446be)
```
Both  of amass enum and Sublist3r are used  for subdomain enumeration as shown above
```

## 5. digging sub-domains using dig +short
![image](https://github.com/user-attachments/assets/e2333386-0edd-4a67-a247-b92d4a2e0a4e)
```text
Output:

shavar.prod.mozaws.net.
52.24.74.7
54.185.134.10
35.167.115.132

We got the Ip of the sub-domain  with this procedure.
```

## 6. Shodan
``` test
We can use shodan website or shodan command to know about  mozilla more.
Use shodan.io for this procedure and search for mozilla.com in it.
```

## 7. nmap
![image](https://github.com/user-attachments/assets/b0952f5e-b29c-455f-a908-be992aa973db)
``` test
I did nmap test on the address of the mozilla.com
PORT    STATE    SERVICE
514/tcp filtered shell
The result is above....
```

The following tools were utilized during reconnaissance:

Tool	                Command/Flags	                           Purpose
whois              	whois example.com                   	Domain registration details
sublist3er 	     subfinder -d example.com -o subs.txt    	Subdomain enumeration
theHarvester	theHarvester -d example.com -b all	        Email & host discovery
nmap            	nmap -sV 192.168.1.100	                Port scanning
dig	              dig example.com +short                	DNS resolution
shodan             shodan search host:example.com         Network monitoring






                                       






