## Post #1
- Username: Gnampf
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jun 05, 2014 8:03 am
- Post datetime: 2014-06-16T13:05:43+00:00
- Post Title: How to open .pak archive?

Hello guys,

I want to open a .pak archive and I'm looking for long time to open it. It's an archive from an older game and I want to edit and to see the files, there are some codes, 3D models and something in it. I've found some .pak unpackers, but none of these works. I think it's an modified archive and I can't open it since today. I hope somebody can help me to open and rebuild that archive. 

Thanks for help!
## Post #2
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-06-16T16:06:12+00:00
- Post Title: How to open .pak archive?

Use this QuickBMS script

```
math OFFSET = 106496

for cur_off = 0 < LSIZE
    get SIZE  long
    get DUMMY long
    get PSIZE long
    get SIZE  long
    getdstring NAME 48
    
    if NAME == "" then
        cleanexit
    endif

    log NAME OFFSET SIZE
    math OFFSET += PSIZE
    savepos cur_off
next
```


Also the file format is very similar to RTL Skispringen 2002. Mind if I ask what game the .pak file is from?
## Post #3
- Username: Gnampf
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jun 05, 2014 8:03 am
- Post datetime: 2014-06-17T20:11:16+00:00
- Post Title: How to open .pak archive?

It's also a RTL game, it's called "Cobra 11 - Director's Cut". Thanks for the code, it works fine.

Did someone know how to open .es, .3d and .scl 3d models/files ?
