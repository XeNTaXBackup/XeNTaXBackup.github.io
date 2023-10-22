## Post #1
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2009-07-16T16:46:21+00:00
- Post Title: RE5 Benchmark

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Gocha
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-16T20:13:17+00:00
- Post Title: RE5 Benchmark

Here is a quickbms script extractor for the pc demo.

```
get VERSION short
get FILES short
for i = 0 < FILES
getdstring NAME 0x40
get UNK1 long
get ZSIZE long
get SIZE 3
get NSIZE byte
get OFFSET long
clog NAME OFFSET ZSIZE SIZE
next i

```


The unk1 tells what the extension of the file is I will update the script to support this feature soon.
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-17T02:46:27+00:00
- Post Title: RE5 Benchmark

Here is a normal and converted texture they just seem to be dds files with a custom header.
[http://www.MegaShare.com/1260160](http://www.MegaShare.com/1260160)
## Post #4
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2009-07-17T09:05:32+00:00
- Post Title: RE5 Benchmark

That's great work chrrox but how to convert other files?

And main goal - how to decode msg files? it's somehow crypted
headers are "MSG2@"
## Post #5
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2009-07-17T09:15:34+00:00
- Post Title: RE5 Benchmark

Try out my Devil May Cry 4 MSG2Editor:
[viewtopic.php?f=10&t=3057&start=60](http://forum.xentax.com/viewtopic.php?f=10&t=3057&start=60)

Maybe works. (I don't have the RE5 Benchmark yet.)
Or upload a MSG2 file.
## Post #6
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2009-07-17T09:38:21+00:00
- Post Title: RE5 Benchmark

i can't fine any .msg2 files in
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-17T22:49:00+00:00
- Post Title: RE5 Benchmark

updated bms script that supports extensions. I ahte capcom they are evil.

```
get VERSION short
get FILES short

for i = 0 < FILES

set MOD string .mod
set RTX string .dds
set DDS string .dds
set DXT string .dds
set SREQ string .sreq
set STRQ string .strq
set XFS string .xfs
set XFS2 string .xfs2
set XFS3 string .xfs3
set XFS4 string .xfs4
set XFS5 string .xfs5
set XFS6 string .xfs6
set XFS7 string .xfs7
set XFS8 string .xfs8
set XFS9 string .xfs9
set XFS10 string .xfs10
set XFS11 string .xfs11
set WAY string .way
set NAV string .nav
set NAV2 string .nav2
set SPAC string .spac
set EFS string .efs
set EAN string .ean
set EFL string .efl
set SDL string .sdl
set SBC1 string .sbc1
set E2D string .e2d
set WAAW string .waaw
set UNK string .unk

getdstring NAME 0x40
get TYPE long
get ZSIZE long
get SIZE 3
get NSIZE byte
get OFFSET long


if TYPE == 1486968918
string NAME += MOD
else if TYPE == 606035435
string NAME += RTX
else if TYPE == 2013850128
string NAME += DDS
else if TYPE == 466372966
string NAME += SREQ
else if TYPE == 377338879
string NAME += STRQ
else if TYPE == 1448649048
string NAME += DXT
else if TYPE == 355479284
string NAME += XFS
else if TYPE == 1706194405
string NAME += XFS2
else if TYPE == 1486386332
string NAME += XFS3
else if TYPE == 60649970
string NAME += XFS4
else if TYPE == 955674563
string NAME += XFS5
else if TYPE == 24794381
string NAME += XFS6
else if TYPE == 644778641
string NAME += XFS7
else if TYPE == 1476572159
string NAME += XFS8
else if TYPE == 517025563
string NAME += XFS9
else if TYPE == 1723094544
string NAME += XFS10
else if TYPE == 1300843869
string NAME += XFS11
else if TYPE == 1597421145
string NAME += WAY
else if TYPE == 1988234625
string NAME += NAV
else if TYPE == 1324456003
string NAME += NAV2
else if TYPE == 2117312876
string NAME += SPAC
else if TYPE == 42153731
string NAME += EFS
else if TYPE == 1312388119
string NAME += EAN
else if TYPE == 1834674260
string NAME += EFL
else if TYPE == 1275967545
string NAME += SDL
else if TYPE == 1375500191
string NAME += SBC1
else if TYPE == 661514423
string NAME += E2D
else if TYPE == 42153731
string NAME += WAAW
else
string NAME += UNK
endif

clog NAME OFFSET ZSIZE SIZE

next i
```
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-18T00:33:33+00:00
- Post Title: RE5 Benchmark

Sorry Here is an updated script to handle more extensions. if any .unk appear let me know where they are located and ill add them

```
get VERSION short
get FILES short

for i = 0 < FILES

set MOD string .mod
set RTX string .dds
set DDS string .dds
set DXT string .dds
set SREQ string .sreq
set STRQ string .strq
set XFS string .xfs
set XFS2 string .xfs2
set XFS3 string .xfs3
set XFS4 string .xfs4
set XFS5 string .xfs5
set XFS6 string .xfs6
set XFS7 string .xfs7
set XFS8 string .xfs8
set XFS9 string .xfs9
set XFS10 string .xfs10
set XFS11 string .xfs11
set XFS12 string .xfs12
set XFS13 string .xfs13
set XFS14 string .xfs14
set XFS15 string .xfs15
set XFS16 string .xfs16
set XFS17 string .xfs17
set XFS18 string .xfs18
set XFS19 string .xfs19
set XFS20 string .xfs20
set WAY string .way
set MTG string .mtg
set NAV string .nav
set CHN string .chn
set CCl string .ccl
set NAV2 string .nav2
set SPAC string .spac
set EFS string .efs
set EAN string .ean
set EFL string .efl
set SDL string .sdl
set SBC1 string .sbc1
set E2D string .e2d
set WAAW string .waaw
set HIT string .hit
set UNK string .unk

getdstring NAME 0x40
get TYPE long
get ZSIZE long
get SIZE 3
get NSIZE byte
get OFFSET long
math COUNTER += 1


if TYPE == 1486968918
string NAME += MOD
else if TYPE == 606035435
string NAME += RTX
else if TYPE == 2013850128
string NAME += DDS
else if TYPE == 466372966
string NAME += SREQ
else if TYPE == 377338879
string NAME += STRQ
else if TYPE == 1448649048
string NAME += DXT
else if TYPE == 1597421145
string NAME += WAY
else if TYPE == 1988234625
string NAME += NAV
else if TYPE == 1324456003
string NAME += NAV2
else if TYPE == 2117312876
string NAME += SPAC
else if TYPE == 42153731
string NAME += EFS
else if TYPE == 1312388119
string NAME += EAN
else if TYPE == 1834674260
string NAME += EFL
else if TYPE == 1275967545
string NAME += SDL
else if TYPE == 1375500191
string NAME += SBC1
else if TYPE == 661514423
string NAME += E2D
else if TYPE == 42153731
string NAME += WAAW
else if TYPE == 39055687
string NAME += HIT
else if TYPE == 1043739205
string NAME += CHN
else if TYPE == 2549759
string NAME += CCL
else if TYPE == 1311764278
string NAME += MTG
else if TYPE == 355479284
string NAME += XFS
else if TYPE == 1706194405
string NAME += XFS2
else if TYPE == 1486386332
string NAME += XFS3
else if TYPE == 60649970
string NAME += XFS4
else if TYPE == 955674563
string NAME += XFS5
else if TYPE == 24794381
string NAME += XFS6
else if TYPE == 644778641
string NAME += XFS7
else if TYPE == 1476572159
string NAME += XFS8
else if TYPE == 517025563
string NAME += XFS9
else if TYPE == 1723094544
string NAME += XFS10
else if TYPE == 1300843869
string NAME += XFS11
else if TYPE == 756211846
string NAME += XFS12
else if TYPE == 466372966
string NAME += XFS13
else if TYPE == 229485410
string NAME += XFS14
else if TYPE == 519773031
string NAME += XFS15
else if TYPE == 1972055735
string NAME += XFS16
else if TYPE == 464002364
string NAME += XFS17
else if TYPE == 578958861
string NAME += XFS18
else if TYPE == 1285711912
string NAME += XFS19
else if TYPE == 121863374
string NAME += XFS20
else
string NAME += UNK
string NAME += COUNTER
endif

clog NAME OFFSET ZSIZE SIZE

next i

```
## Post #9
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2009-07-18T08:05:38+00:00
- Post Title: RE5 Benchmark

im nub  what i can do with those

nwm get it  gonna check it

there are some .unk files 

\stage\s114\havok
\stage\s114\light
\stage\s114\map

also the dmc4model don't work well for re5 , i can't import in any 3d program / invalid vertex
## Post #10
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-18T10:12:56+00:00
- Post Title: RE5 Benchmark

You need to convert the .mod files I can view them fine in any 3d program.
## Post #11
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2009-07-18T11:12:11+00:00
- Post Title: RE5 Benchmark

uhm how ? ... some1 said dmc4model works ( on this forum )
## Post #12
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-18T17:11:03+00:00
- Post Title: RE5 Benchmark

I got it to load the decompressed files just edit the arc file and replace the name with something else and it will look for the real file instead of the arc file.
make sure you edit my script to change .dds to .tex so it can find the files.
## Post #13
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2009-07-18T17:31:02+00:00
- Post Title: RE5 Benchmark

dunno  tex files works , but i still can't import obj files
## Post #14
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-18T17:57:15+00:00
- Post Title: RE5 Benchmark

you have to convert the .mod files into .obj files with the devil may cry 4 converter
there is little point anyway as there are no texture cordiantes supported yet in that converter.
## Post #15
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2009-07-18T18:03:01+00:00
- Post Title: RE5 Benchmark

im using the dmc4model , but i can't import them , well it's the same problem @ dmc4 with the textures ...
## Post #16
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-18T20:10:55+00:00
- Post Title: Re: RE5 Benchmark

What program are you trying to open the obj with?
PS the first re5 mod 
[http://img505.imageshack.us/img505/1518/re2t.jpg](http://img505.imageshack.us/img505/1518/re2t.jpg)
## Post #17
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2009-07-18T21:51:59+00:00
- Post Title: Re: RE5 Benchmark

maya / 3dsmax / lightwave / milkshape
## Post #18
- Username: Gocha
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-26T01:29:24+00:00
- Post Title: Re: RE5 Benchmark

here is my wip re5 extractor and texture converter.

```
get VERSION short
get FILES short

 set MEMORY_FILE2 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x0A\x00\x00\x04\x00\x00\x00\x04\x00\x00\x00\x00\x08\x00\x00\x00\x00\x00\x0B\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x05\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
 set MEMORY_FILE3 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x0A\x00\x00\x02\x00\x00\x00\x02\x00\x00\x00\x00\x04\x00\x00\x00\x00\x00\x0A\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x05\x00\x00\x00\x44\x58\x54\x35\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
 set MEMORY_FILE4 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x0A\x00\x00\x02\x00\x00\x00\x04\x00\x00\x00\x00\x04\x00\x00\x00\x00\x00\x0B\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x05\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
 set MEMORY_FILE5 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x0A\x00\x00\x02\x00\x00\x00\x02\x00\x00\x00\x00\x04\x00\x00\x00\x00\x00\x0A\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x05\x00\x00\x00\x44\x58\x54\x35\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
 set MEMORY_FILE6 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x0A\x00\x00\x01\x00\x00\x00\x02\x00\x00\x00\x00\x02\x00\x00\x00\x00\x00\x0A\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x05\x00\x00\x00\x44\x58\x54\x35\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
 set MEMORY_FILE7 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x02\x00\x00\x02\x00\x00\x00\x02\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x0A\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
 set MEMORY_FILE8 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x02\x00\x00\x01\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x09\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x35\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
 set MEMORY_FILE9 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x0A\x00\x00\x01\x00\x00\x00\x02\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x0A\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x05\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
set MEMORY_FILE10 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x0A\x00\x00\x01\x00\x00\x00\x01\x00\x00\x00\x80\x00\x00\x00\x00\x00\x00\x09\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x05\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
set MEMORY_FILE11 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x02\x00\x80\x00\x00\x00\x00\x02\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x0A\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
set MEMORY_FILE12 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x02\x00\x80\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x09\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x35\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
set MEMORY_FILE13 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x02\x00\x00\x02\x00\x00\x00\x04\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x0B\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x35\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
set MEMORY_FILE14 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x02\x00\x00\x04\x00\x00\x00\x08\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x0C\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
set MEMORY_FILE15 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x02\x00\x00\x02\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x0A\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x35\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
set MEMORY_FILE16 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x02\x00\x40\x00\x00\x00\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x07\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
set MEMORY_FILE17 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x02\x00\x40\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x09\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x35\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
set MEMORY_FILE18 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x02\x00\x00\x01\x00\x00\x00\x04\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x0B\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
set MEMORY_FILE19 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x02\x00\x80\x00\x00\x00\x00\x02\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x0A\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x35\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
set MEMORY_FILE20 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x02\x00\x00\x04\x00\x00\x80\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x0B\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
set MEMORY_FILE21 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x02\x00\x00\x02\x00\x00\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x0A\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
set MEMORY_FILE22 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x02\x00\x80\x00\x00\x00\x80\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x35\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"

#set MEMORY_FILE23 binary ""

#set MEMORY_FILE24 binary ""


for i = 0 < FILES

    getdstring NAME 0x40
    get TYPE1 long
    get ZSIZE long
    get SIZE 3
    get NSIZE byte
    get OFFSET long
    math COUNTER += 1

    clog MEMORY_FILE OFFSET ZSIZE SIZE

    getdstring TYPE 4 MEMORY_FILE
print "%SIZE%"

    if TYPE == "MOD"
       string NAME += ".mod"
else if TYPE == "RTX"
       string NAME += ".rtx"
else if TYPE == "WààW"
       string NAME += ".waaw"
else if TYPE == "XFS"
       string NAME += ".xfs"
else if TYPE == "SDL"
       string NAME += ".sdl"
else if TYPE == "SREQ"
       string NAME += ".sreq"
else if TYPE == "SBC1"
       string NAME += ".sbc1"
else if TYPE == "NAV"
       string NAME += ".nav"
else if TYPE == "WAY"
       string NAME += ".way"
else if TYPE == "STRQ"
       string NAME += ".strq"
else if TYPE == "SPAC"
       string NAME += ".spac"
else if TYPE == "DNRS"
       string NAME += ".dnrs"
else if TYPE == "LCM"
       string NAME += ".lcm"
else if TYPE == "LMT"
       string NAME += ".lmt"
else if TYPE == "EFL"
       string NAME += ".efl"
	endif
    if SIZE == "699148"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE2
        math SIZE -= 0x54
        log NAME 0x54 SIZE MEMORY_FILE
        append

       else if SIZE == "349632"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE3
        math SIZE -= 0x50
        log NAME 0x50 SIZE MEMORY_FILE
        append

       else if SIZE == "0x555BC"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE4
        math SIZE -= 0x54
        log NAME 0x54 SIZE MEMORY_FILE
        append

       else if SIZE == "0x555E4"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE5
        math SIZE -= 0x54
        log NAME 0x54 SIZE MEMORY_FILE
        append

       else if SIZE == "0x2AB20"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE6
        math SIZE -= 0x40
        log NAME 0x40 SIZE MEMORY_FILE
        append


       else if SIZE == "0x2AB08"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE7
        math SIZE -= 0x40
        log NAME 0x40 SIZE MEMORY_FILE
        append

       else if SIZE == "0x155BC"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE8
        math SIZE -= 0x4C
        log NAME 0x4C SIZE MEMORY_FILE
        append

       else if SIZE == "0x155B8"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE9
        math SIZE -= 0x40
        log NAME 0x40 SIZE MEMORY_FILE
        append

       else if SIZE == "0xAB04"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE10
        math SIZE -= 0x4C
        log NAME 0x4C SIZE MEMORY_FILE
        append


       else if SIZE == "0xAB18"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE11
        math SIZE -= 0x40
        log NAME 0x40 SIZE MEMORY_FILE
        append


       else if SIZE == "0xAB1C"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE12
        math SIZE -= 0x4C
        log NAME 0x4C SIZE MEMORY_FILE
        append


       else if SIZE == "0xAAB24"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE13
        math SIZE -= 0x54
        log NAME 0x54 SIZE MEMORY_FILE
        append

       else if SIZE == "0x1555C0"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE14
        math SIZE -= 0x58
        log NAME 0x58 SIZE MEMORY_FILE
        append

       else if SIZE == "0x2AB64"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE15
        math SIZE -= 0x54
        log NAME 0x54 SIZE MEMORY_FILE
        append

       else if SIZE == "0xAFC"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE16
        math SIZE -= 0x44
        log NAME 0x44 SIZE MEMORY_FILE
        append

       else if SIZE == "0x55DC"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE17
        math SIZE -= 0x4C
        log NAME 0x4C SIZE MEMORY_FILE
        append

       else if SIZE == "0x2AB1C"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE18
        math SIZE -= 0x44
        log NAME 0x44 SIZE MEMORY_FILE
        append

       else if SIZE == "0x155E0"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE19
        math SIZE -= 0x50
        log NAME 0x50 SIZE MEMORY_FILE
        append

       else if SIZE == "0x155DC"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE20
        math SIZE -= 0x54
        log NAME 0x54 SIZE MEMORY_FILE
        append

       else if SIZE == "0x55D8"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE21
        math SIZE -= 0x50
        log NAME 0x50 SIZE MEMORY_FILE
        append

       else if SIZE == "0x55B8"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE22
        math SIZE -= 0x48
        log NAME 0x48 SIZE MEMORY_FILE
        append

#       else if SIZE == "0x"
#        append
#        string NAME += ".dds"
#        log NAME 0 128 MEMORY_FILE23
#        math SIZE -= 0x40
#        log NAME 0x40 SIZE MEMORY_FILE
#        append

#       else if SIZE == "0x"
#        append
#        string NAME += ".dds"
#        log NAME 0 128 MEMORY_FILE24
#        math SIZE -= 0x40
#        log NAME 0x40 SIZE MEMORY_FILE
#        append

#       else if SIZE == "0x"
#        append
#        string NAME += ".dds"
#        log NAME 0 128 MEMORY_FILE25
#        math SIZE -= 0x40
#        log NAME 0x40 SIZE MEMORY_FILE
#        append

#       else if SIZE == "0x"
#        append
#        string NAME += ".dds"
#        log NAME 0 128 MEMORY_FILE26
#        math SIZE -= 0x40
#        log NAME 0x40 SIZE MEMORY_FILE
#        append

    else
        log NAME 0 SIZE MEMORY_FILE
    endif
next i

```


converts most textures still need to add some.
Huge thanks for bugtest and his help.
## Post #19
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-07-26T06:56:52+00:00
- Post Title: Re: RE5 Benchmark

Actually: [viewtopic.php?f=10&t=3606&p=30710#p30710](http://forum.xentax.com/viewtopic.php?f=10&t=3606&p=30710#p30710)

I believe that was the first script for this ?
## Post #20
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-07-26T10:13:26+00:00
- Post Title: Re: RE5 Benchmark

chrrox, you can optmize that script modifying the DDS header at runtime.
so instead of specifying various memory_files with different dds headers it's enough that you specify only one that you can modify at runtime.
for example, if you want to put the SIZE variable at offset 0x10 of the dds header:

```
putvarchr MEMORY_FILE 0x10 SIZE long
```

or you want to put a 0xff byte at offset 0x23:

```
putvarchr MEMORY_FILE 0x23 0xff byte
```
