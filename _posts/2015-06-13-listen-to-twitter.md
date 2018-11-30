---
layout: post
title: Making sound from the sentiment of Tweets
date: 2015-06-13
---

This a write up of a hack I originally co-authored as "Noisy Tweets" with [Mark Ormesher](http://markormesher.co.uk/), [Fares Alaboud](http://faresalaboud.me/) and [Kristin Kasavetova](http://krisi.me/) at [MLH](https://mlh.io/) Launch Hack.

Noisy Tweets is an application created in 24 hours that takes in a keyword as input, live-streams all tweets containing that keyword, analyses how happy or sad (sentiment) the tweets are, and plays different musical notes depending on how happy or sad the tweets are.

The happier the general discussion, the higher the pitch of each note; the more tweets there are, the faster the notes play.

I eventually refactored it into a live web application: [listentotwitter.com](http://listentotwitter.com).

![Screenshot from listentotwitter.com]({{ "/img/listentotwitter-screenshot.png" | prepend: site.baseurl }})<br>
*Screenshot from listentotwitter.com.*

The backend of the web application is written in Python, using [Flask](http://flask.pocoo.org/) for the web server, [TextBlob](https://textblob.readthedocs.org/en/dev/) for sentiment analysis, and [socket.io](http://socket.io/) for real-time client communication.

Admittedly, it sounds pretty bad from a musical perspective. It sounds a bit like the "[world's ugliest music](https://www.youtube.com/watch?v=RENk9PK06AQ)". Regardless, it was a fun experiment. There are perhaps way to make it sound more musical, but I don't know much about making music that sounds good.
