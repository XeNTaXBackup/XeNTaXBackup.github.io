## Post #1
- Username: grandmasterjimmy
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Jan 11, 2010 12:40 pm
- Post datetime: 2011-02-10T08:00:26+00:00
- Post Title: MvC3 .ARC files.

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-02-10T15:14:00+00:00
- Post Title: MvC3 .ARC files.

No one can extract any xbox capcom game after devil may cry 4 they change things in microsofts compression so extractors will not work. No one has reversed the compression on the 360. the ps3 version will use zlib just wait for that.
## Post #3
- Username: grandmasterjimmy
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Jan 11, 2010 12:40 pm
- Post datetime: 2011-02-10T16:11:46+00:00
- Post Title: MvC3 .ARC files.

Oh alright. Thanks chrrox.
## Post #4
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2011-02-11T10:48:25+00:00
- Post Title: MvC3 .ARC files.

Oh my God!!!!!!!!!!

We need there models! ah ah ah!
## Post #5
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2011-02-11T10:52:31+00:00
- Post Title: MvC3 .ARC files.

I'm gonna take a look later...

If chrrox says it's hard, it probably is cause he figured out lots of file formats :p

I'm also interested in the Models tho
## Post #6
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-02-11T11:30:12+00:00
- Post Title: MvC3 .ARC files.

I hope chrrox gonna create an extractor for it
Im really interested in dante model
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-02-11T11:34:50+00:00
- Post Title: MvC3 .ARC files.

its the same as resident evil 5 just wait for the ps3 version.
## Post #8
- Username: igammi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jan 25, 2011 7:03 am
- Post datetime: 2011-02-11T11:57:17+00:00
- Post Title: MvC3 .ARC files.

The contents of this post was deleted because of possible forum rules violation.
## Post #9
- Username: MaDetho
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-02-11T21:23:23+00:00
- Post Title: MvC3 .ARC files.

re5 script works its the same engine

```
get idstring long
get version short
get files short
comtype zlib_noerror
for i = 0 < files
getdstring name 0x40
get type long
string name + .
string name + type
get zsize long
get size long
get offset long
clog name offset zsize size
next i

```


the models are very low res 7k polly and 1 1024 x 1024 texture they will ported it to the wii  i bet.
## Post #10
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2011-02-11T22:27:24+00:00
- Post Title: MvC3 .ARC files.

support now?!
## Post #11
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-02-11T23:37:52+00:00
- Post Title: MvC3 .ARC files.

Woo hoo
Now its possible eh
Thanks for the info chrrox
## Post #12
- Username: igammi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jan 25, 2011 7:03 am
- Post datetime: 2011-02-11T23:52:09+00:00
- Post Title: MvC3 .ARC files.

> Reply from chrrox
>
> re5 script works its the same engine
Code: Select allendian big
get idstring long
get version short
get files short
comtype zlib_noerror
for i = 0 < files
getdstring name 0x40
get type long
string name + .
string name + type
get zsize long
get size long
get offset long
clog name offset zsize size
next i
This script and current scripts written for PS3 RE5/Gold doesn't convert the  MvC3 .tex/.dds correctly, since data appears reversed when viewed under a hex editor. Then again its probably my lack of understanding about these archives.
Either way I've notice this game does not have any error handling when a arc is changed (meaning that it doesn't crash when it loads a different arc file).
## Post #13
- Username: grandmasterjimmy
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Jan 11, 2010 12:40 pm
- Post datetime: 2011-02-12T01:12:17+00:00
- Post Title: MvC3 .ARC files.

I'm having trouble with the textures as well. I've tried using the RE5 PS3 script that auto-converts the various files but it just outputs corrupt files.
## Post #14
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-02-12T02:05:29+00:00
- Post Title: MvC3 .ARC files.

