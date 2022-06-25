# Subdomain-Enumeration

# Brief 
  We will explore three different subdomain enumeration methods: Brute Force, OSINT (Open-Source Intelligence) and Virtual Host.

# OSINT - SSL/TLS Certificates 
  When an SSL/TLS (Secure Sockets Layer/Transport Layer Security) certificate is created for a domain by a CA (Certificate Authority).
  Online Tools: https://crt.sh/

# OSINT - Search Engines 
  Go to google and use the search term -site:www.tryhackme.com  site:*.tryhackme.com, which should reveal a subdomain for tryhackme.com.
  
# DNS Bruteforce 
  Example: dnsrecon -t brt -d acmeitsupport.thm
  
# OSINT - Sublist3r
  First Install Sublist3r from google then used it.
  Example: python3 sublist3r.py -d tryhackme.com
  
# Virtual Hosts 
  Example1: ffuf -w /usr/share/wordlists/SecLists/Discovery/DNS/namelist.txt -H "Host: FUZZ.acmeitsupport.thm" -u http://10.10.127.142
  
  Example2: ffuf -w /usr/share/wordlists/SecLists/Discovery/DNS/namelist.txt -H "Host: FUZZ.acmeitsupport.thm" -u http://10.10.127.142 -fs {size}
  This command has a similar syntax to the first apart from the -fs switch, which tells ffuf to ignore any results that are of the specified size.
