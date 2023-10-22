## Post #1
- Username: Malachi
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-08-10T16:54:50+00:00
- Post Title: Requiem: Avenging Angel

Does anybody know in which format are textures from this game?
My guess is that the textures are stored in three *.art files
with the accompaning *.dat files (which contain texture & skin
offsets) but textures (once extracted) are in, to me, unknown
format. Does anybody has any clue to format of these textures?

Thanky in advance!

PS. Sorry for my lousy english.
## Post #2
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2004-08-11T14:08:38+00:00
- Post Title: Requiem: Avenging Angel

Hi there,

If it is unrecognisable to you, then chances are it is probably something the game developers created - for some reason game developers tend to like making up their own image formats.

All I can suggest at the moment it to ensure they are not a generic format. Can you find any file names that let you know the type of file? Are the first few bytes of the image file a group of letters? Are the letters BM (*.bmp) or JFIF (*.jpg)?

If not, then the only thing I can suggest is to try and figure out the format yourself. Somewhere in the start of the file you would probably find a list of 3-byte color values - most game images are only stored as 256 colors or less, especially if the image format is not standard. You should also see some header information outlineing things like the number of colors, the width, and the height of the image.

The pixels are probably going to be the hardest to figure out. One format, the easy one, is just listing all pixels one at a time (raw format), where each byte represents a color in the palette. Another common type is a run-length encoding strucutre - there are many variations but basically it will start off with a number telling you how many pixels are of the next color (for example, the bytes 3,14 would indicate that the next 3 bytes of the image use the color 14, where 14 is a color specified in the color palette).

You could attach an image file to the forum here and we could take a little look at it - maybe we will get lucky  - The good thing is, usually image files are not *too* difficult to figure out.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #3
- Username: Malachi
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-08-12T01:51:22+00:00
- Post Title: Requiem: Avenging Angel

As I said earlier, the games comes with three texture packs, for Direct3D, Glide and Software rendering. I will focus on Direct3D pack.

