## Post #1
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2022-10-31T11:04:00+00:00
- Post Title: Star Ocean: The Divine Force

[https://github.com/wmltogether/CriPakTools/releases](https://github.com/wmltogether/CriPakTools/releases)


[https://github.com/hellman/xortool](https://github.com/hellman/xortool)

```
xortool -l 4 -c 00 m3.asf
```



```
comtype zstd

get NAME basename
string NAME += .asf

idstring "SLZ"
get VER byte
get unk_0 long
get dataSize long
get unk_1 long
get decompressed_size long

set temp decompressed_size
math temp += 0xFFFF
set remainder temp
math remainder % 0xFFFF
math temp - remainder
set chunks temp
math chunks / 0xFFFF

#print "number of chunks: %chunks%"

get unk_2 long
get unk_3 long
get unk_4 long
get unk_5 long
get unk_6 long

get fileSize long
get unk_7 long

append
for i = 0 < chunks
	get ZSIZE short
	savepos OFFSET
	clog MEMORY_FILE OFFSET ZSIZE 0x10000
	math OFFSET + ZSIZE
	goto OFFSET
	next i
log NAME 0 decompressed_size MEMORY_FILE
```
## Post #2
- Username: Henry33
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Oct 31, 2022 2:12 pm
- Post datetime: 2022-10-31T12:18:49+00:00
- Post Title: Star Ocean: The Divine Force

Hello and thank you very much for sharing.
## Post #3
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2022-11-01T13:00:42+00:00
- Post Title: Star Ocean: The Divine Force

Do any one  have the  Star Ocean The Divine Force files.
## Post #4
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2022-11-02T23:23:05+00:00
- Post Title: Star Ocean: The Divine Force

I see some of the asf files throw an error about compressed data being bigger than allocated buffer:

```
--------------------------------------
Info:  algorithm   478
       offset      01dde25e
       input size  0x000004c8 1224
       output size 0x00010000 65536
       result      0xfffffff6 -10

Error: uncompressed data (-10) bigger than allocated buffer (65536)
       It usually means that data is not compressed or uses another algorithm

Last script line before the error or that produced the error:
  37  clog MEMORY_FILE OFFSET ZSIZE 0x10000

- OFFSET       0x01dde25e
- ZSIZE        0x000004c8
- SIZE         0x00010000
  coverage file 0    80%   31385382   39224864   . offset 01dde726
  coverage file -1    0%   0          90570752   . offset 05660000
```


Also, for the files that were successfully decompressed I havent been able to locate a model viewer for them, the one I know is the tool from akderebur for Star Ocean Anamnesis and this game seems to use a similar format, is there a working importer or viewer anywhere?
## Post #5
- Username: winner25
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Apr 21, 2022 2:53 pm
- Post datetime: 2022-11-04T17:16:03+00:00
- Post Title: Star Ocean: The Divine Force

> Reply from GDL ↑Thu Nov 03, 2022 7:23 am at Thu Nov 03, 2022 7:23 am
>
> 
I see some of the asf files throw an error about compressed data being bigger than allocated buffer:
Code: Select all  offset   filesize   filename
--------------------------------------
Info:  algorithm   478
       offset      01dde25e
       input size  0x000004c8 1224
       output size 0x00010000 65536
       result      0xfffffff6 -10

Error: uncompressed data (-10) bigger than allocated buffer (65536)
       It usually means that data is not compressed or uses another algorithm

Last script line before the error or that produced the error:
  37  clog MEMORY_FILE OFFSET ZSIZE 0x10000

- OFFSET       0x01dde25e
- ZSIZE        0x000004c8
- SIZE         0x00010000
  coverage file 0    80%   31385382   39224864   . offset 01dde726
  coverage file -1    0%   0          90570752   . offset 05660000

Also, for the files that were successfully decompressed I havent been able to locate a model viewer for them, the one I know is the tool from akderebur for Star Ocean Anamnesis and this game seems to use a similar format, is there a working importer or viewer anywhere?

I try to use akderebur'tool to export the asf files but failed.
So，it looks like also need a tool to export the modles and textures
## Post #6
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2022-11-12T16:37:02+00:00
- Post Title: Star Ocean: The Divine Force

I've only extracted 2 files.
I used the -e option with QuickBMS to ignore errors.
## Post #7
- Username: winner25
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Apr 21, 2022 2:53 pm
- Post datetime: 2022-11-14T10:53:22+00:00
- Post Title: Star Ocean: The Divine Force

> Reply from TheDude ↑Sun Nov 13, 2022 12:37 am at Sun Nov 13, 2022 12:37 am
>
> 
I've only extracted 2 files.
I used the -e option with QuickBMS to ignore errors.

cool ! nice work! Hope you can extract more files!
## Post #8
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2022-11-20T16:51:02+00:00
- Post Title: Star Ocean: The Divine Force

I'm posting this in hopes someone can figure it out.
[https://mega.nz/file/g5xEgI4T#LJro390SU ... 4ukAjxYtbk](https://mega.nz/file/g5xEgI4T#LJro390SUk11qd3YogEY505vdcs24GQGA4ukAjxYtbk)
They've done something to the vertex data.
Also, it seems to always have a 188 byte section at the beginning.
## Post #9
- Username: winner25
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Apr 21, 2022 2:53 pm
- Post datetime: 2022-12-07T07:30:38+00:00
- Post Title: Star Ocean: The Divine Force

Is there no way to extract the 3d modle  of the game?
## Post #10
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2022-12-07T14:21:59+00:00
- Post Title: Star Ocean: The Divine Force

I needs more of them brain percentages.


EDIT:
Did anyone do anything with SO5?
That looks possible.
## Post #11
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2022-12-07T20:09:40+00:00
- Post Title: Star Ocean: The Divine Force

> Reply from TheDude ↑Wed Dec 07, 2022 10:21 pm at Wed Dec 07, 2022 10:21 pm
>
> 
Did anyone do anything with SO5?
That looks possible.

my understanding of this is that they always use the same formats for all their games (or similar formats), last I saw was SO Anamnesis which includes models from previos titles and some crossovers, I dont remmember anyone creating an importer/exporter for SO5 models
## Post #12
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2023-01-17T13:38:21+00:00
- Post Title: Star Ocean: The Divine Force

Here's a texture I can't figure out:
[https://mega.nz/file/IoYwGJra#YAjZVNlnM ... OXmxRlYpLY](https://mega.nz/file/IoYwGJra#YAjZVNlnMdeTMPZHA9muAoSaMa7Yn9DEAOXmxRlYpLY)

The closest I got to making it look like something was decoding it as EAC-RG11.
## Post #13
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2023-01-17T15:45:15+00:00
- Post Title: Star Ocean: The Divine Force

@TheDude : That's BC5 (ATI2) compression. You can use [rawtex](https://forum.xentax.com/viewtopic.php?t=16461) for quick guessing if you know where raw data starts in a file.
## Post #14
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2023-01-17T19:42:42+00:00
- Post Title: Star Ocean: The Divine Force

I was opening the dds file that Rawtex output, all black, it must not be that format. Wrong.
Turns out that XnView doesn't support BC5.  
Plus the python module I was using ([https://github.com/K0lb3/tex2img](https://github.com/K0lb3/tex2img)) didn't decode it properly.
So both of those were working together to get me confused.
This one ([https://libraries.io/pypi/texture2ddecoder](https://libraries.io/pypi/texture2ddecoder)) worked though.

Also the BC6 images are all less than 100 nits brightness. What's the point then?
