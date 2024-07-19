# Passive Information Gathering
- In passive reconnaissance, you rely on publicly available knowledge.

# To gather Passive Information
1. Whois: a request and response protocol a who is server listen on board for three or four incoming requests.

- The domain registrar is responsible for maintaining the WHO is records for the domain names.

- Domain registrar is responsible for maintaining the WHOIS record.

- Eg: whois 209.11.133.123 --> can see the net range is present to me between these two IP addresses. You can actually check any IP address in order to further gather different information about this particular victim. We can see the NetName, organization name, registration date, updated date,email id of the oraganization.

- Attacker can make use of this mail id so as to do phishing attack.
 
- Eg: whois teslamotors.com --> can get plenty of informations

2. nslookup and dig: Find the IP address of a domain name using nslookup (Name Server Look Up).

- Eg: nslookup solarcity.com --> IP address of the victim machine can be seen.

- nslookup -types=ns solarcity --->  IP address of your machine. Need to get nameserver of the target machine.

- nslookup -type=soa solarcity.com --> to get start of 30 records.

- nslookup -type=mx solarcity.com --> to find mail server of your target machine
