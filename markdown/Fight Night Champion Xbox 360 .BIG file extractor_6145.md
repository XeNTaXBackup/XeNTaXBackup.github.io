## Post #1
- Username: invasion101
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Oct 13, 2010 1:46 am
- Post datetime: 2011-02-27T03:20:20+00:00
- Post Title: Fight Night Champion Xbox 360 .BIG file extractor

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-02-27T16:10:37+00:00
- Post Title: Fight Night Champion Xbox 360 .BIG file extractor

the following script for quickbms should work correctly with all the archives, if you have problems with one of them just upload it and I will check it:

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

comtype xmemdecompress
endian big
get DUMMY short
if DUMMY != 0x4542
    print "the archive doesn't seem a supported BIG one, I try to continue"
endif
get DUMMY short
get FILES long
get DUMMY long
get NAME_OFF long
get NAME_SIZE long
goto 0x30
log MEMORY_FILE NAME_OFF NAME_SIZE
math FOLDER_OFF = FILES
math FOLDER_OFF *= 0x1e
math FOLDER_OFF += NAME_OFF
math FOLDER_OFF x= 0x10
math FOLDER_SIZE = NAME_OFF
math FOLDER_SIZE += NAME_SIZE
math FOLDER_SIZE -= FOLDER_OFF
log MEMORY_FILE2 FOLDER_OFF FOLDER_SIZE

for i = 0 < FILES
    get OFFSET long
    get DUMMY long
    get SIZE long
    get CRC long
    get FOLDER short MEMORY_FILE
    getdstring NAME 0x1c MEMORY_FILE
    math OFFSET *= 0x10

    math LZX = 0
    if SIZE > 8
        savepos TMP
        goto OFFSET
        getdstring SIGN 8
        if SIGN == "chunklzx"
            math LZX = 1
        endif
        goto TMP
    endif
    if LZX == 0
        log NAME OFFSET SIZE
    else
        callfunction UNPACK
    endif
next i

startfunction UNPACK
    savepos TMP
    goto OFFSET
    idstring "chunklzx"
    get DUMMY long
    get FULLSIZE long
    get SIZE long
    get CHUNKS long
    get DUMMY long
    get DUMMY long
    get DUMMY long
    get DUMMY long
    log MEMORY_FILE3 0 0
    append
    savepos OFFSET
    for j = 0 < CHUNKS
        math OFFSET x= 0x8
        for # very lame, made on the fly
            math T = OFFSET
            math T %= 0x10
            if T == 8
                break
            endif
            math OFFSET += 8
        next
        goto OFFSET

        get ZSIZE long
        get DUMMY long
        savepos OFFSET
        clog MEMORY_FILE3 OFFSET ZSIZE SIZE
        math OFFSET += ZSIZE
    next j
    append
    get MYSIZE asize MEMORY_FILE3
    if MYSIZE != FULLSIZE
        print "Alert: MEMORY_FILE3 %MYSIZE% != %FULLSIZE%"
    endif
    log NAME 0 FULLSIZE MEMORY_FILE3
    goto TMP