I've prepared three files, you can download them here:
[http://www.geocities.com/mikimaus69/requiem/](http://www.geocities.com/mikimaus69/requiem/)

The zip file contains extracted two textures from ReqArtD3.art, and the two jpegs are the screenshot of these two textures obtained by modifying ReqArtD3.dat file which contains offsets. And the most likely dimensions of these textures are 128x128 pixels.

Also here is my guess for the header (start at least):

LONG - Uncompressed file size?
LONG - Unknown
LONG - Compressed file size minus 8 Bytes, in other words, LONG + 8 Bytes = File size

The rest is unknown to me. Also I think that textures are compressed beacause of varying file size.

There are no file names of textures in the game (at least I couldn't find them), I think all is done through offsets.
## Post #4
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2004-08-13T14:14:25+00:00
- Post Title: Requiem: Avenging Angel

OK, thanks for that, I will take a look at them and see what I can pick out that may be of use.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-08-13T14:23:45+00:00
- Post Title: Requiem: Avenging Angel

I looked at it and had no luck matching it with known compression. The header as presented is probably true, but the rest is a mystery to me. 

I went through the executable and noticed there's a function being called: "LoadTexture()". I know, because it's in the text of an error message. In another message there's :"LoadTexture(): TexBits() not set. " 

Beyond that, I haven't got a clue yet.
## Post #6
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2004-08-14T11:55:40+00:00
- Post Title: Requiem: Avenging Angel

Well this is what I could determine.

1 - the images are most probably 128x128, as you suggested
2 - the image is paletted, but if the palette is included in each image then the images don't use all 256 colors available (the 2 images you gave would have about 170 colors)
3 - It is possible that the image is simply split apart by single bytes indicating the number of following bytes to copy - I havn't confirmed this fully but I have been able to jump around abit using this. Basically you read a byte, read that number of bytes - 1, then repeat again.
4 - the bytes are to be read as big-endian numbers

I can't really help any more than this though, hope it helps.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #7
- Username: Malachi
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Aug 12, 2004 9:53 am
- Post datetime: 2004-08-14T17:35:05+00:00
- Post Title: Requiem: Avenging Angel

Thank you both!

I will use your information and try to make something out of it, and I will post if I find out something new.

Bye
## Post #8
- Username: Malachi
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Aug 12, 2004 9:53 am
- Post datetime: 2004-08-14T18:38:17+00:00
- Post Title: Requiem: Avenging Angel

friendsofwatto, I've tried your method but I can't get it to work and produce something usefull. Could you please elaborate a bit more your method?

Anyway, I was poking around dat file to see if I can find some simpler textures, and I came across couple of textures which seem to be coloured with single colour. Here are the samples:

[http://www.geocities.com/mikimaus69/req ... 350000.jpg](http://www.geocities.com/mikimaus69/requiem/RAA-38350000.jpg)
[http://www.geocities.com/mikimaus69/req ... 310000.jpg](http://www.geocities.com/mikimaus69/requiem/RAA-3B310000.jpg)
[http://www.geocities.com/mikimaus69/req ... quiem2.zip](http://www.geocities.com/mikimaus69/requiem/requiem2.zip)

Also they only differ in 2 bytes, so they might be more usefull then prevous textures. I will continue my work, and report further progress.

Bye (for now   )
## Post #9
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2004-08-15T04:49:39+00:00
- Post Title: Requiem: Avenging Angel

OK, thanks for posting the better images - hopefully it will make things alittle easier - i already tried to compare the other 2 images you supplied because the first 30-ish pixels are roughly the same, however I didn't have much success.

Oh, and don't worry about my method - it probably doesn't work - i don't see why someone would do it the way i described anyway because it just seems totally illogical.

I will report any progress. Good luck.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #10
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2004-08-15T14:44:25+00:00
- Post Title: Requiem: Avenging Angel

Well I took a look, unfortunately it hasn't helped much though  . I cannot see why there are 2 different bytes between the files - most obviously you would assume it has something to do with the different colors, however I can't see any combination around those bits that would alter the image from red to orange. Also, the bits that differ are only off by about a value of 4, so that can't solely change the color by such a large amount.

The bits towards the end of the file are really confusing - it seems as though there may be about 224 colors set in the palette at the top, however the user is free to define alternate colors if they aren't in the palette. For example, you will notice groups of about 8 characters that look to me like 1 byte telling the number of pixels of that color, followed by a 3-byte color value. However, if you take note of the bit positions between these 8 repeating bytes, you will notice that they increment or decrement by a single byte, in pairs. For example, going up is 1, 3, 7, etc. with the values separated by a single byte, where the separator bytes go down 252, 248, 240, etc. ie. the bytes go 1 252 3 248 7 240 ... or something like that. This to me seems very odd, and I cannot figure out why this is so, unless they are the 4-byte number:RGB pattern i described.

So like I said, I don't think I have progressed any further. I have moved into a state of uncertainty over whether they are little-endian or big-endian stored (obviously the first 16 bits are little-endian).

I hope I have given you some ideas that may help, other than that I don't think I can help any further. Sorry, and good luck! I will be happy to hear of any progress.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #11
- Username: Malachi
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Aug 12, 2004 9:53 am
- Post datetime: 2004-08-15T18:42:33+00:00
- Post Title: Requiem: Avenging Angel

Thank you for your effort.

I will keep trying to get something out of it. 

Bye
## Post #12
- Username: y2keeth
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Sep 19, 2021 5:36 pm
- Post datetime: 2022-10-10T07:59:16+00:00
- Post Title: Requiem: Avenging Angel

watto did figure out how to extract the textures but cannot figure out the art files compression to put modified ones back into the art file
here are the d3d art file textures now if someone could figure out  how to get them back into the art file that would be awesome
that and the requiem .mdl model format

[https://drive.google.com/file/d/1AZhXHj ... sp=sharing](https://drive.google.com/file/d/1AZhXHjtESFmNqHy6kO3zzoW9NIha12zU/view?usp=sharing)

by the way they are .tex files in the art file with game extractor  i converted to .png
## Post #13
- Username: guardianlamppost
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Aug 02, 2022 8:09 pm
- Post datetime: 2022-10-27T18:44:42+00:00
- Post Title: Requiem: Avenging Angel

You should probably be able to compress textures with the ttdecomp-library and place then back in the art-file, updating all the offsets in models3.txt. 

[viewtopic.php?f=10&t=25663](https://forum.xentax.com/viewtopic.php?f=10&t=25663)

Haven't tried it yet though
