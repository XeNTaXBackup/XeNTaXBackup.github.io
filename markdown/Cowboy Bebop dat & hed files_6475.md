## Post #1
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2011-04-21T16:15:26+00:00
- Post Title: Cowboy Bebop dat & hed files

Hi everyone. 
I need help extracting dat & hed files from PS2 Cowboy Bebop.
Here is the sample cut file of dmap.dat and dmap.hed file.
[delete](delete)

Thanks in advance.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-21T16:37:29+00:00
- Post Title: Cowboy Bebop dat & hed files

I know that the following script is horrible but I don't have time and interest at the moment:

```
open FDDE "dat" 1
for i = 0 < 3
    findloc OFFSET string "--DirEnd--"
    goto OFFSET
    get DUMMY string
next i
padding 8
getdstring DUMMY 0x44
for
    get OFFSET long
    get SIZE long
    getdstring NAME 0x20
    get DUMMY long
    if SIZE != 0
        log "" OFFSET SIZE 1
    endif
next
```
sorry
## Post #3
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2011-04-22T06:00:30+00:00
- Post Title: Cowboy Bebop dat & hed files

Thanks for your BMS scripts!
## Post #4
- Username: dddwa
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Feb 02, 2022 10:06 am
- Post datetime: 2022-03-16T02:35:17+00:00
- Post Title: Cowboy Bebop dat & hed files

Any update with this? this quickbms script only worked with the DMAP.dat file
