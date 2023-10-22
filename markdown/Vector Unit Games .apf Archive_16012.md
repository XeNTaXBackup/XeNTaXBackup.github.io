## Post #1
- Username: PhillipGamer3264
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Aug 14, 2016 11:32 am
- Post datetime: 2017-03-17T19:58:19+00:00
- Post Title: Vector Unit Games .apf Archive

This a Vector Unit .apf Games, like Beach Buggy Racing/Biltz, Shine Runner and Riptide GP 1/2.
[http://www.mediafire.com/file/fk749dbxy ... ffiles.zip](http://www.mediafire.com/file/fk749dbxylx4t3a/apffiles.zip)

Here's BMS Script by ALuigi
[http://aluigi.org/bms/riptide_gp2.bms](http://aluigi.org/bms/riptide_gp2.bms)
## Post #2
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2017-03-18T03:02:23+00:00
- Post Title: Vector Unit Games .apf Archive

[http://zenhax.com/viewtopic.php?f=9&t=3979](http://zenhax.com/viewtopic.php?f=9&t=3979)
## Post #3
- Username: AdventureT
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Jun 22, 2019 2:46 pm
- Post datetime: 2021-03-02T13:19:39+00:00
- Post Title: Vector Unit Games .apf Archive

I have updated the script for version 7 of Vector Unit Games. I tested it on Beach Buggy Racing 2 on Steam. Here is the script:

idstring "FPUV"
get VER long    # 5
get OFFSET long
get FILES long
goto OFFSET
for i = 0 < FILES
    get NAME string
    get OFFSET long
    get SIZE long
    get ZSIZE long
    get CRC long
    get DUMMY short
    get ZIP short
    string NAME + .
    if ZIP == 0
        savepos TMP
        goto OFFSET
        get CHECK long
        goto TMP
        math CHECK + 4
        if CHECK == SIZE
            math OFFSET + 4
            math SIZE   - 4
        endif
        log NAME OFFSET SIZE
    else
        if ZIP == 1
            comtype zlib
        elif ZIP == 2
            comtype lzma
        elif ZIP == 3
            comtype snappy
        elif ZIP == 4
            comtype lz4
        elif ZIP == 5
            comtype lz4
        else
            print "Error: unknown compression algorithm %ZIP%, contact me"
            cleanexit
        endif
        clog NAME OFFSET ZSIZE SIZE
    endif
next i
## Post #4
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2021-07-15T07:52:10+00:00
- Post Title: Vector Unit Games .apf Archive

i have a problem, how do i extract the .dat files
## Post #5
- Username: harked
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Mar 22, 2021 4:03 am
- Post datetime: 2021-12-24T22:33:03+00:00
- Post Title: Vector Unit Games .apf Archive

I've also been having problems extracting the .dat files.

Probably nobody is going to find a way to do it, since all their games use an in-house engine, and the games are not that popular.
## Post #6
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2021-12-25T14:50:21+00:00
- Post Title: Vector Unit Games .apf Archive

> Reply from harked ↑Sat Dec 25, 2021 6:33 am at Sat Dec 25, 2021 6:33 am
>
> 
I've also been having problems extracting the .dat files.

Probably nobody is going to find a way to do it, since all their games use an in-house engine, and the games are not that popular.

i made a post about it, but there are some errors, textures can be converted to ktx2 but some or most are corrupted
## Post #7
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2021-12-25T17:29:19+00:00
- Post Title: Vector Unit Games .apf Archive

and when exporting the models from bbr2, everything is 1 material and some of the textures get messed up when you apply it to a mesh that has the proper uv
