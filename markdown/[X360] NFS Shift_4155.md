## Post #1
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2010-02-20T13:35:36+00:00
- Post Title: [X360] NFS Shift

Hello!

Can you please have a look into this files? (Unpacker QuickBMS Script would be nice)

And one Question whats the XTX-Textures any way to open them?

I attach you some BFF Files .. and they from title 1 update 

[http://uploaded.to/file/aqzhkh](http://uploaded.to/file/aqzhkh)
## Post #2
- Username: rstratton
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Feb 03, 2010 1:47 pm
- Post datetime: 2010-02-22T05:59:27+00:00
- Post Title: [X360] NFS Shift

are these files from xbox360?
## Post #3
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2010-02-22T15:07:01+00:00
- Post Title: [X360] NFS Shift

Yes
## Post #4
- Username: Simon
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-02-22T21:55:17+00:00
- Post Title: [X360] NFS Shift

```
Get D Long 0 ;
Get FN Long 0 ;
ReverseLong FN ;
Get DHigh Long 0 ;
ReverseLong High ;
Get DLow Long 0 ;
ReverseLong Low ;
Get PadSize Long 0 ;
ReverseLong PadSize ;
GetDString PAKNAME 256 0 ;
Get EXTOffset Long 0 ;
ReverseLong EXTOffset ;
Get EXTSH Long 0 ;
ReverseLong EXTSH ;
Get EXTSL Long 0 ;
ReverseLong EXTSL ;
Get D Long 0 ;
Get D Long 0 ;
Get D Long 0 ;
SavePos FIS 0 ;
SavePos D 0 ;
Math D += EXTOffset ;
GoTo D 0 ;
GetDString EX 4 0 ;
Get EXSIZE Long 0 ;
ReverseLong EXSIZE ;
GetDString EXNAME 256 0 ;
GetDString EXPath 256 0 ;
GetDString EXPlatform 256 0 ;
SavePos NIS 0 ;
Set J Long 16 ;
Math J *= FN ;
Math NIS += J ;
For T = 1 To FN ;
Math FIS += 12 ;
GoTo FIS 0 ;
Get OFF Long 0 ;
ReverseLong OFF ;
Get SIZE Long 0 ;
ReverseLong SIZE ;
SavePos FIS 0 ;
Math FIS += 22 ;
GoTo NIS 0 ;
Get NS Byte 0 ;
GetDString FName NS 0 ;
SavePos NIS 0 ;
Set PAD String PAKNAME ;
String PAD += "\" ;
String PAD += FName ;
Log PAD OFF SIZE 0 0 ;
Next T ;

```


That will do it in MultiEx Commander. Take the .bms file below and add it to the MRF file (see BMS menu). Follow instructions and then open BFF files.
[bff.zip](https://xentaxbackup.github.io/file/2796_bff.zip)
## Post #5
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2010-02-22T22:45:48+00:00
- Post Title: [X360] NFS Shift

Sorry maybe I'm dumb but it's outputting binary crap
## Post #6
- Username: rstratton
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Feb 03, 2010 1:47 pm
- Post datetime: 2010-02-22T23:22:58+00:00
- Post Title: [X360] NFS Shift

the bms script extracts the files fine but it seems the files are either still encrypted or are just jibberish
\vehicles\bmw_135\bmw_135_body.vud using old script
 <?xml version="1.0" ?>
<body_upgrades>
    <stage level="0">
        <mesh name_pattern="_KIT00_CHASSIS_" />
        <mesh name_pattern="_KIT00_BODYWORK_" />
        <mesh name_pattern="_KIT00_BUMPER_F_" />
        <mesh name_pattern="_KIT00_BUMPER_R_" />
        <mesh name_pattern="_KIT00_BOOT_" />
        <mesh name_pattern="_KIT00_BONNET_" />
    </stage>
and using new script
ÿ
ô R±   4#  UÀ §}”îÚÚîÆ"‘µ6R°ð„jÛnËa·±×Vÿÿ°þ @  Í ‚
 YèÒiM1‰09 =TZwNw{{¨À­½Žì\ZªJ'.5.‰
ÿßø    Ì AÁ4PPQÊ¶Ÿ‚«¼aìd„Ýöï}Ñ{K
¯ð|ëÄÞû!½¦¦µš=…>>ìÏÀ¬,Üx2l¿K\†Ä8>žz^÷éÏ»å¡·oÁù1MDÄ²Tó¶§†¢ÙÖ×öN¯¥¹	Ýõëj¾ük5“Tø¤½{«ô`Ó
³ävÚ`¥Ú‰$zûO0)¡aŒƒ€÷0ACÔ{/Ã3ÚÖýºÐÄÉ¯Ó
?àÃÆ·ŒXeŽÛA¡Ë¦J1y &5ŠÝÁ™vß~m÷|OÕ´ÔÔbý¬Ld'—jÚ #?Í¦
f!–>P—³ã#nÜ˜[{0Ê®vòˆ@ A 2{J"}‰Ù¤¢Üêþ@¼BØkŠ`"‹+ý\(£ŽÑâû¥z!5

older script is as follows

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

comtype XMemDecompress

idstring " KAP"
get DUMMY long
get FILES long

goto 0x118
get X118 long
goto 0x120
get X120 long
math X120 -= 0x308
goto 0x12d
get X12d byte

if X12d == 1
    print "X12d equal to %X12d% has not been tested, contact me"
    cleanexit
endif

callfunction X12dset
log MEMORY_FILE 0x130 X118

callfunction X12dset
set X120OFFSET long 0x438
math X120OFFSET += X118
log MEMORY_FILE2 X120OFFSET X120

for i = 0 < FILES
    encryption "" ""    # reset here instead to do it after each *log

    get CRC1    long MEMORY_FILE
    get CRC2    long MEMORY_FILE
    get OFFSET  long MEMORY_FILE
    get DUMMY1  long MEMORY_FILE
    get ZSIZE   long MEMORY_FILE
    get SIZE    long MEMORY_FILE
    get DUMMY   long MEMORY_FILE
    get DUMMY   long MEMORY_FILE
    get TYPE    byte MEMORY_FILE
    get DUMMY   byte MEMORY_FILE
    get DUMMY   long MEMORY_FILE
    get DUMMY3  long MEMORY_FILE

    get NAMEOFF long MEMORY_FILE2
    get DUMMY   long MEMORY_FILE2
    get DUMMY   long MEMORY_FILE2
    get DUMMY   long MEMORY_FILE2

    savepos TMP MEMORY_FILE2
    math NAMEOFF -= X120OFFSET
    goto NAMEOFF MEMORY_FILE2
    get NAMESZ  byte MEMORY_FILE2
    getdstring  NAME NAMESZ MEMORY_FILE2
    goto TMP MEMORY_FILE2

    callfunction X12dset
    if TYPE == 0
        log NAME OFFSET SIZE
    else if TYPE == 2
        clog NAME OFFSET ZSIZE SIZE
    else
        print "TYPE equal to %TYPE% has not been tested, contact me"
        cleanexit
    endif
next i

startfunction X12dset
    if X12d == 1    # ignored at the moment
        math TMPSZ += 0xf
        math TMPSZ &= 0xfffffff0
    endif
    if X12d == 2
        encryption rc4 "@lLy0urRaC3ar3bE"
    endif
endfunction

```
## Post #7
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2010-02-22T23:26:28+00:00
- Post Title: [X360] NFS Shift

To mention older Script = PC Version 

But output should be the same
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-02-23T06:42:34+00:00
- Post Title: [X360] NFS Shift

Okay, yeah, I noticed that some were encrypted and some not. So does the old script work on the xbox files? Then our job is done here.
## Post #9
- Username: dieinafire
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Feb 23, 2010 7:01 am
- Post datetime: 2010-02-23T07:01:26+00:00
- Post Title: [X360] NFS Shift

To clarify,

Here's a PC header from physicsmenu.bff from the full game:

[](http://img706.imageshack.us/i/pcphysicsmenu.jpg/)

Here's the same file from Xbox 360 DLC2:

[](http://img705.imageshack.us/i/360physicsmenu.jpg/)

If you want to play with both [here they are](http://www.megaupload.com/?d=GBMQBKP0).

The "old" unpacker we have works fine on PC, but not on 360, and the new script succeeds in getting files out of the container, but they're still compressed/encrypted from the look of things.

Basically the reason this is coming up is because the new DLC containing 10 Ferraris is only out for the 360.  A lot of the file formats - .fev, .fsb, .meb, and all the extensions they made up like .vud and .cdf and .hdt which simply read as .xml, ought to contain the same data between 360 and PC, and in the hands of some modders could probably be easily brought across to the PC.  But the unpacker we've got for the PC version doesn't get us very far, the PC version of Shift won't natively read those 360 .bffs, and the new script which does get them out of the 360 container doesn't leave us with readable files.
## Post #10
- Username: dieinafire
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-02-23T08:13:14+00:00
- Post Title: [X360] NFS Shift

Ok, I'll see what I can do. The encryption code for the PC version was @lLy0urRaC3ar3bE apparently. 
Mind, that reads: "All Your Race Are Be(long to us)", always funny, these programmers.
## Post #11
- Username: dieinafire
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Feb 23, 2010 7:01 am
- Post datetime: 2010-02-23T08:18:26+00:00
- Post Title: [X360] NFS Shift

Yeah that's pretty funny   the devs are one of those groups who are almost all ex-modders so I'm sure they knew someone would find that eventually and have a giggle
## Post #12
- Username: rstratton
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Feb 03, 2010 1:47 pm
- Post datetime: 2010-02-23T17:41:15+00:00
- Post Title: [X360] NFS Shift

99% of these ferrari's are in shift already. all that is missing is the models
## Post #13
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2010-02-23T18:03:11+00:00
- Post Title: [X360] NFS Shift

Nope ..

Some Textures, some Physic Files, some Gauges, many vdf files and this things ...
## Post #14
- Username: Simon
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-02-24T08:13:51+00:00
- Post Title: [X360] NFS Shift

The best option is to adapt the script for QuickBMS. The XBOX files are in Big Endian and have a slight change in structure. Perhaps Chrrox can help you, or Luigi.
## Post #15
- Username: dieinafire
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Feb 23, 2010 7:01 am
- Post datetime: 2010-02-24T11:10:36+00:00
- Post Title: [X360] NFS Shift

A-ha, I thought it might be the endian thing.  

Thanks for taking a look, I will see how much sense I can make of mexscript and probably get to HELLO WORLD by the time aluigi gets back
## Post #16
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2010-02-24T14:27:39+00:00
- Post Title: Re: [X360] NFS Shift

Thanks for your help, I Pm'nd Chrrox
## Post #17
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2010-03-02T18:24:27+00:00
- Post Title: Re: [X360] NFS Shift

Bump!
## Post #18
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-03-07T21:58:20+00:00
- Post Title: Re: [X360] NFS Shift

just returned from my vacancy :)

[http://aluigi.org/papers/bms/nfsshift.bms](http://aluigi.org/papers/bms/nfsshift.bms)

the problem was only related to the different endianess used on the x360 platform
## Post #19
- Username: dieinafire
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Feb 23, 2010 7:01 am
- Post datetime: 2010-03-08T01:44:05+00:00
- Post Title: Re: [X360] NFS Shift

Dude, you're the best.
## Post #20
- Username: ram202
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Apr 14, 2010 10:46 am
- Post datetime: 2010-04-17T13:38:07+00:00
- Post Title: Re: [X360] NFS Shift

how to take the model of the DLC? zmodeler not help!
## Post #21
- Username: dieinafire
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Feb 23, 2010 7:01 am
- Post datetime: 2010-04-22T13:30:28+00:00
- Post Title: Re: [X360] NFS Shift

It looks like everything other than plain text data is also in a 360-optimised format (swizzled textures, model coordinates probably also big endian, different .fsb format that the .fsb extractor seems to choke on).  Oleg at zmodeller was asked and said he has no interest in m aking the 360 models load in zmodeller, apparently others are looking at it for other programs though.
## Post #22
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2010-04-22T13:34:39+00:00
- Post Title: Re: [X360] NFS Shift

As far as I know Dave from 3D SimEd is looking into it
## Post #23
- Username: nfsx
- Rank: Banned
- Number of posts: 36
- Joined date: Thu Apr 22, 2010 10:36 pm
- Post datetime: 2010-04-23T16:45:16+00:00
- Post Title: Re: [X360] NFS Shift

I unpacked and everything.With QuickBMS

Tried to import to zmodeler 2 no luck.
## Post #24
- Username: ram202
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Apr 14, 2010 10:46 am
- Post datetime: 2010-04-24T11:30:56+00:00
- Post Title: Re: [X360] NFS Shift

zmodeler 2.2.4 out , please upload cars in ferrari & exotic (in 3ds)
## Post #25
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2010-04-24T11:41:08+00:00
- Post Title: Re: [X360] NFS Shift

This is no Warez Forum here.

BTW Really great news. I wish I had the Full Version of zM2
## Post #26
- Username: salim
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Apr 12, 2010 8:31 pm
- Post datetime: 2010-04-29T19:44:50+00:00
- Post Title: Re: [X360] NFS Shift

hey guys !

you left this ?
not everyone can get zmod2.2.4  so please don't gave up !
