## Post #1
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2014-12-28T15:12:40+00:00
- Post Title: [REQ][PC] The Legend of Korra - textures in .dtt files

Hello. Do anyone know a tool for extracting/importing textures from this game?

Sample files: [LINK](http://ikskoks.playloc.pl/XENTAX/ui.rar) (extracted from CRI cpk archive by aluigi quick bms script)

I saw that some russian guy extracted textures: [LINK](http://ikskoks.playloc.pl/XENTAX/KorraDDSs.zip)


thanks in advance
## Post #2
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-12-28T16:45:38+00:00
- Post Title: [REQ][PC] The Legend of Korra - textures in .dtt files

QuickBMS script, not the ideal way to approach this format but seems to work well enough:

```

for OFFSET = 0 < EOF
    findloc OFFSET string "DDS "
    goto OFFSET
    get ddsMagic long

    findloc SIZE string "DDS " 0 ""

    if SIZE == ""
    get SIZE asize
    endif

    goto SIZE
    math SIZE -= OFFSET    

    get NAME basename
    string NAME p= "%s_%08x.dds" NAME OFFSET
    log NAME OFFSET SIZE
next
```
## Post #3
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2014-12-28T21:45:09+00:00
- Post Title: [REQ][PC] The Legend of Korra - textures in .dtt files

Thank you.
