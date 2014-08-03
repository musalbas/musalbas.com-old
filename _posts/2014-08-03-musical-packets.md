---
layout: post
title: Musical Packets
date: 2014/08/03 10:00
---

Earlier this year I attended [StudentHack](http://www.studenthack.com/) and formed a team with [Fares Alaboud](http://faresalaboud.me/) and [Callum Spawforth](https://twitter.com/spoffeh). For 24 hours we worked on a project called [Musical Packets](https://github.com/musalbas/musicalpackets).

Musical Packets is a Python application that listens to your aggregate network traffic and plays it back as music! It also comes with a web interface that visualises the aggregate packets received.

![](/img/musicalpackets-screen.png)<br>
*Musical Packets web interface.*

The way it works at the moment is by converting the rate of packets received per second to a musical tone. Although it sounds pretty good as it is right now, the original idea (which wasn't developed further due to the 24 hours time constraint) was to assign a different instrument to each network protocol or port. For example, HTTP would sound different than HTTPS.

The application also logs packets into a MongoDB database, so it has the capability of playing back the musical packets.

The project won two of the six prizes at StudentHack:

* Best Use of MongoHQ
* Best Fresher Hack

[The source code is available on GitHub.](https://github.com/musalbas/musicalpackets)

![](/img/studenthack.jpg)
*From left to right: Callum Spawforth, me and Fares Alaboud.*
