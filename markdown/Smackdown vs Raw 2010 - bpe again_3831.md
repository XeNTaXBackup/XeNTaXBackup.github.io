## Post #1
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2009-11-03T09:52:18+00:00
- Post Title: Smackdown vs Raw 2010 - bpe again

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2009-11-04T06:51:32+00:00
- Post Title: Smackdown vs Raw 2010 - bpe again

It's not a standardized BPE format, nothing will decompress them correctly.  It's been about 2-3 years and nobody has gotten anywhere with them.  Hopefully I will finally find the decompression routine in the XEX file and reverse it to make a program that will do it for us, but haven't found it yet, there's alot of routines in the XEX to go thru.
## Post #3
- Username: acidfrehley
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Nov 05, 2009 11:51 am
- Post datetime: 2009-11-05T17:26:40+00:00
- Post Title: Smackdown vs Raw 2010 - bpe again

How did you unpacked the .pac files? I've tried this during the last night, downloaded a bunch of programs but none of them worked. 

I already managed to insert old models into SvR10 by simply replacing the .pac files. But in order to proceed to a more complete modification unpacking/repacking the .pac files its almost obrigatory. 

If you have some tips for a starter would also help. I don't know anything about programming, Im just learning things on my own. 

Thanks.
## Post #4
- Username: acidfrehley
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Nov 05, 2009 11:51 am
- Post datetime: 2009-11-05T23:59:13+00:00
- Post Title: Smackdown vs Raw 2010 - bpe again

I was looking at some .pac files through Hex Workshop and after being tired of seeing a giant mix of letters and numbers making no sense, I actually found some text lines in some archives. 
For a start, would it be easy to just change the character name/overall through a edition on Hex Workshop? Cause it seemed like so. What precautions I have to take before editing the text into a file like that? 

And how the heck could you manage to extract a image file from that? 

lol, Im just lost.
## Post #5
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2009-11-10T06:22:58+00:00
- Post Title: Smackdown vs Raw 2010 - bpe again

@acidfrehley, how did you manage to replace the new pac files with the older ones? do they have to be the same size and name? Also does the pac replacement work with all xbox svr game right from svr07 upwards? 

I managed to extract the files from the pac archive using a hex editor. The only files that are stored in the pac files are files of bpe format. Search for the bpe header ("BPE" text string) and extract manually. Can you also post a few svr07 pac files if you have them, I want to examine the structure to see if this method works with those files as well. I'm interested in the characters unique to that game i.e hogan, booker t, rvd, angle.
## Post #6
- Username: DRAVEN
- Rank: advanced
- Number of posts: 74
- Joined date: Sun Oct 09, 2005 6:07 pm
- Post datetime: 2009-11-10T08:48:03+00:00
- Post Title: Smackdown vs Raw 2010 - bpe again

> Reply from acidfrehley
>
> How did you unpacked the .pac files? I've tried this during the last night, downloaded a bunch of programs but none of them worked. 

I already managed to insert old models into SvR10 by simply replacing the .pac files. But in order to proceed to a more complete modification unpacking/repacking the .pac files its almost obrigatory. 

If you have some tips for a starter would also help. I don't know anything about programming, Im just learning things on my own. 

Thanks.

Please can you explain this process on how to add old models, I used to be apart of the team that released mods for the first SVR and have wanted to make my own personal mods since then... I want LOD in svr2010 plus ECW ext..
## Post #7
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2009-11-10T09:05:32+00:00
- Post Title: Smackdown vs Raw 2010 - bpe again

> Reply from DRAVEN
>
> acidfrehley wrote:How did you unpacked the .pac files? I've tried this during the last night, downloaded a bunch of programs but none of them worked. 

I already managed to insert old models into SvR10 by simply replacing the .pac files. But in order to proceed to a more complete modification unpacking/repacking the .pac files its almost obrigatory. 

If you have some tips for a starter would also help. I don't know anything about programming, Im just learning things on my own. 

Thanks.

Please can you explain this process on how to add old models, I used to be apart of the team that released mods for the first SVR and have wanted to make my own personal mods since then... I want LOD in svr2010 plus ECW ext..

I imagine that you would replace the file using xbox backup creator - image browser. I dont have any of the older xbox svr games to get the models from, so I cant confirm. 

I downloaded your svr patch a few years back and used to follow your threads under the username tekken57.
## Post #8
- Username: DRAVEN
- Rank: advanced
- Number of posts: 74
- Joined date: Sun Oct 09, 2005 6:07 pm
- Post datetime: 2009-11-10T09:11:32+00:00
- Post Title: Smackdown vs Raw 2010 - bpe again

Long time no speak.. lol
I'm still on smacktalks just not as much nowadays 
I found how to edit tons on SVR09 should be the same on this years..
## Post #9
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2009-11-10T09:24:46+00:00
- Post Title: Smackdown vs Raw 2010 - bpe again

