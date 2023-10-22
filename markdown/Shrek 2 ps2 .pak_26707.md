## Post #1
- Username: atanetooo
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Feb 12, 2023 11:52 am
- Post datetime: 2023-04-28T23:47:37+00:00
- Post Title: Shrek 2 ps2 .pak

Hi, i'm working with Shrek 2 for PS2 and I found a compressed .pak file, but I don't know how to decompress it.

here's the file : [https://drive.google.com/file/d/1YyWKgX ... sp=sharing](https://drive.google.com/file/d/1YyWKgXXPXmsGU3kF1kn5UvyLZ7CI9cxY/view?usp=sharing)

Is there any tool to extract the file? Or can someone help me to make one?

Sorry for my bad english
## Post #2
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2023-04-29T02:52:14+00:00
- Post Title: Shrek 2 ps2 .pak

```
# Shrek 2 PS2 (.PAK)
# Version 0.1b
#quickbms script

get name string
get offset threebyte
get size long
math offset * 0x800
get entries long
log name offset size

for rip = 1 to entries
getdstring name 0x0c
get offset long
get size long
math offset * 0x800
log name offset size
next rip
```
## Post #3
- Username: atanetooo
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Feb 12, 2023 11:52 am
- Post datetime: 2023-04-29T11:16:46+00:00
- Post Title: Shrek 2 ps2 .pak

Thank you so much!

Now I have .p2b, .ani and .snd files, is there some way to open them? Because I want to mod the characters or ripping their models...
[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1v5WNX40wowbP1iubzcfYy3QPzsWSiPIm?usp=sharing)

There is also another .pak called ENG.PAK 
[https://drive.google.com/file/d/13xx3fq ... sp=sharing](https://drive.google.com/file/d/13xx3fqf5LWsouLIOFEl98Z45U481-qhj/view?usp=sharing)
## Post #4
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2023-04-29T18:20:46+00:00
- Post Title: Shrek 2 ps2 .pak

```
# Shrek 2 PS2 (.PAK)
# Version 0.1b
#Adaptation from aluigi codes

    getdstring FOLDER 0xc
    get INFO_SIZE long
    get FILES long
    math files * 0x20
math files - 1
for i = 0 < files
    getdstring NAME 0xc
    get OFFSET long
    get SIZE long
    math OFFSET * 0x800
    string FNAME p "%s/%s" FOLDER NAME
    log FNAME OFFSET SIZE

next i


    set PATH string ""
    callfunction LEV_EXTRACT
    cleanexit

startfunction LEV_EXTRACT
    getdstring NAME 8
    string DIR_PATH p "%s/%s" PATH NAME

    get NEXT_OFFSET1 long
    get NEXT_OFFSET2 long
    get FILES long
    for i = 0 < FILES
        getdstring NAME 12
        get OFFSET long
        math OFFSET * 16
        get SIZE long
        string FNAME p "%s/%s" DIR_PATH NAME

        log FNAME OFFSET SIZE
    next i
    if NEXT_OFFSET1 != 0
        goto NEXT_OFFSET1
        callfunction LEV_EXTRACT
    endif
    if NEXT_OFFSET2 != 0
        goto NEXT_OFFSET2
        callfunction LEV_EXTRACT
    endif
endfunction

```


When extract choice r to rename, because have files with same name.
