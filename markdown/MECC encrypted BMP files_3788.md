## Post #1
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2009-10-16T20:34:33+00:00
- Post Title: MECC encrypted BMP files

Hey guys,

So I was able to write a BMS script to extract all of the files from the Opening Night archive.  They are all still very much encrypted.  I'm completely stuck at this point.  I've attached 15 of the bmp files here for anyone who's willing to take a look at them.  Any help would be very appreciated.

Thanks,

 jawharp 
[Test Extraction.rar](https://xentaxbackup.github.io/file/2453_Test Extraction.rar)
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-10-18T23:09:25+00:00
- Post Title: MECC encrypted BMP files

Yes, you did a great job on that script then. I've been looking at those CBMP files and the executable. They *seem* to be simple RLE files, 8 bit, but missing the correct BMP header. I need to take another look at the executable to see where it loads a CBMP. I would prefer next time, you *bump* an existing thread on these files, instead of creating another one. Allrightey?
## Post #3
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2009-10-19T02:42:34+00:00
- Post Title: MECC encrypted BMP files

Hey,

Sorry for the double post.  Won't happen again.  I'll post the script I used here so that anyone can use/modify it if they want.  It will also help because in the 8 folders that are in this archive, there's one called "CBMP" and one called "RLES."  I'm not sure why both exist if the CBMP's are RLE's.  My first instinct would be that the game was coded for windows 3.1, windows 95, and mac os 7.5.  

Perhaps the multiple formats are a compatibility thing?

The script itself is pretty rough at this point.  Just a way to dump the stuff so I could work with it.  I would like to fix the file naming so that it was "xxx.CBMP" and not "CBMPxxx."  Obviously not a top priority.

Anyway, here's the script.  It's formatted for quickbms:

Endian Big;
Get HEADERSIZE Short;
Get UNK1 Long;
IDString "MECC";
Goto 0x56;
Get DIRS Short;
Get FILES Long;
Goto 0xDC;
For i = 0 < FILES;
Getdstring TYPE 0x04;
Getdstring PADDING 0x04;
Get NAME Long;
String TYPE += NAME;
Get OFFSET Long;
Get FILESIZE Long;
log TYPE FILESIZE OFFSET;
next i;
## Post #4
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2009-10-19T03:20:07+00:00
- Post Title: MECC encrypted BMP files

Hey,

So, a bit of false information in the last post.  I just discovered with IDA breakpoints that the CBMP files are the props and backgrounds files for the program.  The RLES are the actors.  

I kind of made the previous assumption without proof.  That, along with the double posts, will not happen again.  

Just thought I'd correct my last post.

Thanks again.
## Post #5
- Username: huckleberrypie
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-10-19T05:32:35+00:00
- Post Title: MECC encrypted BMP files

There is absolutely nothing wrong with doing an assumption first and then proving it was incorrect. That's how science works as well ! So, please do guess on.
## Post #6
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2009-10-21T14:19:37+00:00
- Post Title: MECC encrypted BMP files

Hey,

So I've been trying to look at assembly code to no avail.  I have a hard time understanding that stuff.  

Upon comparing 4 randomly selected RLE files from the archive, a couple things have caught my attention.  

One is that the zero's in the first 14 bytes of each file tend to match up exactly.  I figure these are the 14 bytes required for the BMP header.  If that's so, then the first 2 bytes of each file should be "BM," which obviously they're not.  I've attached a picture to illustrate the zero's matching in the first 14 bytes.

Every file does not have the same 2 bytes at the start of the file, however.  So if the first 14 bytes are the start of the BMP header, they are not all being encrypted with the same key.  

In an effort to get just a little more information, I've also written a script to extract entries from the OPENNITE.ENG file which holds the strings for the program.  Here it is:

```
Get HEADERSIZE Short;
Get UNK1 Long;
IDString "MECC";
Goto 0x56;
Get DIRS Short;
Get FILES Long;
Goto 0x7C;
For i = 0 < FILES;
Getdstring TYPE 0x04;
Getdstring GARBAGE 0x04;
Get NAME Long;
String TYPE += NAME;
Get OFFSET Long;
Get FILESIZE Long;
log TYPE FILESIZE OFFSET;
next i;
```


In the strings file, there are numbers next to each entry for the BMP name in the program.  I believe these to be the reference numbers that should match to the ones in the file index of the main .mdt archive.  Being able to identify which file is which might help a bit.  Gunna see if they match up.

That's all for now,
[hexcomparenew.gif](https://xentaxbackup.github.io/file/2473_hexcomparenew.gif)
## Post #7
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2009-10-21T15:37:05+00:00
- Post Title: MECC encrypted BMP files

Mr. Mouse,

I think I've found it.  Set breakpoint at 456CBB, start program in debug, click on one of the icons on top to load the actor/props/whatever list.  The breakpoint is set right when it starts loading the icon BMP's for all the game elements.

Stepping through the assembly (remember my assembly skills are no where near good), I noticed it doing things with ascii characters "B" and "M."  It also seems to be stepping through a file and performing "OR" commands on it.

I think the answer lies here, but I'm not that good at reading assembly.  I'd appreciate you taking a look at it if you have the time.

Thanks,
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-10-21T15:39:41+00:00
- Post Title: MECC encrypted BMP files

Nice work. We can take a look at that. The header has some information on the width and height of the picture,
## Post #9
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2009-11-03T13:45:35+00:00
- Post Title: MECC encrypted BMP files

Mr. Mouse,

Have you had a chance to take a look at that offset?  I'm still stumped when it comes to the assembly.

Thanks,
## Post #10
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-11-05T20:41:44+00:00
- Post Title: MECC encrypted BMP files

Well, I did take a look, and you're right, there's something going on there. Have not had the change to figure it all out yet.  Busy ......
## Post #11
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2009-11-06T04:25:48+00:00
- Post Title: MECC encrypted BMP files

Totally understand.  Thanks for taking a look.  Let me know if you find anything in the future.
## Post #12
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2011-06-18T13:26:03+00:00
- Post Title: MECC encrypted BMP files

::::bump::::

I know you're busy with DnF stuff among other things, but did you ever get a chance to look at this again, Mr. Mouse?  Any help would be greatly appreciated.  I'm still stumped....

Thanks for your time,
## Post #13
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2011-06-18T20:29:57+00:00
- Post Title: MECC encrypted BMP files

Gah!  I just stumbled across this in OllyDbg:

picture

Set a breakpoint at 765EAA32.  

I think it might be turning that hex string into that bitmap info.  The pBitmapinfo variable.    I've attached a picture to show what I'm talking about.
[olly1.jpg](https://xentaxbackup.github.io/file/4351_olly1.jpg)
## Post #14
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2011-06-18T22:40:01+00:00
- Post Title: MECC encrypted BMP files

Ok, so i think i figured out what's going on with these bitmaps.  My previous post is not 100% incorrect, but it got me thinking.

Basically the first 14 bytes of the compressed bitmap is a custom header.  It's a compressed form of a regular bitmap header.  Basically all information not unique to that particular file is stripped out.  It gets re-injected by the program once it's running and loading the bitmaps.  

I figured this out because I noticed the value at offset 0000000C is equal to "filesize - 14" for every file in the RLES folder that i've tested.  This must be the value fore the start of the image data.  so the first 14 bytes must be the compressed header.

I figure that the other 10 bytes must be sizeh, sizev, and anything else that would change in other bitmap file headers.  i'm going to try some trial and error and rebuild a generic bitmap header and plug the values i find in the compressed header into the different fields that i feel would change per file.

If i'm right, then this might be a big find....

for me....

and this is what i do on saturday night..............
## Post #15
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2011-06-18T23:24:50+00:00
- Post Title: MECC encrypted BMP files

Here is a RAR of some of the RLE files I'm talking about for anyone interested..
[MECC_RLE.rar](https://xentaxbackup.github.io/file/4352_MECC_RLE.rar)
## Post #16
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2011-06-19T16:10:44+00:00
- Post Title: Re: MECC encrypted BMP files

Okay, 

So i took what i learned from the RLES files yesterday and applied it to the CBMP files.  Here's what I believe:

The game was released for mac AND windows.  The 2 different game versions use different versions of the game assets.  

The value i spoke of yesterday (the filesize - 14) that appeared in every RLE file was stored as a big endian 16 bit value.

Upon looking at the CBMP files, they have the same exact value (filesize - 14 bytes) stored in the header as a 16 bit little endian value.

I'm going to go ahead and work under the assumption that the CBMP files are windows assets and the RLES are mac assets.  This knowledge might make trying to handmake a bmp file a bit easier on my windows machine.
## Post #17
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2011-06-19T23:59:35+00:00
- Post Title: Re: MECC encrypted BMP files

Ok, so I checked what I suspected to be the xSize and ySize in the compressed header with an asset in the running game.  I am 99% sure I'm right.  The sizes in this test file and many others match the backgrounds in the game.  Here's the MECC BMP header as I know it now:

01 00     ??
XX XX    xSize
XX XX    ySize    
0E 00 00 00    Header size        
XX XX XX XX   Bitmap data size


i think the first 01 00 might be telling you that RLE-8 is being used, but when i try manually putting all this info into a custom bitmap file with the bitmap data I wind up with something like the attached picture.  

I think the bitmap is misaligned or not being decompressed right.  Any ideas?  someone?   please?  

thanks,
[bitmap.jpg](https://xentaxbackup.github.io/file/4360_bitmap.jpg)
