## Post #1
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2009-07-27T17:39:30+00:00
- Post Title: Summer Athletics 2009

Looks xor, any help?   
Here a sample/attachment (7mb's):
[http://www.zshare.net/download/63238946ae12ce53/](http://www.zshare.net/download/63238946ae12ce53/)
Thanks!!

What i know for this it's:
Movies Theora
Speeches/Musics ogg
SFx's raw pcm
Graphics DDS

I'm not 100% sure...
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-07-30T17:25:48+00:00
- Post Title: Summer Athletics 2009

the files are nameless and some of them are compressed with an unknown compression algorithm (not zlib,inflate,lzss,lzo,explode).

so the following bms script is totally useless but at least can give an idea of the format:

```

idstring "\xef\xbe\xad\xde"
get FILES long
get BASE_OFFSET long
get DUMMY long
get ZERO long

for i = 0 < FILES
    get DUMMY long
    get DUMMY long
    get OFFSET long
    get ZERO long   # 64bit?
    get ZSIZE long
    get ZERO long   # 64bit?
    get SIZE long
    get ZERO long   # 64bit?
    get DUMMY long
    get ZERO long   # 64bit?

    if SIZE == ZSIZE
        log "" OFFSET SIZE
    else
        clog "" OFFSET ZSIZE SIZE
    endif
next i
```
## Post #3
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2009-07-30T20:11:12+00:00
- Post Title: Summer Athletics 2009

Nice!1 thanks for the info, this it's the 1rst step...
