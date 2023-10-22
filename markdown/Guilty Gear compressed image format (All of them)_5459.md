## Post #1
- Username: Insanius
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Apr 01, 2010 11:51 am
- Post datetime: 2010-11-24T23:54:44+00:00
- Post Title: Guilty Gear compressed image format (All of them?)

Well this is my first time posting here but I'll try to be as concise as possible.
A friend and I are building a frame display tool for this game and we have encountered a compressed image format in the game's files.

[http://ggxx.wingdreams.net/](http://ggxx.wingdreams.net/) the game can be downloaded here, for reference.

All game files are stored in generically labeled archives with arbitrary formats, of which I can't go into much detail.  Suffice to say, the files usually begin immediately with an offset pointing to either more offsets or the start of a file.  The archives are also split into chunks by an arbitrary amount of zero padding.
Luckily I've encountered some uncompressed images, which allowed me to to parse the important pieces of information from the header.  I've detailed my findings here
[http://pastebin.com/d3yVY0hc](http://pastebin.com/d3yVY0hc)

And this is the smallest compressed image we've found so far, 128x24 and 4 bit color depth
[http://pastebin.com/16HMZzQY](http://pastebin.com/16HMZzQY)

Finally, I've zipped up a few samples here.

Edit: If this topic fits better in the compressed format subforum please move it.
[imagesamples.zip](https://xentaxbackup.github.io/file/3639_imagesamples.zip)
## Post #2
- Username: Sara
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 17, 2010 6:40 am
- Post datetime: 2010-12-13T06:15:16+00:00
- Post Title: Guilty Gear compressed image format (All of them?)

There's actually a sprite rip hack (and full rips) here: [http://www.justnopoint.com/xenoblip/](http://www.justnopoint.com/xenoblip/)
I believe it has source code, but then again, it probably just grabs the textures out of memory?
It may or may not help you in making a viewer, but I thought it'd be best if you were aware of it.
## Post #3
- Username: Insanius
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Apr 01, 2010 11:51 am
- Post datetime: 2013-05-13T19:24:24+00:00
- Post Title: Guilty Gear compressed image format (All of them?)

Sorry for the revival but I'd like to perhaps get some experienced eyes looking this way again.
Another one of my colleagues has observed the same compressed format among pretty much all of the Guilty Gear games, these have been taken from the XBOX360 version of Guilty Gear Accent Core+
[http://www.mediafire.com/?rx88knqj4ym99ul](http://www.mediafire.com/?rx88knqj4ym99ul)

Although the content is on xbox the format remains little endian.
