## Post #1
- Username: SEFlasher
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jun 20, 2011 6:04 pm
- Post datetime: 2011-06-20T10:17:40+00:00
- Post Title: Submarine Titans (*.DKD, *.DKX)

Could you please look at the *.dkd and *.dkx archives from Submarine Titans - They contain the music, sounds, scripts and textures. Along with the game comes audio files importer. I think it will be easy to make the archives extractor.
[sounds.zip](https://xentaxbackup.github.io/file/4363_sounds.zip)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-06-20T13:10:30+00:00
- Post Title: Submarine Titans (*.DKD, *.DKX)

it has been a pain but I had success, script for quickbms:

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

open FDDE "DKX"
open FDDE "DKD" 1
math NEXT_OFF = 0x20
callfunction EXTRACT

startfunction EXTRACT
    savepos CURR_OFF
    goto NEXT_OFF
    get PREV_OFF long
    get NEXT_XOFF long
    get XSIZE short
    get XTYPE short
    get DUMMY long
    savepos TMPL
    math TMPL += XSIZE
    savepos TMP
    for TMP = TMP < TMPL
        get NEXT_OFF long
        get OFFSET long
        get TYPE byte
        get SIZE long
        get ZIP byte
        get ZSIZE long
        get DUMMY long
        get DATE longlong
        get NAMESZ short
        getdstring NAME NAMESZ
        savepos TMP

        if ZIP == 0
            log NAME OFFSET SIZE 1
        else
            clog NAME OFFSET ZSIZE SIZE 1
        endif

        if OFFSET != 0xffffffff
        if NEXT_OFF != 0xffffffff
        if CURR_OFF != NEXT_OFF
            callfunction EXTRACT
        endif
        endif
        endif
    next
    math NEXT_OFF = NEXT_XOFF
    if NEXT_OFF != 0xffffffff
            callfunction EXTRACT
    endif
    goto CURR_OFF
endfunction

```
*edit* fixed
## Post #3
- Username: SEFlasher
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jun 20, 2011 6:04 pm
- Post datetime: 2011-06-20T15:13:22+00:00
- Post Title: Submarine Titans (*.DKD, *.DKX)

Thanks, but it does not work. Creates an empty file with no extension "sirs_001".

> 01291b10 42054      sirs_001
>
> Error: incomplete input file number 0, can't read 42054 bytes.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-06-20T16:44:26+00:00
- Post Title: Submarine Titans (*.DKD, *.DKX)

ops, shame on me, I forgot an important thing.
recheck my previous post, now the script is fixed
## Post #5
- Username: SEFlasher
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jun 20, 2011 6:04 pm
- Post datetime: 2011-06-21T02:25:41+00:00
- Post Title: Submarine Titans (*.DKD, *.DKX)

Archive is unpacked, but the files are not readable. I think they are encrypted. Can you decrypt this file, please? 
[GM_PEACE300.zip](https://xentaxbackup.github.io/file/4364_GM_PEACE300.zip)
## Post #6
- Username: Priboi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Aug 04, 2015 12:11 am
- Post datetime: 2015-08-03T16:24:46+00:00
- Post Title: Submarine Titans (*.DKD, *.DKX)

Refresh this topic...
I have got the same problem as SEFlasher unpacked dkd and dkx are not readable... Maybe something is wrong with unpacker?? or like SEFlasher said unpacked files are encrypted. Can you help me guys? I noticed the game is written in C++ and I want to look inside the source code. It is game ancient conquest not submarine titans but extensions of files are same.

here one of dkd and dkx file [http://www.speedyshare.com/RP8JH/DATA.rar](http://www.speedyshare.com/RP8JH/DATA.rar)
## Post #7
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2016-03-22T14:53:31+00:00
- Post Title: Submarine Titans (*.DKD, *.DKX)

What I can see unpacker is working fine apart from inter.dkd/dkx, there are however some files with duplicate names.

I managed to work out how to get game's background artwork viewable (its uncompressed) but actual ingame sprite format has totally left me clueless as presumably some kinda compress(?)

Would need some guy to decompile the game executable to figure out the formats as they've been stripped to basics.
## Post #8
- Username: Priboi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Aug 04, 2015 12:11 am
- Post datetime: 2016-04-25T19:33:17+00:00
- Post Title: Submarine Titans (*.DKD, *.DKX)

Thank you for trying help me but things you are talking about overwhelming me. I just starting with RE and I made only noCD crack for Ancient Conquest. Is some person on this forum which is able to help me??
