---
aliases: 
tags:
  - domain
created: 2024-07-10T21:17
updated: 2024-07-22T17:21
---
---
# Key Info

## Host
> Useful Resources: [DIT](https://cipher387.github.io/domain_investigation_toolbox/ip.html), [Censys](https://search.censys.io/), [Shodan](https://www.shodan.io/), [DNSdumpster](https://dnsdumpster.com/)

- Current Host IP: 
	- Host Owner: 
	- Host Location: 
- Historical Host IPs: 

| IP Address | Location | IP Address Owner | Last seen on this IP |
| ---------- | -------- | ---------------- | -------------------- |
|            |          |                  |                      |
|            |          |                  |                      |


- ASN: 
- Traceroute: 
```

```

---
## Domain
> Useful Resources: 
> 1. https://viewdns.info/
> 2. https://dnslytics.com/
> 3. https://who.is/
> 4. https://dnsdumpster.com/

### Enumeration & Connections
> **Description**: describe the main functionalities of the website.

- Web Layer: 
- Top Level Domain: 
- Domain Creation Date: 
- Sub-Domains: 
- Directories / Sub-Pages: 
- Other Related Domains:
- Similar Domains: 
### DNS Records
- [A](https://www.cloudflare.com/learning/dns/dns-records/dns-a-record/) Records (IPv4): 
- [AAAA](https://www.cloudflare.com/learning/dns/dns-records/dns-aaaa-record/) Records (IPv6): 
- [CNAME](https://www.cloudflare.com/learning/dns/dns-records/dns-cname-record/) Records (domain): 
- [NS](https://www.cloudflare.com/learning/dns/dns-records/dns-ns-record/) Records (domain): 
- [MX](https://www.cloudflare.com/learning/dns/dns-records/dns-mx-record/) Records (domain): 
- [SOA](https://www.cloudflare.com/learning/dns/dns-records/dns-soa-record/): 
	- Current Zone Serial Number: 
- [TXT](https://www.cloudflare.com/learning/dns/dns-records/dns-txt-record/) Records: 

### Ownership & Contact Details
- Domain Owner (person / org): 
	- Name: 
	- Physical Address: 
	- Email: 
	- Phone: 
- Administrative Contact: 
	- Name: 
	- Physical Address: 
	- Email: 
	- Phone: 
- Abuse Contact: 
	- Name: 
	- Physical Address: 
	- Email: 
	- Phone: 
- Other Contacts: 
	- Name: 
	- Address: 
	- Phone: 
	- Email: 

### Files & Structure
> Useful Resource: https://well-known.dev/ or locate with `resource:security.txt`.

- /trust.txt: 
- /robots.txt: 
- /security.txt: 
- /ads.txt: 
- /app-ads.txt: 
- /assetlinks.json: 
- /gpc.json: 
- /nodeinfo: 
- /openidconfiguration:  

- PDF files: 
- XML files:
- CSV files: 
- Other files: 

## Certificates
- [TLS](https://testtls.com/)/[SSL](https://www.ssl.com/ssl-certificate-checker/) [Certificate](https://crt.sh/?) Serial:
	- SHA-1: 
	- SHA-256: 
	- Issuer (CA): 
		- CA ID: 
	- Phone: 
	- Email:
	- IP Address: 
- Suspected Back-End Infrastructure: 

- x509 Certificate:
	- [Suspicious](https://blog.gigamon.com/2022/10/24/an-osint-analysis-of-x509-certificates-part-two-digging-into-the-san/) SAN extensions: 
		- Only domain and \*.domain? -> likely phishing
	- SAN: 
		- Different form domain? -> reverse proxy
	- Issuer (CA): 
		- Different from *actual* domain issuer whose subject and SAN is in the tampered cert. -> TLS inspection proxy

`openssl s_client -connect some-domain.com:443 -showcerts`

Find more certificates with: 
- `pip3 install certstream`
- `certstream --full | grep <domain>`
or [persistent monitoring]([https://github.com/CaliDog/certstream-python](https://github.com/CaliDog/certstream-python)).
### ADINT
- Analytics (`UA-`):  
- AdSense (˛`pub-` or `ca-pub`): 
- Amazon (`&tag=`): 
- AddThis (`#pubid` / `pubid`): 
- Metrika ID (`mc.yandex` / `ym`):
- Rambler (`top100`): 
- Mail.ru (`Top.Mail.Ru`): 
- Website Traffic: 
- Web Tracking Code: 

### Ports & Services

| Port | State | Service | Verified: Y/N |     |
| ---- | ----- | ------- | ------------- | --- |
|      |       |         |               |     |
### Archived Versions
1. \[\[date]-\[url]
2. 
3. 

### Outgoing Links
> Useful Resource: https://urlscan.io/

- Social Media: 
- Domains: 
- Ads: 
- References: 

### Incoming Links
- From Online Accounts: 
- From Domains: 
- From Email Headers: 

### Fingerprint
- Created_Date: 
- HTTP Headers: 
	- [ETag](https://cybernomad.online/osint-etag-youre-it-ecd7e923392c): 
- Favicon: 
	- Favicon hash: 
- Banner: 
- BuiltWith: 
- Behaviour: 
- Hash: 
- SimHash: 
	- use `simhash_near:[value]` as a dork to find similar webpages
- SSH Key Fingerprint (of Host Server):
	- RSA: 
	- DSA: 
	- ECDSA: 
- WHOIS registrar, registrant, reg. time (of Domain): 
	- Current: 
	- Historical: 
- [JA3](https://github.com/salesforce/ja3): 
- [JARM](https://github.com/salesforce/jarm): 
- [JA4+]([https://ja4db.com/](https://github.com/FoxIO-LLC/ja4)) (find as `JA4=` / `JA4H=` / `JA4S=` / `JA4X=` / `JA4SSH=` / `JA4T=`): 
- [HHHash](https://www.foo.be/2023/07/HTTP-Headers-Hashing_HHHash): 
	Calculate with:
	```curl -s -D - <domain> -o /dev/null  | awk 'NR != 1' | cut -f1 -d: | sed '/^[[:space:]]*$/d' | sed -z 's/\n/:/g' | sed 's/.$//' | sha256sum | cut -f1 -d " " | awk {'print "hhh:1:"$1'}```

- IP Address Feature Vector ([search](https://viz.greynoise.io/)):
- Domain name syntax -> similar domain names: 
- Aesthetics: 
- Narratives: 
- Vocabulary: 

> Useful Resource: https://gopivot.ing/map/

## Attack Vectors

- Functionality: 
- Suspected Back-End Infrastructure: 
- Security Controls: 
- Security Measures: 
- Technologies: 
# Analysis


# Notes