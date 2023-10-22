## Post #1
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-06-11T21:46:01+00:00
- Post Title: James Bond 007 Everything or Nothing

unusual archives with the CHK extension, no filenames.
script for quickbms:

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

comtype ea
get DUMMY long
if DUMMY > 0xffff
    endian big
endif
get DUMMY long
get DUMMY long
get FILES long
get OFFSET long
get XFILES long
math TMP = XFILES
math TMP *= 0x18
math OFFSET += TMP
for i = 0 < FILES
    get DUMMY long
    get DUMMY long
    get XSIZE long
    get SIZE long
    get ZERO long
    get FLAGS long
    math OFFSET x= 0x800
    if FLAGS & 0x04000000
        clog "" OFFSET SIZE XSIZE
    else
        log "" OFFSET SIZE
    endif
    math OFFSET += SIZE
next i
```
## Post #2
- Username: N/A
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Sep 17, 2014 11:15 pm
- Post datetime: 2016-05-18T17:35:56+00:00
- Post Title: James Bond 007 Everything or Nothing

Yes there are filenames, 8 byte filename field in the 2nd table to be precise. (kinda like fsh texure files in a way)

I unpacked it to the correct file offset within each data stream, simple nested for loop. (and memory file)
Took me longer to debug than to add new code though...

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms
#
# initially coded by Alugi, further documentation of .chk file and expansion of functionality by N/A

set INCLUDEARCHIVENAME 0 //boolean to avoid name conflicts if unpacking 2 or more .chk files

comtype dk2 //quickbms.txt doesn't list ea type, I tried dk2 from on quickbms.txt comments, did a byte-by-byte comparison, identical.
get DUMMY long
if DUMMY > 0xffff
    endian big
endif
get DUMMY long
get TABLEWIDTH long //possibly clarified width of table throughout file.
get DATSTREAMCOUNT long //clarified purpose of integer
get OFFSET long 
get XFILES long 
math TMP = XFILES
math TMP *= TABLEWIDTH
math OFFSET += TMP
for i = 0 < DATSTREAMCOUNT
    get fileTablePtr long //abs offset of first table pointer.
    get filesInStream long //number of files in each stream
    get XSIZE long
    get SIZE long
    get ZERO long
    get FLAGS long
    math OFFSET x= 0x800
    putvarchr MEMORY_FILE XSIZE 0  //allocates internal memory
    if FLAGS & 0x04000000 //little end
        clog MEMORY_FILE OFFSET SIZE XSIZE
    elif FLAGS & 0x00000400 //big end
        clog MEMORY_FILE OFFSET SIZE XSIZE
    else
        log MEMORY_FILE OFFSET SIZE
    endif
    savepos dataStreamTablePtr 0 //saves pointer to revert to after finish parsing datastream
    goto fileTablePtr 0
    for j = 0 < filesInStream
        getdstring NAME 8 0 //gets filename
        //assembles filename to export, to prevent naming conflicts with 2 or more .chk files
        if INCLUDEARCHIVENAME > 0
            get ChkFN BASENAME 0
            String EXPNAME = ChkFN
            String EXPNAME + "."
            String EXPNAME + NAME
        else
            String EXPNAME = NAME
        endif
        get DUMMY long 0 
        get DUMMY long 0 //value = compressed file size it seems
        get FILEOFFSET long 0
        get FILESIZE long 0
        log EXPNAME FILEOFFSET FILESIZE -1
    next j
    goto dataStreamTablePtr 0 
    //no need to keep fileTablePtr as next dataStream gives the offset for the first file in next data stream.
    math OFFSET += SIZE
next i

```
## Post #3
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2016-05-18T20:34:16+00:00
- Post Title: James Bond 007 Everything or Nothing

That`s quite an effort you`ve made N/A, thanks.
## Post #4
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2023-08-04T23:04:13+00:00
- Post Title: James Bond 007 Everything or Nothing

For EON 007, the assets appear to be inside of .viv archives, how do I unpack those?
## Post #5
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-08-05T07:00:06+00:00
- Post Title: James Bond 007 Everything or Nothing

> Reply from AxelNoir ↑Sat Aug 05, 2023 7:04 am at Sat Aug 05, 2023 7:04 am
>
> 
For EON 007, the assets appear to be inside of .viv archives, how do I unpack those?

There are few types of EA BIG/VIV archives [http://wiki.xentax.com/index.php/Differ ... V_archives](http://wiki.xentax.com/index.php/Different_versions_of_EA_BIG/VIV_archives)

The most popular one is BIGF type which can be handled for example by FinalBIG tool [https://www.moddb.com/downloads/final-big-editor](https://www.moddb.com/downloads/final-big-editor)
## Post #6
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2023-08-05T13:33:58+00:00
- Post Title: James Bond 007 Everything or Nothing

> Reply from ikskoks ↑Sat Aug 05, 2023 3:00 pm at Sat Aug 05, 2023 3:00 pm
>
> 
AxelNoir wrote: ↑Sat Aug 05, 2023 7:04 am
For EON 007, the assets appear to be inside of .viv archives, how do I unpack those?


There are few types of EA BIG/VIV archives http://wiki.xentax.com/index.php/Differ ... V_archives

The most popular one is BIGF type which can be handled for example by FinalBIG tool https://www.moddb.com/downloads/final-big-editor

I see, thanks for the information. I'm looking at the PS2 and Xbox versions of the game and both of them appear to be using .viv files, so I don't think the tool you linked me will work. Do you know of any other way of opening those files?
## Post #7
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-08-05T15:23:03+00:00
- Post Title: James Bond 007 Everything or Nothing

You can try to use some other tools listed on the wiki or you can upload some samples to hosting sites like mega.nz or google drive, share a public link here  and then other people could help you with this.
## Post #8
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2023-08-06T14:46:06+00:00
- Post Title: James Bond 007 Everything or Nothing

> Reply from ikskoks ↑Sat Aug 05, 2023 11:23 pm at Sat Aug 05, 2023 11:23 pm
>
> 
You can try to use some other tools listed on the wiki or you can upload some samples to hosting sites like mega.nz or google drive, share a public link here  and then other people could help you with this.

Thanks, I got it working. I decided to check out the gamecube version's files and they're all in .NGC format. With a hex editor I peeked inside and it appears character models are stored inside the map files, which is a little strange to me considering the other EA games the developers have stored the character models in seperate files. Anyway here's a sample .NGC file from the game:

[https://drive.google.com/file/d/1LdFDLj ... sp=sharing](https://drive.google.com/file/d/1LdFDLjZuOFxrjJrKdSsUsQ1zHqZZkqW0/view?usp=sharing)

It looks like the assets are stored inside a .GCM format from what I can tell, but that's about as far as I got.

I'm suspecting it's using tri strip faces and I'm pretty bad at figuring that out so maybe you or someone else can help get a better look.
## Post #9
- Username: Blue47
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Sep 04, 2023 4:33 pm
- Post datetime: 2023-09-04T08:55:06+00:00
- Post Title: James Bond 007 Everything or Nothing

I was able to extract 4 files from the PS2 Dec Prototype Build from the CHK files. It exported .bnk ( [sfxs] open with PSound), .dat, .cl5 (view with a hex editor it shows some file names listed at the bottom so my guess is that this is some sort of project file?), and also .nfc (Which also shows file names listed)

Is there any info on what the DAT files are? There seems to be a bunch of them in the "\DRIVING\[Exported] MISC\data\Actors\models" folder
