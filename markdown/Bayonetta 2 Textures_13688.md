## Post #1
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2015-12-17T07:29:38+00:00
- Post Title: Bayonetta 2 Textures

Hi all. Looking for a bit of assistance with Bayonetta 2. The overall format seems to be the same (or very close) to Bayonetta 1. As such, Noesis seem to work just fine down to the model/skeleton. CPK files are extracted and the DAT files load the model and export to various formats with correct bone weights (from the couple models I tried). However, textures don't load nor do they export. I used QuickBMS to export the DAT file of a model and here is what exports. 



I'm guessing the WTP file is the textures but I can't find any tools that work with it. Hoping someone knows how to extract them or can create a script to do so. I'm not entirely sure it's okay to share the file publicly. I'll share whatever files are needed through PM (or publicly if it's okay) if someone will lend a hand.

Thanks for any assistance.
## Post #2
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2015-12-18T22:21:18+00:00
- Post Title: Bayonetta 2 Textures

Got a bit of help from PredatorCZ. I sent him the files and this is what he found. 

"WTA is header tables for wtp.
WTP is pixel data.
WTA share header of WTB (First Bayonetta texture format).
WTP have color pattern of DXT but are in unknown format (DTT,GTF, or something else)."

I'm hoping someone can figure out how to get usable textures. I know it's been done by a guy on DeviantArt but I dunno how (yes, I've asked him and have not gotten a reply). 

Going to go ahead and share a DL link for the files in hopes of someone else taking a look at them. Files include the DAT file which can be read opened in Noesis and all the files that are extracted with Fatducks quickbms script found at [viewtopic.php?f=10&t=3773](http://forum.xentax.com/viewtopic.php?f=10&t=3773)

[http://www.mediafire.com/download/b34xg ... 67y/c2.rar](http://www.mediafire.com/download/b34xgq3enme467y/c2.rar)
[http://www.mediafire.com/download/2bnbt ... agv/55.rar](http://www.mediafire.com/download/2bnbtn7ygaelagv/55.rar)
[http://www.mediafire.com/download/ru3qn ... 6io/25.rar](http://www.mediafire.com/download/ru3qnmrpk1hh6io/25.rar)
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-12-19T10:33:48+00:00
- Post Title: Bayonetta 2 Textures

problem for C2-files is: the Noesis Bayonetta plugin expects pl00c2.wtb
but there is a pl00c2.wta only

Changing the code from wtb to wta and choosing different DXT types as defaults results in this:



Bayo_Tex_.JPG (41.04 KiB) Viewed 566 times



(mariokart64n posted the WTA Format here:
[viewtopic.php?f=16&t=10147&p=83739&hilit=wtb#p83739](http://forum.xentax.com/viewtopic.php?f=16&t=10147&p=83739&hilit=wtb#p83739)

well, XPR2_headers? I'll check that...)

C2-wta (offsets/sizes should refer to pl00c2.wtp):
8 textures at offsets
00040   00 00 00 00 00 08 00 00  00 28 00 00 00 28 E0 00
00050   00 48 E0 00 00 49 00 00  00 49 40 00 00 4A 40 00

sizes:
00060   00 0A B5 3C 00 2A B5 3C  00 00 C1 1C 00 2A B5 3C
00070   00 00 31 3C 00 00 61 3C  00 01 69 3C 00 05 69 3C

Doesn't make sense to me. Assumed we've big endian notation here:
first tex, offset + size > next offset!?
0x0 + 0xAB53C > 0x80000

Ah, see: the offsets make sense, the sizes might be the uncompressed ones.
## Post #4
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2015-12-19T18:55:13+00:00
- Post Title: Bayonetta 2 Textures

[https://mega.nz/#!6sYCCaga!VufxEo0TlRLY ... h8pv4d_x5k](https://mega.nz/#!6sYCCaga!VufxEo0TlRLYBar95xbZelShjCiVDLt1ph8pv4d_x5k)

Here's the QuickBMS script I made a while back to deal with those textures. Use this on either the WTA or WTP files (doesn't matter, it'll read both anyway) and it'll output a bunch of .GTX files, which you can then use with TexConv2 to change 'em to .DDS.

(This won't work with the ones from the first Bayonetta yet, from what I understand. Hrm.)
## Post #5
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2015-12-19T19:52:29+00:00
- Post Title: Bayonetta 2 Textures

Thank you for the script Random. Worked perfectly. And thank you shakotay2 for the effort. I was actually downloading the first Bayonetta to get ahold of those files in case they could help.
