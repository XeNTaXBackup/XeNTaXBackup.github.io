## Post #1
- Username: Zero Diamond
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Dec 27, 2009 7:10 am
- Post datetime: 2012-11-10T10:01:27+00:00
- Post Title: Quarantine 1 + 2 .SPR

I've been trying to get at Quarantine's sprites for quite some time, and finally had a breakthrough a while back.  For a long time, I've known that the sprites are uncompressed inside the .SPR files, but there was no sign of the palette.  Not too long ago, I finally figured it out: the palette data is stored in the *FLOOR.IMG files.  In Quarantine, it's a letter that corresponds to an equivalent wall and object set (e.g. SFLOOR.IMG for SWALL1.SPR and SOBJECTS.SPR) and in Quarantine 2 the system is similar but divided up clearer by folder structure.

The .SPR files themselves are just uncompressed image data, 8 bits per pixel.  I'm not sure about the ones containing sprites, but the image data in the wall files starts at 0x1A.  The palettes are 3 bits per color, RGB color order and Little Endian with the data starting at 0xD.  Both Quarantine and Quarantine 2 appear to use the same file structure, only differentiated by the use of organizing folders in the latter.  There is probably also image data in the .IMG files themselves, but that appears to be compressed.

Would it be possible for somebody to write a quick and dirty extractor for .SPR files using the information provided?  I've included a link to a sample set from Quarantine containing FLOOR.IMG, WALL1.SPR, OBJECTS.SPR and SKY.IMG.  If anyone wants to take a crack at the .IMG files too, that'd be great, but I'd really appreciate an .SPR extractor ASAP.

[Quarantine sample files](http://www.mediafire.com/download.php?cfq18zpz5z0lp64)
## Post #2
- Username: tigrou
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Feb 22, 2017 6:35 pm
- Post datetime: 2017-02-22T12:12:39+00:00
- Post Title: Quarantine 1 + 2 .SPR

Disclaimer : I know this topic is 5 years old, but my post could be useful for anybody who want to extract ressources of this game.

The SPR files are indeed uncompressed 8 bit (256 colors) data.
However there is a header : first byte is the number of sprites in the SPR files. Then it is followed by byte pairs (as many as the number of sprites). Each pair describe the width and height of each sprite.
Eg : 

```
03 20 10 15 30 70 80
```

We have 3 sprites. First one is 32x16 (0x20 0x10), second one 21x48 (0x15 0x30), third one 112x128 (0x70 0x80).

After that header, is the uncompressed pixel data. Each pixel is one byte.
The pixel data is not stored in a linear (chunky) fashion. Rather, they are grouped into 4 planes. I think it is like that is because the game use Mode X. By storing the data that way, the game can flush data directly into video memory as it is in the file without any conversion.

Eg : how pixel data is stored in the SPR file

```
AAAAAAAABBBBBBBBCCCCCCCCDDDDDDDD
```


How it will be shown on the screen

```
ABCDABCDABCDABCDABCDABCDABCD...
```


Trivia : the appearance of the customers you meet in the game is randomly generated. To generate a new character, the game randomly select a human body (from skinny to fat), then add a pant, shirt, accessories, etc...
Funny fact : those guys are actually [naked under their clothes](http://i.imgur.com/0LyKUXN.png) (you can even see pubic hairs for one of them)
## Post #3
- Username: colinb
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Feb 28, 2019 11:04 pm
- Post datetime: 2019-03-02T20:05:33+00:00
- Post Title: Quarantine 1 + 2 .SPR

Here's the source to an .SPR decoder:

[https://github.com/colinbourassa/imagexcel-decode](https://github.com/colinbourassa/imagexcel-decode)

It covers only the sprite/palette formats described in this thread. I've tested it with JWALL*.SPR, KWALL*.SPR, PWALL*.SPR, SWALL*.SPR, and WWALL*.SPR, and it seemed to work fine.

--Colin
