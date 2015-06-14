---
layout: post
title: Security advisory - E-Detective Lawful Interception System
date: 2015-06-14
---

This is a full disclosure security advisory (also [posted](http://seclists.org/fulldisclosure/2015/Jun/42) on the Full Disclosure mailing list) for multiple vulnerabilities in [Decision Group](http://www.edecision4u.com/index.html)'s [E-Detective](http://www.edecision4u.com/E-DETECTIVE.html) "Real-Time Network Forensics and Lawful Interception System", co-authored by [slipstream/RoL](https://twitter.com/TheWack0lian) and I.

>E-Detective is a real-time Internet interception, monitoring and forensics system that captures, decodes, and reconstructs various types of Internet traffic. It is commonly used for organization Internet behavioral monitoring, auditing, record keeping, forensics analysis, and investigation, as well as, legal and lawful interception for lawful enforcement agencies such as Police Intelligence, Military Intelligence, Cyber Security Departments, National Security Agencies, Criminal Investigation Agencies, Counter Terrorism Agencies etc. It also can provide a compliance solution for many standards or acts like Sarbanes Oxley Act (SOX), HIPAA, GLBA, SEC, NASD, E-Discovery and many others.

Decision Group also [claims](http://www.edecision4u.com/HTTPS-SSL.html) that its products are used by "more than 100 law enforcement agencies", including the National Security Bureau of the Republic of China.

**1. Unauthenticated Local File Disclosure**

The `common/download.php` script in the web root allows for unauthenticated users to read arbitrary files on the system. This may include database credentials and captured data intercepts.

The `file` URL query parameter of the script is "protected" by the following encoding which is trivially reversible: base64 followed by rot40.

A [proof of concept for this vulnerability is available on GitHub](https://github.com/musalbas/edetective-poc/blob/master/pwned-detective.py).

**2. Authenticated Remote Code Execution**

Combining this vulnerability with the Local File Disclosure vulnerability above can result in unauthenticated remote code execution.

The restore feature on the "config backup" page extracts a .tar file encrypted with Blowfish using OpenSSL into the system's root directory (/) as root.

The .tar file must be encrypted with the static key `/tmp/.charlie`. Yes, that's the actual key - the software passes the wrong argument to OpenSSL. `-K` is used to pass the keyfile instead of `-kfile`, meaning that the key is the path of the keyfile rather than the contents of the keyfile.

This allows an attacker to upload a shell into the web root, or overwrite any sensitive system files such as `/etc/shadow`/.
