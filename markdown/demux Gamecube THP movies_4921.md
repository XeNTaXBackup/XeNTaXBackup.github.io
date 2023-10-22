## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-08-24T10:00:12+00:00
- Post Title: demux Gamecube THP movies

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: vovmen
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Oct 09, 2010 3:12 pm
- Post datetime: 2010-10-09T15:19:17+00:00
- Post Title: demux Gamecube THP movies

Script for restoration *.JPEG from *.THP
1. Before script start, in WinHex clean a daw with "Prompt before executing scripts" (Options-> Security).
2. In a place where lies *.THP a file, create a folder "JPEG".
3. To start a script - the conductor window will open - specify arrangement THP-file.
[http://ifolder.ru/19684618](http://ifolder.ru/19684618)
## Post #3
- Username: bxaimc
- Rank: advanced
- Number of posts: 78
- Joined date: Mon May 10, 2010 3:54 am
- Post datetime: 2010-10-09T15:21:44+00:00
- Post Title: demux Gamecube THP movies

Here's the [THP Audio Ripper](http://hcs64.com/files/thp_audio_ripper.zip) we've been using for years thanks to FastElbJa
## Post #4
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-10-09T15:43:44+00:00
- Post Title: demux Gamecube THP movies

> Reply from bxaimc
>
> Here's the THP Audio Ripper we've been using for years thanks to FastElbJa
Oh, ehem, didn't notice that existed.  Thanks!
## Post #5
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-10-09T16:00:29+00:00
- Post Title: demux Gamecube THP movies

Guess what, it doesn't work on my uploaded file in the first post! Or is that a problem of vgmstream? Anyway, you should hae a look into this!
## Post #6
- Username: bxaimc
- Rank: advanced
- Number of posts: 78
- Joined date: Mon May 10, 2010 3:54 am
- Post datetime: 2010-10-10T15:35:07+00:00
- Post Title: demux Gamecube THP movies

Or it could Just be that the developers screwed up the THP format on this game.
## Post #7
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-10-11T07:18:02+00:00
- Post Title: demux Gamecube THP movies

> Reply from bxaimc
>
> Or it could Just be that the developers screwed up the THP format on this game.
Well, I can play the movie with correct audio with thpplayer, so maybe it's just a variant. Who has written the thp_ripper?
## Post #8
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-10-14T20:52:59+00:00
- Post Title: demux Gamecube THP movies

The contents of this post was deleted because of possible forum rules violation.
## Post #9
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-10-14T22:42:03+00:00
- Post Title: demux Gamecube THP movies

I've tested the thp_ripper on several Gamecube games now and it just doesn't work!

Now, I've coded an THP audio extractor (leave out the comments to get a demuxer). The resulting *.aud files seem to have a 0x40 byte header with the decode coefficients at 0x8-0x47 (compact dual decode?). However I still don't know how to construct a valid header out of this. Can anyone please help? HSC maybe? Thanks in advance! 

```
get FSIZE asize
goto 0x30
get SIGN long
if SIGN == 1
    print "No audio present. Aborting..."
    cleanexit
endif
set OFFSET 0x60
log MEMORY_FILE 0 0 
log MEMORY_FILE2 0 0

append
for
    goto OFFSET
    get VIDSIZE long
    get AUDSIZE long
    savepos OFFSET
    #log MEMORY_FILE OFFSET VIDSIZE
    math OFFSET += VIDSIZE
    log MEMORY_FILE2 OFFSET AUDSIZE
    math OFFSET += AUDSIZE
    goto OFFSET
    DO # workaround to find next tuple
        get ZERO long
        savepos TEST
        if TEST == FSIZE
            set QUIT 1
            break
        endif
    WHILE ZERO == 0
    if QUIT == 1
        break
    endif
    savepos OFFSET
    math OFFSET += 4
next
append

#get NAME basename
#string NAME += ".vid"
#get SIZE asize MEMORY_FILE
#log NAME 0 SIZE MEMORY_FILE

get NAME basename
string NAME += ".aud"
get SIZE asize MEMORY_FILE2
log NAME 0 SIZE MEMORY_FILE2

```
## Post #10
- Username: snakemeat
- Rank: advanced
- Number of posts: 45
- Joined date: Wed Jan 28, 2009 12:00 am
- Post datetime: 2011-06-12T16:05:00+00:00
- Post Title: demux Gamecube THP movies

Just wanted to add that the latest version of [VGMToolbox](http://sourceforge.net/projects/vgmtoolbox/), r835, can now demux THP files (including the sample from the first post).
## Post #11
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2011-07-05T22:20:59+00:00
- Post Title: demux Gamecube THP movies

checked it and MAN AM I RELIEVED!!! thanks for this wonderful info!!!
