# Splunk BOTS v1 Recap

This Splunk BOTS recap and walkthrough is based on the Version 1 (2015) event. You can sign up for a free account and play along at https://bots.splunk.com.

## Table of Contents

* [Scenario 1: Website Defacement](#scenario-1-website-defacement)
    * [Q101: What is the likely IPv4 address of someone from the Po1s0n1vy group scanning imreallynotbatman.com for web application vulnerabilities?](#q101-what-is-the-likely-ipv4-address-of-someone-from-the-po1s0n1vy-group-scanning-imreallynotbatmancom-for-web-application-vulnerabilities)
    * [Q102: What company created the web vulnerability scanner used by Po1s0n1vy?](#q102-what-company-created-the-web-vulnerability-scanner-used-by-po1s0n1vy)
    * [Q103: What content management system is imreallynotbatman.com likely using?](#q103-what-content-management-system-is-imreallynotbatmancom-likely-using)
    * [Q104: What is the name of the file that defaced the imreallynotbatman.com website?](#q104-what-is-the-name-of-the-file-that-defaced-the-imreallynotbatmancom-website)
    * [Q105: This attack used dynamic DNS to resolve to the malicious IP. What fully qualified domain name (FQDN) is associated with this attack?](#q105-this-attack-used-dynamic-dns-to-resolve-to-the-malicious-ip-what-fully-qualified-domain-name-fqdn-is-associated-with-this-attack)
    * [Q106: What IPv4 address has Po1s0n1vy tied to domains that are pre-staged to attack Wayne Enterprises?](#q106-what-ipv4-address-has-po1s0n1vy-tied-to-domains-that-are-pre-staged-to-attack-wayne-enterprises)
    * [Q108: What IPv4 address is likely attempting a brute force password attack against imreallynotbatman.com?](#q108-what-ipv4-address-is-likely-attempting-a-brute-force-password-attack-against-imreallynotbatmancom)
    * [Q109: What is the name of the executable uploaded by Po1s0n1vy?](#q109-what-is-the-name-of-the-executable-uploaded-by-po1s0n1vy)
    * [Q110: What is the MD5 hash of the executable uploaded?](#q110-what-is-the-md5-hash-of-the-executable-uploaded)
    * [Q111: GCPD reported that common TTPs (Tactics, Techniques, Procedures) for the Po1s0n1vy APT group, if initial compromise fails, is to send a spear phishing email with custom malware attached to their intended target. This malware is usually connected to Po1s0n1vys initial attack infrastructure. Using research techniques, provide the SHA256 hash of this malware](#q111-gcpd-reported-that-common-ttps-for-the-po1s0n1vy-apt-group-if-initial-compromise-fails-is-to-send-a-spear-phishing-email-with-custom-malware-attached-to-their-intended-target-this-malware-is-usually-connected-to-po1s0n1vys-initial-attack-infrastructure-using-research-techniques-provide-the-sha256-hash-of-this-malware)
    * [Q112: What special hex code is associated with the customized malware discussed in question 111?](#q112-what-special-hex-code-is-associated-with-the-customized-malware-discussed-in-question-111)
    * [Q114: What was the first brute force password used?](#q114-what-was-the-first-brute-force-password-used)
    * [Q115: One of the passwords in the brute force attack is James Brodsky's favorite Coldplay song. We are looking for a six character word on this one. Which is it?](#q115-one-of-the-passwords-in-the-brute-force-attack-is-james-brodskys-favorite-coldplay-song-we-are-looking-for-a-six-character-word-on-this-one-which-is-it)
    * [Q116: What was the correct password for admin access to the content management system running "imreallynotbatman.com"?](#q116-what-was-the-correct-password-for-admin-access-to-the-content-management-system-running-imreallynotbatmancom)
    * [Q117: What was the average password length used in the password brute forcing attempt?](#q117-what-was-the-average-password-length-used-in-the-password-brute-forcing-attempt)
    * [Q119: How many unique passwords were attempted in the brute force attempt?](#q119-how-many-unique-passwords-were-attempted-in-the-brute-force-attempt)

## Scenario 1: Website Defacement

We now first figur out the total index in file using:

```
| eventcount summarize=false index=*
```
![Scenario1(2)](./Images/Scenario1(2).png)

We might find that the index botsv1 have the most count in all event.

List some SourceType:
```
| metadata type=sourcetypes
| fields sourcetype
```
![Scenario1(1)](./Images/Scenario1(1).png)


### Q101: What is the likely IPv4 address of someone from the Po1s0n1vy group scanning imreallynotbatman.com for web application vulnerabilities?

First, we need to identify the IP address that belongs to our web server, which is likely what the threat group is scanning. We can run the below SPL query with the pipe command to return the destination IP address (`dest_ip`) with the highest hits, which is likely indicative of a web server.

