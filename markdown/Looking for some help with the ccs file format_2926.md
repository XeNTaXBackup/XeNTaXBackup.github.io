## Post #1
- Username: Forte
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Aug 07, 2007 4:51 am
- Post datetime: 2008-02-06T00:49:55+00:00
- Post Title: Looking for some help with the ccs file format

I love how the site went down and I pressed preview, making me retype that all...

So, anyway, this is an archive file format found in all of CyberConnect2's PS2 games and I’m having problems with its structure. The file format is some kind of container for other files, and I just can't figure out the way the .max files are read. I'll go over the stuff I found out to give you a basic idea of it. [Here's](http://phorte.ph.ohost.de/ccs/2bcf00.tmp) the file I'll be using in the topic.

First of all, let's start with the header.

The only thing I've figured out is that the word at 44h is the amount of files+1 (here 2+1) and the word at 48h is the amount of what I call objects+1 (here 68h+1).
After the header, we have the two filepaths(of a *.max and a *.bmp), each taking 20h bytes, some padding and then the "objects". There seem to be a lot of these for each model and mostly two for each texture. This leads me to my first question: What possible use could these objects have (and what could they actually be?)?.
After the last object and 8 bytes of padding, the first file begins(the *.max file in this case). Since thse max files are the most confusing part of the file, I'm going to skip that.

If you search the file for 0004CCCC, you'll find all the palettes(6). Let's take a look at one of them:

(I chose this one because it's right infront of the image data)
The first word after 0004CCCC is the amount of colors+5(why they chose 5 is beyond me), so here we have 100h colors(256) and since each color is 4 bytes, the palette takes up 400h bytes. There seems to be other info in the header, but it's kinda not necessary to show the textures properly.

Here we have 6 palettes for one texture, but it's usually one palette per texture/picture.
The image data starts with 0003CCCC and right after the last palette.

The only importand thing is at 10F2Ch. The first byte is the width(2^x) and the second one is the height(2^y) of the picture. Here, it's both 2^8, so the picture size is 256*256.

I like how both the palette and the picture are actually very simple, but the models are not.
Here's the info summed up:
-the palette and picture always start with 0004CCCC/0003CCCC
-thanks to the info in the headers, we have the exact amount of space taken without the typical "offset of file, length of file" thing.

Let's move to the *.max files. Since the workspace of the modellers was shown in several videos and they used 3d studio, it's safe to assume that the max files are indeed 3ds max files. They're so damn confusing that I don't even know how long the header is and how to find them.
The max file starts at DD4h and ends when the first palette starts (duh)(F66Ch), so the length of the whole file is E898h bytes(minus a few bytes for the header). However, I can't figure out how the game knows where the file ends. No even remotely similar number appears anywhere.
The second issue is that the max files have no constant beginning. Sure, it's 2300CCCC in this file, but it's different in any other. 
I'm completely lost at this, so does anyone have any ideas what to look for? Ever encountered similar problems?

[Here's](http://phorte.ph.ohost.de/ccs/eng_atl.rar) a rar of a file which only has bmps. Very easy to read.

[Here's](http://phorte.ph.ohost.de/ccs/barrier.tmp) another interesting file. It has two files that seem to be animation files of some sort, one normal max file and one texture (16 color palette). What I don't understand here are the anm max files. Let's take a look at the bmp, the palette starts at 1298h and the image data at 12F4h, and is 64*64 pixels in size which are 800h bytes (becase the palette only has 16 colors, one byte is two pixels). You might notice that in the filepath index, there's the anm max file after the texture. Also, you might've noticed that file ends here so I'm clueless about that anm max entry.

There are also two other formats in other files, but they're just as evil and I want to figure this out first.

I might make more sense to me if there was any documentation on the max format, but there just isn't. 
Btw, this is the first file format I've ever looked at and I've already learned a lot, so I'm happy about any advice on this (kudos to anyone who has made it this far).
## Post #2
- Username: Forte
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Aug 07, 2007 4:51 am
- Post datetime: 2008-02-09T20:43:54+00:00
- Post Title: Looking for some help with the ccs file format

I've finally figured out most of it.

The format looks quite complicated, but isn't at all. It's actually made pretty logical and kinda noob-friendly.
## Post #3
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-02-11T20:36:11+00:00
- Post Title: Looking for some help with the ccs file format

Care to share your knowledge?
## Post #4
- Username: Forte
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Aug 07, 2007 4:51 am
- Post datetime: 2008-02-11T21:07:44+00:00
- Post Title: Looking for some help with the ccs file format

I will definitely once I'm 100% through with it, but I'm still unsure about a lot of things right now (there're still some minor things that don't mach up for me).
The most disturbing thing is that I know where the models and animations are, but can't read them (see the topic in "3D/2D models").

Seeing that the format is most likely used in at least 7 games(two .hack games, five Naruto), I'll make sure to document it someday.
## Post #5
- Username: Anomy
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Sep 04, 2007 3:04 pm
- Post datetime: 2008-05-17T13:42:17+00:00
- Post Title: Looking for some help with the ccs file format

Did you ever get any further on this, I thought no one else would be working on this format, but it looks like you got to the CCS files as well. It would be nice if someone could finally crack this format for us, can't tell you how many days I spent scratching my head and screaming trying to work out an extractor for it or hoping some one smarter would help.

Anyone else want to take a look and maybe build a script for extraction for it help us lower beings out hehe
