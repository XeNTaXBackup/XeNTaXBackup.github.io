## Post #1
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-12-22T09:02:48+00:00
- Post Title: Sacred 2 index Archives

Hi all,

Please anyone can help me out to repack this files. Or at least BMS script with reimport possible? Game is Sacred 2 and X360 version.Index file is readable with texts...

```
http://dl.dropbox.com/u/38234344/Sacred_2_X360.rar
```


tahnk you
## Post #2
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-12-22T15:45:28+00:00
- Post Title: Sacred 2 index Archives

anyone please ?
## Post #3
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-12-23T11:29:40+00:00
- Post Title: Sacred 2 index Archives

reall noone can help pls ?
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-12-23T11:31:18+00:00
- Post Title: Sacred 2 index Archives

the compression algorithm is a problem because it looks xmemdecompress but there is something wrong with it so the following script does NOT work:

```
# comtype is not correct or tuned!

open FDDE "index"
string DATA p= "%03d" 0
open FDDE DATA 1

comtype xmemdecompress  # doesn't work
endian big
math FILES = 0x7fffffff
math j = 0
for i = 0 < FILES
    get LEVEL byte
    get NAME_OFF threebyte
    get SIZE long
    get ZSIZE long
    get OFFSET long
    if LEVEL >= 9
        putarray 0 j NAME_OFF
        putarray 1 j OFFSET
        putarray 2 j ZSIZE
        putarray 3 j SIZE
        math j += 1
    endif
    if LEVEL == 0
    if NAME_OFF == 0
    if SIZE == 0
        math FILES = i
    endif
    endif
    endif
next i
math FILES = j
savepos NAMES_OFF
math NAMES_OFF -= 4
for i = 0 < FILES
    getarray NAME_OFF 0 i
    getarray OFFSET   1 i
    getarray ZSIZE    2 i
    getarray SIZE     3 i
    math NAME_OFF += NAMES_OFF
    goto NAME_OFF
    get NAME string
    clog NAME OFFSET ZSIZE SIZE 1
next i
```
## Post #5
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-12-23T11:35:55+00:00
- Post Title: Sacred 2 index Archives

thank you for your help. It is very sad, keep doing worst every day with this formats
