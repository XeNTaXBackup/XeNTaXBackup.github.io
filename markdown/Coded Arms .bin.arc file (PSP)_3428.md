## Post #1
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-04-08T15:17:26+00:00
- Post Title: Coded Arms .bin/.arc file (PSP)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-04-14T04:57:23+00:00
- Post Title: Coded Arms .bin/.arc file (PSP)

Bump. Any of you guys have a chance to look at this one yet?
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-06T15:50:01+00:00
- Post Title: Coded Arms .bin/.arc file (PSP)

for the bin file there are no problems, the other is more chaotic (at a first look):

```
goto 0x30
get INFO_OFFSET long
get INFO_SIZE long

goto 0x40
savepos INFO_OFFSET
for INFO_OFFSET = INFO_OFFSET < INFO_SIZE
    get OFFSET long
    get SIZE long
    get DUMMY long
    get DUMMY long
    savepos INFO_OFFSET

    if OFFSET == 0
        if SIZE == 0
            cleanexit
        endif
    endif

    log "" OFFSET SIZE
next
```
## Post #4
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-05-06T22:34:18+00:00
- Post Title: Coded Arms .bin/.arc file (PSP)

Thanks, it's all right, Kataah helped me figure out the archive. I just wanted to rip the audio and it was just PS2 ADPCM, so it's all good.
## Post #5
- Username: poofacetherisen
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Jan 25, 2011 12:02 pm
- Post datetime: 2011-02-10T18:14:21+00:00
- Post Title: Coded Arms .bin/.arc file (PSP)

Is this alright to bump? Because I would like to rip the models (maybe there's animations too  ). I tried pulling some files but they might be missing the footers (they we're corrupt). I also tried Noesis, but it's not a recognized format. Anyone else progress?