just place a header on the files they are so easy to convert...
[trish_tex01_BM.606035435.png](https://xentaxbackup.github.io/file/3898_trish_tex01_BM.606035435.png)
## Post #15
- Username: grandmasterjimmy
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Jan 11, 2010 12:40 pm
- Post datetime: 2011-02-12T02:31:06+00:00
- Post Title: MvC3 .ARC files.

I've never done anything with any of Capcoms formats before so I have no idea how their formats work. At least a spec sheet would be nice if it's so easy to just add a header to them.
## Post #16
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-02-12T02:38:18+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

Holey moley chrrox
Wow you're already converted the texture
Amazing job chrrox
Also how's the mgs4 progress chrrox ???
## Post #17
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2011-02-12T09:02:16+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

Hello, great job! Please explain how to convert models and textures? Is it possible?
## Post #18
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2011-02-12T10:44:08+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

Since i don't have the PS3 but only the Xbox360 version i can't help much but i still had this Script for RE5 Xbox360 Arc's on my HDD which PARTLY worked back in the day...

It starts working on MVC3 Arcs too but crashes rather quickly and i can't figure out why since i don't understand the compression used :/

```
set HFS long 0
set BASE_OFF long 0
get SIGN long
if SIGN == 0x00534648   # " SFH"
    endian big
    set HFS long 1
elif SIGN == 0x48465300 # "HFS "
    endian little
    set HFS long 1
endif

if HFS != 0
    get DUMMY short
    get TYPE short
    if TYPE == 0
        set BASE_OFF long 0x20000
    else
        set BASE_OFF long 0x10
    endif
    goto BASE_OFF
    get SIGN long
endif

if SIGN == 0x00435241   # " CRA"
    endian little
elif SIGN == 0x41524300 # "ARC "
    endian big
else
    cleanexit
endif
get VERSION short
if VERSION == 4
    comtype zlib
elif VERSION == 8
    comtype deflate
elif VERSION == 0x11
    comtype XMemDecompress
else
    comtype zlib
    print "unknown version %VERSION%, I try zlib compression"
endif
get FILES short

for i = 0 < FILES
    getdstring NAME 0x40
    get TYPE long
    get ZSIZE long
    get SIZE long
    get OFFSET long

    if SIZE & 0x40000000
        math SIZE -= 0x40000000
    endif

    if HFS != 0 # used in RE5 PS3
        math ZSIZE += 32
        #math SIZE /= 8
        math TMP = OFFSET
        math TMP /= 0x20000
        math TMP *= 0x10
        math ZSIZE  += TMP
        math SIZE   += TMP
        math OFFSET += TMP
        math OFFSET += 2
    endif

    math OFFSET += BASE_OFF # needed for HFS header
    clog NAME OFFSET ZSIZE SIZE
next i

print "ARC extractor by SillyGoose for 7s"


```
## Post #19
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2011-02-12T10:54:48+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

I am a noob, whos script i have use for extract this models and textures?!
Tutorial!?
## Post #20
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2011-02-12T11:44:06+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

> Since i don't have the PS3 but only the Xbox360 version i can't help much but i still had this Script for RE5 Xbox360 Arc's on my HDD which PARTLY worked back in the day...
>
> 
>
> It starts working on MVC3 Arcs too but crashes rather quickly and i can't figure out why since i don't understand the compression used :/

It seems to only extract the uncompressed data. The actual compressed data isn't uncompressed correctly which results in 0kb files and crashes. Sadly, Capcom has changed the compression slightly. It would be nice if somebody on this forum could figure this out inorder to allow extraction of the latest Capcom games.

Resident Evil 5
Lost Planet 2

etc.
## Post #21
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2011-02-12T11:56:53+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

I have a ps3 version of the game, I extracted files from the ARC's with this script.

```
get idstring long
get version short
get files short
comtype zlib_noerror
for i = 0 < files
getdstring name 0x40
get type long
string name + .
string name + type
get zsize long
get size long
get offset long
clog name offset zsize size
next i
```

Received .dom files - these are models, and .xet files - this is textures. 
How to convert or import .dom files into 3DS MAX? If someone can help, please explain how.
## Post #22
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-02-12T16:07:38+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

There is no way to import them into max yet you need to wait.
Here is the character list in regards to their arc files.

```
0001 - Ryu
0002 - Chunli
0003 - Gouki
0004 - Chris
0005 - Wesker
0006 - VJoe
0007 - Dante
0008 - Trish
0010 - Spencer
0011 - Arthur
0012 - Amaterasu
0013 - Zero
0014 - Tron
0015 - Morrigan
0016 - Leilei
0017 - Felicia
0018 - CViper
0019 - Haggar
0020 - Jill
0021 - SpiderMan
0022 - CapAmerica
0023 - Wolverine
0024 - Magneto
0025 - Hulk
0026 - SheHulk
0027 - TaskMaster
0028 - IronMan
0029 - Thor
0030 - DrDoom
0031 - Phoenix
0032 - Shuma
0033 - Modok
0034 - Dormammu
0035 - DeadPool
0036 - Storm
0037 - SuperSkrull
0038 - Sentinel
0039 - X23
0041 - Galactus

```
## Post #23
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2011-02-12T16:18:44+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

Thank you very much for your quick reply and for the list. I am looking forward!
## Post #24
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2011-02-12T16:43:04+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

> Reply from chrrox
>
> There is no way to import them into max yet you need to wait.
Here is the character list in regards to their arc files.
Code: Select all0000 - cpu dummy
0001 - Ryu
0002 - Chunli
0003 - Gouki
0004 - Chris
0005 - Wesker
0006 - VJoe
0007 - Dante
0008 - Trish
0010 - Spencer
0011 - Arthur
0012 - Amaterasu
0013 - Zero
0014 - Tron
0015 - Morrigan
0016 - Leilei
0017 - Felicia
0018 - CViper
0019 - Haggar
0020 - Jill
0021 - SpiderMan
0022 - CapAmerica
0023 - Wolverine
0024 - Magneto
0025 - Hulk
0026 - SheHulk
0027 - TaskMaster
0028 - IronMan
0029 - Thor
0030 - DrDoom
0031 - Phoenix
0032 - Shuma
0033 - Modok
0034 - Dormammu
0035 - DeadPool
0036 - Storm
0037 - SuperSkrull
0038 - Sentinel
0039 - X23
0041 - Galactus

There outher program? With blender or maya now or not?
## Post #25
- Username: protosk8
- Rank: advanced
- Number of posts: 42
- Joined date: Sun Feb 13, 2011 12:13 am
- Post datetime: 2011-02-12T16:45:25+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

> Reply from chrrox
>
> There is no way to import them into max yet you need to wait.
Here is the character list in regards to their arc files.

sorry if this is a dumb question, is there anyway to view the models tho ? :3
thanks for all the info btw
## Post #26
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-02-12T17:10:54+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

Yes go in game and click model viewer you can look at the models all you want.

I am working on it now just need to figure out a few more things
[fel.png](https://xentaxbackup.github.io/file/3902_fel.png)
## Post #27
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2011-02-12T17:30:11+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

The people scream!!! CHRROX! CHRROX!
## Post #28
- Username: igammi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jan 25, 2011 7:03 am
- Post datetime: 2011-02-12T21:04:40+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

Anybody notice that 0009 and 0040 are missing from this list? Then again the missing numbered arcs are possibly future character release... maybe.
## Post #29
- Username: darkloner
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Feb 12, 2011 12:09 am
- Post datetime: 2011-02-12T22:24:18+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

How about sound? Like music and character voices?
## Post #30
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-02-13T00:00:15+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

that was very fast chrrox
## Post #31
- Username: protosk8
- Rank: advanced
- Number of posts: 42
- Joined date: Sun Feb 13, 2011 12:13 am
- Post datetime: 2011-02-13T09:15:44+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

i'm just learning how to extract from arc files :3
<-- not so good at it.
just got the ps3 version of mvc3
having fun trying to figure this stuff out :D
## Post #32
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2011-02-13T14:48:17+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

> Reply from protosk8
>
> i'm just learning how to extract from arc files :3
<-- not so good at it.
just got the ps3 version of mvc3
having fun trying to figure this stuff out

I did extract the .ARC with this script
> endian big
>
> get idstring long
>
> get version short
>
> get files short
>
> comtype zlib_noerror
>
> for i = 0 < files
>
> getdstring name 0x40
>
> get type long
>
> string name + .
>
> string name + type
>
> get zsize long
>
> get size long
>
> get offset long
>
> clog name offset zsize size
>
> next i

and have a files .number and not files .dom, its fine or not?
## Post #33
- Username: protosk8
- Rank: advanced
- Number of posts: 42
- Joined date: Sun Feb 13, 2011 12:13 am
- Post datetime: 2011-02-13T20:55:37+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

> Reply from logansan25
>
> 

I did extract the .ARC with this scriptendian big
get idstring long
get version short
get files short
comtype zlib_noerror
for i = 0 < files
getdstring name 0x40
get type long
string name + .
string name + type
get zsize long
get size long
get offset long
clog name offset zsize size
next i

and have a files .number and not files .dom, its fine or not?

use a hex editor
## Post #34
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2011-02-13T21:59:58+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

> Reply from protosk8
>
> logansan25 wrote:

I did extract the .ARC with this scriptendian big
get idstring long
get version short
get files short
comtype zlib_noerror
for i = 0 < files
getdstring name 0x40
get type long
string name + .
string name + type
get zsize long
get size long
get offset long
clog name offset zsize size
next i

and have a files .number and not files .dom, its fine or not?


use a hex editor

I dont know use the hex heditor, are you know a tutorial for use this?
## Post #35
- Username: protosk8
- Rank: advanced
- Number of posts: 42
- Joined date: Sun Feb 13, 2011 12:13 am
- Post datetime: 2011-02-14T00:39:05+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

> Reply from logansan25
>
> 
I dont know use the hex heditor, are you know a tutorial for use this?
Well i'm still new to all this, still learning. i'm sure someone here has a tutorial. search the forum :3
## Post #36
- Username: aaronindhouse
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Dec 13, 2010 1:44 am
- Post datetime: 2011-02-14T06:47:43+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

```
0x04: u32           = FILE VERSION?---------------20 00 80 97
0x08: u32           = IMAGE INFO------------HEIGHT,WIDTH,MIP#
0x0C: u32           = UNK-------------------------------00 01  
0x0E: u08           = Image ID-------------LIST OF ID'S BELOW
0X0f: U08           = UNK2---------------------------------01    
0x10: float[MIP#] = HEADER SIZE & MIP OFFSETS----------

@@ IMAGE INFO-0X08 U32 

0xH = Hex Height Value
0xW = Hex Width Value 
_.H = Decimal Height Value
_.W = Decimal Width Value
  H = Height            
  W = Width             
     
  HEIGHT | WIDTH  |MIPMAP#
 0x08 0x09 0x0A  0x0B      
   00   0|0   00  |  00   |00 00 00 00
   20   0|1   00  |  0B   |20 01 00 0B
   04   0|0   80  |  01   |04 00 80 01
__________________________    
   --EX: 20 01 00 --

         = 200||100         
   0xH = 0x200              GET HEX VALUES          
  0xW = 0x100              HEX->DECIMAL            
    _.H = 512                DOULBLE _.H FOR H       
   _.W = 256                MULTIPLY _.W BY 4 FOR W 
_.H*2 = 1024               --DONE                  
_.w*4 = 1024          
   0xH = 0X400
  0xW = 0X400
      H = 1024
     W = 1024
 
SQUARE TEXTURE-- 
__________________________    
   --EX: 04 00 80 --
--------------------------
      = 040||080          
0xH = 0x040              
0xW = 0x080             
_.H = 64               
_.W = 128               
_.H*2 = 128              
_.w*4 = 512              
  0xH = 0X080
  0xW = 0X200
       H = 128
      W = 512
 
RECTANGULAR TEXTURE--

___________________________________
///TABLE OF IMAGE SIZES(SQUARES)///|   
             (DTX1)                |
-----------------------------------|
      | 0x08 | 0x09 | 0x0A | 0x0B  |
 -----|------|------|------|-------|
  2048|  40  |  02  |  00  |  0C   |
 -----|------|------|------|-------| 
  1024|  20  |  01  |  00  |  0B   |
 -----|------|------|------|-------|  
   512|  10  |  00  |  80  |  0A   |
 -----|------|------|------|-------|
   256|  08  |  00  |  40  |  09   |
 -----|------|------|------|-------|  
   128|  04  |  00  |  20  |  08   |
 -----|------|------|------|-------|  
    64|  02  |  00  |  10  |  07   |
 -----|------|------|------|-------|  
    32|  01  |  00  |  08  |  06   |
 -----|------|------|------|-------|    
    16|  00  |  80  |  04  |  05   |
 -----|------|------|------|-------|     
     8|  00  |  40  |  02  |  04   |
 -----|------|------|------|-------|     
     4|  00  |  20  |  01  |  03   |
 -----|------|------|------|-------|
                           |  02   |
                           |-------|
                           |  01   |  
                                 --|     
                        
@@ IMAGE ID-0X0E U08 
___________________________________
////////////IMAGE ID'S/////////////   
 ID'S FOR DIFFERENT TEX MAP TYPES  

HEX VALUE | IMAGE TYPE             |
----------|------------------------|
13            MODEL BM(DIFFUSE MAP)
17            EFFECT BM(DIFFUSE MAP)
19            MM & AM
1E            NM(NORMAL MAP)
2A            UI + GALLERY TEXTURES

@@ HEADER SIZE AND MIPMAP OFFSETS-0X10 FLOAT[MIP#]
EX: 
------         
0X10: 00 00 00 3C|00 00 80 3C|00 00 A0 34|00 00 A8 34
         OFF1=0X3C OFF2=0X803C OFF3=0XA034 OFF4=0XA834      
       
////////MIP OFFSET VALUES ALWAYS START AT 0X10
////////EXAMPLE HEADER LENGTH IS 0X3C
////////EXAMPLE MIPMAP COUNT IS 11


@@ OTHER INFO

.XET USES DTX1,DTX5
  DETERMINE WHICH TO USE WITH FILE ID
  AND FOLDER LOCATION
  --DTX1--
      -TEXTURES USED WITH .DOM FILES
      -ID'S
           13,17,19,1E
  --DTX5--
      -UI IMAGES
      -ID'S
           2A

DTX5 TEXTURES NEED TO BE MESSED WITH
    -SWAP ALPHA AND GREEN CHANNELS WITH EACH OTHER
    -GREEN CHANNEL
	R=  0 
	G=  100
	B=  0
    -RED CHANNEL
	R=  100
	G=  100
	B= -100
    -BLUE CHANNEL
	R= -100
	G=  100
        B=  100

```


If i missed something let me know please cuz im new to this stuff.  hope this helps some of yall

to get .XET files to open as .DDS files, you need to delete the header of the .XET and replace it with the proper DDS header(DTX1 or DTX5)  as well as enter in the proper width and height values into the dds header.  to get the dds header just make a new dds file with photoshop and then copy paste
## Post #37
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2011-02-14T07:53:51+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

Eh... I was a bit confused as to what to do, but I figured it out now. At least, I think I have.
[Tron_tex01_BM_1p.png](https://xentaxbackup.github.io/file/3913_Tron_tex01_BM_1p.png)
## Post #38
- Username: protosk8
- Rank: advanced
- Number of posts: 42
- Joined date: Sun Feb 13, 2011 12:13 am
- Post datetime: 2011-02-14T09:25:09+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

> Reply from RandomTBush
>
> Eh... I was a bit confused as to what to do, but I figured it out now. At least, I think I have.
What's your way of doing it? :D
## Post #39
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2011-02-14T14:53:56+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

> Reply from protosk8
>
> RandomTBush wrote:Eh... I was a bit confused as to what to do, but I figured it out now. At least, I think I have.
What's your way of doing it?It involved yoinking a header from a random TEX file I found from Resident Evil 5, inserting it into the MvC3 textures, and then using trial and error with the hex values to make the texture export properly.
## Post #40
- Username: protosk8
- Rank: advanced
- Number of posts: 42
- Joined date: Sun Feb 13, 2011 12:13 am
- Post datetime: 2011-02-14T21:39:35+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

> Reply from RandomTBush
>
> It involved yoinking a header from a random TEX file I found from Resident Evil 5, inserting it into the MvC3 textures, and then using trial and error with the hex values to make the texture export properly.
can i take a look at the script you used?. if possible
## Post #41
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-02-14T22:46:57+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

just paste a dxt1 or 5 header on the files and delete the bytes it used for the header you will see the number repeat several times like 3C or 2C thats all that is needed.
## Post #42
- Username: aaronindhouse
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Dec 13, 2010 1:44 am
- Post datetime: 2011-02-15T00:44:10+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

```
-----------------------------------------

XET header(This is from Galactus_tex01_BM)
0x00: 00584554200080972001000B00011301
0x10: 0000003C0008003C000A003C000A803C
0x20: 000AA03C000AA83C000AAA3C000AAABC
0x30: 000AAADC000AAAE4000AAAEC   04480540

The important info is stored up to 0x14
0x00: 00584554    20008097  2001000B  0001 13  01
    |File ID   ||File Ver?||Pic Info||UNK||ID||?|
0x10:  0000003C   
       |Header Size|
The important parts for a simple conversion are pic info, id, and Header size
  
  -our goal is to replace the header we have here with one of the dtx headers
  - to do this we need to know how big our current header is so that we know what to delete
  - the header size is located at 0x10 and is a long value(00 00 00 xx)
           -the header size of this file is 00 00 00 3C so 0x00 to 0x3C contains all header information
           -now simply delete this data and your left with the .dds without its proper header but dont delete it yet!
  -before you delete the header you will want to get the size of the image so you don't have to waste time guessing it
           -the image size is the first 6 hex values in pic info
           -calculate the decimal value of the first 3 values(height) and the last 3 values(width)
                     -multiply the first decimal value by 2 for your image height
                     -multiply the second decimal value by 4 for your image width
            -voila, you have your image dimensions
            -Use dtx1 header for textures that belong to models in the game
            -use dtx5 header for textures that belong to the ui or are from the art gallery
             -both dtx headers have the width and height values for the example put in(00 04  which equals 1024 in decimal)
                     -height starts at 0x0C
                     -width starts at 0x10
                


DTX1 Header                               
0x00:   444453207C0000000710000000040000
        0004000000000000000000000B000000
        00000000000000000000000000000000
        00000000000000000000000000000000
        00000000000000000000000020000000
        04000000445854310000000000000000
        00000000000000000000000000100000
        00000000000000000000000000000000
DTX5 Header
0x00:   444453207C0000000710000000040000
        00040000000000000000000001000000
        00000000000000000000000000000000
        00000000000000000000000000000000
        00000000000000000000000020000000
        04000000445854350000000000000000 
        00000000000000000000000000100000
        00000000000000000000000000000000

-also, if the image is using dtx5 then your going to have to do some extra work to get the image to look right
                -use image editing software to swap the alpha and green channels
                -edit each channels rgb values
                        -red channel
                             r=100
                             g=100
                             b=-100
                        -green channel
                             r=0
                             g=100
                             b=-0
                        -blue channel
                             r=-100
                             g=100
                             b=100                

```
## Post #43
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2011-02-15T13:31:06+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

Thank you for your excellent guide! It worked perfectly for me. Too bad it is impossible to get models yet.
## Post #44
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-02-15T14:45:49+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

i'm trying to use this script on xbox360 files
```
get idstring long
get version short
get files short
comtype zlib_noerror
for i = 0 < files
getdstring name 0x40
get type long
string name + .
string name + type
get zsize long
get size long
get offset long
clog name offset zsize size
next i
```
but i get only 0 byte files

Q: how to unpack correctly
## Post #45
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2011-02-15T14:56:08+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

You need a PS3 version of the game! The script does not work with the Xbox 360 version.
## Post #46
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2011-02-15T16:15:24+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

Someone please make Xbox extractor?
## Post #47
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2011-02-15T16:59:31+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

> Reply from C00L12345
>
> Someone please make Xbox extractor?

Nobody knows about the compression used in 360 Capcom's Games after DMC4.
## Post #48
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2011-02-15T18:32:36+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

> Reply from Darko
>
> C00L12345 wrote:Someone please make Xbox extractor?

Nobody knows about the compression used in 360 Capcom's Games after DMC4.

But it's definitly LZX (XCOMPRESS) which isn't working :S
## Post #49
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2011-02-15T21:12:51+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

Where are we friend chrrox????
## Post #50
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-02-16T00:13:16+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

i am fairly stumped on this one not sure what they are doing to the faces some meshes i can import fine while others i can not because the faces defined do not go in order. i have asked a few people i know if they have any ideas.
[felecia1.png](https://xentaxbackup.github.io/file/3926_felecia1.png)
## Post #51
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2011-02-16T00:24:21+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

Well... So far, so good, chrrox. Hope you can figure out how to fix the rest of the problems with importing the models.  

Anyway, as a bit of a heads-up... Capcom announced a costume DLC pack that's gonna be released on March 1st. And yes, it's more on-the-disc DLC, just like Jill and Shuma-Gorath. 0028_04.arc is for Iron Man's DLC costume, for example. So, if anyone wants to extract those models/textures at a later time, they won't have to worry about downloading the DLC for 'em.
## Post #52
- Username: protosk8
- Rank: advanced
- Number of posts: 42
- Joined date: Sun Feb 13, 2011 12:13 am
- Post datetime: 2011-02-16T04:51:37+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

thanks for all the info so far guys. 
and chrrox, good job :D

but hey can i get some help '-'
how do you guys exactly get the arc files.
i only got ryu but i cant get the other characters D: ionno how i did it.


Edit:
Sorry i was looking at the 360 version x.x
i got it.
## Post #53
- Username: Krisan Thyme
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Jan 15, 2011 4:04 am
- Post datetime: 2011-02-17T01:16:12+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

Out of curiosity.. Anyone have any ideas how to create an ARC? Decompressing an ARC is simple enough, but what if I wanted to recreate one after making some modifications to the extracted files?
## Post #54
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2011-02-18T23:29:55+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

Its looks seems very hard!
## Post #55
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2011-02-19T08:47:14+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

The contents of this post was deleted because of possible forum rules violation.
## Post #56
- Username: pcp20
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Feb 20, 2011 3:55 pm
- Post datetime: 2011-02-20T12:47:36+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

The contents of this post was deleted because of possible forum rules violation.
## Post #57
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2011-02-22T12:35:54+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

Any update?!
## Post #58
- Username: aaronindhouse
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Dec 13, 2010 1:44 am
- Post datetime: 2011-02-23T02:05:41+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

well im currently working on making a tool that automates the whole .xet(or tex, whatevs)

its gonna change headers,swap green and alpha channels, and mix the channels to their proper values.

after i do that i was gonna work on the .dom files but i think it will probably be cracked by then.
## Post #59
- Username: protosk8
- Rank: advanced
- Number of posts: 42
- Joined date: Sun Feb 13, 2011 12:13 am
- Post datetime: 2011-02-23T02:40:39+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

> Reply from aaronindhouse
>
> well im currently working on making a tool that automates the whole .xet(or tex, whatevs)

its gonna change headers,swap green and alpha channels, and mix the channels to their proper values.

after i do that i was gonna work on the .dom files but i think it will probably be cracked by then.

sounds fun good luck
:3
## Post #60
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2011-02-23T11:14:42+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

> Reply from aaronindhouse
>
> well im currently working on making a tool that automates the whole .xet(or tex, whatevs)

its gonna change headers,swap green and alpha channels, and mix the channels to their proper values.

after i do that i was gonna work on the .dom files but i think it will probably be cracked by then.

Amazing! Good look!
## Post #61
- Username: Kharaxel
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Apr 29, 2008 8:56 pm
- Post datetime: 2011-02-23T19:21:17+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

The contents of this post was deleted because of possible forum rules violation.
## Post #62
- Username: Chimera
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Feb 24, 2011 11:31 pm
- Post datetime: 2011-02-24T15:41:09+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

Okay so I was able to extract the files from Jills arc file 

but the file extensions appear as .( insert random number here )

how do I fix that ? 

and also Is it possible to get them with the bones or as an OBJ file only ? 

Thank you very much
## Post #63
- Username: aaronindhouse
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Dec 13, 2010 1:44 am
- Post datetime: 2011-02-24T17:56:54+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

@ chimera:
  The "if type == ................" lines in the bms script are using values that arent from mvc3 so its just printing out the values it gets from "get type long".  To fix this you need to find the new type values and change them.

dds dtx5 textures use 8 bits for their alpha channel so repacking back into dds after the green-alpha swap causes a loss in image quality.  Im thinking im going to repack into a tga file?  the format seems simple enough unless there is a better format to use? any requests or suggestions?  

also i'm set up in 010 editor right now(i love how quick it is) but it seems simple enough to get the code running in c++.  any useful docs, or documentation pages for c++ that will help with the porting process?
## Post #64
- Username: Nexus Elite ns
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 09, 2009 1:11 am
- Post datetime: 2011-02-25T00:36:23+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

> Reply from aaronindhouse
>
> @ chimera:
  The "if type == ................" lines in the bms script are using values that arent from mvc3 so its just printing out the values it gets from "get type long".  To fix this you need to find the new type values and change them.

dds dtx5 textures use 8 bits for their alpha channel so repacking back into dds after the green-alpha swap causes a loss in image quality.  Im thinking im going to repack into a tga file?  the format seems simple enough unless there is a better format to use? any requests or suggestions?  

also i'm set up in 010 editor right now(i love how quick it is) but it seems simple enough to get the code running in c++.  any useful docs, or documentation pages for c++ that will help with the porting process?
So There a way to get the meshes then? But how do we find the values for each files then?
## Post #65
- Username: Chimera
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Feb 24, 2011 11:31 pm
- Post datetime: 2011-02-25T04:22:24+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

@aaronindhouse

thank you very much 
I'm also trying to find a way to convert these files into obj and dds
## Post #66
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-02-25T04:31:30+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

its how they stored the models that's the problem they are using a new method for storing indecies If i could figure it out  i would of posted the script already if you can figure out how to read them just post how and the exporter is done.
## Post #67
- Username: Chimera
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Feb 24, 2011 11:31 pm
- Post datetime: 2011-02-25T11:27:32+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

I still couldn't figure out how to get it exported this is actually harder than I thought
## Post #68
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2011-02-25T11:40:21+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

Noesis 2.85 can extract ps3 version archives with proper extensions and load/convert the .tex files, but most models will show as incomplete point clouds. Due to the index issue chrrox mentioned. The models that draw correctly are also missing most vertex data because I haven't even bothered decoding the vertex formats. (more worried about the index buffers) I think the key to this data is to look at the encoding key data present after the main mesh list which corresponds exactly to the total index buffer to each mesh, but I haven't figured out what to do with it.
## Post #69
- Username: darkloner
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Feb 12, 2011 12:09 am
- Post datetime: 2011-02-25T21:13:26+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

The contents of this post was deleted because of possible forum rules violation.
## Post #70
- Username: unkoburizou
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Feb 01, 2010 4:47 pm
- Post datetime: 2011-02-26T06:43:18+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

Thanks MrAdults　  
Noesis is greatest tool!
## Post #71
- Username: Kharaxel
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Apr 29, 2008 8:56 pm
- Post datetime: 2011-02-26T10:59:30+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

> Reply from darkloner
>
> Can anyone tell how to open the .spc files?

Actually scratch my previous post. Use the newest Noesis, as mentioned above, to extract the files. It turns out they have extension: .spac .

Still... dunno what to do with them. I looked around but no answer.
## Post #72
- Username: aaronindhouse
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Dec 13, 2010 1:44 am
- Post datetime: 2011-02-26T18:45:35+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

Mr adults, are you implementing any channel swapping or mixing when you import the dtx5 textures?  I was just wondering because I'm just about to implement it myself and would probably shift my focus to the mod format if you have already done this in neosis
## Post #73
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2011-02-27T01:28:46+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

The .SPC files contain the SFX noises in Resident Evil 5. I have an extractor for this but the sounds are useless.
## Post #74
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-03-02T09:23:21+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

I have compiled some info on this file format and am writing an extractor and compiler in C#.

The format itself is pretty easy, anyone interested in my notes?
## Post #75
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2011-03-02T12:29:58+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

Interesting to see your notes, VILE.
## Post #76
- Username: protosk8
- Rank: advanced
- Number of posts: 42
- Joined date: Sun Feb 13, 2011 12:13 am
- Post datetime: 2011-03-02T20:09:33+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

i'm interested
## Post #77
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2011-03-02T21:48:22+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

> Reply from VILE
>
> I have compiled some info on this file format and am writing an extractor and compiler in C#.

The format itself is pretty easy, anyone interested in my notes?

I am interested in the extractor! I am not a programmer!
## Post #78
- Username: georwar
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jul 23, 2010 2:45 am
- Post datetime: 2011-03-05T04:45:04+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

If you want to extract models marvel vs capcom 3, there is an application called XandrealeV113.exe. i just have to ask codeman2 that abilites mvsc3 models in their application, for the moment can only export models Resident Evil 5 PC and PS3. or someone familiar with the subject to do so ...... look at this issue 
[http://z6.invisionfree.com/Resident_Evi ... 770&st=140](http://z6.invisionfree.com/Resident_Evil_4_PC/index.php?showtopic=12770&st=140)
## Post #79
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-03-05T14:10:10+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

This is not the same format as re5 they did something very different in marvel vs capcom 3.
## Post #80
- Username: protosk8
- Rank: advanced
- Number of posts: 42
- Joined date: Sun Feb 13, 2011 12:13 am
- Post datetime: 2011-03-06T06:05:21+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

aw, so there's still no way D:
## Post #81
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2011-03-06T17:25:37+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

> Reply from protosk8
>
> aw, so there's still no way D:

I dont believe this!!!!!!!!! Its here there are the best programmers!!!!!!!!!!!!!!
## Post #82
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-03-06T17:57:58+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

it has nothing to do with programing.
The format is very easy to read the problem is how they are storing the data.
Its like if i gave you a 26 character password but the letters are in the wrong order figure it out.
its not going to happen.
I am working on trying to reverse engineer the xex file with a lot of help from other people.
Once we are able to debug the xex the format will be posted here right away.
## Post #83
- Username: protosk8
- Rank: advanced
- Number of posts: 42
- Joined date: Sun Feb 13, 2011 12:13 am
- Post datetime: 2011-03-08T03:02:03+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

that's kool :D
*waits *
## Post #84
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2011-03-08T22:46:34+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

Kinect SDK (2010) Xcompress.lib fails to decompress the LZX archive. It's basically the same as the .lib contained in the previous builds.

Oh dear.
## Post #85
- Username: maniacoloco
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Mar 05, 2011 10:19 pm
- Post datetime: 2011-03-12T15:32:23+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

Any updates??
## Post #86
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-03-12T16:32:59+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

Unless someone gets an xbox sdk with a sidecar this game will not be supported or a debug ps3.
## Post #87
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-03-13T00:27:44+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

The main reason I haven't posted back in this thread is because I can't find the info to actually build all of the headers.
## Post #88
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2011-03-13T13:25:21+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

Well I don't have an XDK, what difference would it make? I doubt it's possible to crack the compression with one x_x
## Post #89
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-03-13T14:08:07+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

its very possible to crack everything with an xdk console
## Post #90
- Username: DerMeister
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Mar 31, 2009 4:37 am
- Post datetime: 2011-03-15T01:50:17+00:00
- Post Title: Re: MvC3 .ARC files. Older Capcom .ARC extractors don't work

The RGB values for channels don't seem to work for certain pictures, like the special art ones. I also think it doesn't work too well for the endings, but I'm not sure. Haggar's 2nd ending pic looks off. I have only converted Haggar's ending.

To be more specific, it seems as if the green basically isn't doing its job of making things fucking green. Hulk, for example, is blue. So is Morrigan's hair.

I'm using Photoshop CS4 and doing this with the channel mixer.

Anyone know proper values for those pics or something?

I've tried different combinations, but I've got nothing.

EDIT: Haggar's 1st ending pic is off too.

EDIT2: The values don't seen to be correct for anything. Maybe it's Photoshop being a dickbutt. Any suggestions?
## Post #91
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-03-15T07:50:29+00:00
- Post Title: Re: MvC3 .ARC files.

Could anyone provide MvC3 files from a ps3 iso?
## Post #92
- Username: maniacoloco
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Mar 05, 2011 10:19 pm
- Post datetime: 2011-03-15T13:51:39+00:00
- Post Title: Re: MvC3 .ARC files.

> Reply from VILE
>
> Could anyone provide MvC3 files from a ps3 iso?

Yep, which one??
## Post #93
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-03-16T08:03:23+00:00
- Post Title: Re: MvC3 .ARC files.

IDK any character, pick your favorite.
## Post #94
- Username: maniacoloco
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Mar 05, 2011 10:19 pm
- Post datetime: 2011-03-16T14:16:44+00:00
- Post Title: Re: MvC3 .ARC files.

The contents of this post was deleted because of possible forum rules violation.
## Post #95
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-03-17T06:18:34+00:00
- Post Title: Re: MvC3 .ARC files.

If someone can post zlib compression/decompression algorithms I can write a program to extract/build new ARC files.

I also found some files and am working on reverse engineering them (I have some basic info on changing their attributes, if someone wants to help they can test these files for me).
## Post #96
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2011-03-17T13:06:21+00:00
- Post Title: Re: MvC3 .ARC files.

> Reply from VILE
>
> If someone can post zlib compression/decompression algorithms I can write a program to extract/build new ARC files.

I also found some files and am working on reverse engineering them (I have some basic info on changing their attributes, if someone wants to help they can test these files for me).

You are a machine!!!!!!!!!!!!
## Post #97
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-03-17T13:28:11+00:00
- Post Title: Re: MvC3 .ARC files.

I hope master chrrox will create a model extractor for it
Or i hope MrAdults gonna make a model exporter for it
## Post #98
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2011-03-17T17:02:45+00:00
- Post Title: Re: MvC3 .ARC files.

Actually we have support for 2 of the 3 mesh format variation of *.Dom files but the most interesting one (the hight poly mesh) use some weird system on the faces indices, i am still studying it to found out the trick used to draw polys, it seems to be a ps3 specific one but maybe not 
so for example the files supported have a latter atached to the filename :
FeliciaC.Dom = supported
FeliciaF.Dom = supported
Felicia.Dom = not supported (weird thing in the face indices)
## Post #99
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-03-18T09:39:58+00:00
- Post Title: Re: MvC3 .ARC files.

If someone can at least give me the algorithm that is used to decompress zlib compressed files with a 64 81 signature, I may be able to reverse it and make the compression.

Cmon, someone around here must know it.
## Post #100
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2011-03-18T23:12:22+00:00
- Post Title: Re: MvC3 .ARC files.

omg..someone with XDK please crask the 360 compression.
## Post #101
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-03-18T23:46:19+00:00
- Post Title: Re: MvC3 .ARC files.

> Reply from C00L12345
>
> omg..someone with XDK please crask the 360 compression.

It will come eventually. It is bound to happen because apparently a tonne of newer games have the compression.
## Post #102
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-18T23:59:05+00:00
- Post Title: Re: MvC3 .ARC files.

ton of new games?
only the capcom ones, the rest of the xbox games use the classical XMemCompress algorithm
## Post #103
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2011-03-19T00:02:12+00:00
- Post Title: Re: MvC3 .ARC files.

Anyone actually own an XDK? LOL


This compression is a mess. Why would they modify it x_x;

It looks like every single capcom game for 360 will be using this compression in future.
## Post #104
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-03-19T00:19:29+00:00
- Post Title: Re: MvC3 .ARC files.

everything re5 and after use it they do t to prevent porting to the pc.
## Post #105
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-03-19T02:42:40+00:00
- Post Title: Re: MvC3 .ARC files.

Just a little update with my research.

I have documented how command combos (special attacks eg. Hadouken) work (not entirely complete), character status (far from complete, to really complete this I am going to have to do some trial and error), the .arc archives (fully complete, easy format) and have started on the attack info (this is probably gonna be a hard one, so don't expect too much from it yet).

I plan to document all the easy formats completely in the near future and have some research on the more difficult ones.

I think I'm just gonna use the zlib.dll instead of writing my own compression method.

PS: Anyone who wants to test my files when I write my .arc builder, post here or pm me.
## Post #106
- Username: DerMeister
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Mar 31, 2009 4:37 am
- Post datetime: 2011-03-19T03:14:38+00:00
- Post Title: Re: MvC3 .ARC files.

Maybe you could help with the colors of the UI images and stuff, while you're at it.

Shit's colors are fucked. Badly. Like, grey Hulk, brown pants for Haggar, etc.
## Post #107
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-03-19T04:09:42+00:00
- Post Title: Re: MvC3 .ARC files.

> Reply from DerMeister
>
> Maybe you could help with the colors of the UI images and stuff, while you're at it.

Shit's colors are fucked. Badly. Like, grey Hulk, brown pants for Haggar, etc.

I can't even get files that require DTX5 headers to work.
## Post #108
- Username: DerMeister
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Mar 31, 2009 4:37 am
- Post datetime: 2011-03-19T11:26:07+00:00
- Post Title: Re: MvC3 .ARC files.

> Reply from VILE
>
> DerMeister wrote:Maybe you could help with the colors of the UI images and stuff, while you're at it.

Shit's colors are fucked. Badly. Like, grey Hulk, brown pants for Haggar, etc.

I can't even get files that require DTX5 headers to work.

Use [Noesis](http://oasis.xentax.com/index.php?content=downloads). It can extract and convert the textures that use DTX5 headers. It does the whole "swap green and alpha channel and apply these RGB values" thing too, even tho, as you will notice, the colors are messed up.
## Post #109
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2011-03-19T12:32:56+00:00
- Post Title: Re: MvC3 .ARC files.

> Reply from chrrox
>
> everything re5 and after use it they do t to prevent porting to the pc.
I see, still wish I could extract those files..
## Post #110
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-03-20T01:00:48+00:00
- Post Title: Re: MvC3 .ARC files.

zlib1.dll is giving me trouble, so I don't think I will be able to write a compiler any time soon.

I am also writing me own .tex converter (converts tex files to other formats and back).
## Post #111
- Username: DerMeister
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Mar 31, 2009 4:37 am
- Post datetime: 2011-03-20T02:00:54+00:00
- Post Title: Re: MvC3 .ARC files.

What's up with some textures? They seem to have the ID 27 and show up as corrupted when previewing with Noesis. I also can't seem to convert them via hexing. For example, Tron Bonne's eye texture and some of her effects.

I've attached Tron Bonne's eye texture (specifically, the one from her 3P color) if anyone wants to help with these freaky things.
[Tron_eye.rar](https://xentaxbackup.github.io/file/4085_Tron_eye.rar)
## Post #112
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-03-22T06:10:43+00:00
- Post Title: Re: MvC3 .ARC files.

So no one at all has any info on the compression for the ps3 files (it uses zlib apparently).
## Post #113
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-03-22T06:52:36+00:00
- Post Title: Re: MvC3 .ARC files.

I need someone with a modified ps3 to test a file for me.
## Post #114
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2011-03-22T23:18:50+00:00
- Post Title: Re: MvC3 .ARC files.

> Reply from VILE
>
> I need someone with a modified ps3 to test a file for me.I can try it out.
## Post #115
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-03-23T06:36:40+00:00
- Post Title: Re: MvC3 .ARC files.

> Reply from RandomTBush
>
> VILE wrote:I need someone with a modified ps3 to test a file for me.I can try it out.

Thanks for the offer, I already got this file tested, but I will probably ask you to test one later.

Also, do you know any C++/C# RandomTBush?
## Post #116
- Username: protosk8
- Rank: advanced
- Number of posts: 42
- Joined date: Sun Feb 13, 2011 12:13 am
- Post datetime: 2011-03-26T04:22:21+00:00
- Post Title: Re: MvC3 .ARC files.

keep it up guys
you can do it :D
## Post #117
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-03-27T06:41:30+00:00
- Post Title: Re: MvC3 .ARC files.

> Reply from protosk8
>
> keep it up guys
you can do it

If I wasn't such a noob and new how to use zlib.net.dll it would already be done.
## Post #118
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2011-03-27T06:59:53+00:00
- Post Title: Re: MvC3 .ARC files.

> Reply from VILE
>
> Also, do you know any C++/C# RandomTBush?Can't say that I do.
## Post #119
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2011-03-30T14:04:22+00:00
- Post Title: Re: MvC3 .ARC files.

This forum dead?!!!!!!! Or any update!!!!!!!
## Post #120
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-04-02T01:17:07+00:00
- Post Title: Re: MvC3 .ARC files.

Ok guys there is hope, I finally found a zlib library that I could understand. Now if I can replicate the compression for MvC3, we are set.

EDIT: OK I need a person to test some files soon, I'm gonna finalize my .pak extractor and builder.
## Post #121
- Username: Chimera
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Feb 24, 2011 11:31 pm
- Post datetime: 2011-04-02T10:09:43+00:00
- Post Title: Re: MvC3 .ARC files.

Wow Congrats Vile !!!   


and what kind of testing ?
## Post #122
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-04-03T00:00:18+00:00
- Post Title: Re: MvC3 .ARC files.

No, I need someone to test a file on their ps3.

Still looking for a tester.

EDIT: !It works! Replace 0023_00.arc and in game select Wolverines default, yellow and blue costume. Report back with results and if it works, pictures.
## Post #123
- Username: grandmasterjimmy
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Jan 11, 2010 12:40 pm
- Post datetime: 2011-04-03T04:10:46+00:00
- Post Title: Re: MvC3 .ARC files.

> Reply from VILE
>
> No, I need someone to test a file on their ps3.

Still looking for a tester.

EDIT: http://www.mediafire.com/?e2jfseaccrjr1k3 Replace 0023_00.arc and in game select Wolverines default, yellow and blue costume. Report back with results and if it works, pictures.

Sorry for the quality, my capture device isn't the best.
## Post #124
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-04-03T04:32:48+00:00
- Post Title: Re: MvC3 .ARC files.

SWEET!

Did you notice any changes in loading time?

Well now that I know the compression works, I'm gonna work on finishing my app.

I am going to make a blog and forum for MvC3 hacking guys, I plan on releasing apps, hacks and info on file formats on it.
## Post #125
- Username: Malakesh
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun May 30, 2010 8:46 pm
- Post datetime: 2011-04-03T05:00:18+00:00
- Post Title: Re: MvC3 .ARC files.

I tried it too. No change in loading time when I played it.
## Post #126
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-04-03T05:41:22+00:00
- Post Title: Re: MvC3 .ARC files.

Well If there was a change it would be VERY minuscule (unnoticeable).
## Post #127
- Username: grandmasterjimmy
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Jan 11, 2010 12:40 pm
- Post datetime: 2011-04-03T05:53:46+00:00
- Post Title: Re: MvC3 .ARC files.

I didn't notice any changes in loading times while testing.
## Post #128
- Username: DerMeister
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Mar 31, 2009 4:37 am
- Post datetime: 2011-04-04T00:13:16+00:00
- Post Title: Re: MvC3 .ARC files.

VILE, are you by chance the same VILE that used to hang around that StackSmash joint?

Also, will you publicly release your tool anytime soon?
## Post #129
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-04-04T05:42:22+00:00
- Post Title: Re: MvC3 .ARC files.

> Reply from DerMeister
>
> VILE, are you by chance the same VILE that used to hang around that StackSmash joint?

Also, will you publicly release your tool anytime soon?

Yes I am the guy who used to hang around the StackSmash joint  I was on the team and posted like 1 or 2 hacks lol.

And when I get the tool running flawlessly, I will release it, for now it will be a private matter.
## Post #130
- Username: DerMeister
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Mar 31, 2009 4:37 am
- Post datetime: 2011-04-04T09:50:06+00:00
- Post Title: Re: MvC3 .ARC files.

> Reply from VILE
>
> DerMeister wrote:VILE, are you by chance the same VILE that used to hang around that StackSmash joint?

Also, will you publicly release your tool anytime soon?

Yes I am the guy who used to hang around the StackSmash joint  I was on the team and posted like 1 or 2 hacks lol.

And when I get the tool running flawlessly, I will release it, for now it will be a private matter.

Awesome. I asked because Androu1 said he wants to get some MvC3 modding done or something like that.
## Post #131
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-04-04T22:27:41+00:00
- Post Title: Re: MvC3 .ARC files.

> Reply from DerMeister
>
> VILE wrote:DerMeister wrote:VILE, are you by chance the same VILE that used to hang around that StackSmash joint?

Also, will you publicly release your tool anytime soon?

Yes I am the guy who used to hang around the StackSmash joint  I was on the team and posted like 1 or 2 hacks lol.

And when I get the tool running flawlessly, I will release it, for now it will be a private matter.

Awesome. I asked because Androu1 said he wants to get some MvC3 modding done or something like that.

Lol Androu1.

Anyway, I'll go talk to him about it.
## Post #132
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2011-04-05T09:19:40+00:00
- Post Title: Re: MvC3 .ARC files.

Ooh, texture hacking! I'd like to see what kinds of alternative textures people could come up with for the existing characters.

(I already know the first one that someone would make for Felicia, though...   )
## Post #133
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-04-05T10:00:16+00:00
- Post Title: Re: MvC3 .ARC files.

> Reply from RandomTBush
>
> Ooh, texture hacking! I'd like to see what kinds of alternative textures people could come up with for the existing characters.

(I already know the first one that someone would make for Felicia, though...   )

Hey RandomTBush, good timing. Would you be interested in helping me figure out the model format for MvC3 (I already know you have a knowledge of 3d formats already)?

I mainly just want to get the vectors and face points out to a simple OBJ.
## Post #134
- Username: Chimera
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Feb 24, 2011 11:31 pm
- Post datetime: 2011-04-05T12:30:29+00:00
- Post Title: Re: MvC3 .ARC files.

when we extract the models will they come out as obj or with bones ?
## Post #135
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2011-04-05T14:25:03+00:00
- Post Title: Re: MvC3 .ARC files.

I've only ever worked with the MDL0 format, and seeing how others are having problems with the models from MvC3 at the moment, I think that a novice such as myself wouldn't know how to get 'em working...
## Post #136
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-04-05T22:48:00+00:00
- Post Title: Re: MvC3 .ARC files.

> Reply from RandomTBush
>
> I've only ever worked with the MDL0 format, and seeing how others are having problems with the models from MvC3 at the moment, I think that a novice such as myself wouldn't know how to get 'em working...

Still, any assistance would be appreciated. I mainly want to know the how to make a solid OBJ (texture previews and vertex hacks).
## Post #137
- Username: nightFlarer
- Rank: beginner
- Number of posts: 33
- Joined date: Thu May 13, 2010 3:25 pm
- Post datetime: 2011-04-06T03:27:43+00:00
- Post Title: Re: MvC3 .ARC files.

Post a model sample and someone might be able to help.
## Post #138
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-04-06T08:22:13+00:00
- Post Title: Re: MvC3 .ARC files.

[http://www.mediafire.com/?m3vql7k7pf7nqvm](http://www.mediafire.com/?m3vql7k7pf7nqvm)

Spiderman's model. Any info would be helpful.
## Post #139
- Username: DerMeister
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Mar 31, 2009 4:37 am
- Post datetime: 2011-04-11T23:37:04+00:00
- Post Title: Re: MvC3 .ARC files.

No news, I see.
## Post #140
- Username: darkloner
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Feb 12, 2011 12:09 am
- Post datetime: 2011-04-25T14:09:04+00:00
- Post Title: Re: MvC3 .ARC files.

Anything new about this?
## Post #141
- Username: protosk8
- Rank: advanced
- Number of posts: 42
- Joined date: Sun Feb 13, 2011 12:13 am
- Post datetime: 2011-04-27T16:48:20+00:00
- Post Title: Re: MvC3 .ARC files.

someday they'll figuer it out xD
## Post #142
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-06-01T12:05:31+00:00
- Post Title: Re: MvC3 .ARC files.

Ok guys remember how I said I would release a tool to extract and pack MvC3's archive files? Well recently I started it (lol late) and after a couple of hours I think it is complete.

Before I release it, I need to know it works though! Could someone kindly test a file that my tool spat out?

[http://www.megaupload.com/?d=X2XY2NOH](http://www.megaupload.com/?d=X2XY2NOH) - It goes over wolverine (0023_00).

There is nothing specific to look for, it is just an original Wolverine archive that has been extracted and packed again. If there is anything strange, please let me know.

(NOTE: There is an equal chance that it will work and that it won't, I remember while writing the extractor there were a few files that weren't compressed and my tool automatically compresses every file. It should work because I'm pretty sure the game checks if the header is zlib before it decompresses, but if it doesn't or those files have a different form of compression, then the file won't work).


I should probably tell you a little about my tool. It is noob friendly (no GUI, but all it requires is to double click the program, type a number and file name). It also allows you to expand the archives (add more files in), which will be pretty useless until a script editor is created for the actions of the characters (I intend to make one at some point), when we get that far, this game will be close to being on par with SSBB in terms of how mod-able it is (we just need to make a program to create model files, which I encourage people from this board to start working on again).
## Post #143
- Username: grandmasterjimmy
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Jan 11, 2010 12:40 pm
- Post datetime: 2011-06-01T14:58:03+00:00
- Post Title: Re: MvC3 .ARC files.

Loaded just fine for me VILE.
## Post #144
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-06-01T22:19:04+00:00
- Post Title: Re: MvC3 .ARC files.

> Reply from grandmasterjimmy
>
> Loaded just fine for me VILE.

Awesome.
## Post #145
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-06-23T02:56:14+00:00
- Post Title: Re: MvC3 .ARC files.

Ok, I'm gonna need another tester. This is primarily a 3d model related test.

Name it "0018_02.arc" and replace that file - [http://www.mediafire.com/?b9q17j3v1nnx8yh](http://www.mediafire.com/?b9q17j3v1nnx8yh)

I'm not exactly sure what color it is for C. Viper, but try them all (square, triangle, X and R1) and tell me the results.
## Post #146
- Username: grandmasterjimmy
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Jan 11, 2010 12:40 pm
- Post datetime: 2011-06-23T03:44:27+00:00
- Post Title: Re: MvC3 .ARC files.

> Reply from VILE
>
> Ok, I'm gonna need another tester. This is primarily a 3d model related test.

Name it "0018_02.arc" and replace that file - http://www.mediafire.com/?b9q17j3v1nnx8yh

I'm not exactly sure what color it is for C. Viper, but try them all (square, triangle, X and R1) and tell me the results.

When I select the character the game hangs. The character select screen just shows a solid black version of the character, and the game never continues to the next screen.
## Post #147
- Username: Krisan Thyme
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Jan 15, 2011 4:04 am
- Post datetime: 2011-06-24T17:22:28+00:00
- Post Title: Re: MvC3 .ARC files.

> Reply from DerMeister
>
> What's up with some textures? They seem to have the ID 27 and show up as corrupted when previewing with Noesis. I also can't seem to convert them via hexing. For example, Tron Bonne's eye texture and some of her effects.

I've attached Tron Bonne's eye texture (specifically, the one from her 3P color) if anyone wants to help with these freaky things.
I'm noticing the same problem with Tron's eye texture. Not really sure what's up with these, but it'd be nice to get them properly converted.
## Post #148
- Username: iK1L73r
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Aug 08, 2011 6:21 am
- Post datetime: 2011-08-08T23:32:50+00:00
- Post Title: Re: MvC3 .ARC files.

can somebody tellme how to convert the .mod to .obj or something like that
i try 2 convert them with noesis but when i try 2 export it crashes and xandreale dont open them
## Post #149
- Username: maniacoloco
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Mar 05, 2011 10:19 pm
- Post datetime: 2011-08-08T23:43:02+00:00
- Post Title: Re: MvC3 .ARC files.

> Reply from iK1L73r
>
> can somebody tellme how to convert the .mod to .obj or something like that
i try 2 convert them with noesis but when i try 2 export it crashes and xandreale dont open them

Noesis exports MVC3 mod files to obj directly, you don't need to use xandreale.
## Post #150
- Username: iK1L73r
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Aug 08, 2011 6:21 am
- Post datetime: 2011-08-08T23:55:27+00:00
- Post Title: Re: MvC3 .ARC files.

> Reply from maniacoloco
>
> iK1L73r wrote:i try 2 convert them with noesis but when i try 2 export it crashes 

Noesis exports MVC3 mod files to obj directly, you don't need to use xandreale.
yes i tryed but noesis crashes
## Post #151
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2011-08-09T08:56:14+00:00
- Post Title: Re: MvC3 .ARC files.

> Reply from iK1L73r
>
> maniacoloco wrote:iK1L73r wrote:i try 2 convert them with noesis but when i try 2 export it crashes 

Noesis exports MVC3 mod files to obj directly, you don't need to use xandreale.
yes i tryed but noesis crashes
I wish people would report crashes in the Noesis thread, and provide crash info and offending files, because it's blind luck that I even happened to read this post. I'm often too lazy to keep up on these per-game threads.

MVC3->OBJ works fine for me on the 10 or so models I've tested. What model are you trying to convert? And are you using the latest version of Noesis, and did you actually get it from the Xentax Noesis site?
## Post #152
- Username: iK1L73r
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Aug 08, 2011 6:21 am
- Post datetime: 2011-08-09T13:13:04+00:00
- Post Title: Re: MvC3 .ARC files.

> Reply from MrAdults
>
> iK1L73r wrote:

I wish people would report crashes in the Noesis thread, and provide crash info and offending files, because it's blind luck that I even happened to read this post. I'm often too lazy to keep up on these per-game threads.

MVC3->OBJ works fine for me on the 10 or so models I've tested. What model are you trying to convert? And are you using the latest version of Noesis, and did you actually get it from the Xentax Noesis site?

ok thanx i think i did something wrong
edit: i was trying to export the ps3 model
now i only need the x360 wolverine arc
## Post #153
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2011-10-19T03:35:01+00:00
- Post Title: Re: MvC3 .ARC files.

Sorry for bumping a old topic, Does anyone have Juggernaut exported as a OBJ possibly? I don't need the textures just the model if anyone can help me on this one it would be greatly appreciated. I just do papercrafting and if I can get the OBj I can turn the helmet into a papercraft model with my Pepakura Designer program. I know it sounds like a odd request but I'm hoping someone can help me. I just don't know how to use Noesis or do any of this programming stuff or I would do it myself. Thanks.
## Post #154
- Username: Sammael666
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri May 21, 2010 12:23 am
- Post datetime: 2014-12-17T15:34:45+00:00
- Post Title: Re: MvC3 .ARC files.

Hello, can everbody convert this tex files to dds files.

[https://www.sendspace.com/file/g0cyhd](https://www.sendspace.com/file/g0cyhd)
