## Post #1
- Username: Kara6321
- Rank: beginner
- Number of posts: 26
- Joined date: Sat Dec 02, 2017 1:02 am
- Post datetime: 2018-08-12T16:24:33+00:00
- Post Title: Prototype 2 Language Files Help

Prototype 2 language files I am going to make a patch in Turkish
## Post #2
- Username: Kara6321
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2018-08-14T19:11:54+00:00
- Post Title: Prototype 2 Language Files Help

Please only use 1 thread.
## Post #3
- Username: hnnewgames
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Nov 22, 2017 10:11 am
- Post datetime: 2018-08-21T11:11:19+00:00
- Post Title: Prototype 2 Language Files Help

> Reply from Kara6321
>
> Prototype 2 language files I am going to make a patch in Turkish

These tools are used to edit the game text.
-------------------------------------------------------------
Prototype_2_Tools_By_Swuforce:
[https://yadi.sk/d/wCv1J-_13aRZxz](https://yadi.sk/d/wCv1J-_13aRZxz)
## Post #4
- Username: UtkuGARIP
- Rank: beginner
- Number of posts: 38
- Joined date: Tue Feb 28, 2017 8:53 am
- Post datetime: 2018-09-10T08:30:40+00:00
- Post Title: Prototype 2 Language Files Help

> Reply from Kara6321
>
> Prototype 2 language files I am going to make a patch in Turkish

Send language file.
## Post #5
- Username: sinnerclown
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Aug 22, 2020 5:49 am
- Post datetime: 2021-12-07T09:15:53+00:00
- Post Title: Prototype 2 Language Files Help

hello how can i import language file back to rcf file?
## Post #6
- Username: sinnerclown
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Aug 22, 2020 5:49 am
- Post datetime: 2021-12-09T07:40:04+00:00
- Post Title: Prototype 2 Language Files Help

# Prototype 2 RZ
get EXT extension
if EXT == "RZ"  # conflict with idstring/putdstring
    idstring "RZ"
    getdstring ZERO 6
    get SIZE longlong
    savepos OFFSET
    get ZSIZE asize
    math ZSIZE - OFFSET
    get NAME basename
    clog NAME OFFSET ZSIZE SIZE
else
    comtype zlib_compress
    log MEMORY_FILE 0 0
    putdstring "RZ" 2 MEMORY_FILE
    for x = 0 < 6
        put 0 byte MEMORY_FILE
    next x
    get SIZE asize
    put SIZE longlong MEMORY_FILE
    get NAME filename
    string NAME + ".rz"
    log NAME 0 16 MEMORY_FILE
    append
    clog NAME 0 SIZE SIZE
    append
endif

There is a compression script written by Aluigi, but the size decreases to 300 mb in the file and it does not work.
