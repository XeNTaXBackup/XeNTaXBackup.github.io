## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-03-21T04:06:51+00:00
- Post Title: Silent Hill: Shattered Memories *.arc

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-03-21T12:00:17+00:00
- Post Title: Silent Hill: Shattered Memories *.arc

goto 0x4
get FILES long
goto 0x8

got i = 0 < FILES
   get UNK01 long
   get OFFSET long
   get ZSIZE long
   get SIZE long
   if ZSIZE == SIZE
      log i OFFSET ZSIZE
   else
      clog i OFFSET SIZE ZSIZE
   endif
next i

this should be the correction
also if the compressed file starts with 78DA it is zlib.
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-03-21T12:01:28+00:00
- Post Title: Silent Hill: Shattered Memories *.arc

you can also just run offzip Since there are no names.

is there a name table anywhere in the files?
## Post #4
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-03-21T14:39:28+00:00
- Post Title: Silent Hill: Shattered Memories *.arc

I have several notes on your script:

why did you leave out the idstring? It works perfectly...
offset 0x08 holds the data start, 0x0C is always empty (so your script will always fail since the first file info starts at 0x10; apart from that, doesn't "goto 0x04" and "get FILES long" already set the cursor at 0x08?)
"got i=0<FILES" - correct would be "for i = 0 < FILES" (note the spaces!). But yes, I forgot to initialize i 
from 0x10 on: first comes the compressed size, then the uncompressed size (why did you just reverse it in your script? didn't you take a look at the sample?)
when the second size (uncompressed) equals ZERO (not ZSIZE==SIZE!), the files are (seemingly) uncompressed

So well, I corrected your script and it works now. I didn't notice that if no ComType is statet, QuickBMS assumes it as standard zip - nice to know! 
Also thanks for the tip with offzip. However, it doesn't find all the zip blocks (1997 of 2007) and strangely stops extracting after 62 files... Well, never mind, seems to work now. 

I've extracted 2007 files from the data.arc and also found the music.  The names are inside each file for this but I don't know how I could find a name table unless I scan through every file... 

Here's the working script; works for Wii and PS2!  

```
# files: DATA.ARC, IGC.ARC
# platforms: PS2, Wii, PSP
# (c) 2010 by AlphaTwentyThree

idstring "\x10\xfa\x00\x00"
get FILES long
math FILES -= 1

get DATASTART long
get DUMMY long

for i = 0 < FILES
   get DUMMY long
   get OFFSET long
   get SIZE long
   get ZSIZE long
   if ZSIZE == 0
      log i OFFSET SIZE
   else
      clog i OFFSET SIZE ZSIZE
   endif
 next i
```
## Post #5
- Username: tpu
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Jul 09, 2009 2:42 pm
- Post datetime: 2010-03-22T15:10:01+00:00
- Post Title: Silent Hill: Shattered Memories *.arc

The ARC file only save the hash of file name.
the hash: 

hash ^= name*33;
## Post #6
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-03-22T16:45:06+00:00
- Post Title: Silent Hill: Shattered Memories *.arc

> Reply from tpu
>
> The ARC file only save the hash of file name.
the hash: 

hash ^= name*33;
Sorry, I'm not familiar with hash. Could you please explain this? 
For example, if the hash name is 1E049456, what's the ASCII name?
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-03-22T17:38:51+00:00
- Post Title: Silent Hill: Shattered Memories *.arc

this format looks exactly like the one reversed here (I noticed the 0xfa10 signature and remembered it):
[viewtopic.php?p=34576#p34576](http://forum.xentax.com/viewtopic.php?p=34576#p34576)
## Post #8
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-03-22T19:14:35+00:00
- Post Title: Silent Hill: Shattered Memories *.arc

> Reply from aluigi
>
> this format looks exactly like the one reversed here (I noticed the 0xfa10 signature and remembered it):
viewtopic.php?p=34576#p34576
Whoops...   Didn't see that.   
However, can you explain how to get the file names out of the hash value?
Thanks.
## Post #9
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-03-22T19:29:50+00:00
- Post Title: Silent Hill: Shattered Memories *.arc

my mistake was in the log part i just had them reversed.
## Post #10
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-03-23T03:36:13+00:00
- Post Title: Silent Hill: Shattered Memories *.arc

The contents of this post was deleted because of possible forum rules violation.
[arc_ext_empty.7z](https://xentaxbackup.github.io/file/2875_arc_ext_empty.7z)
## Post #11
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-03-23T13:03:14+00:00
- Post Title: Silent Hill: Shattered Memories *.arc

Ok, finished my script. It's rather long due to the various file identifiers. Works for all platforms now, including PSP. 
You'll notice that if possible it writes filename and extension to the file. This is especially handy for the music files (*.fev) and pictures. I only included the main types (occuring more than 5 times) As a little bonus I've included an XM extractor - all .xm files can be played with Winamp after the extraction! 

```
# files: DATA.ARC, IGC.ARC
# platforms: PS2, Wii, PSP
# (c) 2010 by AlphaTwentyThree of Xentax

get SIZE asize
set PS2 binary 0

if SIZE > 300000000
   if SIZE < 400000000        # DATA.ARC (PS2)
      set PS2 binary 1
   else
      if SIZE > 600000000
         if SIZE < 700000000  # IGC.ARC (PS2)
            set PS2 binary 1
         endif
      endif
   endif
endif

idstring "\x10\xfa\x00\x00"
get FULLNAME basename
string FULLNAME += "_"

goto 0x04
get FILES long

math FILES -= 1
get DATASTART long
get DUMMY long

for i = 1 <= FILES
   
   get CRC long
   get OFFSET1 long
   get SIZE1 long
   get ZSIZE1 long
   savepos CURR1

   get CRC long
   get OFFSET2 long
   get SIZE2 long
   get ZSIZE2 long
   savepos CURR2

   if OFFSET1 == OFFSET2
      print "Skipping first entry of offset %OFFSET1%..."
      set OFFSET OFFSET2
      set SIZE SIZE2
      set ZSIZE ZSIZE2
      set CURR CURR2
      math i += 1           # raise counter to skip one offset entry
   else
      set OFFSET OFFSET1
      set SIZE SIZE1
      set ZSIZE ZSIZE1
      set CURR CURR1
   endif

   if ZSIZE == 0
      log MEMORY_FILE OFFSET SIZE        # write file into memory
   else
      clog MEMORY_FILE OFFSET SIZE ZSIZE
   endif
   get SIZE asize MEMORY_FILE
   
   set NAME string FULLNAME
   string NAME += i
   goto 0 MEMORY_FILE
   get TYPE short MEMORY_FILE         # analyze file type, extract name if possible
   set TYPED 1
   SET OFFSET 0
   set SKIP byte 0                    # marker to skip file (e.g. empty table)

   if TYPE == 3841
      goto 0x14 MEMORY_FILE
      get NAME2 string MEMORY_FILE
      string NAME += " - "
      string NAME += NAME2
      string NAME += ".fev"

   elif TYPE == 1814
      if PS2 == 1
         FindLoc NAMEOFF string "PS2" MEMORY_FILE ""
         if NAMEOFF != ""
            goto NAMEOFF MEMORY_FILE
            get DUMMY threebyte MEMORY_FILE        # test if string is the right one
            get Z_TEST byte MEMORY_FILE
            if Z_TEST == 0
               math NAMEOFF += 0x14
               goto NAMEOFF MEMORY_FILE
               get NAME2 string MEMORY_FILE
               if NAME2 != ""
                  string NAME += " - "
                  string NAME += NAME2
               endif
            endif
         endif
      endif
      string NAME += ".txd"                 # no PS2

   elif TYPE == 2
      string NAME += ".sub"
   elif TYPE == 64016
      string NAME += ".arc"
   elif TYPE == 18770
      string NAME += ".at3"

   elif TYPE == 800
      string NAME += ".fbxf"
   elif TYPE == 2016
      string NAME += ".fbxf"
   elif TYPE == 6528
      string NAME += ".fbxf"
   elif TYPE == 8224
      string NAME += ".fbxf"
   elif TYPE == 16416
      string NAME += ".fbxf"
   elif TYPE == 18464
      string NAME += ".fbxf"
   elif TYPE == 18528
      string NAME += ".fbxf"
   elif TYPE == 20512
      string NAME += ".fbxf"
   elif TYPE == 22560
      string NAME += ".fbxf"
   elif TYPE == 22624
      string NAME += ".fbxf"
   elif TYPE == 26720
      string NAME += ".fbxf"
   elif TYPE == 24672
      string NAME += ".fbxf"
   elif TYPE == 24608
      string NAME += ".fbxf"
   elif TYPE == 26656
      string NAME += ".fbxf"
   elif TYPE == 0x0360
      string NAME += ".lvl"
   elif TYPE == 0x036A
      string NAME += ".lvl"
   elif TYPE == 16956
      string NAME += ".boot"
   elif TYPE == 55551
      string NAME += ".jpeg"
   elif TYPE == 20617
      string NAME += ".png"
   elif TYPE == 265
      string NAME += ".drk"
   elif TYPE == 268
      string NAME += ".drk"
   elif TYPE == 280
      string NAME += ".drk"
   elif TYPE == 285
      string NAME += ".drk"
   elif TYPE == 308
      string NAME += ".drk"
   elif TYPE == 309
      string NAME += ".drk"
   elif TYPE == 312
      string NAME += ".drk"
   elif TYPE == 339
      string NAME += ".drk"
   elif TYPE == 341
      string NAME += ".drk"
   elif TYPE == 345
      string NAME += ".drk"
   elif TYPE == 864
      string NAME += ".drk"
   else
      set TYPED 0
   endif

   if TYPED == 0                     # no sign or unknown
      set OFF SIZE                   # check if format is CSV
      math OFF -= 2
      goto OFF MEMORY_FILE
      get CSV_DES short MEMORY_FILE
      if CSV_DES == 0x0A0D
         string NAME += ".csv"
      else
         goto 0 MEMORY_FILE
         FindLoc XM_DES string "Extended Module:" MEMORY_FILE ""
         if XM_DES != ""
            goto 0 MEMORY_FILE
            get NAME string MEMORY_FILE
            set OFFSET XM_DES
            math SIZE -= XM_DES
         else
            string NAME += ".type"
            string NAME += TYPE
         endif
      endif
   endif

   log NAME OFFSET SIZE MEMORY_FILE
   goto CURR

next i
```
## Post #12
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-03-23T16:26:35+00:00
- Post Title: Silent Hill: Shattered Memories *.arc

Ok, here is an extractor for the *.fev files that were extracted by my last script:

```
# format: *.fev
# platforms: Wii, PS2, PSP
# (c) 2010 by AlphaTwentyThree of Xentax forums

idstring "\x01\x0f\x00\x00"
goto 0xa4
get NAME string
goto 0xa4
FindLoc EXT string "\x2e\x66\x73\x62" 0 ""  # ".fsb"
if EXT == ""
   string NAME += ".fsb"
endif
FindLoc OFFSET string "FSB4" 0 ""
if OFFSET == ""
   print "No fsb containers found in fev file."
   cleanexit
endif
get SIZE asize
math SIZE -= OFFSET

log NAME OFFSET SIZE
```

And and here's the batch code you might find helpful to extract all *.fev files in a folder (requires the upper script in the same folder):

```
md FSB
move *.fsb FSB
```
## Post #13
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2010-03-24T08:35:18+00:00
- Post Title: Silent Hill: Shattered Memories *.arc

nice works AlphaTwentyThree
## Post #14
- Username: Barnaby
- Rank: advanced
- Number of posts: 47
- Joined date: Tue Dec 15, 2009 12:41 am
- Post datetime: 2010-03-24T21:34:20+00:00
- Post Title: Silent Hill: Shattered Memories *.arc

Nice one Alpha, thanks for this!
## Post #15
- Username: tpu
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Jul 09, 2009 2:42 pm
- Post datetime: 2010-03-28T14:49:08+00:00
- Post Title: Silent Hill: Shattered Memories *.arc

> Reply from AlphaTwentyThree
>
> tpu wrote:The ARC file only save the hash of file name.
the hash: 

hash ^= name*33;
Sorry, I'm not familiar with hash. Could you please explain this? 
For example, if the hash name is 1E049456, what's the ASCII name?

for file "FontJAP":
1. FontJAP -> fontjap
2.
    name = "fontjap"
    hash = 0;
    for(i=0; i<7; i++){
        hash *= 33;
        hash ^= name;
    }
3. hash result: 0xf63bd6a8
## Post #16
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-03-29T15:39:22+00:00
- Post Title: Re: Silent Hill: Shattered Memories *.arc

Thanks for the explanation. 
So the file names aren't accesible, right? :-\
## Post #17
- Username: caws
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Mar 02, 2008 2:57 am
- Post datetime: 2010-03-31T21:00:26+00:00
- Post Title: Re: Silent Hill: Shattered Memories *.arc

can i repack the files back to the data.arc with the wuick bms??
## Post #18
- Username: caws
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Mar 02, 2008 2:57 am
- Post datetime: 2010-04-10T14:41:53+00:00
- Post Title: Re: Silent Hill: Shattered Memories *.arc

So, i've created a tool to edit the .sub files (ingame texts), it creates a new sub file with everything working, the problem is when i insert the new sub file in the .arc ... i compressed the new sub (zlib), and in the arc i've put the adress of the file the size of it compressed and the size of it decompressed, but the game keeps using a file  non edited, why? Please help me.. need to translate this game!!   

Sorry for my english.
## Post #19
- Username: tpu
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Jul 09, 2009 2:42 pm
- Post datetime: 2010-04-15T01:28:16+00:00
- Post Title: Re: Silent Hill: Shattered Memories *.arc

> Reply from caws
>
> So, i've created a tool to edit the .sub files (ingame texts), it creates a new sub file with everything working, the problem is when i insert the new sub file in the .arc ... i compressed the new sub (zlib), and in the arc i've put the adress of the file the size of it compressed and the size of it decompressed, but the game keeps using a file  non edited, why? Please help me.. need to translate this game!!   

Sorry for my english.

There have a boot.arc embeded in EBOOT.BIN. You need edit this file and repack it.
## Post #20
- Username: caws
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Mar 02, 2008 2:57 am
- Post datetime: 2010-04-16T05:22:38+00:00
- Post Title: Re: Silent Hill: Shattered Memories *.arc

> Reply from tpu
>
> caws wrote:So, i've created a tool to edit the .sub files (ingame texts), it creates a new sub file with everything working, the problem is when i insert the new sub file in the .arc ... i compressed the new sub (zlib), and in the arc i've put the adress of the file the size of it compressed and the size of it decompressed, but the game keeps using a file  non edited, why? Please help me.. need to translate this game!!   

Sorry for my english.

There have a boot.arc embeded in EBOOT.BIN. You need edit this file and repack it.

Dude, thanks, u saved my life, i own you one.!!!

So now i just have to edit this arc.. and find a way to put it back in the eboot.bin!

Qhen i release my translation, there will be credits with your name.

EDIT:Inside of it, there is the boot.arc (witch has just 9 files, it has only the memory stick texts, not the ingame texts)
       There is a data.arc, but it only has the 8000 header of the data.arc in the iso... i will try to modify the pointer, size check and uncompressed check in this part and in the arc to see if it works. Thx for helping.!

EDIT: |Already undestood it thx.
## Post #21
- Username: lUIGUIPIETRO
- Rank: veteran
- Number of posts: 87
- Joined date: Sat Mar 13, 2010 10:59 pm
- Post datetime: 2012-04-22T10:33:18+00:00
- Post Title: Re: Silent Hill: Shattered Memories *.arc

Thanks for all, and,... How can open TXD files?
## Post #22
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-12-14T13:13:18+00:00
- Post Title: Re: Silent Hill: Shattered Memories *.arc

PS: Found ~600 Filenames (used always lowercase)
[SHSM_ARCUnpacker_1.0.0.rar](https://xentaxbackup.github.io/file/6087_SHSM_ARCUnpacker_1.0.0.rar)
## Post #23
- Username: |SyKy|
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Dec 27, 2012 7:13 pm
- Post datetime: 2013-01-01T12:48:28+00:00
- Post Title: Re: Silent Hill: Shattered Memories *.arc

> Reply from caws
>
> So, i've created a tool to edit the .sub files (ingame texts), it creates a new sub file with everything working, the problem is when i insert the new sub file in the .arc ... i compressed the new sub (zlib), and in the arc i've put the adress of the file the size of it compressed and the size of it decompressed, but the game keeps using a file  non edited, why? Please help me.. need to translate this game!!   

Sorry for my english.

Please send me your tool for edit .sub files  I want make Czech translation for this game.  Thanks for your reply.
## Post #24
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-25T15:53:48+00:00
- Post Title: Re: Silent Hill: Shattered Memories *.arc

Updated filelist. Nothing special. Found files like:

```
strings.enu
strings.fre
strings.fru
strings.ger
strings.ita
strings.jap
strings.spa
strings.spu
```

[SHSM_Projects_0.2.rar](https://xentaxbackup.github.io/file/6218_SHSM_Projects_0.2.rar)
## Post #25
- Username: |SyKy|
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Dec 27, 2012 7:13 pm
- Post datetime: 2013-05-05T18:41:19+00:00
- Post Title: Re: Silent Hill: Shattered Memories *.arc

Please help with put files back into .ARC archive.
## Post #26
- Username: |SyKy|
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Dec 27, 2012 7:13 pm
- Post datetime: 2013-05-31T17:26:26+00:00
- Post Title: Re: Silent Hill: Shattered Memories *.arc

Please how extract only language files "ENG" via Quick BMS? Thanks for answer.
