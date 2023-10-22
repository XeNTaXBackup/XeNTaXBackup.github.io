## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-27T01:24:20+00:00
- Post Title: Simple image viewer

Suddenly felt the urge to make GUI applications with visual studio in C#.

One thing I've always wanted was a simple tool that allowed me to pass in two images and just return the differences. Maybe some large image editor software already has this built-in, but oh well

Cause you know, I'm horrible when it comes to a game of "find the differences" so I figured I might just cheat...

Just exploring the kinds of things I can quickly do by clicking a few buttons, and it's pretty cool.





One thing I would like is to replace the two "input" boxes on the left with an actual list of images, so that you can select two images that you want to "compare" rather than hardcoding them.

I would also like to quickly be able to just combine images together, with some control over it.
Of course I could just do this in any decent image editor, but I just want to have a list of images on the side that I want to combine, then just select one, "add layer", then select another, "add layer" and so on. Of course it's not really layers; it's just me copying the pixels over but it achieves the same effect.

What I don't like about my code is that all of the event handling is done in one big main Form1 class. Logic is separated into other classes, but still all of the events are just in one place (menu clicks, drag/drop, picture clicks...)

Usage is pretty simple...just drag images over the boxes and then go to tools and select an option.
You can drag two images at a time and it will automatically load them into each box.

ctrl+Z will just spit out the differences
ctrl+X will switch the order of the input

Built on .net 3.5

I'm still trying to figure out the best way to make "easy to use". Now if there was a way to make it so I can use single-key shortcuts rather than having a ctrl/alt/shift ...
[ImageViewer.zip](https://xentaxbackup.github.io/file/5602_ImageViewer.zip)
