## Post #1
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-01-23T12:11:07+00:00
- Post Title: How to extract Samurai Shodown Sen K2MP file.

"xof 0303bin 0032" is model file.
"DDS....DXT3" is texture file.
Here are some K2MP files.
[delete](delete)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-01-23T21:47:11+00:00
- Post Title: How to extract Samurai Shodown Sen K2MP file.

uhmmm it looks like k2mp is a generic container but then the archived files have their formats and some of them are just like archives.
an example is "TBSx" which contains the dds.

in my opinion it's better to go with a generic ripper.

anyway the following is a script for takeing the archives from k2mp:

```
idstring "K2MP"
get DUMMY long
get MAX_OFF long
get DUMMY long
for
    savepos MYOFF
    if MYOFF >= MAX_OFF
        break
    endif
    get OFFSET long
    get SIZE long
    if OFFSET != 0
    if OFFSET != 0xffffffff
        log "" OFFSET SIZE
    endif
    endif
next
```
