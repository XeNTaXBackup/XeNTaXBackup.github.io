## Post #1
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2011-03-20T02:55:40+00:00
- Post Title: PS2 .mb file

Hi,
I really want to know how to extract .mb files from MSG Encounters in Space PS2.
First 8 bytes header "MB12CDVD"

Here is the sample cut file of game.mb.
[delete](delete)
## Post #2
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2011-03-20T09:43:28+00:00
- Post Title: PS2 .mb file

try this[viewtopic.php?p=46752#p46752](http://forum.xentax.com/viewtopic.php?p=46752#p46752)
## Post #3
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2011-03-20T09:48:09+00:00
- Post Title: PS2 .mb file

> Reply from alon
>
> try thisviewtopic.php?p=46752#p46752
I've tried.
The two files are much alike, but they do have differences.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-20T10:17:35+00:00
- Post Title: PS2 .mb file

script for quickbms:

```
get FILES long
get BASE_OFF long
for i = 0 < FILES
    get OFFSET long
    getdstring NAME 0x20
    if OFFSET == -1
        get OFFSET long
        math OFFSET *= 0x800
        math OFFSET += BASE_OFF
    else
        get DUMMY long
        get DUMMY long
        set BASE_OFF long OFFSET
    endif
    get SIZE long
    log NAME OFFSET SIZE
next i
```
## Post #5
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2011-03-20T12:07:21+00:00
- Post Title: PS2 .mb file

> Reply from aluigi
>
> script for quickbms:
Code: Select allgetdstring SIGN 8
get FILES long
get BASE_OFF long
for i = 0 < FILES
    get OFFSET long
    getdstring NAME 0x20
    if OFFSET == -1
        get OFFSET long
        math OFFSET *= 0x800
        math OFFSET += BASE_OFF
    else
        get DUMMY long
        get DUMMY long
        set BASE_OFF long OFFSET
    endif
    get SIZE long
    log NAME OFFSET SIZE
next i

Thanks. You've been very helpful.
## Post #6
- Username: Eradicon
- Rank: beginner
- Number of posts: 28
- Joined date: Fri Feb 11, 2011 1:20 am
- Post datetime: 2013-10-27T03:20:38+00:00
- Post Title: PS2 .mb file

I've been trying to get the video files from the video game Gundam SEED Never Ending Tomorrow, the script works on it's .mb files, but it's not giving me the files I need. Is there any script identical to it that can let it work properly?
