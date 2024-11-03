# Splunk BOTS v1 Recap

This Splunk BOTS recap and walkthrough is based on the Version 1 (2015) event. You can sign up for a free account and play along at https://bots.splunk.com.

## Table of Contents

* [Scenario 1: Website Defacement](https://github.com/chan2git/splunk-bots/tree/main/botsv1#scenario-1-web-site-defacement)

    * [Q101: What is the likely IPv4 address of someone from the Po1s0n1vy group scanning imreallynotbatman.com for web application vulnerabilities?](https://github.com/chan2git/splunk-bots/tree/main/botsv1#q102-what-company-created-the-web-vulnerability-scanner-used-by-po1s0n1vy)

    * [Q102: What company created the web vulnerability scanner used by Po1s0n1vy?](https://github.com/chan2git/splunk-bots/blob/main/botsv1-recap.md#q102-what-company-created-the-web-vulnerability-scanner-used-by-po1s0n1vy)

    * [Q103: What content management system is imreallynotbatman.com likely using?](https://github.com/chan2git/splunk-bots/tree/main/botsv1#q103-what-content-management-system-is-imreallynotbatmancom-likely-using)

    * [Q104: What is the name of the file that defaced the imreallynotbatman.com website? Please submit only the name of the file with extension?](https://github.com/chan2git/splunk-bots/tree/main/botsv1#q104-what-is-the-name-of-the-file-that-defaced-the-imreallynotbatmancom-website-please-submit-only-the-name-of-the-file-with-extension)

    * [Q105: This attack used dynamic DNS to resolve to the malicious IP. What fully qualified domain name (FQDN) is associated with this attack?](https://github.com/chan2git/splunk-bots/tree/main/botsv1#answer-poisonivy-is-coming-for-you-batmanjpeg)

    * [Q106: What IPv4 address has Po1s0n1vy tied to domains that are pre-staged to attack Wayne Enterprises?](https://github.com/chan2git/splunk-bots/tree/main/botsv1#q106-what-ipv4-address-has-po1s0n1vy-tied-to-domains-that-are-pre-staged-to-attack-wayne-enterprises)

    * [Q108: What IPv4 address is likely attempting a brute force password attack against imreallynotbatman.com?](https://github.com/chan2git/splunk-bots/tree/main/botsv1#q108-what-ipv4-address-is-likely-attempting-a-brute-force-password-attack-against-imreallynotbatmancom)

    * [Q109: What is the name of the executable uploaded by Po1s0n1vy?](https://github.com/chan2git/splunk-bots/tree/main/botsv1#q109-what-is-the-name-of-the-executable-uploaded-by-po1s0n1vy)

    * [Q110: What is the MD5 hash of the executable uploaded?](https://github.com/chan2git/splunk-bots/tree/main/botsv1#q110-what-is-the-md5-hash-of-the-executable-uploaded)

    * [Q111: GCPD reported that common TTPs (Tactics, Techniques, Procedures) for the Po1s0n1vy APT group, if initial compromise fails, is to send a spear phishing email with custom malware attached to their intended target. This malware is usually connected to Po1s0n1vys initial attack infrastructure. Using research techniques, provide the SHA256 hash of this malware](https://github.com/chan2git/splunk-bots/tree/main/botsv1#q111-gcpd-reported-that-common-ttps-tactics-techniques-procedures-for-the-po1s0n1vy-apt-group-if-initial-compromise-fails-is-to-send-a-spear-phishing-email-with-custom-malware-attached-to-their-intended-target-this-malware-is-usually-connected-to-po1s0n1vys-initial-attack-infrastructure-using-research-techniques-provide-the-sha256-hash-of-this-malware)

    * [Q112: What special hex code is associated with the customized malware discussed in question 111?](https://github.com/chan2git/splunk-bots/tree/main/botsv1#q112-what-special-hex-code-is-associated-with-the-customized-malware-discussed-in-question-11)

    * [Q114: What was the first brute force password used?](https://github.com/chan2git/splunk-bots/tree/main/botsv1#q114-what-was-the-first-brute-force-password-used)

    * [Q115: One of the passwords in the brute force attack is James Brodsky's favorite Coldplay song. We are looking for a six character word on this one. Which is it?](https://github.com/chan2git/splunk-bots/tree/main/botsv1#q115-one-of-the-passwords-in-the-brute-force-attack-is-james-brodskys-favorite-coldplay-song-we-are-looking-for-a-six-character-word-on-this-one-which-is-it)

    * [Q116: What was the correct password for admin access to the content management system running "imreallynotbatman.com"?](https://github.com/chan2git/splunk-bots/tree/main/botsv1#q116-what-was-the-correct-password-for-admin-access-to-the-content-management-system-running-imreallynotbatmancom)

    * [Q117: What was the average password length used in the password brute forcing attempt? (Round to the closest whole integer)](https://github.com/chan2git/splunk-bots/tree/main/botsv1#q117-what-was-the-average-password-length-used-in-the-password-brute-forcing-attempt-round-to-the-closest-whole-integer)

    * [Q119: How many unique passwords were attempted in the brute force attempt?](https://github.com/chan2git/splunk-bots/tree/main/botsv1#q119-how-many-unique-passwords-were-attempted-in-the-brute-force-attempt)


* [Scenario 2: Ransomware](https://github.com/chan2git/splunk-bots/tree/main/botsv1#scenario-2-ransomware)

    * [Q200: What was the most likely IPv4 address of we8105desk on 24AUG2016?](https://github.com/chan2git/splunk-bots/tree/main/botsv1#q200-what-was-the-most-likely-ipv4-address-of-we8105desk-on-24aug2016)

    * [Q201: Amongst the Suricata signatures that detected the Cerber malware, which one alerted the fewest number of times? Submit ONLY the signature ID value as the answer. (No puinctuation, just 7 digits)](https://github.com/chan2git/splunk-bots/tree/main/botsv1#q201-amongst-the-suricata-signatures-that-detected-the-cerber-malware-which-one-alerted-the-fewest-number-of-times-submit-only-the-signature-id-value-as-the-answer-no-puinctuation-just-7-digits)
    
    * [Q202: What fully qualified domain name (FQDN) does the Cerber ransomware attempt to direct the user to at the end of its encryption phase?](https://github.com/chan2git/splunk-bots/tree/main/botsv1#q202-what-fully-qualified-domain-name-fqdn-does-the-cerber-ransomware-attempt-to-direct-the-user-to-at-the-end-of-its-encryption-phase)

    * [Q203: What was the first suspicious domain visited by we8105desk on 24AUG2016?](https://github.com/chan2git/splunk-bots/tree/main/botsv1#q203-what-was-the-first-suspicious-domain-visited-by-we8105desk-on-24aug2016)

    * [Q204: During the initial Cerber infection a VB script is run. The entire script from this execution, pre-pended by the name of the launching .exe, can be found in a field in Splunk. What is the length of the value of this field?](https://github.com/chan2git/splunk-bots/tree/main/botsv1#q204-during-the-initial-cerber-infection-a-vb-script-is-run-the-entire-script-from-this-execution-pre-pended-by-the-name-of-the-launching-exe-can-be-found-in-a-field-in-splunk-what-is-the-length-of-the-value-of-this-field)

    * [Q205: What is the name of the USB key inserted by Bob Smith?](https://github.com/chan2git/splunk-bots/tree/main/botsv1#q205-what-is-the-name-of-the-usb-key-inserted-by-bob-smith)

    * [Q206: Bob Smith's workstation (we8105desk) was connected to a file server during the ransomware outbreak. What is the IPv4 address of the file server?](https://github.com/chan2git/splunk-bots/tree/main/botsv1#q206-bob-smiths-workstation-we8105desk-was-connected-to-a-file-server-during-the-ransomware-outbreak-what-is-the-ipv4-address-of-the-file-server)

    * [Q207: How many distinct PDFs did the ransomware encrypt on the remote file server?](https://github.com/chan2git/splunk-bots/tree/main/botsv1#q207-how-many-distinct-pdfs-did-the-ransomware-encrypt-on-the-remote-file-server)

    * [Q208: The VBscript found in question 204 launches 121214.tmp. What is the ParentProcessId of this initial launch?](https://github.com/chan2git/splunk-bots/tree/main/botsv1#q208-the-vbscript-found-in-question-204-launches-121214tmp-what-is-the-parentprocessid-of-this-initial-launch)

    * [Q209: The Cerber ransomware encrypts files located in Bob Smith's Windows profile. How many .txt files does it encrypt?](https://github.com/chan2git/splunk-bots/tree/main/botsv1#q209-the-cerber-ransomware-encrypts-files-located-in-bob-smiths-windows-profile-how-many-txt-files-does-it-encrypt)

    * [Q210: The malware downloads a file that contains the Cerber ransomware cryptor code. What is the name of that file?](https://github.com/chan2git/splunk-bots/tree/main/botsv1#q210-the-malware-downloads-a-file-that-contains-the-cerber-ransomware-cryptor-code-what-is-the-name-of-that-file)

    * [Q211: Now that you know the name of the ransomware's encryptor file, what obfuscation technique does it likely use?](https://github.com/chan2git/splunk-bots/tree/main/botsv1#q211-now-that-you-know-the-name-of-the-ransomwares-encryptor-file-what-obfuscation-technique-does-it-likely-use)
