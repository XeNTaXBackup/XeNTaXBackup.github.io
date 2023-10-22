## Post #1
- Username: haypo
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jan 02, 2006 8:42 pm
- Post datetime: 2006-01-02T13:12:31+00:00
- Post Title: Worms2 file format and Hachoir program

Hi,

I'm the author of the software [Hachoir](http://www.haypocalc.com/wiki/Hachoir). This program aims to split files into chunks like MultiEx does with game files. You may try it, it's a free ("libre") software under GPL licence and written in Python language.

I'm writing to you because I'm trying to read Worms2 game files (.dir files), and I don't understand Sprite pixels encoding. Hachoir is able to read most important informations from Images and Font, but can not read Sprite data. For Sprite (animations), it can read color palette, number of frame, and frame informations : (x,y) and (width, frame).

Ask me if you need help to run the Hachoir, and if you just want file format. And can also send you DIR example file.

Haypo
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-02T13:44:46+00:00
- Post Title: Worms2 file format and Hachoir program

Hi! 

Nice program you have there! It's a layout especially suited for programmers! We should talk, because it may be, from the look of the screenshots, that there might be a MultiEx script<->Hachoir conversion routine possible.
## Post #3
- Username: haypo
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jan 02, 2006 8:42 pm
- Post datetime: 2006-01-02T13:47:34+00:00
- Post Title: Worms2 file format and Hachoir program

Ok, here are the command to test the Hachoir with a Worms2 dir file :

```
cd hachoir
wget http://www.haypocalc.com/tmp/Gfx.dir
./hachoir.py Gfx.dir
```

Double clic on field "resoures". You will see :
* Sprite from res[0] .. res[589]
* Image from res[590] .. res[712]
* Font from res[713] .. res[739]

Haypo
## Post #4
- Username: haypo
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jan 02, 2006 8:42 pm
- Post datetime: 2006-01-02T13:49:26+00:00
- Post Title: Worms2 file format and Hachoir program

