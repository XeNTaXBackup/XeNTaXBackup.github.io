## Post #1
- Username: dbeetle
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Nov 28, 2010 8:04 pm
- Post datetime: 2010-12-14T16:28:43+00:00
- Post Title: Disney Interactive: Tangled .bag file

I tried using 3d ripper dx, but the mesh comes out distorted. The character models seem like the only thing that is coming out like that.  The environment seems ok.

Here's a .bag file if anyone wants to take a look.  I have no idea if the models are even in it since I've never come across this type of file before.
[http://www.4shared.com/file/6S80_yDj/le ... rolic.html](http://www.4shared.com/file/6S80_yDj/level_first_frolic.html)
## Post #2
- Username: dbeetle
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Nov 28, 2010 8:04 pm
- Post datetime: 2010-12-17T18:18:41+00:00
- Post Title: Disney Interactive: Tangled .bag file

The distorted mesh is caused by a corrupt installation.  It works fine with 3dripper dx now.  I would still like to be able to get into the .bag file and look around.
## Post #3
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2010-12-22T12:01:59+00:00
- Post Title: Disney Interactive: Tangled .bag file

Sound files and dialogue are in FMOD and wav formats, respectively; I managed to open a few music files in Mafia II Audio Extractor, but yeah, the bag archives seem to be interesting enough to peek at.

NINJA EDIT: It appears as though the archives don't seem to have a definite header; each of them have different sigs for the first few bytes. I'm not an expert at this, but a quick run with HxD confirmed this:

First Frolic:
EC 02 00 00

Goat Cart:
6B 01 00 00

Village:
E6 01 00 00