> Reply from DRAVEN
>
> Long time no speak.. lol
I'm still on smacktalks just not as much nowadays 
I found how to edit tons on SVR09 should be the same on this years..

What do you manage to edit? I was only abel to replace titantrons and some of the music.
## Post #10
- Username: DRAVEN
- Rank: advanced
- Number of posts: 74
- Joined date: Sun Oct 09, 2005 6:07 pm
- Post datetime: 2009-11-10T09:36:19+00:00
- Post Title: Smackdown vs Raw 2010 - bpe again

Same... On the xbox.. just had problems gettin them to show up in game? plus I couldnt get the music
## Post #11
- Username: plodtrew
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-11-25T15:35:19+00:00
- Post Title: Smackdown vs Raw 2010 - bpe again

bpe has been extracted "not by me"
This uses the exact same format as rumble roses.

[http://asmodean.reverse.net/pages/unrrbpe.html](http://asmodean.reverse.net/pages/unrrbpe.html)
## Post #12
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2009-11-26T09:08:57+00:00
- Post Title: Smackdown vs Raw 2010 - bpe again

> Reply from chrrox
>
> bpe has been extracted "not by me"
This uses the exact same format as rumble roses.

http://asmodean.reverse.net/pages/unrrbpe.html

dude you're a star!!!    four years of waiting for an uncompressor comes to an end. This works pefectly with the ps2 versions. 

It also uncompresses the xbox versions but this has a wierd model format with the header jboy. I'll post some files soon, maybe someone can help decipher it.
## Post #13
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-11-26T14:39:38+00:00
- Post Title: Smackdown vs Raw 2010 - bpe again

This is the 2010 model you see in the screenshot.
I know the format of the jboy "yobj" I am working on a converter I need to look ito the weights and bones before I post it here.
## Post #14
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2009-11-27T08:08:13+00:00
- Post Title: Smackdown vs Raw 2010 - bpe again

> Reply from chrrox
>
> This is the 2010 model you see in the screenshot.
I know the format of the jboy "yobj" I am working on a converter I need to look ito the weights and bones before I post it here.

didnt notice the picture before. awesome work, really looking forward to what you come up. Can you view the actual model texture though, the bpe conversion doesnt seem to uncompress this file completely and only shows the first bit of the texture? I can view the bump maps and other textures fine.
## Post #15
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-27T11:39:56+00:00
- Post Title: Smackdown vs Raw 2010 - bpe again

this particular type of compression (that I have called "yuke_bpe") is now included in QuickBMS 0.3.9a
## Post #16
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2009-11-27T14:37:51+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

> Reply from aluigi
>
> this particular type of compression (that I have called "yuke_bpe") is now included in QuickBMS 0.3.9a
Once again you come through and save me from having to make a program myself.  Thanks!

Now if only someone takes the time to make a compressor for this format, I will be totally work free, and use what little free time I have on the game instead.
## Post #17
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-11-27T15:40:01+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

The game can read uncompressed and compressed files there is no real need to re compress the content to have it load.
## Post #18
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2009-11-27T17:06:24+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

@chrrox, the problem I have with uncompressed files is the bigger filezies.  I cant replace the originals with the bigger files on the disc without the game freezing.
## Post #19
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-11-27T18:02:55+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

You must edit the whole pac file that is the problem.
you need to adjust the offsets there to accommodate the bigger file sizes.
even if you could re-compress the files they would not be the exact same size.
the easiest thing to modify would be the last pach file in each pac file because it would be simple to modify the size with a hex editor and it would only be one value you need to edit.
if you mention what you wish to accomplish I can try to help you.
## Post #20
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2009-11-27T23:29:29+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

> Reply from chrrox
>
> The game can read uncompressed and compressed files there is no real need to re compress the content to have it load.
Ok, that's good to know, I was going to test that, but now I don't need to.

Here is a QuickBMS script that will extract the character model PAC files for easy access.  It only works on the chXXX.pac files and it will extract the compressed files into a folder and then extract the uncompressed files into another folder.  The folder name will start with the basename of the chXXX.pac file.  I've only tested it so far on SvR2010 for Xbox 360.

I know it could prolly be rewritten better, but hey, it works.  

```
Get MASTERNAME FILENAME
Get NAME BASENAME
Set AFOLDER NAME
String AFOLDER + Attire
GoTo 0x0800
IDString "EMD "
Get NUMBERPACS SHORT
Math NUMBERPACS / 4
Set DIRPOSITION 0x0814
For i = 0 < NUMBERPACS
Open "." MASTERNAME
Set FOLDERNAME AFOLDER
String FOLDERNAME + i
Set NAME FOLDERNAME
STRING NAME + \
STRING NAME + FOLDERNAME
STRING NAME + ".pac"
GoTo DIRPOSITION
get PACOFFSET long
get PACLENGTH long
math PACOFFSET += 8    # 0x4000
math PACOFFSET *= 0x800
math PACLENGTH *= 0x100
Log NAME PACOFFSET PACLENGTH
Math DIRPOSITION + 16
Set NAME FOLDERNAME
STRING NAME + ".pac"
Open FOLDERNAME NAME
IDString "PACH"
Get FILENAME BASENAME
Set CFOLDER FILENAME
String CFOLDER + compressed
Set UFOLDER FILENAME
String UFOLDER + uncompressed
GoTo 0x0004
Get NUMBERFILES LONG
SavePos DIROFFSET
Math TMP = NUMBERFILES
Math TMP * 12
Math DATAOFFSET = DIROFFSET
Math DATAOFFSET + TMP
GoTo DIROFFSET
For k = 0 < NUMBERFILES
Get UNKNOWN LONG
Get OFFSET LONG
Get LENGTH LONG
Math TMP = DATAOFFSET
Math TMP + OFFSET
Set NAME CFOLDER
STRING NAME + \
STRING NAME + file
if k < 10
STRING NAME + 0
endif
STRING NAME + k
STRING NAME + ".compressed"
Log NAME TMP LENGTH
next k
For k = 0 < NUMBERFILES
Set NAME file
if k < 10
STRING NAME + 0
endif
STRING NAME + k
STRING NAME + ".compressed"
Open CFOLDER NAME
IDString "BPE "
GoTo 0x008
Get ZSIZE LONG
Get SIZE LONG
ComType yuke_bpe
Set NAME UFOLDER
STRING NAME + \
STRING NAME + file
if k < 10
STRING NAME + 0
endif
STRING NAME + k
Clog NAME 16 ZSIZE SIZE
next k
next i
```
## Post #21
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2009-11-27T23:56:52+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

Here is a QuickBMS script to extract the EDXX.pac files in the edit folder.  Once again, it could prolly be done better, but it works!    

```
Get MASTERNAME FILENAME
Get NAME BASENAME
Set AFOLDER NAME
String AFOLDER + PacFile
GoTo 0x0804
Get NUMBERPACS SHORT
Math NUMBERPACS / 3
Set PACOFFSET 0x4000
Set DIRPOSITION 0x0813
For i = 0 < NUMBERPACS
Open "." MASTERNAME
Set FOLDERNAME AFOLDER
String FOLDERNAME + i
Set NAME FOLDERNAME
STRING NAME + \
STRING NAME + FOLDERNAME
STRING NAME + ".pac"
GoTo DIRPOSITION
Get PACLENGTH LONG
Log NAME PACOFFSET PACLENGTH
Math DIRPOSITION + 12
Math PACOFFSET + PACLENGTH
GoTo PACOFFSET
FindLoc OFFSET string "PACH" 0 0
Set PACOFFSET OFFSET
Set NAME FOLDERNAME
STRING NAME + ".pac"
Open FOLDERNAME NAME
IDString "PACH"
Get FILENAME BASENAME
Set CFOLDER FILENAME
String CFOLDER + compressed
Set UFOLDER FILENAME
String UFOLDER + uncompressed
GoTo 0x0004
Get NUMBERFILES LONG
SavePos DIROFFSET
Math TMP = NUMBERFILES
Math TMP * 12
Math DATAOFFSET = DIROFFSET
Math DATAOFFSET + TMP
GoTo DIROFFSET
For k = 0 < NUMBERFILES
Get UNKNOWN LONG
Get OFFSET LONG
Get LENGTH LONG
Math TMP = DATAOFFSET
Math TMP + OFFSET
Set NAME CFOLDER
STRING NAME + \
STRING NAME + file
if k < 10
STRING NAME + 0
endif
STRING NAME + k
STRING NAME + ".bpe"
Log NAME TMP LENGTH
next k
For k = 0 < NUMBERFILES
Set NAME file
if k < 10
STRING NAME + 0
endif
STRING NAME + k
STRING NAME + ".bpe"
Open CFOLDER NAME
IDString "BPE "
GoTo 0x008
Get ZSIZE LONG
Get SIZE LONG
ComType yuke_bpe
Set NAME UFOLDER
STRING NAME + \
STRING NAME + file
if k < 10
STRING NAME + 0
endif
STRING NAME + k
Clog NAME 16 ZSIZE SIZE
next k
next i
```
## Post #22
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2009-11-28T00:44:19+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

Here is a QuickBMS Script to extract the bgXX.pac files in the bg folder.  As before, not the best script writing, but it works.    

```
Get MASTERNAME FILENAME
Get NAME BASENAME
Set AFOLDER NAME
String AFOLDER + PacFile
GoTo 0x0800
IDString "STG "
Get NUMBERPACS SHORT
Math NUMBERPACS / 3
Set PACOFFSET 0x4000
Set DIRPOSITION 0x0813
For i = 0 < NUMBERPACS
Open "." MASTERNAME
Set FOLDERNAME AFOLDER
String FOLDERNAME + i
Set NAME FOLDERNAME
STRING NAME + \
STRING NAME + FOLDERNAME
STRING NAME + ".pac"
GoTo DIRPOSITION
Get PACLENGTH LONG
Log NAME PACOFFSET PACLENGTH
Math DIRPOSITION + 12
Math PACOFFSET + PACLENGTH
GoTo PACOFFSET
FindLoc OFFSET string "PACH" 0 0
Set PACOFFSET OFFSET
Set NAME FOLDERNAME
STRING NAME + ".pac"
Open FOLDERNAME NAME
IDString "PACH"
Get FILENAME BASENAME
Set CFOLDER FILENAME
String CFOLDER + compressed
Set UFOLDER FILENAME
String UFOLDER + uncompressed
GoTo 0x0004
Get NUMBERFILES LONG
SavePos DIROFFSET
Math TMP = NUMBERFILES
Math TMP * 12
Math DATAOFFSET = DIROFFSET
Math DATAOFFSET + TMP
GoTo DIROFFSET
For k = 0 < NUMBERFILES
Get UNKNOWN LONG
Get OFFSET LONG
Get LENGTH LONG
Math TMP = DATAOFFSET
Math TMP + OFFSET
Set NAME CFOLDER
STRING NAME + \
STRING NAME + file
if k < 10
STRING NAME + 0
endif
STRING NAME + k
STRING NAME + ".bpe"
Log NAME TMP LENGTH
next k
For k = 0 < NUMBERFILES
Set NAME file
if k < 10
STRING NAME + 0
endif
STRING NAME + k
STRING NAME + ".bpe"
Open CFOLDER NAME
IDString "BPE "
GoTo 0x008
Get ZSIZE LONG
Get SIZE LONG
ComType yuke_bpe
Set NAME UFOLDER
STRING NAME + \
STRING NAME + file
if k < 10
STRING NAME + 0
endif
STRING NAME + k
Clog NAME 16 ZSIZE SIZE
next k
next i
```
## Post #23
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2009-11-28T00:58:19+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

If the script extracts a compressed folder, but not an uncompressed folder, then it means the compressed files aren't in BPE format, so you have to open them in hex editor and determine what format they are in.  

These should get you started, I'll make more as I figure them out.
## Post #24
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-28T01:31:59+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

the following quickbms script should be able to extract (and unpack automatically) any EPAC archive:
*edit* use the yuke.bms code posted below (it's EXACTLY like the one I posted plus separate handling of standalone PACH and BPE files)
## Post #25
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-28T01:45:19+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

well, I have decided to do a complete job including support also for PACH files and EBP chunks (so not only those included in the EPAC archives but also other provided as "stand-alone" files):
[http://aluigi.org/papers/bms/yuke.bms](http://aluigi.org/papers/bms/yuke.bms)
## Post #26
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-28T02:01:45+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

chrrox pointed me to those "EMD " fields of the EPAC archives which must be skipped, so I have updated the script to version 0.1.1
## Post #27
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2009-11-28T02:03:57+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

It works on most of them, but here is one EPAC file it doesn't work on, plus an example of an EPK8 file (this one is John Cena's character file).

[An EPAC file that doesn't work and also an example of an EPK8 file.](http://brienj.home.insightbb.com/pacfiles.zip)

Thanks for your help.
## Post #28
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2009-11-28T02:07:24+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

> Reply from aluigi
>
> chrrox pointed me to those "EMD " fields of the EPAC archives which must be skipped, so I have updated the script to version 0.1.1
I get an error now that says: MEMORY_FILE has not been used in the script yet
## Post #29
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-11-28T02:40:01+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

the problem is the svr pac files don't contain that part so it just needs a simple if statement checking if the 4 bytes it reads is that and if not don't skip those 4 bytes.
## Post #30
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2009-11-28T02:56:46+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

I figured it out, until he comes back, this is the script that will work:

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

comtype yuke_bpe

# the following is only for being able to handle all the 3 files
get NAME filename
string NAME += ".unpacked"
getdstring SIGN 4
if SIGN == "PACH"
    print "PACH file"
    get SIZE asize
    log MEMORY_FILE 0 SIZE
    callfunction pach_unpack
    cleanexit
elif SIGN == "BPE "
    print "BPE chunk"
    get DUMMY long
    get ZSIZE long
    get SIZE long
    savepos OFFSET
    clog NAME OFFSET ZSIZE SIZE
    cleanexit
elif SIGN != "EPAC"
    cleanexit
endif

#idstring "EPAC"
print "EPAC archive"
goto 0x80C
for
    getdstring NAME 4
    if NAME == ""
        cleanexit
    endif
    get OFFSET long
    get SIZE long
    math OFFSET += 8    # 0x4000
    math OFFSET *= 0x800
    math SIZE   *= 0x100
    if NAME != "EMD "
        log MEMORY_FILE OFFSET SIZE
        callfunction pach_unpack
    endif
next

startfunction pach_unpack
    # unpack the PACH files
    getdstring SIGN 4 MEMORY_FILE
    if SIGN == "PACH"
        get CHUNKS long MEMORY_FILE
        savepos INFO_OFF MEMORY_FILE
        math BASE_OFF = CHUNKS
        math BASE_OFF *= 12
        math BASE_OFF += 8
        putvarchr MEMORY_FILE2 SIZE 0   # partial pre-allocation (speed)
        log MEMORY_FILE2 0 0
        append
        for j = 0 < CHUNKS
            goto INFO_OFF MEMORY_FILE
            get DUMMY long MEMORY_FILE
            get CHUNK_OFF long MEMORY_FILE
            get CHUNK_SIZE long MEMORY_FILE
            savepos INFO_OFF MEMORY_FILE
            math CHUNK_OFF += BASE_OFF
            goto CHUNK_OFF MEMORY_FILE
            getdstring SIGN 4 MEMORY_FILE
            if SIGN == "BPE "
                get DUMMY long MEMORY_FILE
                get ZSIZE long MEMORY_FILE
                get SIZE long MEMORY_FILE
                savepos OFFSET MEMORY_FILE
                clog MEMORY_FILE2 OFFSET ZSIZE SIZE MEMORY_FILE
            else
                log MEMORY_FILE2 CHUNK_OFF CHUNK_SIZE MEMORY_FILE
            endif
        next j
        append
        get SIZE asize MEMORY_FILE2
        log NAME 0 SIZE MEMORY_FILE2
    else
        log NAME 0 SIZE MEMORY_FILE
    endif
endfunction

```
## Post #31
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-11-28T02:59:18+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

I sent a message asking for the files o be split up also as it will be easier to mod them separated rather than in one big file.
## Post #32
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2009-11-28T03:04:07+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

> Reply from chrrox
>
> I sent a message asking for the files o be split up also as it will be easier to mod them separated rather than in one big file.
The scripts that I made will split the files up.  

Split files will make it easier to change the files, but the way he has it makes it easier to see the whole "picture" and what the file is supposed to be.  Both type of scripts would be useful, and now that I see how the offsets work, I will be working on revising my script some.
## Post #33
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-11-28T03:11:02+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

I am looking at the file formats from a 3d model perspective and the developers must have split the files up in memory due to the fact that all the offsets are based on if each file ws seperated rather than one big file. but it is interesting to see it as one big file.
## Post #34
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2009-11-28T05:46:15+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

> Reply from chrrox
>
> I am looking at the file formats from a 3d model perspective and the developers must have split the files up in memory due to the fact that all the offsets are based on if each file ws seperated rather than one big file. but it is interesting to see it as one big file.
I updated the script for the chXXX.pac files, now that I see how the offsets and sizes are stored, thanks to aluigi, it is scripted better, and it also extracts files into seperated files, just like you want.

I'll update the other ones too, but all my scripts extract each individual pac file, then it extracts all the compressed files out of the pac file into seperate compressed files, then it decompresses each of those files (if it is BPE format) and put those files seperately in a different folder.  If you haven't tried one yet, it does exactly like you want.
## Post #35
- Username: NMCM
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Apr 15, 2009 2:02 pm
- Post datetime: 2009-11-28T07:23:23+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

I've been reading through topics looking for a tool that can extract model textures or anything from the .bpe files from wwf smackdown 2 know your roles(Ps1). I've downloaded both the quickbms and the unrrbpe. Nothing seems to work when I try to open the pac files or the .bpe files themselves with the extractor. Could someone help me?
## Post #36
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-28T11:27:23+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

fixed both the bug of MEMORY_FILE (because one of the file had size 0) and the compatibility with the EPK8 archives (names of 8 bytes instead of 4)
released [script 0.1.2](http://aluigi.org/papers/bms/yuke.bms)
## Post #37
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-11-28T17:23:51+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

The script works great
## Post #38
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-28T19:13:02+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

for anyone, the latest version of the script is 0.2.1 (thanx to chrrox and brienj for the testing eh eh eh)
## Post #39
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2009-11-28T19:13:27+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

What is the format of the model files?
## Post #40
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-11-28T19:50:24+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

Here is the converter
[viewtopic.php?f=16&t=3903](http://forum.xentax.com/viewtopic.php?f=16&t=3903)
## Post #41
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2009-11-29T00:18:11+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

The yukes.bms that aluigi made misses some DDS files, it doesn't give them a .dds extension, so I changed it to rename those properly.  The lines I added say "# added by me" at the end of them.  Maybe there is a better way to fix it?

```
#   note that this script is really big and chaotic and the function
#   which guesses the extension simply "guesses" it so don't consider it much
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

comtype yuke_bpe
putarray 0 0 0

# the following is only for being able to handle all the 3 files
get NAME filename
string NAME += ".unpacked"
getdstring SIGN 4
if SIGN == "PACH"
    print "PACH file"
    get SIZE asize
    log MEMORY_FILE 0 SIZE
    callfunction pach_unpack
    cleanexit
elif SIGN == "BPE "
    print "BPE chunk"
    get DUMMY long
    get ZSIZE long
    get SIZE long
    savepos OFFSET
    clog NAME OFFSET ZSIZE SIZE
    cleanexit
endif

set NAMESZ long 4
if SIGN == "EPAC"
    set NAMESZ long 4
elif SIGN == "EPK8"
    set NAMESZ long 8
else
    cleanexit
endif

#idstring "EPAC"
print "EPAC archive"
goto 0x800
for
    savepos OFFSET
    getdstring SIGN 4
    if SIGN == ""
        cleanexit
    endif
    string SIGN -= 1
    if SIGN == "EMD"
        get DUMMY long
        get DUMMY long
    elif SIGN == "EVP"
        get DUMMY long
        get DUMMY long
    elif SIGN == "EVT"
        get DUMMY long
        get DUMMY long
    else
        goto OFFSET
        getdstring NAME NAMESZ
        get OFFSET long
        get SIZE long
        math OFFSET += 8    # 0x4000
        math OFFSET *= 0x800
        math SIZE   *= 0x100
        log MEMORY_FILE OFFSET SIZE
        callfunction pach_unpack
    endif
next

startfunction pach_unpack
    set FOLDER string NAME
    getarray GLOBAL_COUNTER 0 0
    if SIZE == 0    # will be fixed in the next quickbms
        # they are empty folders, so skip them
        #log NAME 0 SIZE
    elif SIZE < 8
        log MEMORY_FILE2 0 SIZE MEMORY_FILE
        string NAME -= " "
        string NAME += /
        string NAME += GLOBAL_COUNTER
        callfunction gimme_a_name
        math GLOBAL_COUNTER += 1
        putarray 0 0 GLOBAL_COUNTER
    else
        getdstring SIGN 4 MEMORY_FILE
        if SIGN == "PACH"
            get CHUNKS long MEMORY_FILE
            savepos INFO_OFF MEMORY_FILE
            math BASE_OFF = CHUNKS
            math BASE_OFF *= 12
            math BASE_OFF += 8
            for j = 0 < CHUNKS
                set NAME string FOLDER
                string NAME -= " "
                string NAME += /
                string NAME += GLOBAL_COUNTER
                goto INFO_OFF MEMORY_FILE
                get DUMMY long MEMORY_FILE
                get CHUNK_OFF long MEMORY_FILE
                get CHUNK_SIZE long MEMORY_FILE
                savepos INFO_OFF MEMORY_FILE
                math CHUNK_OFF += BASE_OFF
                goto CHUNK_OFF MEMORY_FILE
                getdstring SIGN 4 MEMORY_FILE
                if SIGN == "BPE "
                    get DUMMY long MEMORY_FILE
                    get ZSIZE long MEMORY_FILE
                    get SIZE long MEMORY_FILE
                    savepos OFFSET MEMORY_FILE
                    clog MEMORY_FILE2 OFFSET ZSIZE SIZE MEMORY_FILE
                else
                    log MEMORY_FILE2 CHUNK_OFF CHUNK_SIZE MEMORY_FILE
                    math SIZE = CHUNK_SIZE
                endif
                callfunction gimme_a_name

                math GLOBAL_COUNTER += 1
                putarray 0 0 GLOBAL_COUNTER
            next j
        else
            string NAME -= " "
            string NAME += /
            string NAME += GLOBAL_COUNTER
            log MEMORY_FILE2 0 SIZE MEMORY_FILE
            callfunction gimme_a_name
            math GLOBAL_COUNTER += 1
            putarray 0 0 GLOBAL_COUNTER
        endif
    endif
endfunction

startfunction gimme_a_name
    get SIGN long MEMORY_FILE2
    get SIGN2 long MEMORY_FILE2
    if SIGN == 0x594f424a
        string NAME += ".YOBJ"
        log NAME 0 SIZE MEMORY_FILE2
    elif SIGN == 0x20455042
        string NAME += ".DAT"
        #get DUMMY long MEMORY_FILE2
        get ZSIZE long MEMORY_FILE2
        get SIZE long MEMORY_FILE2
        savepos OFFSET MEMORY_FILE2
        clog NAME OFFSET ZSIZE SIZE MEMORY_FILE2
    elif SIGN == 0x34425346
        string NAME += ".fsb"
        log NAME 0 SIZE MEMORY_FILE2
    elif SIGN == 0x48434150 # memory_files are not recursive
        string NAME += ".PACH"
        log NAME 0 SIZE MEMORY_FILE2
    elif SIGN == 0x20534444  # added by me
        string NAME += ".dds" # added by me
        log NAME 0 SIZE MEMORY_FILE2 # added by me
    elif SIGN & 0xffff0000  # guessed, should be good for the 99,9% of files
        string NAME += ".POF0"
        log NAME 0 SIZE MEMORY_FILE2
    elif SIGN2 == 0x00000100
        goto 0 MEMORY_FILE2
        get TEXTURES long MEMORY_FILE2
        goto 16 MEMORY_FILE2
        for z = 0 < TEXTURES
            getdstring TEX_NAME 16 MEMORY_FILE2
            if TEX_NAME == ""
                string NAME += ".TEX"
                log NAME 0 SIZE MEMORY_FILE2
                math z = TEXTURES
            else
                getdstring TEX_EXT 4 MEMORY_FILE2
                set TMP_NAME string FOLDER
                string TMP_NAME += /
                string TMP_NAME += TEX_NAME
                string TMP_NAME += "."
                string TMP_NAME += TEX_EXT
                get TEX_SIZE long MEMORY_FILE2
                get TEX_OFFSET long MEMORY_FILE2
                get DUMMY long MEMORY_FILE2
                log TMP_NAME TEX_OFFSET TEX_SIZE MEMORY_FILE2
            endif
        next z
    else
        string NAME += ".DAT"
        log NAME 0 SIZE MEMORY_FILE2
    endif
endfunction

```
## Post #42
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-29T11:39:19+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

the following lines:

```
        get DUMMY long
        get DUMMY long
    elif SIGN == "EVP"
        get DUMMY long
        get DUMMY long
    elif SIGN == "EVT"
        get DUMMY long
        get DUMMY long
```
can be substituited with:

```
    if SIGN == "E"  # EMD, EVP, EVT, ED1 and so on
```
because all these separators/subfolders start with 'E' avoiding problems with the EPK8 archives, you can do a comparison with the script 0.2.1a
## Post #43
- Username: JBP
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 29, 2009 3:54 pm
- Post datetime: 2009-11-29T17:37:03+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

I'd like to try and figure out the burning method for this a little better.  I think I read earlier that the game can read compressed and uncompressed data. If someone can explain in a little more detail about how to burn the game after the edits that would be great! For example let's say I edit John Cenas ch139.pac (I think that's his) when putting the newly edited files into the iso do I need to put everything in the ch folder, or do I need to put everything in a new folder inside the ch folder. Thanks in advance!

Also brienj have you got blender working yet?
## Post #44
- Username: NMCM
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Apr 15, 2009 2:02 pm
- Post datetime: 2009-11-30T03:02:17+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

I've read up on the subject in the smackdown vs raw 2010 .bpe again topic. I've downloaded the tools that were posted but am not too sure on how to use them. I tried opening the .bpe files that were extracted from my C2.PAC and DENT.PAC files with quickbms and unrrbpe but nothing happens. I would like to upload some files and have them tested if someone cares to help. I would really like to find something.

Edit:It works but I think I need someone to make a script compatible with SD!2. Someone please test this and tell me what happens.
Here's my Dent.PAC
[http://www.megaupload.com/?d=LPX86EPJ](http://www.megaupload.com/?d=LPX86EPJ)
## Post #45
- Username: JBP
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 29, 2009 3:54 pm
- Post datetime: 2009-11-30T09:49:54+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

Alright well adding a folder to the iso was harder than it sounds. Actually with modio and xbox backup creator I had zero luck. So I figure I'm not using the right program or something.....
## Post #46
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2009-11-30T14:33:01+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

> Reply from JBP
>
> I'd like to try and figure out the burning method for this a little better.  I think I read earlier that the game can read compressed and uncompressed data. If someone can explain in a little more detail about how to burn the game after the edits that would be great! For example let's say I edit John Cenas ch139.pac (I think that's his) when putting the newly edited files into the iso do I need to put everything in the ch folder, or do I need to put everything in a new folder inside the ch folder. Thanks in advance!

Also brienj have you got blender working yet?
Use Xbox Backup Creator v2.6 Build:0260 By Redline99 and open the game iso in the image browser.  Right click the file that needs replaced and then select replace.  Choose your replacement file and it will replace the old one.

No, I am so busy adding wrestlers from SvR2009 to the game, that I haven't had time to mess with that yet.
## Post #47
- Username: JBP
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 29, 2009 3:54 pm
- Post datetime: 2009-11-30T22:42:00+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

Awesome! I can't wait to see your progress.  I hope you share the wealth!
## Post #48
- Username: JBP
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 29, 2009 3:54 pm
- Post datetime: 2009-12-01T08:32:55+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

Alright well I've replaced single files a ton of times with Xbox backup creator but these uncompressed pacs are serveral files I'm trying to replace over one and it won't let me do that, nor will it let me replace a file with a folder.
## Post #49
- Username: The Red Rooster
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Dec 01, 2009 11:30 am
- Post datetime: 2009-12-02T09:34:57+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

Is there any way to recompress a .pac file after it has been extracted using quickbms?
I have tried using winrar to compress it and changing the extension to .pac but it causes the game to freeze.
## Post #50
- Username: noneedforun
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu May 14, 2009 5:42 am
- Post datetime: 2009-12-02T16:20:58+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

the script works quite nicely, thnx   . all files seem to work uncompressed. however, ive ran into tga textures that only work when bpe compressed. uncompressed, they are 8bpp indexed images with alpha mapping. i ran both the same ingame textures, compressed and uncompressed, to test if the uncompressed version would work and it doesn't. it isn't a matter of the textures size since the system seems to look for the textures consecutively, ignoring the actual texture size within the individual pac just as long as each pac is the right size. is there a way to reverse the process and compress these particular files into the yuke_bpe format to be made legible by the system again. ive attached both the compressed and uncompressed files for convenience. much appreciated. thanks.
[03F2.zip](https://xentaxbackup.github.io/file/2585_03F2.zip)
## Post #51
- Username: JBP
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 29, 2009 3:54 pm
- Post datetime: 2009-12-03T01:47:11+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

> Reply from The Red Rooster
>
> Is there any way to recompress a .pac file after it has been extracted using quickbms?
I have tried using winrar to compress it and changing the extension to .pac but it causes the game to freeze.

Wondering this as well.
## Post #52
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2009-12-03T09:58:53+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

The contents of this post was deleted because of possible forum rules violation.
## Post #53
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2009-12-04T19:09:25+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

Hi Guys,

I was wondering if anybody knows where the  bella twins models might be located?
According to the titantron movies there should be a ch421.pac file, but I cannot find this one.

It appears that all 7 twin character model .pacs are missing, which I believe should be:
ch400.pac
ch401.pac
ch404.pac
ch409.pac
ch412.pac
ch414.pac
ch421.pac

Just wondering if anyone knows why and how to fix this?
## Post #54
- Username: The Red Rooster
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Dec 01, 2009 11:30 am
- Post datetime: 2009-12-05T00:44:26+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

> Reply from toonhound
>
> Hi Guys,

I was wondering if anybody knows where the  bella twins models might be located?
According to the titantron movies there should be a ch421.pac file, but I cannot find this one.

It appears that all 7 twin character model .pacs are missing, which I believe should be:
ch400.pac
ch401.pac
ch404.pac
ch409.pac
ch412.pac
ch414.pac
ch421.pac

Just wondering if anyone knows why and how to fix this?
The Bella Twins are ch294.pac and ch295.pac
## Post #55
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2009-12-05T12:20:08+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

> Reply from The Red Rooster
>
> toonhound wrote:Hi Guys,

I was wondering if anybody knows where the  bella twins models might be located?
According to the titantron movies there should be a ch421.pac file, but I cannot find this one.

It appears that all 7 twin character model .pacs are missing, which I believe should be:
ch400.pac
ch401.pac
ch404.pac
ch409.pac
ch412.pac
ch414.pac
ch421.pac

Just wondering if anyone knows why and how to fix this?
The Bella Twins are ch294.pac and ch295.pac

Thanks for the info!

I see now that it's the videos I'm missing and not the models.
## Post #56
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2009-12-05T12:35:07+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

> Reply from toonhound
>
> Hi Guys,

I was wondering if anybody knows where the  bella twins models might be located?
According to the titantron movies there should be a ch421.pac file, but I cannot find this one.

It appears that all 7 twin character model .pacs are missing, which I believe should be:
ch400.pac
ch401.pac
ch404.pac
ch409.pac
ch412.pac
ch414.pac
ch421.pac

Just wondering if anyone knows why and how to fix this?
If you want the number assigned to each wrestler and how to find it, read my tutorial.
[viewtopic.php?f=29&t=3926](http://forum.xentax.com/viewtopic.php?f=29&t=3926)
## Post #57
- Username: locakert22
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Mar 28, 2011 9:47 pm
- Post datetime: 2011-04-30T08:42:59+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

The contents of this post was deleted because of possible forum rules violation.
## Post #58
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2011-04-30T20:20:58+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

The contents of this post was deleted because of possible forum rules violation.
## Post #59
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2011-05-23T13:14:55+00:00
- Post Title: Re: Smackdown vs Raw 2010 - bpe again

check out my blog for tools and tutorials on how to inject uncompressed data back into the game.
