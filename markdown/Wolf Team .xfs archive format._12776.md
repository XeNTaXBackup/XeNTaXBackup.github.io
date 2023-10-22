## Post #1
- Username: napoleon321
- Rank: advanced
- Number of posts: 60
- Joined date: Tue Nov 16, 2010 7:11 pm
- Post datetime: 2015-04-17T06:51:40+00:00
- Post Title: Wolf Team *.xfs archive format.

Hello, I wonder have anyone of you skilled reverse engineers  checked the archive file format of the game called Wolf Team ([http://wolfteam.aeriagames.com/](http://wolfteam.aeriagames.com/)). The file format is .xfs, and so far i haven't seen anyone extracting it. I wonder can someone take a look at it? (and maybe write one of your those bms scripts?) The main archive file however is 2.2gb,(no worries, i have uploaded it on dropbox) also i have  cut a piece of it with hex editor.
here's samle of the xfs file format:

[http://www.mediafire.com/download/xp2xl ... /sound.xfs](http://www.mediafire.com/download/xp2xll6idpkp6jl/sound.xfs)   (70 Mb)

[http://www.mediafire.com/download/z6p98 ... m_wolf.xfs](http://www.mediafire.com/download/z6p98w8i1qfii96/sample_cut_from_wolf.xfs)  (113 Mb)

and here's the 2,2 Gb file...

[https://www.dropbox.com/s/znsyg9s5ys7tsw4/wolf.xfs?dl=0](https://www.dropbox.com/s/znsyg9s5ys7tsw4/wolf.xfs?dl=0)

I hope someone can figure out this format

Thanks for your time and understanding.
## Post #2
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-04-17T12:50:48+00:00
- Post Title: Wolf Team *.xfs archive format.

It's just chunks of zlib compressed data. offzip worked on it pretty well. It's odd that there's no file table info, perhaps it's stored in another file.
## Post #3
- Username: napoleon321
- Rank: advanced
- Number of posts: 60
- Joined date: Tue Nov 16, 2010 7:11 pm
- Post datetime: 2015-04-18T19:31:31+00:00
- Post Title: Wolf Team *.xfs archive format.

I checked offzip.. but it extracts tones of 64kb files.. that's are in no use to me... I'm sure they are not supposed to be in this form.. maybe something is wrong...
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2015-04-18T21:22:13+00:00
- Post Title: Wolf Team *.xfs archive format.

use the -1 option to merge them.
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2015-04-19T09:06:39+00:00
- Post Title: Wolf Team *.xfs archive format.

[https://www.youtube.com/watch?v=ZBq29FJ ... GrVNJ2kS2f](https://www.youtube.com/watch?v=ZBq29FJEUJE&index=1&list=PLP26ZYnLb5EVqqBHDgltL6oGrVNJ2kS2f)

Some more details in this Let's MultiEx
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2015-04-19T14:12:39+00:00
- Post Title: Wolf Team *.xfs archive format.

very annoying archive format.
Its recursive that is what those numbers are before the folder names.
Root
----am_br_dist_thun.wav
----br_rain.wav
----wt_snd
--------interface
------------chat_message.wav
------------msg_no_die_blue.wav
------------msg_round_exbase_red_start.wav
------------msg_round_first_kill.wav
------------popup_window_close.wav
------------box_animation.wav

so the path for box_animation.wav would be
Root\wt_snd\interface\box_animation.wav
## Post #7
- Username: napoleon321
- Rank: advanced
- Number of posts: 60
- Joined date: Tue Nov 16, 2010 7:11 pm
- Post datetime: 2015-04-21T20:07:44+00:00
- Post Title: Wolf Team *.xfs archive format.

Hello, I'm sorry for bumping the topic, but do you have any new development on the archive format? I'm not trying to rush you, I'm just hoping to see something new about it. 
Thank you for your time and understanding.
## Post #8
- Username: napoleon321
- Rank: advanced
- Number of posts: 60
- Joined date: Tue Nov 16, 2010 7:11 pm
- Post datetime: 2015-04-28T19:40:46+00:00
- Post Title: Wolf Team *.xfs archive format.

Really big thanks to Luigi Auriemma, who wrote a bms scrip for the archive type after I have sent him the samples. 

[http://aluigi.altervista.org/papers/bms/xenesis.bms](http://aluigi.altervista.org/papers/bms/xenesis.bms)

Thanks again!
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2015-04-28T20:26:45+00:00
- Post Title: Wolf Team *.xfs archive format.

Nice work. 

Here it is also:

```
"# Xenesis File System
#   Wolf Team and maybe other AeriaGames titles
#
#   The archives are incrementally updated after every
#   patch and the new file table is appended at the end,
#   that's the reason why the total amount of extracted
#   files is minor than the original (big) archive size.
# script for QuickBMS http://quickbms.aluigi.org

get OFFSET long
# XFS2 uses a 32bit offset instead of 48 bit one so let's use a work-around to guess it
get TMP asize
if TMP u> 0xffffffff
    get OFFSET48 short 
    xmath OFFSET "OFFSET | (OFFSET48 << 32)"
endif
goto OFFSET
get ZSIZE byte
savepos OFFSET
clog MEMORY_FILE OFFSET ZSIZE 0x40

idstring MEMORY_FILE "XFS"
get XFS_VERSION byte MEMORY_FILE
get DUMMY long MEMORY_FILE
get ENTRIES long MEMORY_FILE
get ZERO long MEMORY_FILE
get XFS_OFFSET long MEMORY_FILE

math OFFSET + ZSIZE
goto OFFSET
if XFS_VERSION == ' '
    get INFO_SIZE threebyte
    get INFO_ZSIZE threebyte
else
    get INFO_ZSIZE threebyte
    xmath INFO_SIZE "ENTRIES * 0x80"
endif
savepos OFFSET
clog MEMORY_FILE OFFSET INFO_ZSIZE INFO_SIZE

if XFS_VERSION == ' '
    set PATH string ""
    set NAME string ""
    callfunction EXTRACT

elif XFS_VERSION == '2'
    for INFO_OFF = 0 < INFO_SIZE
        getdstring NAME 0x70 MEMORY_FILE
        get OFFSET long MEMORY_FILE
        get DUMMY long MEMORY_FILE  # 1
        get SIZE long MEMORY_FILE
        get ZSIZE long MEMORY_FILE
        savepos INFO_OFF MEMORY_FILE
        callfunction EXTRACT_FILE 1
    next

else
    print "Error: unknown XFS version %XFS_VERSION%"
    cleanexit
endif



startfunction EXTRACT
    string PATH + NAME
    string PATH + /
    get ENTRIES long MEMORY_FILE
    get NAMESZ byte MEMORY_FILE
    getdstring NAME NAMESZ MEMORY_FILE
    get OFFSET long MEMORY_FILE
    get OFFSET48 short MEMORY_FILE
    xmath OFFSET "OFFSET | (OFFSET48 << 32)"
    get SIZE long MEMORY_FILE
    get ZSIZE long MEMORY_FILE
    get IS_FILE byte MEMORY_FILE

    if IS_FILE != 0
        string NAME p "%s%s" PATH NAME
        callfunction EXTRACT_FILE 1
    endif

    for i = 0 < ENTRIES
        callfunction EXTRACT
    next i
endfunction



startfunction EXTRACT_FILE
    xmath END_OFFSET "OFFSET + ZSIZE"
    putvarchr MEMORY_FILE2 SIZE 0
    log MEMORY_FILE2 0 0
    append
    for OFFSET = OFFSET != END_OFFSET
        goto OFFSET
        get CHUNK_SIZE threebyte
        xmath FLAGS "CHUNK_SIZE >> 22"
        math CHUNK_SIZE & 0x3fffff

        if FLAGS & 2
            if FLAGS & 1
            else
                get CHUNK_ZSIZE threebyte
            endif
        endif
        if FLAGS == 0
            math CHUNK_ZSIZE = CHUNK_SIZE
            math CHUNK_SIZE = 0x10000
        endif
        get DUMMY short
        savepos OFFSET

        if FLAGS & 1
            log MEMORY_FILE2 OFFSET CHUNK_SIZE
            math OFFSET + CHUNK_SIZE
        else
            clog MEMORY_FILE2 OFFSET CHUNK_ZSIZE CHUNK_SIZE
            math OFFSET + CHUNK_ZSIZE
        endif
    next
    append
    log NAME 0 SIZE MEMORY_FILE2
endfunction
```
