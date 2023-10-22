## Post #1
- Username: ubrax
- Rank: advanced
- Number of posts: 46
- Joined date: Sun Mar 15, 2009 9:16 pm
- Post datetime: 2010-01-01T19:03:42+00:00
- Post Title: BASPACK - Drawn: The Painted Tower - Archive

I'll appreciate any help or guidance to unpack the "data.pak" archive from "Drawn - The Painted Tower". 
The head.bin and tail.bin 
> Drawn_head_and_tail.rar is attached hereto.

Thanks in advance!
[Drawn_head_and_tail.rar](https://xentaxbackup.github.io/file/2685_Drawn_head_and_tail.rar)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-01-01T19:16:32+00:00
- Post Title: BASPACK - Drawn: The Painted Tower - Archive

can you upload the whole file this is my best guess at it.

```
get TABLEOFFSET long
get FILES short
goto TABLEOFFSET
for i = 1 < FILES
filexor ""
get OFFSET long
get SIZE long
getdstring NAME 0xFF
filexor "0x37"
clog NAME OFFSET SIZE
next i
```
## Post #3
- Username: ubrax
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-01-01T19:46:35+00:00
- Post Title: BASPACK - Drawn: The Painted Tower - Archive

I downloaded it this should work

```
get TABLEOFFSET long
get FILES long
goto TABLEOFFSET
for i = 1 < FILES
getdstring NAME 0xFF
get OFFSET long
get SIZE long
filexor "0x37"
log NAME OFFSET SIZE
filexor ""
next i

```
## Post #4
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2010-06-13T19:46:08+00:00
- Post Title: BASPACK - Drawn: The Painted Tower - Archive

How to repack extracted BASPACK?

Can anyone help with writing tool for that? By on script it's shoudn't be hard.
## Post #5
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-06-14T19:02:49+00:00
- Post Title: BASPACK - Drawn: The Painted Tower - Archive

Here's a very simple PAK maker/extractor.
And I have an idea to improve it, so the next step will be the "Update" function, so how to replace only a few files, without extracting everything, and rebuilding again
that 600 megabytes sized huge PAK file. (Just like in my BIN updater for the "Darkness Within 2")

Updated version!
Now it works like my .VST util: You can use the "Replace" function, if you want to replace only one file in the archive!
## Post #6
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-06-23T06:23:29+00:00
- Post Title: BASPACK - Drawn: The Painted Tower - Archive

This is the commandline version of the Update (Replace) function.
## Post #7
- Username: ubrax
- Rank: advanced
- Number of posts: 46
- Joined date: Sun Mar 15, 2009 9:16 pm
- Post datetime: 2021-12-09T14:32:55+00:00
- Post Title: BASPACK - Drawn: The Painted Tower - Archive

Used the BASPACK Unpacker/Packer [Drawn-Dark_Flight_PAK_unpacker_1.0.zip by XpoZed] (and command line version by bacter) on various BASPACK archives. Never experienced any problems:
1. BASPACK - Drawn: The Painted Tower - Archive et.al.
2. BASPACK - Travelogue 360 (both Rome and London).

BASPACK - Travelogue 360 Paris doesn't work.

The attached BASPACK file seems to predate the BASPACK evolutionary line and fails to open using the unpacker.

Archive Analysis file: [http://ubrax.com/bms/data.pak.zip](http://ubrax.com/bms/data.pak.zip)

I will appreciate any help I may receive to unpack this archive.

Regards, and thanx!
[data.pak.zip](https://xentaxbackup.github.io/file/21364_data.pak.zip)
