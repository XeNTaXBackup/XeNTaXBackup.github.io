## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-01-16T04:04:24+00:00
- Post Title: BlazBlue 360

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-01-16T15:00:10+00:00
- Post Title: BlazBlue 360

xsb aren't archives, they act in a way like index files.
for example the xwb are the archives with nameless files in them and sometimes the names could be contained in the xsb files but xsb are not simple to parse and not necessary
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-01-16T20:09:50+00:00
- Post Title: BlazBlue 360

Thanks to aluigi we can now convert the audio to wave format 
[http://aluigi.org/papers.htm#unxwb](http://aluigi.org/papers.htm#unxwb)
and on the resulting wav files use the xmaencode from the xbox sdk
xmaencode.exe /X output.wav input_xma.wav
now we just need to decode these bmp image files.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-01-16T22:40:15+00:00
- Post Title: BlazBlue 360

I need only to highlight that is needed at least version 0.3.3 of unxwb because I have fixed the creation of the xma headers just today.
and in case someone is interested to the source code (xma_header.h) I have implemented the creation of all the available xma headers supported by xmaencode:
- xma1
- xma2
- xma2 xact (it's the one which uses the "XMA2" tag instead of "fmt ")

last thing, I and chrrox noticed that the PCM (aka uncompressed audio) files on xbox360 use the native endianess of this console (big endian) so they cannot be played because all the samples are inverted (example in a 16 bit file we will have 11 22 instead of 22 11).

to resolve the problem I have created a script for quickbms that reverses the endianess of these wav files to the little endian one:
[http://aluigi.org/papers/bms/wav_endian.bms](http://aluigi.org/papers/bms/wav_endian.bms)
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-01-17T21:48:48+00:00
- Post Title: BlazBlue 360

the mystery has been solved
## Post #6
- Username: interloko
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Oct 27, 2009 12:53 am
- Post datetime: 2010-01-19T11:37:47+00:00
- Post Title: BlazBlue 360

how you do that chrrox?
with the 2 steps you said or you need an extra step?

can you help me on that?
i'm not sure about downloading the right sdk XDD
sorry to bother you but i was behind this game (graphics)

can you post a link to the sdk and a step by step tutorial please?
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-18T22:00:26+00:00
- Post Title: BlazBlue 360

sorry for the info posted on multiple threads, I want to have each one updated with the correct info as reference.
script for quickbms:
[http://aluigi.org/papers/bms/arcsys.bms](http://aluigi.org/papers/bms/arcsys.bms)
