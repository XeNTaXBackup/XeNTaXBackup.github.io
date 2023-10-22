## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-01-11T08:07:45+00:00
- Post Title: Ghost Recon: Advanced Warfighter (PS2) - *.IMG archives

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-01-11T15:38:30+00:00
- Post Title: Ghost Recon: Advanced Warfighter (PS2) - *.IMG archives

```

quickbmsver 0.3.12
get FULLSIZE long
get OFFSET1 long
get INFO_OFF long
get OFFSET3 long
get NAMES_OFF long
get BASE_OFF long
get OFFSET6 long
get OFFSET7 long
get OFFSET8 long

goto INFO_OFF
math FILES = OFFSET3
math FILES -= INFO_OFF
math FILES /= 0x30
for i = 0 < FILES
    set PATH string ""
    callfunction extract 1
    if OFFSET != 0
        getarray FULLNAME 0 0
        if ZSIZE == SIZE
            log FULLNAME OFFSET SIZE
        else
            clog FULLNAME OFFSET ZSIZE SIZE
        endif
    endif
next i

startfunction extract
    get NAME_OFF long
    get CURR_ID long
    get PREV_ID long
    get NEXT_ID long
    get DUMMY4 long
    get TYPE long
    get ZSIZE long
    get SIZE long
    get OFFSET long
    get DUMMY6 long
    get DUMMY7 long
    get DUMMY8 long

    math NAME_OFF += NAMES_OFF
    savepos TMP2
    goto NAME_OFF
    get NAME string
    goto TMP2

    if PREV_ID != 0
        set PATH2 string PATH
        set PATH string NAME
        string PATH += /
        string PATH += PATH2

        savepos MYOFF
        callfunction seek 1
        goto PREV_OFF
        callfunction extract
        goto MYOFF
    else
        set FULLNAME string NAME
        string FULLNAME += /
        string FULLNAME += PATH
        string FULLNAME -= 1
        putarray 0 0 FULLNAME
    endif
endfunction

startfunction seek
    math PREV_OFF = PREV_ID
    math PREV_OFF *= 0x30
    math PREV_OFF += INFO_OFF
endfunction
```
## Post #3
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-01-11T15:44:17+00:00
- Post Title: Ghost Recon: Advanced Warfighter (PS2) - *.IMG archives

Works perfectly!!! THANKS A LOT, LUIGI! 

I'm always wondering about the amazing speed at which you write these scripts...
## Post #4
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-01-23T20:12:24+00:00
- Post Title: Ghost Recon: Advanced Warfighter (PS2) - *.IMG archives

If anyone's interested in extracting the *.PKG archives (also from the PS2 version), here's the script I've written. It's my first one, it's working and I'm a bit proud about it. 

```
# Ghost Recon: Advanced Warfighter (PS2)
# (c) 2010 by AlphaTwentyThree of Xentax

get DATASTART long
get FILES long

for i = 1 <= FILES
   savepos POS   
   get NAMEPOS long
   math NAMEPOS + POS
   get OFFSET long
   savepos POS

   goto NAMEPOS
   getdstring NAME 0x40
   goto POS

   if i == FILES
      get SIZE asize
   else
      get DUMMY long
      get SIZE long
   endif
   math SIZE - OFFSET
   log NAME OFFSET SIZE

   goto POS
next i
```

Enjoy!
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-01-23T23:14:57+00:00
- Post Title: Ghost Recon: Advanced Warfighter (PS2) - *.IMG archives

Bloody excellent job, Alpha23. 

Everyone should be writing in BMS.
## Post #6
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-01-23T23:40:42+00:00
- Post Title: Ghost Recon: Advanced Warfighter (PS2) - *.IMG archives

Thanks!