endfunction
```
## Post #3
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2011-02-27T16:23:05+00:00
- Post Title: Fight Night Champion Xbox 360 .BIG file extractor

Thanks, I will try this!
## Post #4
- Username: invasion101
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Oct 13, 2010 1:46 am
- Post datetime: 2011-02-28T02:51:06+00:00
- Post Title: Fight Night Champion Xbox 360 .BIG file extractor

thanks so much aluigi. thanks so much, but when i try to extract the file it says "Error: operation x" in quickbms? u know what that means? what am i doing wrong?
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-02-28T02:57:21+00:00
- Post Title: Fight Night Champion Xbox 360 .BIG file extractor

update to the newest version of quickbms your version is to old
## Post #6
- Username: invasion101
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Oct 13, 2010 1:46 am
- Post datetime: 2011-02-28T03:01:53+00:00
- Post Title: Fight Night Champion Xbox 360 .BIG file extractor

i got it thanks guys so much!
## Post #7
- Username: invasion101
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Oct 13, 2010 1:46 am
- Post datetime: 2011-02-28T03:34:01+00:00
- Post Title: Fight Night Champion Xbox 360 .BIG file extractor

im tryin to get the Soundtrack out of the game.... and in the folder "music" there is a file .SBS i dont know what this file is but EA games created this file... is there any way to extract it il upload it its kinda big
## Post #8
- Username: ace513
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Mar 15, 2011 12:03 am
- Post datetime: 2011-03-14T16:08:33+00:00
- Post Title: Fight Night Champion Xbox 360 .BIG file extractor

Thanks for the info on how to extract the BIg from fight night champion.

My question is once you done the extraction using quickBSM and you make changes in the file, how do you then extract them back or join them back like they where before. Will this work with another quick bsm script if so could you post it on here Thanks in advanced.

Vip3r
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-14T16:33:42+00:00
- Post Title: Fight Night Champion Xbox 360 .BIG file extractor

quickbms supports the reinjection of files but unfortunately this particular game uses files divided in chunks and so there is nothing to do easily
## Post #10
- Username: ace513
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Mar 15, 2011 12:03 am
- Post datetime: 2011-03-14T17:13:52+00:00
- Post Title: Fight Night Champion Xbox 360 .BIG file extractor

Oh ok i see well thanks for your help aluigi.

I think i am better of looking for a way round in the xex file.

Thank you dude.

Vip3r
## Post #11
- Username: d2rnattakorn
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Mar 19, 2010 9:18 pm
- Post datetime: 2011-04-04T16:58:31+00:00
- Post Title: Fight Night Champion Xbox 360 .BIG file extractor

Hi everyone, I need help on extracting the character file thank.

I use the quickbms script as posted in here, on the ge_char.big file.
At the quickbms extract, its extract file up to 42 fils and its ask me: "the file "pr" already exists do you want to overwrite it <y/N/all>?"
But after Yes or No or All its make quickbms error and close its self.
I am using the newest version of quickbms (0.4.1) please help.

Also with the 42 files that I have extract, .XPR, .RSF, .CHSF, .GEO, .GEOM and .x
I use ea_multi_xma.exe on them with the offset of -o 0x10
but none of the file seen to be working with ea_multi_xma.exe.
The input that I use is "ea_multi_xma.exe ad_corner_skinhead_low_2.geo <-o 0x10>"
I don't know what I did wrong please help with this too.

Thank you.
## Post #12
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-04T23:06:01+00:00
- Post Title: Fight Night Champion Xbox 360 .BIG file extractor

the latest version of quickbms is 0.4.10b and not 0.4.1.

anyway try to upload one of these files that give problems and I will take a look at them
## Post #13
- Username: d2rnattakorn
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Mar 19, 2010 9:18 pm
- Post datetime: 2011-04-05T15:04:18+00:00
- Post Title: Fight Night Champion Xbox 360 .BIG file extractor

The contents of this post was deleted because of possible forum rules violation.
## Post #14
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-05T18:57:49+00:00
- Post Title: Fight Night Champion Xbox 360 .BIG file extractor

judging the names I see for sure a problem in the file format used in the bms script.
but I need the BIG file or at least the first 10 megabytes
## Post #15
- Username: d2rnattakorn
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Mar 19, 2010 9:18 pm
- Post datetime: 2011-04-10T17:08:17+00:00
- Post Title: Fight Night Champion Xbox 360 .BIG file extractor

Hi Aluigi, sorry I been away with work.
The ge_char.big file is 1.45 GB and I am don't know how to get the first 10 megabytes.
Can I use RAR to cut it into many parts and upload the first file which is 10 megabytes?
But then I think the RAR compression will change the code.

Do you know the way I can upload the first 10 megabytes?
Thank
## Post #16
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-11T14:51:28+00:00
- Post Title: Re: Fight Night Champion Xbox 360 .BIG file extractor

you can cut it with one of the following tools:
[http://wiki.xentax.com/index.php?title=Game_Requests](http://wiki.xentax.com/index.php?title=Game_Requests)
## Post #17
- Username: d2rnattakorn
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Mar 19, 2010 9:18 pm
- Post datetime: 2011-04-20T15:13:11+00:00
- Post Title: Re: Fight Night Champion Xbox 360 .BIG file extractor

The contents of this post was deleted because of possible forum rules violation.
## Post #18
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-20T19:27:19+00:00
- Post Title: Re: Fight Night Champion Xbox 360 .BIG file extractor

excellent I have not only fixed the problem but I have even implemented the usage of the folders that was missed in the previous version.
the link is ever the usual:
[http://aluigi.org/papers/bms/fightnight.bms](http://aluigi.org/papers/bms/fightnight.bms)

let me know if now it's all ok with all the files
## Post #19
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-09-13T16:39:09+00:00
- Post Title: Re: Fight Night Champion Xbox 360 .BIG file extractor

I have updated the script to support fifa12 (chunkzip):
[http://aluigi.org/papers/bms/chunklzx.bms](http://aluigi.org/papers/bms/chunklzx.bms)
## Post #20
- Username: manstopper
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Mar 01, 2011 6:09 am
- Post datetime: 2011-09-27T18:56:28+00:00
- Post Title: Re: Fight Night Champion Xbox 360 .BIG file extractor

> Reply from aluigi
>
> I have updated the script to support fifa12 (chunkzip):
http://aluigi.org/papers/bms/chunklzx.bms

Nice work! Is there a setting in quickbms, which would be forced to put the extracted file next to the original in a subfolder? Parameter . puts everything in a location quickbms.exe
## Post #21
- Username: Yuredacy2311
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Aug 31, 2011 8:36 am
- Post datetime: 2013-08-12T07:16:57+00:00
- Post Title: Re: Fight Night Champion Xbox 360 .BIG file extractor

Could anyone help me in extracting the 3d model of this game files?
 I have used aluigi bms to extract the ge_char.big, and i got many geom file, and textures as xpr.
 Here are the samples file  
[http://www.mediafire.com/?1bqd1wipoxz50y2](http://www.mediafire.com/?1bqd1wipoxz50y2)

 I really want to see the model of Isaac Frost, that was one of the hardest bosses in gaming universe.
 So really thanks to someone can spare some time for help me with this.
