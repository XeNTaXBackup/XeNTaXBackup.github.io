## Post #1
- Username: sakis720
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Jul 05, 2022 6:51 pm
- Post datetime: 2022-08-20T19:39:41+00:00
- Post Title: Ghostbusters The Video Game (2009) POD5 Files

Hi i want to make a mod for Ghostbusters The Video Game (2009) i found a program that unpacks this pod5 files [https://blog.gib.me/2009/06/19/ghostbusters/](https://blog.gib.me/2009/06/19/ghostbusters/)
but i didn't find a program that repacks the pod5 files

Here is some sites that have some information
[https://github.com/gibbed/Gibbed.Ghostbusters](https://github.com/gibbed/Gibbed.Ghostbusters)
[https://github.com/gibbed/Gibbed.IO](https://github.com/gibbed/Gibbed.IO)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-08-21T11:15:07+00:00
- Post Title: Ghostbusters The Video Game (2009) POD5 Files

Can you upload some samples?
## Post #3
- Username: sakis720
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Jul 05, 2022 6:51 pm
- Post datetime: 2022-08-21T16:49:31+00:00
- Post Title: Ghostbusters The Video Game (2009) POD5 Files

[https://www.mediafire.com/file/iyzeb8g9 ... N.rar/file](https://www.mediafire.com/file/iyzeb8g98q3r3hi/COMMON.rar/file)
## Post #4
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2022-08-21T17:04:58+00:00
- Post Title: Ghostbusters The Video Game (2009) POD5 Files

Try this, from aluigi.
to unpack.
to repack just use the reimport commando 
> Quickbms.exe -G -w -r -r  and select the same script you used to unpack.

```
#   The Walking Dead Survival Instinct
#   Country Dance 2
#   Silent Hill Book of Memories
# script for QuickBMS http://quickbms.aluigi.org

idstring "POD5"
get ZERO long
getdstring NAME 0x50
get FILES long
goto 0x108
get INFO_OFF long
get ZERO long
get NAMES_SIZE long

get NAMES_OFF asize
math NAMES_OFF - NAMES_SIZE

math ENTRY_SIZE = NAMES_OFF
math ENTRY_SIZE - INFO_OFF
math ENTRY_SIZE / FILES

for i = 0 < FILES
    goto INFO_OFF
    get NAME_OFF long
    get ZSIZE long
    get OFFSET long
    get SIZE long
    math INFO_OFF + ENTRY_SIZE

    math NAME_OFF + NAMES_OFF
    goto NAME_OFF
    get NAME string

    if ZSIZE == SIZE
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
next i


```
## Post #5
- Username: sakis720
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Jul 05, 2022 6:51 pm
- Post datetime: 2022-08-21T17:19:29+00:00
- Post Title: Ghostbusters The Video Game (2009) POD5 Files

i unpacked but can you tell me exactly how to repacked them i'm new with quickbms
## Post #6
- Username: sakis720
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-08-21T18:00:16+00:00
- Post Title: Ghostbusters The Video Game (2009) POD5 Files

> Reply from sakis720 ↑Mon Aug 22, 2022 1:19 am at Mon Aug 22, 2022 1:19 am
>
> 
i unpacked but can you tell me exactly how to repacked them i'm new with quickbms

You can use reimport mode. More info here [http://aluigi.zenhax.com/papers/quickbms.txt](http://aluigi.zenhax.com/papers/quickbms.txt)
or here [https://www.google.com/search?client=fi ... o+reimport](https://www.google.com/search?client=firefox-b-d&q=quickbms+how+to+reimport)
## Post #7
- Username: sakis720
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Jul 05, 2022 6:51 pm
- Post datetime: 2022-08-21T18:06:23+00:00
- Post Title: Ghostbusters The Video Game (2009) POD5 Files

thanks everyone it's working now i can finaly do the mod
