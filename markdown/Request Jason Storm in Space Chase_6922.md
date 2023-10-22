## Post #1
- Username: glaufan
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jul 06, 2011 1:56 pm
- Post datetime: 2011-07-06T06:07:26+00:00
- Post Title: Request: Jason Storm in Space Chase

[http://www.classicdosgames.com/files/ga ... jason1.zip](http://www.classicdosgames.com/files/games/safari/jason1.zip)

storm1.ssp seems to be an archive of its data files, trying to figure out if it's possible to extract the midi music for the game
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-09-04T10:12:09+00:00
- Post Title: Request: Jason Storm in Space Chase

the midi files or pseudo-midi files are contained in the other ss* files.

anyway for the others interested in the SSP file the following is the quickbms script:

```

get FILES short
for i = 0 < FILES
    get SIZE long
    putarray 0 i SIZE
next i
getdstring DUMMY 0x80
for i = 0 < FILES
    get NAME string
    putarray 1 i NAME
    strlen NAMESZ NAME
    do
        get TMP byte
    while TMP == 0
    savepos TMP
    math TMP -= 1
    goto TMP
next i
get OFFSET asize
math FILES -= 1
for i = FILES >= 0
    getarray SIZE 0 i
    getarray NAME 1 i
    math OFFSET -= SIZE
    log NAME OFFSET SIZE
    math i -= 1
next
```
