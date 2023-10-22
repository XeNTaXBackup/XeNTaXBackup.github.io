## Post #1
- Username: danny
- Rank: beginner
- Number of posts: 22
- Joined date: Mon Apr 11, 2011 6:16 pm
- Post datetime: 2011-06-10T14:14:10+00:00
- Post Title: Ghost WHISPERER i need the code to file .dat

Helo friends i need te code to decompress the file lang_end.dat

THE FILE lang.dat
[http://www.mediafire.com/?pzooe6fimmosss7](http://www.mediafire.com/?pzooe6fimmosss7)

thanks
## Post #2
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2011-06-10T15:15:02+00:00
- Post Title: Ghost WHISPERER i need the code to file .dat

Dude, link broken.
## Post #3
- Username: danny
- Rank: beginner
- Number of posts: 22
- Joined date: Mon Apr 11, 2011 6:16 pm
- Post datetime: 2011-06-10T15:42:49+00:00
- Post Title: Ghost WHISPERER i need the code to file .dat

> Reply from delutto
>
> Dude, link broken.
Thanks por the response a new link in the post
## Post #4
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2011-06-11T07:25:46+00:00
- Post Title: Ghost WHISPERER i need the code to file .dat

What game is this? Any link to the site of the game?
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-06-11T10:36:20+00:00
- Post Title: Ghost WHISPERER i need the code to file .dat

script for quickbms:

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

idstring "GRF"
goto 8
get OFFSET long
get SIZE asize
math SIZE -= OFFSET
comtype unzip_dynamic
clog MEMORY_FILE OFFSET SIZE SIZE
math CURR = 5
goto CURR MEMORY_FILE
get FILESIZE asize
get MEMSIZE asize MEMORY_FILE
for CURR = CURR < MEMSIZE
    get DUMMY byte MEMORY_FILE
    get NUM long MEMORY_FILE
    get DUMMY long MEMORY_FILE
    get DUMMY byte MEMORY_FILE
    get NAMESZ byte MEMORY_FILE
    getdstring NAME NAMESZ MEMORY_FILE
    get OFFSET long MEMORY_FILE
    get SIZE long MEMORY_FILE
    get ZIP byte MEMORY_FILE
    math ZSIZE = FILESIZE
    math ZSIZE -= OFFSET
    clog NAME OFFSET ZSIZE SIZE
    savepos CURR MEMORY_FILE
next
```


@delutto
stop writing in bold, learn the netiquette
