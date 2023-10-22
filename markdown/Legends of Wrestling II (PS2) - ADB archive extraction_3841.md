## Post #1
- Username: Metalitia
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Oct 03, 2007 1:25 am
- Post datetime: 2009-11-05T21:21:30+00:00
- Post Title: Legends of Wrestling II (PS2) - ADB archive extraction?

There are quite a few of these, and they contain all the sound for the game (the largest, at ~540 MB, contains the entrance music). All are labeled "sounds.adb" and are in subfolders of the "Audio" directory.

Opening one in Hex Workshop reveals that the sounds within are all VAG format.
Scanning these in CubeMedia results in the sounds within being read as "ADPCM RAW Compressed", and trying to listen to them sounds absolutely terrible.

Main Question: How do I extract the proper files from the ADB archives?
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-11-05T21:57:44+00:00
- Post Title: Legends of Wrestling II (PS2) - ADB archive extraction?

please read the rules you must post a sample to ask for help
## Post #3
- Username: Metalitia
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Oct 03, 2007 1:25 am
- Post datetime: 2009-11-10T17:44:39+00:00
- Post Title: Legends of Wrestling II (PS2) - ADB archive extraction?

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-10T18:33:55+00:00
- Post Title: Legends of Wrestling II (PS2) - ADB archive extraction?

that file is a sequence of VAG audio files (ps/ps2 audio).
I guess exists an index file somewhere there anyway no problem, the following quickbms script can do the extraction job of all the files contained in this adb archive:

```
get MAXSIZE asize
set OFFSET long 0
for i = 0
    getdstring SIGN 3
    if SIGN == "VAG"
        getdstring DUMMY 9
        get SIZE long
        math SIZE += 48
    elif SIGN == "AAA"
        getdstring DUMMY 17
        get SIZE long
        math SIZE *= 2
        math SIZE += 40
    else
        print "unknown type of audio file %SIGN%"
        cleanexit
    endif
    set NAME long i
    string NAME += "."
    string NAME += SIGN
    log NAME OFFSET SIZE
    math OFFSET += SIZE
    if OFFSET >= MAXSIZE
        cleanexit
    endif
    goto OFFSET
next i
```
## Post #5
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2009-11-10T19:33:55+00:00
- Post Title: Legends of Wrestling II (PS2) - ADB archive extraction?

The AAAp block probably contains 2 sounds, not just one.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-10T21:18:50+00:00
- Post Title: Legends of Wrestling II (PS2) - ADB archive extraction?

in any case AAA is one file so it's all correct.
the fact that it acts as a stereo VAG is related to the internal structure of the AAA file and not of the ADB archive.

I guess that hcs would like to add support for AAA to vgmstream :)
## Post #7
- Username: Metalitia
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Oct 03, 2007 1:25 am
- Post datetime: 2009-11-16T06:56:55+00:00
- Post Title: Legends of Wrestling II (PS2) - ADB archive extraction?

> Reply from aluigi
>
> that file is a sequence of VAG audio files (ps/ps2 audio).
I guess exists an index file somewhere there anyway no problem, the following quickbms script can do the extraction job of all the files contained in this adb archive:
Code: Select allbunch of code

I'm rather new to the whole "running script" portion of game file navigation. Do I compile it in something? Insert it into some sort of "create script function" area of an existing one?     

Very helpful, though; and I intend on extracting the themes this way (hopefully correctly)...whatever this way actually is.

EDIT: Never mind, I just saw QuickBMS over there in the other area. So I just enter that code into it and then run the ADB archive through it?
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-16T11:23:30+00:00
- Post Title: Legends of Wrestling II (PS2) - ADB archive extraction?

it's simple:
- copy that code in a text file, for example adb.bms
- download quickbms: [http://aluigi.org/papers.htm#quickbms](http://aluigi.org/papers.htm#quickbms)
- double click on quickbms.exe
- select adb.bms
- select your adb file
- select the folder where you want to extract the files
- ...extraction in progress...
simple :)
## Post #9
- Username: Metalitia
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Oct 03, 2007 1:25 am
- Post datetime: 2009-11-17T18:00:13+00:00
- Post Title: Legends of Wrestling II (PS2) - ADB archive extraction?

Success!

ENTRANCE/SOUNDS.ADB was successfully extracted from, and there are a bunch of AAA files and VAG files. The VAG files appear to be the Announcer Calls (the names you can pick from in the Create-A-Legend) and the AAA files are the musics, compressed ADPCM.
New topic on the resulting files here: [viewtopic.php?f=17&t=3877](http://forum.xentax.com/viewtopic.php?f=17&t=3877)
## Post #10
- Username: godzfire
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jun 02, 2014 10:21 am
- Post datetime: 2014-06-04T07:23:30+00:00
- Post Title: Legends of Wrestling II (PS2) - ADB archive extraction?

Hello, sorry to bump an old topic, however I am actually trying to extract the exact same thing, the ADB archives. It does work, however the resulting AAA and VAG files don't play on vgastream or any other audio player I throw them at. I think I must have done something wrong.

I've uploaded the adb files [HERE](https://mega.co.nz/#!M9wlyaKL!vPqhmLZTgPd6oi9y-NJr_faF0_9ivfY7jjg77fBZ4nQ). Would someone be nice enough to take a look and see if they can get them extracted properly?

EDIT: Here's one of the AAA files it churned out that doesn't open: [https://mega.co.nz/#!8kpVnC7Y!qAm0aOiVT ... LvTw3ilMe4](https://mega.co.nz/#!8kpVnC7Y!qAm0aOiVTJo8UW_M3gBEjvXqohG1QOtkmLvTw3ilMe4)