> Reply from Mr.Mouse
>
> We should talk
Here my addresses:
[http://www.haypocalc.com/wiki/Victor_St ... _contacter](http://www.haypocalc.com/wiki/Victor_Stinner#Me_contacter)

> Reply from Mr.Mouse
>
> there might be a MultiEx script<->Hachoir conversion routine possible.
Yep, sure, it's always possible.

Haypo
## Post #5
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-01-02T14:08:15+00:00
- Post Title: Worms2 file format and Hachoir program

Hi mate,

Sure, we would be happy to help  . I took a look at your program - I like it a lot - it is definately something that is benificial and I wish you the best with it.

I don't know how much assistance I will be able to provide, considering the file you request is image/animation based, but I will definately help out as much as possible. I know Mr Mouse would be similar in this.

If you could provide us with the specifications you have so far, it would definately be a help, and any files you could provide would be excellent - maybe just zip up a few things and send it over - we will do our best to help you out wherever possible.

Thanks, keep up the excellent work with your program!

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #6
- Username: haypo
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jan 02, 2006 8:42 pm
- Post datetime: 2006-01-02T14:34:20+00:00
- Post Title: Worms2 file format and Hachoir program

Try to read source code of Worms2 plugin:
[http://svn.berlios.de/viewcvs/happyboom ... iew=markup](http://svn.berlios.de/viewcvs/happyboom/haypo/hachoir/trunk/plugins/worms2.py?view=markup)

Palette is a color palette with RGB colors:
[http://svn.berlios.de/viewcvs/happyboom ... iew=markup](http://svn.berlios.de/viewcvs/happyboom/haypo/hachoir/trunk/generic/image.py?view=markup)

For Worms2, they are a few classes:
- Worms2_Dir_File: Just call Resource (1st level)
- Resource: One resource (size + data) (2nd level) 
- Sprite, Font, Image: differents resource type (3rd level)
- ImageData, MysteriousHeader, SpriteFrame: informations (4th level)

Just read __init__ methods, and especially "read()" functions which have prototype:

```
def read(identifier, description, (type, arg1, arg2, ...))
```


Haypo
## Post #7
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-01-02T16:06:31+00:00
- Post Title: Worms2 file format and Hachoir program

> Reply from haypo
>
> Mr.Mouse wrote:We should talk
Here my addresses:
http://www.haypocalc.com/wiki/Victor_St ... _contacter
Mr.Mouse wrote:there might be a MultiEx script<->Hachoir conversion routine possible.  
Yep, sure, it's always possible.

Haypo

I'll be in touch.
## Post #8
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-01-02T22:41:16+00:00
- Post Title: Worms2 file format and Hachoir program

I think i understand some of this - it was a bit confusing at first because the source on the webpage you gave above is not the same as the source of your program, and in fact the website one looks like it is missing a few lines.

Anyway, at the moment I see it as something like this...

```
| Worms 2 *.spr |
+---------------+

4 - Header (SPR + (byte)26)
4 - File Size
X - Filename (null)
4 - Unknown Constant (5292040)

// for (81)
  1 - Red
  1 - Green
  1 - Blue
  
1 - Unknown (174)
2 - Number Of Flags (1/2)
8 - null

// for each flag
  4 - Flag

4 - null
4 - Unknown Constant (7428)
2 - null

2 - X Position ? (0)
1 - null
2 - Y Position ? (1)
2 - Image Width
2 - Image Height
2 - Number Of Frames
1 - null

// for each frame
  2 - Size Of Control Characters?
  1 - Unknown
  2 - Unknown
  2 - Unknown
  2 - Unknown
  2 - Unknown
  1 - Size Of Changed Data?
  
2 - Extra Size To Make The Complete File
  
// for each Changed Block
  X - Data For The Change
  1 - null
```


It is a bit of a mix of things, so let me hopefully explain some of it here. And I know its alittle rough and whatever - I havn't really been strict in documenting it correctly at this point in time. 

I see several possibilities. ..

1. There are several frames, and the lower part of the file it like a script that tells the pixels that are to be changed with each frame. Each "script" block is terminated with a null byte, so if there are 36 nulls (as in the file I was looking at - arrowdnb.spr), there are 36 frames.
2. The sprite is just a single image, because the lower part of the file has the same number of bytes as (width-X * height-Y) - but this could be just coincidental
3 - If you add up the values in the loop labled "Size Of Control Characters" and "Size Of Changed Data" for each of the "frames", you get the size of the data following the "frames" directory, so maybe these 2 fields both somehow reflect things that I used for the description names
4. The other 2-byte field in the "frames" directory are probably just as before - X,Y,W,H

I see the whole thing being a little like a GIF animation image - you would start off with 1 single frame, and then for each frame following you only store the changed pixels rather than each frame in its completeness.

Hopefully some of this helps - you might be able to make some suggestions or something based on whatever you know about the format or the game.

Like I said - hope it helps!

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #9
- Username: haypo
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jan 02, 2006 8:42 pm
- Post datetime: 2006-01-03T00:34:56+00:00
- Post Title: Worms2 file format and Hachoir program

> Reply from friendsofwatto
>
> I think i understand some of this - it was a bit confusing at first because the source on the webpage you gave above is not the same as the source of your program, and in fact the website one looks like it is missing a few lines.
You speak about Hachoir's source code? There are a lot of versions. Last stable release is 2005-12-28. But most interesting version is the last one : you have to use SubVersion (works like CVS, do you know it?).

I worked a lot with lodesi (a friend) on Worms2 file format. Here is my informations about the format.

```
| Worms 2 *.spr |
+---------------+

4 - Header (SPR + (byte)26)
4 - File Size
X - Filename (null)
1 - Bits / pixel (bpp=8)
1 - Unknow constant (192 for sprite or 128 for others resources)
2 - Number of colors (nb_colors)

// for (nb_colors)
  1 - Red
  1 - Green
  1 - Blue
  
2 - Number of mysterious headers
2 - null ?
// for (nb_colors)
  2 - a ??? (a=0 ?)
  2 - b ??? (b=0 ?)
  2 - c ??? (c=0 ?)
  2 - d ???
  2 - e ??? (e=0 ?)
  2 - f ???

2 - X
2 - Y
2 - Image Width
2 - Image Height
2 - Number Of Frames

// for each frame
  1 - a ???
  1 - b ???
  1 - c ???
  2 - X
  2 - Y
  2 - Width
  2 - Height
  
X - ***DATA***
1 - Separator (sep=26)
```


Here is the data of a picture: 640x480 pixels, 80 color, only one frame. Can you help me to understand which compression method was used?

```
  16: FF 84 27 4D 84 D8 FF 85 28 FF 86 A6 4D 87 49 FF
  32: 87 B7 FF 86 BB 4D 87 52 FF 87 AE FF 86 CC 4D 87
  48: 57 FF 87 A9 FF 86 DA 4D 87 5C FF 87 A4 FF 86 E6
  64: 4D 87 5F FF 87 A1 FF 86 F2 4D 87 64 FF 87 9C FF
  80: 86 FB 4D 87 65 FF 87 9B FF 87 04 4D 87 68 FF 87
  96: 98 FF 87 0B 4D 87 6A FF 87 97 FF 87 13 4D 87 6C
 112: FF 87 FF FF 82 26 4D 87 6E FF 87 FF FF 82 2A 4D
 128: 87 6F FF 87 FF FF 87 91 30 87 E3 3A 87 70 FF 87
 144: 90 FF 87 28 1E 87 71 FF 87 FF FF 82 36 4D 87 72
 160: FF 87 FF FF 82 39 4D 87 74 FF 87 FF FF 82 3C 4D
 176: 87 75 FF 87 FF FF 82 3E 4D 87 76 FF 87 FF FF 82
 192: 40 4D 87 77 FF 87 FF FF 82 42 4D 87 77 FF 87 FF
 208: FF 82 44 4D 87 78 FF 87 FF FF 82 45 4D 87 79 FF
 224: 87 FF FF 82 46 4D 87 7A FF 87 FF FF 82 47 4D 87
 240: 7B FF 87 FF FF 82 47 4D 87 7B FF 87 FF FF 82 48
 256: 31 80 00
```

Ideas about "changed pixels" is interresting. I will check it after understanding basic picture encoding 

Haypo
## Post #10
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-01-03T01:47:34+00:00
- Post Title: Worms2 file format and Hachoir program

Yeah, I was referring to the source for that program. I kinda know what CVS etc is and how it works, but i've never really used it. Never mind, thanks for completing the specs for me 

I will take a look at the sample image you draw above - see if I can pick something out of it. It would have to be very good compression if thats a full 640x480 image!

Some common image compressions are based on RLE encoding - basically just replacing duplicates with a control character that says "repeat X times". For example, instead of actually storing the hex FF FF FF... FF 640 times (if the first line was all the same color), it would just write something equivalent to 640 FF - thus using 2 bytes instead of 640 bytes. Chances are the compression would be like this, but I am still amazed at the size of the compressed data. If it only stores the "changed data" like I initially thought, then compression could be quite good because there would be many lines that are just empty with the same value (like all FF's or something), indicating that this data was the same as the previous frame - that would compress heaps, as in my above example. I know they did this kind of thing in The Sims image sprites (SPR_SPR2).

If you want to read up about RLE encoding - the best place to start would be googling about the RLE compression in BMP images - BMP images are really easy to learn, and there are heaps of resources on the net about them. It would probably be a bit advanced to look at the specs for the The Sims sprites, but it you want to you can take a look - the website can be found on SourceForge - its called something like The Sims Technical Resource.

Good luck. I will see whether I can determine anything from the hex you posted.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #11
- Username: haypo
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jan 02, 2006 8:42 pm
- Post datetime: 2006-01-03T04:17:15+00:00
- Post Title: Worms2 file format and Hachoir program

> Reply from haypo
>
> Here is the data of a picture: 640x480 pixels, 80 color, only one frame. Can you help me to understand which compression method was used?
HEY! The picture is 640x28 pixels, not 640x480 ... sorry. I think that it's possible to store 640x28 in 259 bytes 

Haypo
## Post #12
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-01-03T05:37:13+00:00
- Post Title: Worms2 file format and Hachoir program

Im sorry to interupt this. but i dont think it is possible
to store a 640x28 picture in just 259 bytes. if its not totally black
or just 1 color. not even with a very good compression.

It wouldnt just work, too much information have to be discarded.

anyone agree with me , or am I the party-destroyer here to today? =(
## Post #13
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-01-03T05:47:39+00:00
- Post Title: Worms2 file format and Hachoir program

To explain what i mean, i made a very simple 1 bitplane picture in
640x28 and using GIF (LZW compression , which is far better than RLE encoding), and i dont even think that "changed data" compression
will achive such incredibly low bitrates.

=o
[NamnlÃ¶st-1.gif](https://xentaxbackup.github.io/file/543_NamnlÃ¶st-1.gif)
## Post #14
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-01-03T06:01:15+00:00
- Post Title: Worms2 file format and Hachoir program

Something interesting, though. when restructuring the data of the above "640x28" picture it looks like this.

138001
C50080
01BD81
A8C782
6AFF82
96FF84
274D84
D8FF85
28FF86
A64D87
49FF87
B7FF86
BB4D87
52FF87
AEFF86
CC4D87
57FF87
A9FF86
DA4D87
5CFF87
A4FF86
E64D87
5FFF87
A1FF86
-------
etc etc
last block
318000


notice how the numbers are made in 3 byte blocks.
the middlebyte are almost always FF or 4D
and the last byte is 80 or over up to 87.

first block 138001
last block 318000

also some strange similarity.

I dont know what this meens, but i thought it could help you
in some odd way =o
## Post #15
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-01-03T12:26:57+00:00
- Post Title: Worms2 file format and Hachoir program

640x28 - that sounds much nicer 

In regards to storing this amount of data in the small number of bytes - it could still be possible if the image is mostly a single color, or a transparency (as I suspect is probably the case).

In regards to the arrangement in 3-byte groups - that could obviously map directly to a pixel encoding like RGB or a bit-mapped variation to include an alpha. However, it is probably not the case (i also think you said that there is a palette, which means this would almost definately be wrong). My guess at the moment is that these "middle" values would be the control characters for an RLE-like compression, and the bytes either side could be some grouping of pixel values.

Thanks for putting forward some ideas - i would be interested to see whether the "middle" byte you found actually means something!

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #16
- Username: haypo
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jan 02, 2006 8:42 pm
- Post datetime: 2006-01-03T15:21:25+00:00
- Post Title: 

New informations!

My "mysterious headers" are "steps". One animation contains one to six (or more ?) steps. Example with 9 frames and 3 steps:
* Image => 50x50 pixels at (0,1) => 50x49 pixels ?

* Step 0 : size=6808
* Step 1 : size=6400
* Step 2 : size=4560

* Frame 0 : size=40x40 (bytes), offset=0, step=0
* Frame 1 : size=40x40 (bytes), offset=1600, step=0
* Frame 2 : size=40x40 (bytes), offset=3200, step=0
* Frame 3 : size=44x42 (bytes), offset=4960, step=0 ~~~> 4960+44*42 = 6808

* Frame 4 : size=44x44 (bytes), offset=0, step=1
* Frame 5 : size=48x46 (bytes), offset=1936, step=1
* Frame 6 : size=48x47 (bytes), offset=4144, step=1

* Frame 7 : size=48x48 (bytes), offset=0, step=2
* Frame 8 : size=48x47 (bytes), offset=2304, step=2

---

AND ... Another way to see raw data is to split them when bit 7 is set.

Resource  56 : 60x60 pixels at (0,1) => 60x59. Each frame is 8x8 bytes (34x34 pixels at (26,26)) :

```
88 00 00                                 - (  8)    0    0
88 06 10 0D 0A 0A 0D                     - (  8)    6   16   13   10   10   13
88 06 11 0A 32 32 0A 0D                  - (  8)    6   17   10   50   50   10   13
A0 07 0F                                 - ( 32)    7   15
90 07 0D 0A 0F 10                        - ( 16)    7   13   10   15   16
98 07 0D 11 10                           - ( 24)    7   13   17   16
90 20                                    - ( 16)   32
88 1B                                    - (  8)   27
98 30                                    - ( 24)   48
A0 37                                    - ( 32)   55
C0 3F                                    - ( 64)   63
88 00                                    - (  8)    0
98 3F                                    - ( 24)   63
88 25                                    - (  8)   37
90 2F 10 0D 20 1C 0B                     - ( 16)   47   16   13   32   28   11
90 2B 0D 32 32 22                        - ( 16)   43   13   50   50   34
90 64 10 4B 22                           - ( 16)  100   16   75   34
98 60                                    - ( 24)   96
98 27                                    - ( 24)   39
80 40 07                                 - (  0)   64    7
90 79                                    - ( 16)  121
88 67                                    - (  8)  103
90 66                                    - ( 16)  102
90 43                                    - ( 16)   67
88 56 20 32 50                           - (  8)   86   32   50   80
98 7F 1C 32 22                           - ( 24)  127   28   50   34
98 7F 0B                                 - ( 24)  127   11
90 46                                    - ( 16)   70
80 80 01                                 - (  0)  128    1
98 97                                    - ( 24)  151
B0 A7 0D 10 0F 0A                        - ( 48)  167   13   16   15   10
98 07 0F                                 - ( 24)    7   15
88 CD                                    - (  8)  205
90 4F                                    - ( 16)   79
90 D5                                    - ( 16)  213
98 BF                                    - ( 24)  191
88 E5                                    - (  8)  229
80 C0 0A 0A 22 4B                        - (  0)  192   10   10   34   75
98 BF 22 32 32                           - ( 24)  191   34   50   50
98 BC 0B 32 4E                           - ( 24)  188   11   50   78
98 87                                    - ( 24)  135
A8 97                                    - ( 40)  151
80 C0 08 0A 22 0B                        - (  0)  192    8   10   34   11
98 BF                                    - ( 24)  191
88 38                                    - (  8)   56
98 BF 50 32 4E                           - ( 24)  191   80   50   78
A0 BF                                    - ( 32)  191
90 FA                                    - ( 16)  250
A8 D5                                    - ( 40)  213
80 40 00                                 - (  0)   64    0
80 00                                    - (  0)    0   *** End marker (0x80 0x00)
```

EDIT: Value in parenthesis is first byte AND 127 (0x90 & 127 => 16).

Haypo
## Post #17
- Username: haypo
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jan 02, 2006 8:42 pm
- Post datetime: 2006-01-03T15:41:52+00:00
- Post Title: 

Some ideas:
- I think that friendsofwatto was right : first frame is "complete" (using RLE compression?), and next frames are "pixels which have changed". But where is the transparency ?
- In first frame, we can see colors : values in 0..(nb_color-1)
- In next frames, we can see values >= nb_color
(nb_color = 80 in 99% of sprites)

Haypo
## Post #18
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-01-03T19:50:41+00:00
- Post Title: 

The animations are 50x50  (around) and not 640x28?

that would make it much more probable to go with the "changed data" compression =o

another strange approach would be that One byte is X, and next is Y
and the third is the Color of the changed pixel.
but now im just theorising. the only way to achive good compression
with that scheme would be if the frames have very few changes in them
between frames.
## Post #19
- Username: haypo
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jan 02, 2006 8:42 pm
- Post datetime: 2006-01-03T20:32:30+00:00
- Post Title: 

> Reply from Strobe
>
> The animations are 50x50  (around) and not 640x28?
No, I was speaking about another sprite. Please try the Hachoir, it's hard to copy/past a lot of numbers here  (I already gave command to try the Hachoir, read above)

Haypo
## Post #20
- Username: haypo
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jan 02, 2006 8:42 pm
- Post datetime: 2006-01-03T20:58:12+00:00
- Post Title: 

Hey, I found pictures there:
[http://www.angelfire.com/games4/striker ... /Anims.zip](http://www.angelfire.com/games4/striker_002/downloads/Anims.zip)
(lot of animated GIF files, maybe extracted with screen capture ?)

And they are maybe something interestring here:
[http://www.angelfire.com/games4/striker ... s/sdk4.zip](http://www.angelfire.com/games4/striker_002/downloads/sdk4.zip)
(lot of GIF but non animated)

Haypo
## Post #21
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-01-03T21:20:39+00:00
- Post Title: 

Its not about not being able to test Hachoir,
its me not having Worms 2 ;D

so im just theorising here on what you write here 
for the moment. i might be able to download some worms 2 files
next weekend though when im home again. =)
## Post #22
- Username: haypo
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jan 02, 2006 8:42 pm
- Post datetime: 2006-01-03T21:37:32+00:00
- Post Title: 

> Reply from Strobe
>
> Its not about not being able to test Hachoir,
its me not having Worms 2 ;D

Download Worms2 demo:
[http://www.worms2.com/main.html?page=go ... emo&file=3](http://www.worms2.com/main.html?page=good&area=demo&file=3)

You will find Gfx.dir in data/ subdirectory.

Here is another Gfx.dir file (file size are quite the same):
[http://www.haypocalc.com/tmp/Gfx.dir](http://www.haypocalc.com/tmp/Gfx.dir)

Haypo
## Post #23
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2006-01-03T22:53:56+00:00
- Post Title: 

OK, this is looking good - glad you figured out the frames 

In regards to "transparency", I don't actually mean that it is transparent. What I was actually referring to was, if the frames only stored the "changed" data, then the data that is not changed for that frame is thus transparent. 

Think of it like this - you first build the complete first frame. Then, for the remaining frames, you just copy the previous frame and put the new "changed" pixels over the top. All the "unchanged" pixels are the same as overlaying a transparent pixel at that position.

Now, if it really does only store the changed pixels, then I will propose that it probably uses an encoding similar to the The Sims one I mentioned previously. I will try to explain its technique here. (note that the byte values I use below are not correct, because I can't remember them, but I am only trying to describe the technique)

The encoding went line by line through the image. It uses single-byte control characters that tell what to do next. For example, the main ones were...

"L" means that the entire line was unchanged (ie skip to the next line)
"T#" meant the start of the next line, and the next # bytes are unchanged
"E" meant the end of the line.

So, if you had a line with 10 unchanged, 2 changed, and 14 unchanged, it would be encoded as follows...
"T10", then the 2 pixel values, then the "E" indicating to go to the next line (the rest of the line is unchanged)

If there were unchanged pixels in between the changed pixels, they would just use the palette index for the transparent color (which I think you said was index 80).

For example, if a line was 10 unchanged, 2 changed, 5 unchanged, 4 changed, and 14 unchanged, it would be stored as...
"T10", then the 2 pixels, then 5 pixel values of "80", then the 4 pixels, and the "E" marker.


This worked well for The Sims because all the images had the same maximum dimension, and if the image was smaller than the maximum it would be placed in the middle of the dimension, meaning that there was always a lot of unchanged lines, and a lot of unchanged data to the left and right of each image.

The encoding for Worms 2 will probably be something along these lines.

Hope this helps.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #24
- Username: des
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Feb 10, 2006 7:48 pm
- Post datetime: 2006-02-10T11:53:47+00:00
- Post Title: 

This is a .dir viewer for worms armageddon -- it opens the worms 2 gfx.dir file as well and extracts .spr .img or .fnt files from it but i dont know how to use any of them once i extract them... 

It may not work right for w2 since it was made for W:A  -- it does throw an error when i select a .IMG file from the gfx.dir but it doesnt shut down the program and i can still extract a .IMG.

Anyway -- Let me know if this is usefull 
[WASpriteEditor.zip](https://xentaxbackup.github.io/file/607_WASpriteEditor.zip)
## Post #25
- Username: des
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Feb 10, 2006 7:48 pm
- Post datetime: 2006-02-10T11:55:23+00:00
- Post Title: 

I opened this file in PE Explorer and there is some code viewable in the resource editor -- maybe that information will help for w2 also -- let me know if it does or if i am just wasting your time. Thanks! :p
## Post #26
- Username: des
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Feb 10, 2006 7:48 pm
- Post datetime: 2006-02-10T12:03:34+00:00
- Post Title: 

[http://www.computerhead.biz/gfx.zip](http://www.computerhead.biz/gfx.zip)

Here is the gfx.dir from Worms 2 full  -- the link to the gfx.dir file above doesnt seem to work so if anyone needs it here it is
