## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-22T17:13:35+00:00
- Post Title: FINAL FANTASY XIV: A Realm Reborn (*.DAT0;*.INDEX)

Well benchmark availble. Download: [here](http://gdl.square-enix.com/ffxiv/download/media/FFXIV-ARR-Bench-World.zip) (469MB)

Names hashed and pass through CALL 00508E90

```
006251BA    51              PUSH ECX                                  //String length
006251BB    8D4C24 10       LEA ECX,DWORD PTR SS:[ESP+0x10]
006251BF    E8 CC3CEEFF     CALL ffxiv.00508E90                       //CRC func

```


Examples: 

```
bg/ffxiv/fst_f1/dun/f1d1/grass/f1d1_terrain_h_7_0_11.gtd - BF17B473 <> 73B417BF

```

Note: [MS-PTS - CRC Calc](http://msdn.microsoft.com/en-us/library/ff385753%28v=office.12%29.aspx)

Someone is looked this? INDEX seems contained only Hashes and Offset.. Size ect in DAT0.. Any help is appreciated 

@Edited: Old [thread](http://www.ffevo.net/topic/2878-ffxiv-20-dat-mining/) from other forum about archives. it would be great if someone could compile Projects using class SqPack for C#
## Post #2
- Username: Loumie
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 12, 2012 3:00 pm
- Post datetime: 2013-02-23T19:36:45+00:00
- Post Title: FINAL FANTASY XIV: A Realm Reborn (*.DAT0;*.INDEX)

From what I've seen (from today only so that's not that much) the formats are pretty simple for unpacking dat files.

All hashes in the SqPack files are sha1, I did not see any crc32 in those files. (only in patch files)
The index contains:
  - list of files in the dat
  - free list in the dat
  - directory like structure relying on hash or type, I don't know, most likely to search quickly in the file.

The dat contains all the files zlib compressed.
## Post #3
- Username: Loumie
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 12, 2012 3:00 pm
- Post datetime: 2013-03-05T19:31:56+00:00
- Post Title: FINAL FANTASY XIV: A Realm Reborn (*.DAT0;*.INDEX)

It doesn't seem that much people are interested in this one.

However, while fiddling around with the files, I came across and extracted a file conveniently named SE in which there are references to SEDBSSCF files that are named with Yoshida and maybe other devs names.

I was curious if anybody knows how to read these files, I saw that it was a wrapper for Ogg but I didn't see any vorbis/ogg in the files and am very curious about their content
## Post #4
- Username: quantico
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Sep 19, 2010 6:19 pm
- Post datetime: 2013-03-08T23:33:27+00:00
- Post Title: FINAL FANTASY XIV: A Realm Reborn (*.DAT0;*.INDEX)

Where do you actually get the file names from? Most actual data is pretty easy to extract (I've also came across multiple files with SEDBSSCF header, from different dats) but I don't remember seeing filenames anywhere.
## Post #5
- Username: kaspar
- Rank: n00b
- Number of posts: 15
- Joined date: Wed May 04, 2011 1:43 am
- Post datetime: 2013-07-06T09:58:29+00:00
- Post Title: FINAL FANTASY XIV: A Realm Reborn (*.DAT0;*.INDEX)

not sure this can help but.. these guys seems to be working on the same stuffs

[http://www.ffevo.net/topic/2878-ffxiv-20-dat-mining/](http://www.ffevo.net/topic/2878-ffxiv-20-dat-mining/)
## Post #6
- Username: ShadowRoze
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Jun 24, 2008 1:50 am
- Post datetime: 2013-08-22T19:03:37+00:00
- Post Title: FINAL FANTASY XIV: A Realm Reborn (*.DAT0;*.INDEX)

Hi, I've been sitting and pondering on this myself for the past couple of hours, and this far, I have a php script to decode and show an image-frame on the fly (takes some time, php is slow), however, this only works by guessing the dimensions of the image contained, and its kinda bad.
So, I thought I'd post my thoughts this far to see if anyone can fuel my thoughts.

Frame is always started with 

```
10 00 00 00 00 00 00 00
```

followed by two Int32, compressed size and uncompressed size
sometimes, the first one is 32000 and second one is the byte-count in the frame, dont know if its compressed or not, 
or what the significance of 32000 is.
Each frame is limited to 16000 bytes of uncompressed data, hence there can be a couple of frames in sequence to build a larger file
Edit: The frames themselvs seems null padded to 128 bytes, each data-segment has its own padding, which can confuse, since the last frames padding and the datasegments padding is indistinguishable at first

The segment/data headers differs a bit, so here is two I've found and guessed a bit on.
Thoughts have been partially collected from previous mentioned threads at ffevo

Data, Signature 

```
80 00 00 00 02 00 00 00
```


Guesswork:

0x16 - Int32  Number of frames to follow

Header:

```
00000030 6C 01 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 l.............................
00000060 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 ..............................
00000090 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 ..............................
00000120 00 00 00 00 00 00 00 00                                                                   ........                      

```



Frame+padding:

```
00000030 61 CE 86 0A 68 62 02 40 2C 09 65 AB 7A EA C2 C5 D5 90 D8 EA 48 6C 0D 24 B6 26 12 BB D2 09 a...hb.@,.e.z.......Hl.$.&....
00000060 C1 AE 42 62 57 23 B1 6B 90 D8 B5 48 EC 3A 38 BB C1 AE 1E 89 DD 80 C4 6E 44 62 37 21 B1 9B ..BbW#.k...H.:8........nDb7!..
00000090 11 E6 D8 B7 20 B1 5B 91 D8 6D 48 EC 76 24 76 07 9C ED 60 DF 89 C4 EE 42 62 77 23 B1 7B 90 .... .[..mH.v$v...`....Bbw#.{.
00000120 D8 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 ..............................
00000150 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 ..............................
00000180 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 ..............................
00000210 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 ..............................
00000240 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00                                           ................              

```




Data, Signature 

```
80 01 00 00 04 00 00 00
```

Total length 464

Guesswork:

```
0xD8 - Int32  Number of frames to follow

```


The data this segment holds is Gzipped DX1 Compressed Graphics data, seems to be 9 or more different images with halved size in the data.
First one is 256x256 compressed and 1024x1024 uncompressed. However, I have no clue this far, as to what parts of the header actually denotes 
the dimensions of the image, the last game had its GTEX-files for this, and that header does not seem to match the new ones

Header:

```
00000030 03 00 00 00 08 00 00 00 00 00 21 00 00 00 D0 4F 03 00 00 E3 00 00 00 00 02 00 21 00 00 00 ..........!....O..........!...
00000060 09 00 00 00 D0 32 04 00 80 42 00 00 00 80 00 00 2A 00 00 00 03 00 00 00 50 75 04 00 80 12 .....2...B......*.......Pu....
00000090 00 00 00 20 00 00 2D 00 00 00 01 00 00 00 D0 87 04 00 80 05 00 00 00 08 00 00 2E 00 00 00 ... ..-.......................
00000120 01 00 00 00 50 8D 04 00 00 02 00 00 00 02 00 00 2F 00 00 00 01 00 00 00 50 8F 04 00 00 01 ....P.........../.......P.....
00000150 00 00 80 00 00 00 30 00 00 00 01 00 00 00 50 90 04 00 80 00 00 00 20 00 00 00 31 00 00 00 ......0.......P....... ...1...
00000180 01 00 00 00 D0 90 04 00 80 00 00 00 08 00 00 00 32 00 00 00 01 00 00 00 50 91 04 00 80 00 ................2.......P.....
00000210 00 00 08 00 00 00 33 00 00 00 01 00 00 00 D0 91 04 00 80 00 00 00 08 00 00 00 34 00 00 00 ......3...................4...
00000240 01 00 00 00 00 16 80 1A 80 19 00 17 00 1A 00 17 80 18 80 1A 00 08 80 19 00 1F 80 24 00 22 ...........................$."
00000270 00 21 00 20 00 1B 00 0B 00 22 80 1B 00 21 00 23 00 27 00 1D 80 1F 80 0F 80 18 00 17 80 17 .!. ....."...!.#.'............
00000300 00 19 80 1B 00 15 80 0F 00 08 00 1B 80 1A 00 1B 00 20 00 1C 80 22 80 18 80 18 00 03 80 20 ................. ..."....... 
00000330 80 20 80 01 80 12 80 05 00 02 00 01 80 00 80 00 80 00 80 00 00 00 00 00 00 00 00 00 00 00 . ............................
00000360 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 80 00 20 34 ............................ 4
00000390 00 00 00 04 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 50 00 00 00 50 00 08 00 ......................P...P...
00000420 50 00 0A 00 50 80 0A 00 50 A0 0A 00 50 A8 0A 00 50 AA 0A 00 D0 AA 0A 00 F0 AA 0A 00 F8 AA P...P...P...P...P.............
00000450 0A 00 00 AB 0A 00 00 00 00 00 00 00 00 00                                                 ..............                

```


Frame start, frame length: 5606:

```
00000030 EC 69 5A 51 D2 13 CB 63 83 C7 34 87 8C CF 26 65 4C 93 B1 46 A2 27 1E 7A 4E B0 88 8D 19 A5 .iZQ...c..4...&eL..F.'.zN.....
00000060 35 D6 98 14 A4 6C 1C 50 F6 6C B0 48 24 CF 18 38 C1 6C DD C5 71 D3 DA A4 06 3D 8C 91 B2 51 5....l.P.l.H$..8.l..q....=...Q
00000090 76 69 69 C2 6B 40 B2 79 65 BB F1 36 E5 11 43 8A B1 64 1E A6 BB 36 0F 1B 5B 96 E6 EE BD 22 vii.k@.ye..6..C..d...6..[...."
00000120 A5 B4 3C 6C 88 E9 92 9E 9D 7F BE 73 67 EE DC B9 8F EF 7E BF DF F7 7D 77 7A B4 3A 1D 50 46 ..<l.......sg.....~...}wz.:.PF
00000150 CB 53 D2 E6 52 00 54 01 57 46 0E 09 C0 F9 00 41 66 43 09 14 0C 4B C1 A0 04 0F 9A 74 6B C3 .S..R.T.WF.....AfC...K.....tk.
00000180 99 50 C8 7F 2C E3 05 D9 05 B0 28 E3 05 06 16 00 A7 60 60 05 28 95 EB F5 89 02 02 96 83 B1 .P..,.....(......``.(.........
00000210 07 75 3C F7 2A 0D 6C 25 87 E6 ...                                                         .u<.*.l%..                    

```



Any suggestions?
## Post #7
- Username: ShadowRoze
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Jun 24, 2008 1:50 am
- Post datetime: 2013-08-23T11:22:05+00:00
- Post Title: FINAL FANTASY XIV: A Realm Reborn (*.DAT0;*.INDEX)

Some new stuff
The File entries seems to begin with the length of its header, followed by the type of content, 2 seems to be whatever data, where 4 is a texture, this is significant cause all 4-types have an additional 80-byte header before its first frame, suggested to be the image header.
This header alsto contains the width/height of the uncompressed image, this far, I have found no hint to any compressed width/height.
Also, this header most probably also specifies the image encoding used, have yet to find that thou.
Images is as in last game, mostly DX1 and DX5 encoded

Furthermore, without the index-files, these data-files are more or less useless, sure you can iterate over them and bruteforceing your way over padded area, but the file-block padding does not seem coherent and thus I am not able to calculate it, however, the index-files points exactly to a file entry in the dat-files, making iteration of just dat-elements kind of pointless.
## Post #8
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2013-08-24T20:21:19+00:00
- Post Title: FINAL FANTASY XIV: A Realm Reborn (*.DAT0;*.INDEX)

UPDATED AGAIN:
In the 2.6GB Benchmark, I can extract many many of the .DAT0 files using just the SQDB files.
Use these QuickBMS scripts on the .SQDB files, and when it asks you what other file you want to open, type in the name of the .DAT0 file. Note that some .DAT0 files may contain different types of files. These scripts will extract the Type2, Type3, and Type4 subfiles. Also if the script crashes it has already reached the end of the file.:
For the Type2 files

```
log MEMORY_FILE1 0 0 ;
log MEMORY_FILE2 0 0 ;
log MEMORY_FILE3 0 0 ;
ComType deflate_noerror ;
Get QT ASIZE 0 ;
Math QQT = QT ;
Math QQT += 0x8 ;
Math foxhound = 1 ;
GoTo 0x800 0 ;
SavePos base 0 ;
Do ;
GoTo base 0 ;
Get null Long 0 ;
Get foxhound Long 0 ;
Math pos = foxhound ;
Math pos *= 0x80 ;
GoTo base 0 ;
GoTo 0x18 0 SEEK_CUR ;
Get name String 0 ;
Math base += 0x108 ;
If base < QT ;
GoTo base 0 ;
Get null Long 0 ;
Get foxhound Long 0 ;
Else ;
Math foxhound = 0 ;
EndIF ;
GoTo pos 1 ;
GoTo 0x14 1 SEEK_CUR ;
Get files Long 1 ;
SavePos ztable 1 ;
GoTo pos 1 ;
GoTo 0x4 1 SEEK_CUR ;
Get jump Long 1 ;
If jump != 2 ;
Math foxfox = 0 ;
Math files = 0 ;
Else ;
Math foxfox = 1 ;
GoTo pos 1 ;
Get adj Long 1 ;
GoTo pos 1 ;
GoTo adj 1 SEEK_CUR ;
SavePos filebase 1 ;
EndIF ;


For x = 1 To files ;
If foxfox != 0 ;
GoTo ztable 1 ;
Get jump Long 1 ;
Get zsize Short 1 ;
Get size Short 1 ;
SavePos ztable 1 ;
GoTo filebase 1 ;
GoTo jump 1 SEEK_CUR ;
Get null Long 1 ;
Get null Long 1 ;
Get zsize Long 1 ;
Get size Long 1 ;
SavePos offset 1 ;
EndIF ;
If foxfox != 0 ;
Append ;
CLog MEMORY_FILE2 offset zsize size 1 ;
Append ;
EndIF ;
Next x ;
If foxfox != 0 ;
Get total ASIZE MEMORY_FILE2 ;
Log name 0 total MEMORY_FILE2 ;
EndIF ;
log MEMORY_FILE2 0 0 ;
If foxhound = 0 ;
CleanExit ;
EndIF ;
While base < QT ;
```


For the Type3 files:

```
log MEMORY_FILE1 0 0 ;
log MEMORY_FILE2 0 0 ;
log MEMORY_FILE3 0 0 ;
ComType deflate_noerror ;
Get QT ASIZE 0 ;
Math QQT = QT ;
Math QQT += 0x8 ;
Math foxhound = 1 ;
GoTo 0x800 0 ;
SavePos base 0 ;
For z = 1 To 123456789 ;
GoTo base 0 ;
Get null Long 0 ;
Get foxhound Long 0 ;
Math pos = foxhound ;
Math pos *= 0x80 ;
GoTo base 0 ;
GoTo 0x18 0 SEEK_CUR ;
Get name String 0 ;
Math base += 0x108 ;
If base < QT ;
GoTo base 0 ;
Get null Long 0 ;
Get foxhound Long 0 ;
Else ;
Math foxhound = 0 ;
EndIF ;
GoTo pos 1 ;
GoTo 0x14 1 SEEK_CUR ;
Get files Short 1 ;
Get jump Short 1 ;
SavePos ztable 1 ;
GoTo pos 1 ;
GoTo 0x4 1 SEEK_CUR ;
Get jump Long 1 ;
If jump != 3 ;
Math foxfox = 0 ;
Math files = 0 ;
Else ;
Math files = 1 ;
Math foxfox = 1 ;
GoTo pos 1 ;
Get adj Long 1 ;
GoTo pos 1 ;
GoTo adj 1 SEEK_CUR ;
SavePos filebase 1 ;
GoTo pos 1 ;
GoTo 0xC 1 SEEK_CUR ;
Get max Long 1 ;
Math max *= 0x80 ;
Math max += pos ;
EndIF ;


For x = 1 To files ;
GoTo filebase 1 ;
SavePos near 1 ;
Math far = near ;
Math far -= 4 ;
GoTo far 1 ;
SavePos far 1 ;
Do ;
GoTo far 1 ;
findloc far string "\x10\x00\x00\x00\x00\x00\x00\x00" 1 QT ;
GoTo far 1 ;
GoTo 0x8 1 SEEK_CUR ;
SavePos far 1 ;
Get zsize Long 1 ;
Get size Long 1 ;
SavePos offset 1 ;
If far < max ;
Append ;
CLog MEMORY_FILE2 offset zsize size 1 ;
Append ;
EndIF ;
While far < max ;
Next x ;
If foxfox != 0 ;
Get total ASIZE MEMORY_FILE2 ;
Log name 0 total MEMORY_FILE2 ;
EndIF ;
log MEMORY_FILE2 0 0 ;
If base > QT ;
CleanExit ;
EndIF ;
GoTo base 0 ;
Get null Long 0 ;
Get test Long 0 ;
If test = 0 ;
CleanExit ;
EndIF ;
Next z ;
```


For the Type4 files:

```
log MEMORY_FILE1 0 0 ;
log MEMORY_FILE2 0 0 ;
log MEMORY_FILE3 0 0 ;
ComType deflate_noerror ;
Get QT ASIZE 0 ;
Math QQT = QT ;
Math QQT += 0x8 ;
Math foxhound = 1 ;
GoTo 0x800 0 ;
SavePos base 0 ;
Do ;
GoTo base 0 ;
Get null Long 0 ;
Get foxhound Long 0 ;
Math pos = foxhound ;
Math pos *= 0x80 ;
GoTo base 0 ;
GoTo 0x18 0 SEEK_CUR ;
Get name String 0 ;
Math base += 0x108 ;
If base < QT ;
GoTo base 0 ;
Get null Long 0 ;
Get foxhound Long 0 ;
Else ;
Math foxhound = 0 ;
EndIF ;
GoTo pos 1 ;
GoTo 0x14 1 SEEK_CUR ;
Get files Short 1 ;
Get jump Short 1 ;
SavePos ztable 1 ;
GoTo pos 1 ;
GoTo 0x4 1 SEEK_CUR ;
Get jump Long 1 ;
If jump != 4 ;
Math foxfox = 0 ;
Math files = 0 ;
Else ;
Math foxfox = 1 ;
GoTo pos 1 ;
Get adj Long 1 ;
GoTo pos 1 ;
GoTo adj 1 SEEK_CUR ;
SavePos filebase 1 ;
EndIF ;


For x = 1 To files ;
If foxfox != 0 ;
GoTo ztable 1 ;
Get jump Long 1 ;
Get null Long 1 ;
Get null Long 1 ;
Get null Long 1 ;
Get f2 Long 1 ;
SavePos ztable 1 ;
GoTo filebase 1 ;
GoTo jump 1 SEEK_CUR ;
SavePos near 1 ;
Math far = near ;
Math far -= 4 ;
Else ;
Math f2 = 0 ;
EndIF ;
For y = 1 To f2 ;
GoTo far 1 ;

findloc far string "\x10\x00\x00\x00\x00\x00\x00\x00" 1 0 ;
GoTo far 1 ;
GoTo 0x8 1 SEEK_CUR ;
SavePos far 1 ;
Get zsize Long 1 ;
Get size Long 1 ;
SavePos offset 1 ;
Append ;
CLog MEMORY_FILE2 offset zsize size 1 ;
Append ;
Next y ;
Next x ;
If foxfox != 0 ;
Get total ASIZE MEMORY_FILE2 ;
Log name 0 total MEMORY_FILE2 ;
EndIF ;
log MEMORY_FILE2 0 0 ;
If foxhound = 0 ;
CleanExit ;
EndIF ;
While base < QT ;
```

I need to make a new script for the remaining file  types (Type1? Type5?).
## Post #9
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-11T17:50:14+00:00
- Post Title: FINAL FANTASY XIV: A Realm Reborn (*.DAT0;*.INDEX)

W.I.P

Example : Loaded 050000.win32.dat0 (contained shaders)

FolderHash\FileNameHash



Current status: Problem with hashes. Don't know how it works. Someone has information about hashes?
## Post #10
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2013-09-11T21:13:40+00:00
- Post Title: FINAL FANTASY XIV: A Realm Reborn (*.DAT0;*.INDEX)

> Reply from Ekey
>
> W.I.P

Example : Loaded 050000.win32.dat0 (contained shaders)

FolderHash\FileNameHash



Current status: Problem with hashes. Don't know how it works. Someone has information about hashes?

With ALL DUE RESPECT, the NEW (not the old), benchmark, contains BOTH HASHES, and ASCII FILENAMES.
If you are serious about figuring out the hashes reverse them, using the NEW benchmark.
## Post #11
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-11T22:15:52+00:00
- Post Title: FINAL FANTASY XIV: A Realm Reborn (*.DAT0;*.INDEX)

> Reply from FurryFan
>
> 
With ALL DUE RESPECT, the NEW (not the old), benchmark, contains BOTH HASHES, and ASCII FILENAMES.
If you are serious about figuring out the hashes reverse them, using the NEW benchmark.
Yeah i have latest benchmark. All file names with hashes contained in SQDB files but FFXIV client does not have them. I found 2 hash algos, CRC32 and FNV-1a. Through CRC passing full file name with path like chara/human/c0701/animation/f0002/nonresident/emot/huh.pap but index contained 2 hashes : FolderHashName and FileHashName. Something like this:

FolderHashName : chara/human/c0701/animation/f0002/nonresident/emot/
FileHashName : huh.pap

[Here](http://www.sendspace.com/file/ry8uko) i collected all hashes with file names from benchmark.
## Post #12
- Username: SirLoon
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 19, 2009 12:26 am
- Post datetime: 2013-09-16T21:36:51+00:00
- Post Title: FINAL FANTASY XIV: A Realm Reborn (*.DAT0;*.INDEX)

hi, did somebody find something about lua scripts? by viewing ffxiv.exe I know that lua 5.1.x is binded and scripts are loaded. Problem is i dont know path which are scripts using and main event name- ie OnLoad, OnGameStart etc. Can someone extract all *.lua or *.luac files please? Thanks
## Post #13
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-25T08:05:08+00:00
- Post Title: FINAL FANTASY XIV: A Realm Reborn (*.DAT0;*.INDEX)

WIP - Now dirs and file names can be detected
## Post #14
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-10-01T04:32:25+00:00
- Post Title: FINAL FANTASY XIV: A Realm Reborn (*.DAT0;*.INDEX)

I'm going to see if i can dump the vertex info from memory.

They use .TEX textures apparently
004A40A0   68 683DF100      PUSH ffxiv.00F13D68                      ; ASCII "common/graphics/texture/-dither.tex"

K dumping all the textures see how this goes



[http://cra0kalo.com/upload/staging/store/push/raw1](http://cra0kalo.com/upload/staging/store/push/raw1)
## Post #15
- Username: alexfilth
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Oct 17, 2011 10:00 am
- Post datetime: 2013-10-31T05:09:48+00:00
- Post Title: FINAL FANTASY XIV: A Realm Reborn (*.DAT0;*.INDEX)

Hey Ekey, are you still working on the unpacker? I think you're the only hope for an unpacker with name detection.
## Post #16
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2013-11-14T01:47:13+00:00
- Post Title: Re: FINAL FANTASY XIV: A Realm Reborn (*.DAT0;*.INDEX)

Nice work Ekay, i look forward to using this when it's in a releasable state, been wanting to get a hold of a few weapon models for IRL re-creation.

on a side note, has anyone figured out how to access the data relating to your characters 3d model and which separate parts it loads onto a skeleton to create your ingame character?
## Post #17
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2014-09-18T22:50:50+00:00
- Post Title: Re: FINAL FANTASY XIV: A Realm Reborn (*.DAT0;*.INDEX)

any way to convert SEDBSSCF header please
## Post #18
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2014-10-29T11:37:15+00:00
- Post Title: Re: FINAL FANTASY XIV: A Realm Reborn (*.DAT0;*.INDEX)

up for news please
## Post #19
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-10-29T14:23:07+00:00
- Post Title: Re: FINAL FANTASY XIV: A Realm Reborn (*.DAT0;*.INDEX)

[http://www.ffevo.net/topic/2878-ffxiv-2 ... ing/page-6](http://www.ffevo.net/topic/2878-ffxiv-20-dat-mining/page-6)
