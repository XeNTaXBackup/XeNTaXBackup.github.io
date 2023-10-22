## Post #1
- Username: hithewo123
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Mar 01, 2022 5:56 pm
- Post datetime: 2022-03-14T15:52:51+00:00
- Post Title: Crazy Chicken Jewel of Darkness mooh.stg file

Hi. I'm looking for how to extract the mooh.stg file in 2008 game "Crazy Chicken Jewel of Darkness". I found some OGGs and stuff inside it, but I don't know how to extract them, but I think it's an archive file.

Here is the mooh.stg file: 
```
https://mega.nz/file/1hRXnDgQ#vWuyqjLZV3--xw1ulGaFyvTPbJvGIYb2kulXUULd01s
```


Thanks in advance.
## Post #2
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2022-03-14T18:03:36+00:00
- Post Title: Crazy Chicken Jewel of Darkness mooh.stg file

try this:

```
#scriptforQuickBMShttp://quickbms.aluigi.org

idstring "stg2"
getdstring ondinha 0x0e
get end_table long
get entries long
get dummy short

for rip = 1 to entries
get offset_info long
get checkfile long

if checkfile != 0
savepos temp
goto offset_info

for A = 0 < checkfile
get name_size short
get dummy long
get zero byte
get size long
get offset long
getdstring name name_size

log name offset size

for checkbyte = 0 == 0
get checkbyte byte
next

savepos position
math position -= 1
goto position
math rip += 1
next A

goto temp
endif
next
```
## Post #3
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2022-03-14T18:05:57+00:00
- Post Title: Crazy Chicken Jewel of Darkness mooh.stg file

You can use this from alugi.

work as same than mine.
but little better.

```

idstring "stg2"
get VER long
get OFFSET long

set NAME string ""
set PATH string ""
callfunction EXTRACT

startfunction EXTRACT
    string PATH + NAME
    string PATH + /

    savepos BACKUP_OFFSET
    goto OFFSET

    get DUMMY short
    get OFFSET long
    get INFO_SIZE long
    get FILES long
    get ENTRYSZ short
    xmath RESTSZ "ENTRYSZ - (2 + 1 + 4 + 4 + 4)"

    goto OFFSET
    for i = 0 < FILES
        get OFFSET long
        get SUB_FILES long

        savepos BACKUP_OFFSET2
        goto OFFSET
        for x = 0 < SUB_FILES
            get NAMESZ short
            get DUMMY byte
            get DUMMY long
            get SIZE long
            get OFFSET long
            getdstring NAME RESTSZ
            putvarchr NAME NAMESZ 0
            if SIZE == 0
                callfunction EXTRACT
            else
                string FNAME p "%s%s" PATH NAME
                log FNAME OFFSET SIZE
            endif

            math x + 1
            math i + 1
        next
        goto BACKUP_OFFSET2
    next

    goto BACKUP_OFFSET
endfunction

```
## Post #4
- Username: hithewo123
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Mar 01, 2022 5:56 pm
- Post datetime: 2022-03-15T02:51:24+00:00
- Post Title: Crazy Chicken Jewel of Darkness mooh.stg file

Wow it worked! Thanks, dude.
Btw I didn't know that the bms file is already available for Intenium games
## Post #5
- Username: hithewo123
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Mar 01, 2022 5:56 pm
- Post datetime: 2022-03-15T03:25:17+00:00
- Post Title: Crazy Chicken Jewel of Darkness mooh.stg file

After checking the extracted files, pretty disappointed that those OGGs are SFXs, the actual game music is in TrackMenu.skm. Again it has OGGs in it, but probably just the soundfont files for Midi (given its small file size ~222Kb).
## Post #6
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2022-03-15T05:05:36+00:00
- Post Title: Crazy Chicken Jewel of Darkness mooh.stg file

> Reply from hithewo123 ↑Tue Mar 15, 2022 11:25 am at Tue Mar 15, 2022 11:25 am
>
> 
After checking the extracted files, pretty disappointed that those OGGs are SFXs, the actual game music is in TrackMenu.skm. Again it has OGGs in it, but probably just the soundfont files for Midi (given its small file size ~222Kb).

to extract those oggs from trackmenu.skm.
use this.

```
do
    goto OFFSET
    get DUMMY long
    findloc NEXT_OFFSET longlong 0x000002005367674f 0 ""
    if NEXT_OFFSET == ""
        get SIZE asize
    else
        math SIZE = NEXT_OFFSET
    endif
    math SIZE -= OFFSET

    log "" OFFSET SIZE
    math OFFSET = NEXT_OFFSET
while NEXT_OFFSET != ""
```
