## Post #1
- Username: scorpionking674
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Dec 18, 2017 9:26 am
- Post datetime: 2017-12-18T05:32:45+00:00
- Post Title: Rules of Survival [PC]

Hello, i am trying to unpack some files of this game. I dont know how to extract it or do anything with it.

[https://g61.gdl.netease.com/ros_setup_117485.exe](https://g61.gdl.netease.com/ros_setup_117485.exe)

npk file link: [https://drive.google.com/open?id=1X8ft- ... 9NiUEkDNJr](https://drive.google.com/open?id=1X8ft-CQb0ug6Owb3ajf4DM9NiUEkDNJr)


i tried unpacking with some bms scripts online and it extracted alot of .dat files. I dont know what or how to open or mod them. please also mention the software names i can use to open the files.

this is the script i used to unpack the .npk files:

```
# script for QuickBMS http://quickbms.aluigi.org

idstring "NXPK"
get FILES long
get OFFSET asize
xmath OFFSET "OFFSET - (FILES * 0x1c)"
goto OFFSET
for i = 0 < FILES
    get NAME_CRC long
    get OFFSET long
    get ZSIZE long
    get SIZE long
    get ZCRC long
    get CRC long
    get FLAGS long
    if FLAGS == 2
        comtype lz4
    else    # 0
        comtype zlib
    endif
    if SIZE == ZSIZE
        log "" OFFSET SIZE
    else
        clog "" OFFSET ZSIZE SIZE
    endif
next i   
```
## Post #2
- Username: barumbads
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun May 14, 2017 2:05 pm
- Post datetime: 2018-08-25T02:43:33+00:00
- Post Title: Rules of Survival [PC]

> Reply from scorpionking674
>
> Hello, i am trying to unpack some files of this game. I dont know how to extract it or do anything with it.

https://g61.gdl.netease.com/ros_setup_117485.exe

npk file link: https://drive.google.com/open?id=1X8ft- ... 9NiUEkDNJr


i tried unpacking with some bms scripts online and it extracted alot of .dat files. I dont know what or how to open or mod them. please also mention the software names i can use to open the files.

this is the script i used to unpack the .npk files:
Code: Select all# NXPK (script 0.1.1)
# script for QuickBMS http://quickbms.aluigi.org

idstring "NXPK"
get FILES long
get OFFSET asize
xmath OFFSET "OFFSET - (FILES * 0x1c)"
goto OFFSET
for i = 0 < FILES
    get NAME_CRC long
    get OFFSET long
    get ZSIZE long
    get SIZE long
    get ZCRC long
    get CRC long
    get FLAGS long
    if FLAGS == 2
        comtype lz4
    else    # 0
        comtype zlib
    endif
    if SIZE == ZSIZE
        log "" OFFSET SIZE
    else
        clog "" OFFSET ZSIZE SIZE
    endif
next i

what npk did you extracted? i think some of the .dat files are images and model files so you cant read it
some are just simple table/text files ? anyway, do you have any idea how to repack it(i success fully modded mine but donno how to repack it)?
## Post #3
- Username: melanin
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Nov 19, 2018 12:07 am
- Post datetime: 2018-11-18T16:09:12+00:00
- Post Title: Rules of Survival [PC]

I don't know but many people use cheat for rule of survival games and the main culprit is [https://www.exiledros.me/](https://www.exiledros.me/)
