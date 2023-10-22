## Post #1
- Username: SySTeL
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Aug 22, 2009 10:34 pm
- Post datetime: 2012-02-19T17:24:47+00:00
- Post Title: Prime World (zlib uncompress \ compress)

Hi.

Game: ru.playpw.com (Russian Dota)
Link on resource pack: [http://narod.ru/disk/41254771001/_data.pile.html](http://narod.ru/disk/41254771001/_data.pile.html) (400 mb  )

At me it has turned uncompress it.
1) i'm use offzip, but it unpacks without catalogs. And all names of files others =(
2) But me interests, how to pack files back?
3) Some resources are packed with the help sharpziplib, somebody can prompt than it is possible to unpack such archive?

Please help who can, I badly know programming 

And sorry me for my bad English.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-20T02:36:22+00:00
- Post Title: Prime World (zlib uncompress \ compress)

```
# script for QuickBMS http://quickbms.aluigi.org

idstring "Pile"
goto -0x18
idstring "Pile"
get DUMMY short
get DUMMY short
get FILES long
get NAMES_OFF long
get NAMES_SIZE long
log MEMORY_FILE NAMES_OFF NAMES_SIZE
get OFFSET long
goto OFFSET
for i = 0 < FILES
    get ZSIZE long
    get SIZE long
    get OFFSET long
    get ZIP long
    get NAME_OFF long
    get CRC long
    goto NAME_OFF MEMORY_FILE
    get NAME string MEMORY_FILE
    if ZIP == 0
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
next i
```
read section 3 of quickbms.txt for reinjecting the modified files back (size <= original size)
## Post #3
- Username: SySTeL
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Aug 22, 2009 10:34 pm
- Post datetime: 2012-02-20T11:03:53+00:00
- Post Title: Prime World (zlib uncompress \ compress)

> Reply from aluigi
>
> Code: Select all# Prime World
# script for QuickBMS http://quickbms.aluigi.org

idstring "Pile"
goto -0x18
idstring "Pile"
get DUMMY short
get DUMMY short
get FILES long
get NAMES_OFF long
get NAMES_SIZE long
log MEMORY_FILE NAMES_OFF NAMES_SIZE
get OFFSET long
goto OFFSET
for i = 0 < FILES
    get ZSIZE long
    get SIZE long
    get OFFSET long
    get ZIP long
    get NAME_OFF long
    get CRC long
    goto NAME_OFF MEMORY_FILE
    get NAME string MEMORY_FILE
    if ZIP == 0
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
next iread section 3 of quickbms.txt for reinjecting the modified files back (size <= original size)

Thanks! All its work! (During unpacking swears on identical names files, but it is a trifle)
All files uncompress.
But reimport not worked 
It is impossible to specify an imported folder, only a file 


In the client there is one more file with resources ( [http://narod.ru/disk/41327896001/resources.assets.html](http://narod.ru/disk/41327896001/resources.assets.html) )
But he compress sharpziplib, maybe you know how it to uncompress?
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-20T14:40:41+00:00
- Post Title: Prime World (zlib uncompress \ compress)

you must do the exact steps you did for the extraction, it's the job of quickbms to do the rest.

looking at your image seems you did it correctly but you specified an internal folder instead of the output one specified during the extraction.
so you must specify c:\1 and not c:\1\sub_folder\sub_folder
## Post #5
- Username: SySTeL
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Aug 22, 2009 10:34 pm
- Post datetime: 2012-02-20T19:13:52+00:00
- Post Title: Prime World (zlib uncompress \ compress)

i'm understand, but  quickbms don't select folder.
If I try to allocate [choose] to  a folder (c:\1), he opens it. 

UP1:
I can choose folder, but not worker reimport 
Example (I tried on version 0.5.8 - too most)


UPD2:
I have tried to make small changes.
Has changed the name, but game began to give out Crit error
## Post #6
- Username: SySTeL
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Aug 22, 2009 10:34 pm
- Post datetime: 2012-02-21T11:52:12+00:00
- Post Title: Prime World (zlib uncompress \ compress)

UPD3:
Files reimport it is normal, but! Then the client can't open files from a folder which we reimport.
Look a screenshot log of game [i'm reimport 1 file, but he don't open all files in folder  ]
[http://i39.tinypic.com/2aewgsz.jpg](http://i39.tinypic.com/2aewgsz.jpg)
## Post #7
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-02-21T12:08:30+00:00
- Post Title: Prime World (zlib uncompress \ compress)

It's CRC check
## Post #8
- Username: SySTeL
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Aug 22, 2009 10:34 pm
- Post datetime: 2012-02-21T12:57:42+00:00
- Post Title: Prime World (zlib uncompress \ compress)

The contents of this post was deleted because of possible forum rules violation.
## Post #9
- Username: gamerlock
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Apr 03, 2012 10:37 pm
- Post datetime: 2012-04-03T14:40:21+00:00
- Post Title: Prime World (zlib uncompress \ compress)

I have managed to access the world and previewed this [prime world ](http://www.dotmmo.com/prime-world-6897.html)game
