

# Look for acquisitions 

- https://www.crunchbase.com/
- Grab main domain of each acquisition if any and put them in the mind map

# Look for ASNs

- https://bgp.he.net/
- Grab main and acquisitions ASNs and put them in mind map
- run  `amas intel --asn [asn number]`
- this Will give you website roots
- you can also use metabigor or asnlookup (for automated ASNs fetching)

# Reverse WHOIS

- https://www.whoxy.com/
- look for domains with same company name
- You can use a took called domlink to get the domains

# AD Analytics Relationships

- https://builtwith.com/
- Search domain and go to relationship tab
- you can automate this by using getrelationship.py by @M4IIOK

# GOOGLE-FU

- copy the copyright tag from the website and search at google 
- exmaple `"All rights reserved by Capgemini." -www.capgemini.com`

# How to find SUBDomains

- Crawl website with spider tool (OWASP ZAP, gobuster, gospider, hakrawler(js files))
- subdomainizer (finds subdomain, cloud services referenced in js files) from hackrawler
- subscraper (is better if you are just looking for subdomain)

