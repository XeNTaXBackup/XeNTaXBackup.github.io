## Post #1
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-05-10T02:53:39+00:00
- Post Title: I.M.Meen (1995 PC/DOS) CMP format

Alright, thanks to Bugtest I was able to extract these files.

The images are: CMP (I thought Colormap for a moment but this seems not to be the case as they contain actual image data.)

Thanks, this is the last thing needed to be dealt with in my plans I believe. Any lossless format conversion works as I've got a tool for dealing with TGA, PCX, PNG, BMP.
[CMPs.rar](https://xentaxbackup.github.io/file/2022_CMPs.rar)
## Post #2
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-05-14T01:48:30+00:00
- Post Title: I.M.Meen (1995 PC/DOS) CMP format

Anything discernible found? I think each image has a palette since I've found no palette elsewhere.
## Post #3
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-05-17T04:50:48+00:00
- Post Title: I.M.Meen (1995 PC/DOS) CMP format

Some of them seem compressed. Not sure exactly.
## Post #4
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-05-19T00:10:30+00:00
- Post Title: I.M.Meen (1995 PC/DOS) CMP format

Okay, gotten a little closer, it may be a variation of BMP or PCX, not exactly sure.
## Post #5
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-05-21T00:00:30+00:00
- Post Title: I.M.Meen (1995 PC/DOS) CMP format

Here's some stuff I've discovered, not much I know but it gives a visual aid.
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-05-21T06:56:46+00:00
- Post Title: I.M.Meen (1995 PC/DOS) CMP format

Making good progress there Darkfox!
## Post #7
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-05-23T15:07:29+00:00
- Post Title: I.M.Meen (1995 PC/DOS) CMP format

Great progress, no doubt!

I'll try to help you with some general advise for palette image formats, as I'm a bit busy to analyze those files right now.

First of all, take (if you can) a screenshot of the game, in a lossles-compression format, like tga, being this format very simple. Then, and with the help of an hex editor, go comparing how each tga pixel is represented in the unknown format. In this process, you can find very  relevant info.

Furthermore, if the format uses some kind of compression (which is very common in palette-based games from those years) there may be some special codes for doing certain operations. Maybe 0 represents filling the width*height of the image with a colour (or transparent), 128 end of a row, some codes for managing transparencies, another one for representing m-n pixels of m colour... You can imagine other codes and see them in the hex editor.

And last but not least: When you find where is the palette data stored, if you haven't done so yet, just notice that it may be not the "real" colour, but a value that has to be fixed, for example multiplying it by a constant (or any other operation). You can see this if the bytes oscillate between 0-50 or any other suspicious values.

So, if you have the right pixels but bad colour, try playing around that. In my experience, I had to multiply by 4 all values in a KB.pal palette, to get the right colour and not a messed thing like that on your image.

Nothing more, I think. I'll see that files a minute and if I find something I'll tell. As I've said, don't have much time. But keep up this, as you're very near to the solution.

Cheers!
## Post #8
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-05-23T15:43:26+00:00
- Post Title: I.M.Meen (1995 PC/DOS) CMP format

Well, I took a fast look with the hex to the files, but only found a large header, with values including widht/height among other motley data. 

As I previously recommended, to solve this problem it will be very handy to have the equivalent of the image already in a uncompressed format. I think the image you posted before is this one:



(Correct me if I'm wrong)

Anyway, we still need to know which of the cmp's is that image from. Maybe BOY0.CMP ?¿

Once we know, and if everything correct, we can start decoding, or at least, guessing.

See you.
## Post #9
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-05-23T19:17:13+00:00
- Post Title: I.M.Meen (1995 PC/DOS) CMP format

Oh hey! I'll do that right now. I'll snag a screenshot of the face graphic.
[MeenFaces.png](https://xentaxbackup.github.io/file/2054_MeenFaces.png)
## Post #10
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-05-23T20:58:19+00:00
- Post Title: I.M.Meen (1995 PC/DOS) CMP format

That's great, now what image is that? I mean, what CMP does it represent, to start the investigation.

(I converted it to tga for simplicity purposes)

The first thing to do now is to search the image's widht and height in that CMP so we better understand the header.
## Post #11
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-05-23T21:49:25+00:00
- Post Title: I.M.Meen (1995 PC/DOS) CMP format

The face to the leftt is the boy's face, BOY0.CMP, the right is the girl, GIRL0.CMP.
## Post #12
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-05-23T21:52:08+00:00
- Post Title: I.M.Meen (1995 PC/DOS) CMP format

Me again!

I see we're getting somewhere. The images you attached are 56*73 (the girl one 55*73 because of the missing right line, you can see if you zoom on the image)

And the first values of the header from boy0.cmp and girl0.bmp go as this:
R...8.>.
Z...8.>.

Oka, what it means:

4 bytes -> 3674 for girl0.cmp (or 90) and 3666 for boy0.cmp (or 82).  ¿Some kind of signature? In boy1.cmp is 90, again. Still investigating.
2 bytes -> It seems to be always 56. WIDTH.
2 bytes -> It seems to be always 62. HEIGHT. (But not matching with the images you attached!!!)

More interesting data I've found: Both boy0.cmp and girl0.cmp start and end with 56 zeros as this:
000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000

Graphically, this matches as you can see a single-byte line of the same colour at the top and under the image. I think we've identified the frame!  

Supposing this is correct, we also have delimited when the header ends. But this may be chance, we have to make further checks, because neither 56*73 nor 56*62 give us the number of bytes in the body. This can be because of some compression. I dunno yet.

But I think this is correct, and that we've identified how does it manage single pixels.

Anyway, with a header of 206 bytes and maybe compression this has just started. I think palette has to be placed along with the header.

I hope this will be useful, will take another look when I have time.  

And as always, excuse my english. It must be very hard to read all of that! LOL How much errors per line? New record maybe? hehe

Until next time!
## Post #13
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-05-23T21:53:20+00:00
- Post Title: I.M.Meen (1995 PC/DOS) CMP format

Yeah, thx for the answer, but I've already supposed so! hahahah
## Post #14
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-05-23T23:35:45+00:00
- Post Title: I.M.Meen (1995 PC/DOS) CMP format

What do you mean?
## Post #15
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-05-23T23:51:38+00:00
- Post Title: I.M.Meen (1995 PC/DOS) CMP format

Finally, structure unveiled. So this is what I mean:

unsigned long CMPSize-4
unsigned short Width
unsigned short Height
unsigned short Unknown
unsigned char Unknown
unsigned char Palette[m] (where m is 3*numberofcolours, I guess, but not yet discovered how is numberofcolours indicated)
unsigned char Pixels[n] This are the actual pixels, each byte represents a number which determines colourPosition like this: Pixel[n] * 3 + 11 (Header) 

Right now I'm coding a viewer. I'll attach it when I finnish.

As you can see, there's still some gaps to fill. How is the size of the palette determined, and how does the palette exactly manage colours. I think we can fix that.

Good night!
## Post #16
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-05-24T00:08:06+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

Oh, hey, thanks. XD Maybe we'll be able to crack the IMG format too. I plan to update soon on that and show the corresponding texture images as I find them ingame. This will be fun once it is cracked. The only things that are unconvertable currently are the IMG files and CMP.

But yeah, thanks for the help! Ever since I saw this goofy game (made by the same people who made CD-i Zelda) I've been wanting to access the game sprites and textures. The game uses WAVs, and midis, and PCXs, but for smaller graphics and textures they use a proprietary format, CMP and IMG, which looking at it now, the IMGs are structured similarly to the CMP so cracking this will allow IMG to fall in place.
## Post #17
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-05-24T01:28:18+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

Oka! So cracking this format will be more than al half of the work!  

This time I come with substantial updates hahaha I've attached a tool for viewing cmp!

It has some lacks, yet. Because of palette size indicator not discovered, it only opens the cmp which I include in the zip. But this is a matter of time: the algorithm works with any file. Furthermore, I didn't include a "file selector" for time reasons. If I don't find the way to know this pallete size indicator, I have in mind an algorithm that can guess it right. The problem is that is not an easy algorithm (it has to read all pixels of the image and compare them to get the higher-value one, this*3 determines the palette size). As you can guess, this is an expensive operation and it's not the best way to go.

The other lack is the colour. It's messed up. The pixels are all in their places but you can see the colour is not correct. I can't understand this yet. The palette has to be RGB 3 byte per colour, but interpreted like this it just messes up. I dunno if it's strangely fixed or upside-down... I think this is our biggest problem now: to guess how is the colour stored.

I'll continue working in this interesting topic whenever I have time. If you make any discoverie, just post to keep us working efficiently.

Well friend, time to sleep. bye!
[CMP Viewer.zip](https://xentaxbackup.github.io/file/2055_CMP Viewer.zip)
## Post #18
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-05-24T02:45:54+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

Thanks, I hope we can crack this. You've been an awesome help! I'll test out this viewer and tell you how well it works.
## Post #19
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-05-24T09:04:33+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

You're welcome!

Someone has to figure how is the colour indirected. It's pretty sure that this is not done by simple using 3 bytes one for each colour, because I've searched many colours from the "screenshot" in the cmp and didn't found any matches. This also indicates that the structure may be this one:

unsigned long CMPSize-4
unsigned short Width
unsigned short Height
unsigned char Palette[m] (where m is 3*numberofcolours, I guess, but not yet discovered how is numberofcolours indicated)
unsigned char Pixels[n] This are the actual pixels, each byte represents a number which determines colourPosition like this: Pixel[n] * 3 + 11 (Header) 

Thus, the 3 "unknown" bytes dissapear and are part of the palette. The question is how does this palette represent colours... a palette which sometimes is not multiple of 3!

Maybe I'm not in the point. We'll have to play a bit more around the hex editor an see if we can any idea of using colour, so we can test it with the tool.
## Post #20
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-05-25T00:47:04+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

Well, I've yet to run into anything consistent of an external palette so it must be part of the image. I'll see if I can dig up more.

I guess I'll have to tinker with this with a hex editor and see what happens.
## Post #21
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-05-25T00:58:33+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

Great, as you say, the palette could be outside there. Anyway I think that the palette is actually what we think the palette is, but may be encrypted or compressed.

So, I continue making experiments with the hex editor. I wouldn't like to leave now when 80 per cent of the work is done.

I have to say that it has been lot of fun cracking this format, and it's still annoying us heheh

Very particular way of representing palettized image data, sure.

Best regards!
## Post #22
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-05-25T01:20:23+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

I counted out an external palette as I could find none.

Now I'm just throwing this out here.but could the palette be RIFF encrypted?

The ANI files (not to be confesed with animated cursors, this is a yet-to-be decrypted video format), these contain an RIFF encrypted palette. Could this also be the case with these?
## Post #23
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-05-25T02:03:00+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

It could be any kind of encryption/compression, except RLE which I already tested. The bytes don't seem to be inverted, either.

Unfortunately, I don't know what do you mean with "RIFF compression". I thought RIFF was an audio/video format in which wav/avi is based.

Anyway those files you mention with encrypted palettes may come handy!! If you can upload some...

Time to sleep (again)
## Post #24
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-05-25T04:35:06+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

There exists such a thing as a RIFF Pal. This file contains a RIFF pal. You can see it at the block that says "RIFF" then "Pal data" and make a comparison there.
[SC14.rar](https://xentaxbackup.github.io/file/2061_SC14.rar)
## Post #25
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-05-25T07:17:04+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

Thank you very much.

In a fast look now I've just awaken it seems this are the colours I was searching everywhere.

At least, I've seen 88 88 88 among others. Now I have to leave, but I'll check later if all the colours match, with my tool.

Great finding Darkfox!! see you!
## Post #26
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-05-25T16:58:35+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

Too much updates this time.

First, the good news: I've attached new version of the tool which can view any xxx0.CMP
Why not any other like BOY8.CMP? Because those CMP files of 1 KB (more or less) are slightly different: they have the same header described before, same palette (if that's truly the palette) BUT bytes are encoded. I think I've already found some codes like 80, 90 in hex.

It'll be easy to manage that when the palette is discovered, so I want to end with xxx0.CMP first.

The bad news: the supposed palette in SC14 doesn't match. I've only found a coincidence which was just product of randomness. I'd say that PAL there doesn't stand for palette, but for Phase Alternating Line, as we are talking of video. But this is just my speculation. I've also found in that video file som basic structure, and audio. What I'm pretty sure is:

4 bytes string -> Signature ANI.
4 bytes unsigned long -> FileSize+6
4 bytes string -> Signature HDR. (High Dynamic Range?)
Not much yet. As you can see, I have poor experience with video formats and don't know if I can further help you with that. Maybe much work on the hex + a captured stream will help us with this task in the future.

SUMMING UP:
-CMP0 FORMAT-
unsigned long CMPSize-4
unsigned short Width
unsigned short Height
unsigned char Palette[m] (variable size, unknown colours yet)
unsigned char Pixels[Width*Height] Each of these chars (bytes) has a range 0-255, so it represents a point of colour 0-255.
You can determine Pixels Position, even being the palette size variable, with this: (CMPSize+4)-(Width*Height) (As we started counting from the end of the file)  

-UPDATED TOOL ATTACHED

-DISCOVERED SOME CODE ROUTINES WITH CMPx FORMAT (80, 90 hex)- 

-SOME BASIC STRUCTURE KNOWLEDGE OF THE VIDEO FORMAT (Read above)

-I INCLUDE ALL MY FILES, SOURCES, RESOURCES, DOCS ABOUT FORMATS AND TOOL'S USAGE ETC...

That's all, 'til next time... 

Download (400 KB): [http://www.fileden.com/getfile.php?file ... 3/CMPs.zip](http://www.fileden.com/getfile.php?file_path=http://www.fileden.com/files/2006/12/25/553903/CMPs.zip)
## Post #27
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-05-25T18:38:50+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

Hey thanks!

PAL refers to palette, and hdr refers to header. I was just using that as a guess at what is making the palette so hard to read. But I realize the palette for the CMP files would have to have some RIFF identifier.

And I wasn't saying that was the palette. Just maybe the palette format. The ANI files would not contain a palette for the images, sadly.
## Post #28
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-05-25T19:16:01+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

> Reply from Darkfox
>
> PAL refers to palette, and hdr refers to header. I was just using that as a guess at what is making the palette so hard to read. But I realize the palette for the CMP files would have to have some RIFF identifier.

That's it. We'll have time to investigate about that topic later.

> Reply from Balder
>
> And I wasn't saying that was the palette. Just maybe the palette format. The ANI files would not contain a palette for the images, sadly.

I understand. I'll continue trying with what we have. This is almost finnished, I want to get those colours in the right way!

I'm a bit curious, what are you going to do with this resources? I saw "old" posts by you about other resources in this game.  

I'm sorry this is going so slow, but I can't concentrate only on this as I'll start exams very soon. I hope you'll have this cracked soon
## Post #29
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-05-26T01:29:28+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

Resuming with the colour thing... I have to update the CMP structure due to new findings in the last hours:

-CMP0 FORMAT- // This is applicable to all those CMP'S which are like xxxxx0.CMP and weight about 4KB

unsigned long CMPSize-4 // Image total size - 4
unsigned short Width // Image widht
unsigned short Height // Image Height
unsigned short pixelCompression // This is 00 for CMP0 (for other cmps it seems to take different values: 12, 14, etc)
unsigned short Unknown // This is height-1 for CMP0 (for other cmps it's value ranges, maybe related with compression)
unsigned short Unknown // This is 00 for the 3 CMP0 examples I have (for other cmps it ranges...)
unsigned short Unknown // This is widht-1 for CMP0 (for other cmps it's value ranges, maybe related with compression)
unsigned short numberOfColours // numberOfColours in the palette (65 for girl0.cmp 57 for boy0.cmp 11 for tablo0.cmp) 
unsigned char Palette[m] (Encrypted after header)
unsigned char Pixels[Width*Height] Each of these chars (bytes) has a range 0-255, so it represents a point of colour 0-255.

Note: You can determine Pixels Position, even being the palette size variable, with this: (CMPSize+4)-(Width*Height) 

Aside from that, I leave an example of the palettes:

Colour	RED 	GREEN   BLUE
0	        36	36	    16	
1	        84	84	    84
2	        72	72	    72
3	       100	92	    64
4	       132	124	    84
5	       148	144	    100
6	       168	168	    88
7	       184	184	    96
...
until 57

Encrypted one:
103 8 199                219 217 216                 93 92 91        89 96 95     88 176 218                 and so on!
               (These 3 numbers are suspicious)    (again)          Humm...

Now I'll try to find a pattern in all these... maybe some header info is involocrated in this encryption. Dunno yet.

These bytes are very suspicious of being colours, so I think we are on the right path. The previous problem was the header being bad, so I was analyzing the header instead of the encrypted palette. I hope it's right now, but I don't discard any future change, I don't like the 103 8 199 at all, cause it's supposed to be the first colour, and the first colour of the image has two componentes which are the same. But as I couldn't relate it to anything else it might be good like that.

You can make your own guess.

Finally, I wanted to aske you, if possible, for a TABLO0.CMP screenshot like the others. As the other two images are pretty the same, I cannot contrast it much. And, more important, this one has only 11 colours, so I can remake the palette easily and the dencryptation will be easier too.
If you don't know what "image" is in the game I can say: Configure my tool for viewing TABLO0.CMP. Execute my tool. You'll see what thing is it.

The one who thought about making a single palette for each image and encryt it after the header was totally MAD. That's all for now friend!
## Post #30
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-05-26T11:24:40+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

Ignore the previous post, I don't need TABLO0.cmp as I've already solved the problem with this format  

I can't write a full specification right now, but this evening, maybe before I'll do. The thing is that there's not encryption, but another indirection. That supposed palette on the header is not a palette but and index of colours which is refered by each pixel byte. That index of colours has as many bytes as colours used in the image, and are represented by a single byte from 0-255. This colours may be in other file common to all graphics, probably of 256*3 bytes. Or it may be a "normalized one". I think.

The unknown entries I posted before are probably margins.

Later I'll post the complete specification and maybe an updated tool.

'til then!
## Post #31
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-05-26T19:29:54+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

Final structure, for both CMP0 and CMPx formats:

```

-HEADER-
04 bytes - nnnnnnnn - cmpSize -4
02 bytes - nnnn     - width in pixels of a block (complete image)
02 bytes - nnnn     - height in pixels of a block (complete image)
02 bytes - nnnn     - ?superior margin?
02 bytes - nnnn     - ?image height?
02 bytes - nnnn     - ?left margin?
02 bytes - nnnn     - ?image width?
01 bytes - nn       - numberOfColours

-BODY FOR CMPX-
numberOfColours bytes      
variable            - coded lines

Decoding: 
Lines of 26 pixels
if byte < 80h paint pixel
if byte = 80h end of line
if byte > 80h skip (byte -80h) pixels

-BODY FOR CMP0-
numberOfColours bytes      - {probably from a extern palette}
height*2 bytes        - {line offsets}
height*width bytes    - {table of pixels of each line}
```


Also attached updated version of CMPViewer adapted to this changes and even with some of the colours of the palette, which I guessed with help of the screenshots. You can see now that half of the image mor or less has good colour. That's the colours of the palette I guessed.

If you don't understand something or need anything else, just tell me over here.

I hope this comes handy to you, bye!
[CMP Viewer.zip](https://xentaxbackup.github.io/file/2064_CMP Viewer.zip)
## Post #32
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-05-28T00:11:58+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

Sorry for being gone for a day, my old router got fried. Here's some comparisons to help that I went through to make:



This is as it appears in the viewer, looking much better might I add!



As it appears ingame, but special note of detail... it is stretched vertically! I notice repeated pixels! I will later painstakingly remove each repeated pixel line (thicker than the rest all the way through), but for now here's a squished version:



Same with the girl:

  

Viewer, ingame, and fixed proportions. There will of course be issues between them because I used MSPaint to squish it down, not all repeated lines were removed and some details were lost. I'll give a more accurate image with repeated lines removed.

Point I'm trying to make is, the game stretched the graphics vertically.

P.S.: The numbered entries like GIRLx.CMP are the expressional eyes and mouth used ingame.
## Post #33
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-05-28T01:57:10+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

> Reply from Darkfox
>
> Sorry for being gone for a day, my old router got fried.
No problem, but I admit I missed you a bit hahaha

> Reply from Darkfox
>
> As it appears ingame, but special note of detail... it is stretched vertically! I notice repeated pixels! I will later painstakingly remove each repeated pixel line (thicker than the rest all the way through), but for now here's a squished version:
Yeah, don't worry I've already noticed that the screenshots were stretched. I thought it was a matter of DOSbox or the capturing program. This didn't affect colours, which is the only thing I need from the images.
DON'T LOOSE TIME CORRECTING THE SCREESHOTS. I've already said it, so you're advised that it's not necessary now... heheh

> Reply from Balder
>
> P.S.: The numbered entries like GIRLx.CMP are the expressional eyes and mouth used ingame.
It's good to know. Whatever they are, they weren't the same: pixels were coded. I have already decoded them which hasn't been very difficult as there were few codes. The biggest problem was having the screenshots incorrect, so I couldn't go comparing byte per byte.

Anyway, as I've said, the formats are already known.

There's only one task to be acomplished: discover the rest of the colours in the palette. As I've said in older posts, the palette is not in the header, but an index of colours which points to  an "standard" palette or external one.

The images are still looking bad because of not discovered colour palette. I've only added a few colours to show you the result. (about the 15% of the image is good, then )

The question is: How to discover a colour? Let's give number to them: The first pixel colour is the first colour, the next new colour (if it's a different one, as the other is already numbered) is colour two, and so on til the last colour. So, I go to paint application, I zoom in the screenshot and I go using the thing which select colours (don't ask me the name) then I go to custom colours an there it shows: Red, Green, Blue componentes of that colour. Now I know that colour 1 is: 00 87 49 (for example). Great, so now I go to the index of colours for that image in the hex editor and I see what value has the first colour. For example 84. So I go to my palette (formed by three arrays of 256 bytes each) and place in position 84 the values 00, 87, 49 for red, green and blue arrays.

This is the only way to find out the palette with the files I have. Obviously, this process has to be repeated for every image which has different colours, so we can complete the 256 colours in the palette. (If there aren't any images which contain all colours the game uses...)

I hope you understand the matter. So I wait for your response for knowing what do you want to do about it.
## Post #34
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-05-28T04:17:49+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

Time consuming but it does work. However, I have had a theory. If I can't find the palettes in any of the LAB files or in the game folder, I think I can come to another conclusion: They are in the executable itself. I will tell you the outcome of this investigation. It seems only logical though.

I understand what your saying though, it'll be the only option if I can't find the palette even after digging through it so deeply.

Edit: I pulled out part of the executable at the header "RIFF" and the "PAL data" bits. Though I doubt this is it. I have another lead though that is stored within another file.
[PALDontKnow.rar](https://xentaxbackup.github.io/file/2070_PALDontKnow.rar)
## Post #35
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-05-28T07:54:12+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

I'll test that this evening. If it results not to be the palette you could send .exe to give a try with the dissasembler. But I'm not good at that so don't expect much... at least there's another way to know it!
## Post #36
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-05-28T14:53:18+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

It seems there are more than one "RIFF PAL" on that file. Anyway, I din't find any of the already discovered colours in that palette. 

I suggest searching with an hex editor in the game's exe some particular colours as:

848484 (54 54 54 in Hex)
or
727272 (48 48 48 H)

(Considering executable not compressed, which is pretty probable in those years)

If there's a match it's pretty secure the palette is in there, and if not...
## Post #37
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-07-26T10:19:10+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

Some data that relates to the makers of this game and possibly can be translated to decoding I.M.Meen:

Tools that can possibly be used to get an idea
[http://paololiistro.e3b.org/cd-i/](http://paololiistro.e3b.org/cd-i/)

The origin topic.
[http://cdinteractive.co.uk/forum/viewto ... sc&start=0](http://cdinteractive.co.uk/forum/viewtopic.php?t=2379&postdays=0&postorder=asc&start=0)
## Post #38
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-08-01T23:37:22+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

The palettes I extracted from the executable I showed are RLE compressed. Perhaps decompressing them and trying them will get the palettes?
## Post #39
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-10-22T21:14:10+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

Just updating to let it be known that I haven't given up on this, I'm still searching for possible palette data to associate with these images as well as the textures.

Thought: The palettes extracted from the EXE may be the actual ingame palettes for sprites and textures respectively.
## Post #40
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-11-20T05:28:23+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

I'm also still alive althought not specially healthy   Well I'd like to take another look to these project just as I have some time. (now I'm finnishing a tool to deal with paletized and encoded images from Heroes of Might and Magic 2, being able also to animate, show, convert etc so I make it a reusable class on the HoMM2 remake)

As I remember all format related thing was already figured out, I have that info on my external HD at home. Just we couldn't find the palettes.

As an observation I'd say it would be very strange to see a palette RLE-compressed. Run Lenght Encode works like this: "aaaaah" "5ah" 33,3% of compression achieved. But wen you take something were all near components are differente, as a colour palette, you get: "ahahajasf" "1a1h1a1h1a1j1a1s1f" which means 100% more lenght.

Also it would be very strange to see a palette inside an .exe (not impossible thought), as they are usually small .PAL files, on the game's directory or inside another format bigger file (.dat for example).

We'll continue with this soon. It's almost finnished and wouldn't be nice to leave it now.

A pleasure to see you again Darkfox!
## Post #41
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-11-22T07:57:49+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

Glad to see your still active too! Want me to make a running game dump and find the palette in there?
## Post #42
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-11-22T14:08:54+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

That would be a good point to start. Try to find strings like "PAL" "colour" etc. We may have luck with that, because as palettes don't have any special signature searching for it as binary would be difficult.

Another idea is to take one of the colours we already had and search for it with an hex editor! That would indicate use were is it placed (at least if the palette colours are not "fixed", in that case we can search RealColour/4 or RealColour/2.
## Post #43
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-12-01T22:11:57+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

The contents of this post was deleted because of possible forum rules violation.
## Post #44
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-12-01T22:48:11+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

Great  

So if you already find some colour matches, finding where the palette start it's straightforward, remember they are usually 256 bit * 3 = 768 bytes.

I'll take a look to this this weekend, I think I'll have some time.

Just trying to determine which file contains it.

Cheers!
## Post #45
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-12-01T22:59:36+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

Well, it is a memory dump, so it is a (not very big) single file. I'll need to run a special file search tool to check all files for the color matches.
## Post #46
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-12-01T23:05:54+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

Yeah, pretty easy from there I think you'll find such a tool even without having to code it yourself. (In such case we could make it just in a couple of hours)

Once the palette is found just tell me to update the tools, so the pixel coulours are output correctly.

Keep it up!
## Post #47
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-12-01T23:22:36+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

ALRIGHT, I extracted what seems to contain the palette we've been looking for!

I'll see if I can clean it up a bit. But it seems to contain the full palette.
[PaletteMaybe.rar](https://xentaxbackup.github.io/file/2584_PaletteMaybe.rar)
## Post #48
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-12-02T03:16:07+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

As I said, I'll try to confirm that palette this weekend
## Post #49
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-12-03T03:46:01+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

Right, I'll be looking forward to it. ^_^
## Post #50
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-12-04T20:24:33+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

Good news/bad news moment

Good News: 

The palette I extracted works with all textures AND sprites.

Bad News: 

Sprites no matter the setting appear off, specific tools for extraction may be necessary to gain desirable results. But now that the palette is extracted and known for these, it should not be too hard now.

Bad News: 

It doesn't seem to be the same palette that the CMP uses. =/

Edit: I provide the corrected palette file.

Edit2: It appears that it is not only the first palette I've found but the ONLY palette, so a CMP must read it differently.
[MeenMapPalette.rar](https://xentaxbackup.github.io/file/2589_MeenMapPalette.rar)
## Post #51
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-12-06T20:09:22+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

Another update:

The palette file attached in the above post is the ONLY palette used in-game. Almost all textures are viewable and can be converted using TILEDGGD, however, animated sprites are not, but that's for later. CMPs map differently to the palette but all colors neccesary are in there. Thus we are very close to finishing up the CMPs. Then all that would leave is the animated sprites contained in IMAGES.IMG. But we need to finish up the CMPs.

The end is in sight! Victory is eminent.
## Post #52
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-12-06T23:41:44+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

Hey! Back here and glad to see these progress. As that seems to be the palette and having now two days off (monday and tuesday) I'll try to figure out how is the palette used by the CMP's. Can't promise anything, but I'll try my best. There was also some unknown data at the end of each CMP that can be related to this problem so we'll see.

I think you can start thinking of having the game completely unpacked (and not just dreaming hehe)

Now a bit of rest for me as I had too much problems lately.

See tomorrow!
## Post #53
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-12-07T19:33:19+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

> Reply from Balder
>
> I think you can start thinking of having the game completely unpacked (and not just dreaming hehe)

Yup! CMPs, animated doors, and sprite are the last needed graphics. When they are decoded, consider I.M.Meen resources cracked. And in celebration of that, I'm recreating the maps in Doom with what we've accomplished thus far!
## Post #54
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-12-07T23:31:38+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

That sounds fantastic  

Sorry again, some unplanned business took me 4 hours and so I'll try to see that tomorrow if there isn't any new trouble (one can never be completely on holidays!)

That's it, see you soon!
## Post #55
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-12-08T20:42:04+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

Eh, it's alright. We are getting close to finally cracking the CMP files. Then we'd be 2/3 complete. (the final 3/3 is the sprites and textures with transparency)
## Post #56
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-12-09T00:03:44+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

Have taken a look over that. I got the same "fucked up" image as you show up, so It may take some time to figure the correcto order of the palette. Don't promise anything. I'll be away some time now I think (exams business) but any free time one of my tasks will be finding this out.

I hope yo keep too trying on this project.

Bye!!!
## Post #57
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-12-09T00:27:42+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

Well I'll be trying (key word there "trying") to get the sprite graphics and animated/transparency doors to display correctly instead of broken up as they appear now (IMG files exclusively). Maybe the sprites would be easier to work on as the palette works with them. Though you've done very good so far on the CMPs.

Overall we are 1/3 finished. 1/3 being finding the palette and displaying and extracting the textures (minus the animated doors and transparent walls) Funny enough, our project here has gained external interest since the game has escalated to internet fame. I myself have decided to put our progress to recreate this game in GZDoom minus the grammar puzzles for fun and as a classic FPS enthusiast.

Edit: I discovered why the sprites were displaying wrong as they were compressed by removing the numerous transparent portions and storing their portions in data stored at the beginning of the instance.
## Post #58
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-12-13T10:16:30+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

And so just CMP's remaining to hack huh?
## Post #59
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-12-13T18:41:22+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

Well, the CMPs and the IMGs. Primarily, IMAGES.IMG
## Post #60
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2010-11-08T03:25:13+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

Well, with Images.IMG cracked pretty much all that is left it seems is CMPs. And the way I see it now is that CMPs use a color lookup table as opposed to raw palette usage like with the IMGs. The numbers indicate portions of the palette and pick specific colors inside. I could cross examine simpler things like the pointers and icons which can be ripped without distortion.

Edit: They also use the masking that was used in IMAGES.IMG for transparency.
## Post #61
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-05-17T08:53:25+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

Sorry to bump this, but due to the recent cracking of I.M.Meen's IMG format (Chill Manor being investigated since in is V2 IMG format) I have a renewed interest in cracking CMP to "finish it off". First off, I looked deeper into the format and it, like IMGs, contains a masking check for images with transparency, like cursors and inventory icons. It ALSO uses the external palette differently as was established here. I am almost positive that CMPs actually make a kind of... color map. Actually pick out colors in the palette instead of using them in a raw format unlike textures and other sprites. Why is beyond me, but tests point in this direction as well. The palettes at the end of each START_SCR.PCX are the only palette used and is the same for all PCX files in this game. Made sure on the face PCX files as well for player selection. Yes, the game uses a palette from a PCX as opposed to one shared palette. This supports my hypothesis.

So, part of the unknown data would be the masking, the other would be the colors picked out from the palette. The only other possibility in my mind would be an RLE palette per image which would be... kinda dumb if there's only one game palette and all colors are just in there.
## Post #62
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2012-03-22T12:13:55+00:00
- Post Title: Re: I.M.Meen (1995 PC/DOS) CMP format

It's been a long time away. Is there any news on this topic? Greetings.
