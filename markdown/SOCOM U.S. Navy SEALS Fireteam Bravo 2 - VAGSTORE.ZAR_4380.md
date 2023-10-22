## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-04-25T00:09:16+00:00
- Post Title: SOCOM U.S. Navy SEALS: Fireteam Bravo 2 - VAGSTORE.ZAR

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-25T00:57:46+00:00
- Post Title: SOCOM U.S. Navy SEALS: Fireteam Bravo 2 - VAGSTORE.ZAR

I have seen that there are these "padding" files that should not be extracted but I have decided to extract them too:

```

get DUMMY long
get NAMES long
get INFO_OFF long
get NAME_BLAH long
get ALIGN long
log MEMORY_FILE 0x64 INFO_OFF
math INFO_OFF += 0x64
math INFO_OFF += 12
goto INFO_OFF
get FILES long
savepos BASE_OFF
math TMP = FILES
math TMP *= 16
math BASE_OFF += TMP
math BASE_OFF x= ALIGN
for i = 0 < FILES
    get NAME_OFF long
    get OFFSET long
    get SIZE long
    get DUMMY long
    math NAME_OFF -= NAME_BLAH
    goto NAME_OFF MEMORY_FILE
    get NAME string MEMORY_FILE
    math OFFSET += BASE_OFF
    if NAME == "padding"
        string NAME += _
        string NAME += i
    endif
    log NAME OFFSET SIZE
next i
```
## Post #3
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-04-25T11:21:15+00:00
- Post Title: SOCOM U.S. Navy SEALS: Fireteam Bravo 2 - VAGSTORE.ZAR

Hm, I get the error Invalid operator 'x'. I have the newest quickBMS though.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-25T15:15:11+00:00
- Post Title: SOCOM U.S. Navy SEALS: Fireteam Bravo 2 - VAGSTORE.ZAR

the 'x' operator has been introduced in version 0.3.15 so you are using an old version or, if you downloaded it, you got the file from your browser's cache.
## Post #5
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-04-26T19:26:54+00:00
- Post Title: SOCOM U.S. Navy SEALS: Fireteam Bravo 2 - VAGSTORE.ZAR

> Reply from aluigi
>
> the 'x' operator has been introduced in version 0.3.15 so you are using an old version or, if you downloaded it, you got the file from your browser's cache.
Damn Windows 7 with it's non-workable file options!!!
Besides, I've noticed that those "padding" files could actually be folders in which the files till the next "padding" are saved because there were some duplicate-name files. Is it possible that you change the script so it will extract the files into folders named 'padding_1', 'padding_2' and so on? Thanks!
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-26T23:10:06+00:00
- Post Title: SOCOM U.S. Navy SEALS: Fireteam Bravo 2 - VAGSTORE.ZAR

the following script does exactly what you asked (note that I have not tested it):

```

get DUMMY long
get NAMES long
get INFO_OFF long
get NAME_BLAH long
get ALIGN long
log MEMORY_FILE 0x64 INFO_OFF
math INFO_OFF += 0x64
math INFO_OFF += 12
goto INFO_OFF
get FILES long
savepos BASE_OFF
math TMP = FILES
math TMP *= 16
math BASE_OFF += TMP
math BASE_OFF x= ALIGN
set PATH string ""
for i = 0 < FILES
    get NAME_OFF long
    get OFFSET long
    get SIZE long
    get DUMMY long
    math NAME_OFF -= NAME_BLAH
    goto NAME_OFF MEMORY_FILE
    get NAME string MEMORY_FILE
    math OFFSET += BASE_OFF
    if NAME == "padding"
        string NAME += _
        string NAME += i
        set PATH string NAME
    else
        set FULLNAME string PATH
        string FULLNAME += /
        string FULLNAME += NAME
        log FULLNAME OFFSET SIZE
    endif
next i
```
