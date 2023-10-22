## Post #1
- Username: ecraven
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 27, 2016 12:27 am
- Post datetime: 2016-06-26T16:39:40+00:00
- Post Title: (Original) Railroad Tycoon PIC format

Greetings!

I've been looking into the original Railroad Tycoon (Sid Meier & Microprose).
All the image data seems to be in .PIC files, which are different than the .PIC files used by Civilization and Darklands (which appeared a year or so later).

They all start with
0x0f/0x07 0x00  maybe some sort of version? 
0x40 0x01  320  (I'm fairly certain the image resolution is 320x200)
0xc8 0x00  200
data...

I haven't been able to find anything about anyone ever trying to reverse engineer the game or its data formats, has any one of you ever come across any pertinent information relating to this?

I'd be glad about any help 

Sid Meier's Railroads has a link to a freeware version of Railroad Tycoon:
[http://www.2kgames.com/railroads/downloads.html](http://www.2kgames.com/railroads/downloads.html), however this seems to be the Deluxe version (which has yet different PICs), not the original game :-/

Thank you very much, greetings,

ecraven   

PS: how do I add .pic files? zip them? forum doesn't want me to attach them :-/
[logo.png](https://xentaxbackup.github.io/file/11119_logo.png)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-07-15T11:16:34+00:00
- Post Title: (Original) Railroad Tycoon PIC format

> Reply from ecraven
>
> PS: how do I add .pic files? zip them? forum doesn't want me to attach them :-/
yeah zip them and attach to post or if too big you can upload to external file host
no one can really help you without samples to look at
## Post #3
- Username: ecraven
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 27, 2016 12:27 am
- Post datetime: 2016-10-03T11:10:53+00:00
- Post Title: (Original) Railroad Tycoon PIC format

Attached two images, LABS and LOGO, with a screenshot. They are displayed as 640x400, but bytes 2,3 are 0x40 0x01 (0x140 -> 320) and bytes 4,5 are 0x00c8 (-> 200), so I believe that is in fact the correct resolution. They seem to be merely scaled by 2 on each axis.
I'm guessing there's some sort of RLE or so going on here, but I have no idea how to find out :-/

I'd appreciate any help!
[pics.zip](https://xentaxbackup.github.io/file/11759_pics.zip)
## Post #4
- Username: MM1nd
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Apr 11, 2017 6:34 pm
- Post datetime: 2017-04-11T11:19:36+00:00
- Post Title: (Original) Railroad Tycoon PIC format

I hope to once again get people interested in this file format.

First of all, the .PIC format for Sid Meier's Covert action has been decoded:

[https://www.gog.com/forum/sid_meiers_co ... _fun/post6](https://www.gog.com/forum/sid_meiers_covert_action/reverse_engineering_for_mods_and_fun/post6)

Second of all, so has the Format for CIV Dos:

[https://forums.civfanatics.com/threads/ ... st.478234/](https://forums.civfanatics.com/threads/map-pic-and-pal-formats-figured-out-almost.478234/)

However, despite having the same ending, Sid Meier's Railrod Tycoon Deluxe files seem to be in a different format and I very much doubt that it is an LZW-Format.

The game can be obtained for free from the publisher, the original poster shared the link. Like the OP says, this is different from the original (non deluxe) game.

The following concerns the deluxe version.

With the game comes an intro.exe which displays labs.pic as the first thing so that might be an natural starting point for investigation.

The File begins thus:

0x0000: 00 48 38 00 - unknown
0x0004: 80 02 90 01 - image resolution (640x400)
0x0008 - 0x0037: palette data (16 colors * 3 bytes)

The rest of the file is pixel data. The little I was able to find out is the following:

- The data is layered in bits (i. e. LSB stored first for all pixels). There is a total of 4 layers, this matches the 16 palette entries.
- there is some kind of RLE going on.

Example (continued):

0x0038: 48 09 - unknown

0x003A: 55 55 - also unknown but this might be a magic value to signify the begining of some sort of block. It reoccurs within the file at suspicious positions, e. g. the beginning of layers. But also within layers so idk. Changing it seems to break the file rather than changing image data but I'm not so sure.

0x003C: 00 - this the pattern for setting bits, i. e. setting this to AA sets the bit for every other pixel for some time, but not throughout the whole layer.

0x003D: FF F8 FC - this is a consecutive block of length FC+1 filled with the same pattern. This seems to be the longest run length handled by the encoder. The sequence FF F8 FC is found in many files and at many positions. The actual effect of the first FF is some kind of super pattern, i. e. a pattern affecting blocks of 8 pixels. I think I have isolated the pattern but then again that might have been an artifact of the decoder, so I'm trying not to influence people on that one. I have no idea whatsoever, what the F8 does.

0x0040: FF F8 FC - this is to say, there is no further "pattern byte" (cf. 0x003C), the RLE just continues.

As you can see I don't really have an idea what I am doing here. I have not been able to figure out sequences which contain actual image information rather than long sequences of the same color. I hope however that something in my analysis is meaningful to people who know better. Or that I have sparked someones curiosity.

Hints howto continue analysis are also appreciated.
