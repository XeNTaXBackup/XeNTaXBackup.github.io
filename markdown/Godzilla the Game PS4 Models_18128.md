## Post #1
- Username: UltramanUltimo
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Dec 20, 2016 10:11 am
- Post datetime: 2018-05-23T02:38:18+00:00
- Post Title: Godzilla the Game PS4 Models

Hi there.

I recently managed to track down a homebrewed version of the Godzilla the Game for the PS4 and successfully extracted all of it's contents.

The content is the same for the ps3 content but the only difference is a larger roster and more content. To my understanding there is a forum here that has a script or program that can extract the content (found here [viewtopic.php?f=16&t=16930](http://forum.xentax.com/viewtopic.php?f=16&t=16930)), but I've tried using it and got nothing to work.

Perhaps because it was set for the ps3 version. That is why I am here, I've tried various methods to extract the models and their textures from the pac files but I can't seem to get anything to work, that is why I am here seeking assistance.

I'll put in an upload of a zip containing the pac files. There's video files that can help identify the monster for each one is. Models 01 and 18 are Godzilla and the 1964 Godzilla, they lack intros

The file's abit big so I couldn't upload it as an attachment: [http://www.mediafire.com/file/c4jjj807y ... s.zip/file](http://www.mediafire.com/file/c4jjj807yzjl4da/Godzilla_Ps4_Models.zip/file)

I'm not sure if that's allowed but I'll remove the link if it is.

Any help is apperciated!!
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-05-24T03:53:35+00:00
- Post Title: Godzilla the Game PS4 Models

> Reply from UltramanUltimo
>
> I've tried various methods to extract the models and their textures from the pac files but I can't seem to get anything to work, that is why I am here seeking assistance.
this bms script will extract and decompress the files from your pac samples  


 GodzillatheGame_PS4_pac.zip
(642 Bytes) Downloaded 64 times
## Post #3
- Username: UltramanUltimo
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Dec 20, 2016 10:11 am
- Post datetime: 2018-05-24T06:39:25+00:00
- Post Title: Godzilla the Game PS4 Models

> Reply from AceWell
>
> UltramanUltimo wrote:I've tried various methods to extract the models and their textures from the pac files but I can't seem to get anything to work, that is why I am here seeking assistance.
this bms script will extract and decompress the files from your pac samples  
Code: Select all# script for QuickBMS http://aluigi.altervista.org/quickbms.htm

get FOLDER basename
idstring "add\0"
get VERSION long //??
get HEADER_SIZE long //??
get ENTRY_TABLE_STRIDE long //??
get FILES long
get PAC_SIZE long
get ZERO longlong
for i = 0 < FILES
    get OFFSET long
    get SIZE long
    get ZERO long
    get UNK long
    get STR_OFFSET long
    getdstring ZERO 0xc
    savepos TMP
    goto STR_OFFSET
    get NAME string
    goto OFFSET
    get CHECK long
    if CHECK == 0x00535A4C
        log memory_file OFFSET SIZE
        goto 0x0 -1
        idstring -1 "LZS\0"
        getdstring DUMMY 4 -1
        get OFFSET long -1
        get DICT_OFFSET long -1
        get SIZE long -1
        get ZSIZE long -1
        getdstring DUMMY 8 -1
        get NAME string -1
        goto DICT_OFFSET -1
        math DICT_SIZE = ZSIZE 
        math DICT_SIZE - DICT_OFFSET
        getdstring DICT DICT_SIZE -1
        comtype LZS_UNZIP DICT DICT_SIZE -1
        math ZSIZE = DICT_OFFSET 
        math ZSIZE - OFFSET
        string NAME p "%s\%s" FOLDER NAME
        clog NAME OFFSET ZSIZE SIZE -1
    else	
        string NAME p "%s\%s" FOLDER NAME
        log NAME OFFSET SIZE
    endif
    goto TMP
next i

While I've never made quickbms script i can certainly give it a shot, thank you for your assistance sir. I'll report on my progress as I go along. But just the same, could you add the script as an attachment so I can use it? Perhaps as a reference in the future.

Update: Well I figured out how to put the code in text and run it in quickbms
but it keeps telling me there's the variable index is invalid, there is an error in this tool. I followed the instructions of a youtube video, put the script in first, then the pac, then the output, but it only extracts one snd file before it gives that error message
## Post #4
- Username: SporeAltair
- Rank: advanced
- Number of posts: 63
- Joined date: Sun Mar 20, 2016 1:47 am
- Post datetime: 2019-07-11T17:28:20+00:00
- Post Title: Godzilla the Game PS4 Models

And how to open .dae and .dds?
## Post #5
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2019-07-11T20:29:45+00:00
- Post Title: Godzilla the Game PS4 Models

> Reply from SporeAltair ↑Fri Jul 12, 2019 1:28 am at Fri Jul 12, 2019 1:28 am
>
> 
And how to open .dae and .dds?

The reason you can't open it is because you haven't spammed this shit enough in every thread possible
How about you create 6 more posts?
## Post #6
- Username: lkw019
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jul 18, 2011 9:22 pm
- Post datetime: 2019-09-10T02:34:16+00:00
- Post Title: Godzilla the Game PS4 Models

Thank you for sharing.
