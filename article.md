---
layout: post
title: Did you know that Firefox sends every URL you visit to Google?
#date: 2014-01-27
---

*My plea to the Mozilla Privacy Team.*

As part of an effort to "<a href="http://www.ibtimes.co.uk/lets-make-2014-all-about-privacy-respecting-encryption-aware-software-1432608" target="_blank">decloud</a>" myself, I was alarmed to see connections to Google in netstat even when I haven't explicitly visited a Google website.

I then remembered that by default Firefox disappointingly sends every URL you visit to Google as part of its <a href="https://www.mozilla.org/en-US/firefox/security/#secure" target="_blank">safe browsing</a> feature to protect users against phishing sites. That is something I would obviously expect from Chrome or Internet Explorer, not Firefox - given the <a href="https://www.mozilla.org/about/manifesto/" target="_blank">Mozilla Manifesto</a>.

The same <a href="https://www.mozilla.org/en-US/firefox/security/#privacy" target="_blank">page</a> that advertises this feature also advertises a "privacy" feature that states: *"When you browse, you leave a trail of data that potentially contains all sorts of personal information. We believe this info belongs to you and you alone (and least of all to overzealous advertisers), and have built in features to ensure that’s the case"*.

Do I even have to mention the hypocrisy here? The <a href="https://blog.mozilla.org/privacy/" target="_blank">Mozilla Privacy Team</a> have been doing a lot of good work to enhance privacy on the web, but I can't help but feel that it's ruined by the lousy fact that Firefox still sends every URL you visit to Google by default.

One of the <a href="https://wiki.mozilla.org/Manifesto/1.0_Changes#Include_explicit_reference_to_privacy" target="_blank">proposed changes</a> to the Firefox manifesto is to introduce the statement *"Individuals' security and privacy on the Internet are fundamental and cannot be treated as optional"*. My plea to the Mozilla Privacy Team is that if you really care about the manifesto, you should reconsider the way the safe browsing feature currently works.

<a href="https://wiki.mozilla.org/Privacy/Principles#Limited_Data" target="_blank">One of the principles</a> of the privacy principles guide is *"Establish default settings in our products and services that balance safety and user experience as appropriate for the context of the transaction"*. There's no need to sacrifice privacy for safety when it comes to blocking malware and phishing sites. There's a <a href="https://easylist-downloads.adblockplus.org/malwaredomains_full.txt" target="_blank">subscription list</a> for <a href="https://adblockplus.org" target="_blank">Adblock Plus</a> that's updated daily which blocks malware sites.

At the time of writing, the list blocks 17,515 URLs and is 141kb big compressed with gzip. Even if Google's list is orders of magnitude bigger, would there really be a logistical problem in implementing this feature in vanilla Firefox? For daily updates, it could be made that only additions and removals to the list are published to save bandwidth.

<a href="https://wiki.mozilla.org/Privacy/Principles#Real_Choices" target="_blank">Another principle</a> is *"Give our users actionable and informed choices by informing and educating at the point of collection and providing a choice to opt-out whenever possible"*. I certainly don't remember being informed or educated about any choices before my URLs were sent to Google ("at the point of collection").

<a href="https://wiki.mozilla.org/Privacy/Principles#Trusted_Third_Parties" target="_blank">Another principle</a> is *"Make privacy a key factor in selecting and interacting with partners"*. If Google was selected for privacy, you're doing it wrong.

In the meantime I would suggest that users who are concerned about their privacy to disable the "Block reported attack sites" and "Block reported web forgeries" options under the Security tab in Firefox preferences, and use <a href="https://adblockplus.org" target="_blank">Adblock Plus</a> malware blocking instead.
