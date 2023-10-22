## Post #1
- Username: bleedslow
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Nov 08, 2011 10:33 am
- Post datetime: 2011-11-08T02:37:33+00:00
- Post Title: Path Of Exile

[http://www.pathofexile.com/](http://www.pathofexile.com/)

I've been trying to unpack this game so i could get the ui images they use  but all the content  is in a .ggpk   file extension and i have no idea how to open it,  has anyone tried this?  or know what would open it ?
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2011-12-13T19:24:36+00:00
- Post Title: Path Of Exile

The contents of this post was deleted because of possible forum rules violation.
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-12-13T22:30:00+00:00
- Post Title: Path Of Exile

this script doesn't support the folders because their format is not clear:

```
for MYOFF = 0 < FULLSIZE
    get INFO_SIZE long
    getdstring INFO 4
    # PDIR not supported
    if INFO == "FILE"
        get NAMESZ long
        math NAMESZ *= 2
        getdstring HASH 32
        getdstring NAME NAMESZ
        set NAME unicode NAME

        savepos OFFSET
        math TMP = OFFSET
        math TMP -= MYOFF
        math SIZE = INFO_SIZE
        math SIZE -= TMP
        log NAME OFFSET SIZE
    endif
    math MYOFF += INFO_SIZE
    goto MYOFF
next
```
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2011-12-19T20:56:49+00:00
- Post Title: Path Of Exile

How get all stored files without unpacking Content.ggpk (2.28 GB)   

[http://www.progamercity.net/game-files/ ... #post14966](http://www.progamercity.net/game-files/2143-info-path-exile-ggpk-resources.html#post14966)
