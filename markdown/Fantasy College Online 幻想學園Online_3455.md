## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-01T21:15:33+00:00
- Post Title: Fantasy College Online "幻想學園Online"

I decided to extract this game in the hopes it might be using nif files but it is not 
It seems to be using a very simple file format but I do not recognize it.
Here is an extractor script.

```
     get VERSION long
     get FILES short #not 100% correct but extracts every file"
     getdstring UNKOWN1 5

    goto 816139279
    for i = 0 < FILES
    get NAMESIZE long
    getdstring NAME NAMESIZE
    getdstring COMPRESSED 1
    get OFFSET long
    get ZSIZE long
    get SIZE long
    

    clog NAME OFFSET ZSIZE SIZE
    next i

```

Here is some information about the game.
website [http://fc.runup.com.hk/index/](http://fc.runup.com.hk/index/)
download [http://fc.runup.com.hk/download/](http://fc.runup.com.hk/download/) or [http://fc.runup.cn/down_site.php](http://fc.runup.cn/down_site.php)
[](http://xs.to/xs.php?h=xs139&d=09185&f=fc2911.jpg)[](http://xs.to/xs.php?h=xs139&d=09185&f=fc3186.jpg)[](http://xs.to/xs.php?h=xs139&d=09185&f=fc4204.jpg)
[model.rar](https://xentaxbackup.github.io/file/2009_model.rar)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-02T09:39:37+00:00
- Post Title: Fantasy College Online "幻想學園Online"

you should upload the beginning and the end of one of these archives.
judging the "Goto" you used I guess that the name table is at the end of the archive
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-02T23:06:59+00:00
- Post Title: Fantasy College Online "幻想學園Online"

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-02T23:41:53+00:00
- Post Title: Fantasy College Online "幻想學園Online"

```
get INFO_OFF long
get INFO_END long

goto INFO_OFF
math INFO_END += INFO_OFF

for INFO_OFF = INFO_OFF < INFO_END
    get NAMESIZE long
    getdstring NAME NAMESIZE
    get ZIP byte
    get OFFSET long
    get ZSIZE long
    get SIZE long
    savepos INFO_OFF

    if ZIP == 1
        clog NAME OFFSET ZSIZE SIZE
    else
        log NAME OFFSET SIZE
    endif
next
```
