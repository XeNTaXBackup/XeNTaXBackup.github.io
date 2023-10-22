## Post #1
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2010-08-16T20:12:12+00:00
- Post Title: [Wii] Arc Rise Fantasia - wtm-File (WTMD)

I made some progress with this kind of graphicfiles.
It looks like the format is quite similar to the standard texture-format of the GC/Wii. See [http://hitmen.c02.at/files/yagcd/yagcd/ ... sec15.20.1](http://hitmen.c02.at/files/yagcd/yagcd/chap15.html#sec15.20.1)
I tried to verify some values of the data and they matched but there are still some unknown values left. Here is what I found out by using the yagcd:

Offset Size Description
0x06 2byte Palette Offset - offset to Palette Data
0x08 2byte Width
0x0A 2byte Height
0x0C 1byte Imageformat - RGB565/RGBA8/CI4/CI4... see yagcd for more info
0x12 2byte Data Offset - offset to image Data

So there are images with and without a palette possible. I was not able to find the value that specifies the paletteformat since my version of the dolphin emulator does not show transparent images right and on newer version I dont get the buttons to work... Just from guessing I would say its 0x15.

This should be enough data to dump the images of the game 

Some images: [http://filebeam.com/cd883cf48bb793d9b05163d2f83b5fad](http://filebeam.com/cd883cf48bb793d9b05163d2f83b5fad)

PS. Is there a tool that lets you specify the palette and imageformat in a way that its possible to view the WTMD files? It must have support for the vaious formats like RGB565/RGBA8/CI4/CI4...
[logo.zip](https://xentaxbackup.github.io/file/3354_logo.zip)
## Post #2
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2011-03-26T11:13:15+00:00
- Post Title: [Wii] Arc Rise Fantasia - wtm-File (WTMD)

Since there was some progress going on I bump this.
## Post #3
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2011-03-27T16:35:10+00:00
- Post Title: [Wii] Arc Rise Fantasia - wtm-File (WTMD)

Looks interesting. I hope you succeed in hack this format
## Post #4
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2011-03-28T19:34:46+00:00
- Post Title: [Wii] Arc Rise Fantasia - wtm-File (WTMD)

With my very limited coding experience I wrote a converter... BUT it just creates a TPL-header from the data of the WTMD-file  Now its no problem to use one of the known tools to convert the TPL to png oder something else. However this is just a workaround and at this time it only works for RGBA8. Its a shame that I dont understand the sourcecode of the various tpl converter out there  Basicly its just changing the offsets to get a TPLconverter working for WTMD files.

Some eyecandy 
[](http://www.apload.de/bild/106755/picpmrk00sswtmJ3EK9.png)[](http://www.apload.de/bild/106757/picpwil00sswtmQS4YA.png)

When I find some time I try to learn more about programming and maybe I get so far that I can code a real converter. If this will not happen at least the format is known now.
## Post #5
- Username: yabari
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 01, 2011 7:54 am
- Post datetime: 2011-05-01T00:02:11+00:00
- Post Title: [Wii] Arc Rise Fantasia - wtm-File (WTMD)

what a nice work, cheers!  
and im work hard with my .brfnt file decode.
