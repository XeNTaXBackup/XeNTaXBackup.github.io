## Post #1
- Username: huelarl
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Feb 02, 2011 11:56 am
- Post datetime: 2011-02-02T04:07:25+00:00
- Post Title: Arcana  Heart 3 Pac/Pk3 Files

I am interested in the pac and pk3 file format on the AH3 Disc. The pac format seems to be closely related to those used in the BlazeBlue Games (ArcSystemWorks aswell). There are blazblue sprite/gallery rips floating around so there have been ways to extract those. I also found an Arcana heart topic regarding .dds(xpr2) here but its unavailable. Maybe someone can help me out here.
thank you in advance
## Post #2
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2011-02-02T08:33:07+00:00
- Post Title: Arcana  Heart 3 Pac/Pk3 Files

Hmm. Well, most likely, it's already ripped.

Yep.
[http://www.justnopoint.com/lbends/index ... tion=stuff](http://www.justnopoint.com/lbends/index.php?location=stuff)

Also, there a ripped someone on the net for the first one, chances are, it might work for the third one. If you can post the file, I'll see if it works.
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-02-02T15:00:08+00:00
- Post Title: Arcana  Heart 3 Pac/Pk3 Files

Its using the same format as blaze blue its just compressed with the common container segs. (ps3 version)
this will extract the segs files from the big dat file.

```
endian big
for i = 0 < 0xFFFF
set name name1
string name + _
string name + i
string name + .segs
FindLoc Offset string "\x73\x65\x67\x73"
goto Offset
get Unk01 long
get Unk02 short
get files short
get Unk03 long
get size long
math size + 0x10
math files * 8
math size + files
log name offset size
next i

```


then just run offzip on the segs file 
offzip.exe -1 -a -z -15 c:\file.segs c:\extract 0x0
i could make it auto decompress the segs but i am lazy.
## Post #4
- Username: huelarl
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Feb 02, 2011 11:56 am
- Post datetime: 2011-02-02T17:38:42+00:00
- Post Title: Arcana  Heart 3 Pac/Pk3 Files

> Reply from chrrox
>
> Its using the same format as blaze blue its just compressed with the common container segs. (ps3 version)
this will extract the segs files from the big dat file.
...
then just run offzip on the segs file 
offzip.exe -1 -a -z -15 c:\file.segs c:\extract 0x0
i could make it auto decompress the segs but i am lazy.
Thank you very much for your help. This got me further on the PS3 side. I borrowed the XBOX360 Version from a friend at the same time and the files are already there after the usual content extraction from the disk.

> Reply from ShinKun
>
> Hmm. Well, most likely, it's already ripped.
Yep. http://www.justnopoint.com/lbends/index ... tion=stuff

Also, there a ripped someone on the net for the first one, chances are, it might work for the third one. If you can post the file, I'll see if it works.
I am especially interested in the gallery contents on the console version. These rips are missing artworks and so on. I have looked into the pac format but it seems to be different. But i am not very experienced in dealing with such stuff  I would like to post the file if thats allowed.
## Post #5
- Username: Insanius
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Apr 01, 2010 11:51 am
- Post datetime: 2011-02-23T18:26:42+00:00
- Post Title: Arcana  Heart 3 Pac/Pk3 Files

Believe me the PAC format is the same, you just have to change to big endian when dealing with 360 files.
As for PK3 files, the ones in the console ports are the frame data files.  No compression whatsoever.  Now if we were talking about the arcade dump...

Oh and I apologize, but not everything on my website is readily accessible from the webpage, I'm still working on that   

[http://www.justnopoint.com/lbends/ArcanaGallery/](http://www.justnopoint.com/lbends/ArcanaGallery/)


Regarding that big dat file you're referring to, did you mean bddata.bin?  Or do I need to do something to it to get a dat file?
Edit: Tried it out, errored on a file with negative size, I am definitely doing something wrong.

Edit2: Nevermind it worked, sucks that I don't have filenames, thought I may be to fix some of the extensions by reading the file headers.  In particular, the PAC files are easily identified.

Edit3: Offzip failed on a vast majority of the seg files that were dumped, my batch file just finished and I was dissapointed to see only 35 files successfully decompressed.
I'm going to make a tool to properly unpack these segs files, the lack of encryption should make this trivial.

Edit4: I've got it down to 15 segs files I cannot decompress, any ideas would be appreciated.  I wrote a program in java to facilitate this by the way:
[http://www.justnopoint.com/lbends/junk/ ... acker.java](http://www.justnopoint.com/lbends/junk/SegsUnpacker.java)

And some of the files, for testing purposes.  Half of them work half of them don't.
[http://www.justnopoint.com/lbends/junk/segsamples.zip](http://www.justnopoint.com/lbends/junk/segsamples.zip)
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-18T21:57:37+00:00
- Post Title: Arcana  Heart 3 Pac/Pk3 Files

sorry for the info posted on multiple threads, I want to have each one updated with the correct info as reference.
script for quickbms:
[http://aluigi.org/papers/bms/arcsys.bms](http://aluigi.org/papers/bms/arcsys.bms)
## Post #7
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2011-04-12T15:47:22+00:00
- Post Title: Arcana  Heart 3 Pac/Pk3 Files

The contents of this post was deleted because of possible forum rules violation.
## Post #8
- Username: Insanius
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Apr 01, 2010 11:51 am
- Post datetime: 2011-04-13T19:11:47+00:00
- Post Title: Arcana  Heart 3 Pac/Pk3 Files

Arcade pk3s are compressed.  First you read in two bytes as compression flags.  Start from the highest bit.  For each 0, read in two bytes and add them to the output buffer.  For each 1 read in two bytes again, but use the lower 12 bytes as an offset from the end of the output buffer to start copying data, and the upper 4 bytes (+1) as the number of bytes to be copied.

Figuring this out was all mauve's doing I simply applied it.
## Post #9
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2011-04-14T03:49:24+00:00
- Post Title: Arcana  Heart 3 Pac/Pk3 Files

So, how do I unpack'em?
[http://aluigi.org/papers/bms/arcsys.bms](http://aluigi.org/papers/bms/arcsys.bms)

Also, I used this on the PS3 version "bddata.bin" and it didn't work.
## Post #10
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2011-05-02T11:07:53+00:00
- Post Title: Arcana  Heart 3 Pac/Pk3 Files

Any help?
## Post #11
- Username: Insanius
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Apr 01, 2010 11:51 am
- Post datetime: 2011-05-02T13:44:28+00:00
- Post Title: Arcana  Heart 3 Pac/Pk3 Files

Use chrrox's script first.
## Post #12
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2011-05-20T09:39:47+00:00
- Post Title: Arcana  Heart 3 Pac/Pk3 Files

How? is it BMS script?

Edit: I used the script, and got the segs, but offzip said it wasn't a valid segs file. I tired that SegsUnpacker.java, and I seem to get that to run. I tired java SegsUnpacker.java *.segs and and single segs file.
## Post #13
- Username: lUIGUIPIETRO
- Rank: veteran
- Number of posts: 87
- Joined date: Sat Mar 13, 2010 10:59 pm
- Post datetime: 2011-06-22T17:10:35+00:00
- Post Title: Arcana  Heart 3 Pac/Pk3 Files

some files LA Noire (PS3) seem to be is secs format. No way to remove them?
