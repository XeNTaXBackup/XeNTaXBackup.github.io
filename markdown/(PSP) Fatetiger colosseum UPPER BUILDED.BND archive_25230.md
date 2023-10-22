## Post #1
- Username: CGm1y4
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Apr 08, 2022 11:02 pm
- Post datetime: 2022-04-08T15:20:49+00:00
- Post Title: (PSP) Fate/tiger colosseum UPPER BUILDED.BND archive

Hi! I've been trying to extract this game for the longest time. I've used patapon.bms before and it worked fine for the previous game in the series (Fate/tiger colosseum) but when I tried to use it for this specific game it only game me mostly gibberish randomly numbered files. If it's possible I want to get the image files (.gim) and scripts (.pac) at the very least. Any kind of help will be greatly appreciated.

[https://drive.google.com/file/d/1q2YbsU ... sp=sharing](https://drive.google.com/file/d/1q2YbsUxY9yBx2MqSw5N-sZ9uAx3k-StU/view?usp=sharing)
## Post #2
- Username: VendorX
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 13, 2018 5:16 am
- Post datetime: 2022-04-08T21:17:57+00:00
- Post Title: (PSP) Fate/tiger colosseum UPPER BUILDED.BND archive

```

getdstring Magic 4
get VER long
get DUMMY long
get DUMMY long
get DUMMY long
get FILES_OFF long
get DUMMY long
get DUMMY long
get FILES long
get ENTRIES long

if VER == 0
    for i = 0 < ENTRIES
        get NAME_CRC long
        get ZERO long
        get OFFSET long
        get SIZE long
        string NAME p "%08x." NAME_CRC
        log NAME OFFSET SIZE
    next i
    cleanexit
endif

```
## Post #3
- Username: CGm1y4
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Apr 08, 2022 11:02 pm
- Post datetime: 2022-04-09T00:32:01+00:00
- Post Title: (PSP) Fate/tiger colosseum UPPER BUILDED.BND archive

That's... exaxtly what patapon.bms did to extract the file, yes.

Also, the TZIP files (.tzi) confuse me. How am I supposed to extract/decompress these files?
## Post #4
- Username: VendorX
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 13, 2018 5:16 am
- Post datetime: 2022-04-09T06:40:10+00:00
- Post Title: (PSP) Fate/tiger colosseum UPPER BUILDED.BND archive

... ask Devs.
