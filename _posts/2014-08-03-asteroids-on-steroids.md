---
layout: post
title: Asteroids on Steroids
date: 2014/08/03 11:00
---

Asteroids on Steroids is a desktop game I developed in Python using the [Pygame](http://pygame.org) library in the summer of 2012, when I was 17.

It was my first ever Python project, and although the code for this project is pretty horrible and unstructured, I've been hooked on Python ever since and use it for almost everything.

The idea for the game is to make it possible to play the classic arcade game Asteroids with anything - not just asteroids. Instead of shooting asteroids, you can shoot elements of any image you specify. There's also a desktop mode that allows you to shoot at your computer desktop.

The game automatically determines what the different elements (or "asteroids") of the user-specified image are. It does this by considering which regions of the image are connected by the same (or similar) colour. This method was inspired by the [fuzzy selection tool in GIMP](http://docs.gimp.org/en/gimp-tool-fuzzy-select.html).

Initially, I attempted to implement my own fuzzy selection algorithm in raw Python using a queue-based implementation, but I quickly realised that Python and scripting languages in general were way too slow (for a responsive game) to process the millions of pixels in an image on their own. My implementation in Python took several minutes per image to execute. I eventually found [OpenCV](http://opencv.org/), an image processing library available for Python that had a "fuzzy selection"-type function (in the end it was probably unnecessary because Pygame itself has a "fuzzy selection"-type function).

[The source code for the game is available on GitHub.](https://github.com/musalbas/Asteroids-on-Steroids)

![]({{ "/img/Asteroids-on-Steroids/gameplay_shot_1.png" | prepend: site.baseurl }})<br>
*A screenshot of gameplay in desktop mode, on an Ubuntu desktop.*

![]({{ "/img/Asteroids-on-Steroids/gameplay_shot_2.png" | prepend: site.baseurl }})<br>
*A screenshot of gameplay when an image of Barack Obama's face is used as input.*
