## Post #1
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2011-12-11T07:14:28+00:00
- Post Title: Midnight Nowhere [PC] .res

Hello. Can I get some help with opening the .res containers from Midnight Nowhere?

animgfx.res
gfx.res
models.res
scenes.res
sound.res
TEXTS.RES

I tried Centauri_Production_Resource_File_3.10 (which works with .res files from AlternativA and other games from the same developer) but it's a no go. 

Uploading gfx.res (~10MB unzipped) as the smallest in the family. What I'm eventually trying to do is to get pre-rendered backgrounds which are most likely in scenes.res.

[http://www.mediafire.com/?4i38clqc4w8lf9e](http://www.mediafire.com/?4i38clqc4w8lf9e)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-12-11T09:04:24+00:00
- Post Title: Midnight Nowhere [PC] .res

script for QuickBMS:

```
for i = 0 < FILES
    getdstring NAME 0x80
    get OFFSET long
    get SIZE long
    log NAME OFFSET SIZE
next i
```
## Post #3
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2011-12-11T09:27:58+00:00
- Post Title: Midnight Nowhere [PC] .res

Superfast reply! Thanks a lot aluigi.
