## Post #1
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-04-12T17:23:08+00:00
- Post Title: extracting .bin files help please

hey guys/girls im new to this site so i dont know where to look im trying to extract the files for final fantasy xiii-2

so i can play around with the modeling  but im lost i can't open the .bin file

i used Quick BMS with this script 

get NAME BASENAME
log MEMORY_FILE 0 0
put NAME string MEMORY_FILE
get size asize MEMORY_FILE
math size - 4
goto size MEMORY_FILE
getdstring EXT2 4 MEMORY_FILE
if EXT2 == "360"
set EXT "x360"
else
set EXT ps3
endif

comtype unzip_dynamic
for
findloc START string \x78\xDA
goto START
findloc END string

\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00
set SIZE end
math SIZE - START
goto END
if SIZE > 0x40
clog MEMORY_FILE START SIZE SIZE
getdstring SEDB 8 MEMORY_FILE
if SEDB == "SEDBRES "
goto 0x30 MEMORY_FILE
get COUNT long MEMORY_FILE
math COUNT * 16
math COUNT + 0x40
goto COUNT MEMORY_FILE
getdstring TRB 7 MEMORY_FILE
if TRB == "SEDBtxb"
string START + .
string START + EXT
get SIZE asize MEMORY_FILE
set NAME START
string NAME + .trb
log NAME 0 SIZE MEMORY_FILE
set NAME START
string NAME + .imgb
clog NAME OFFSET ZSIZE2 SIZE2
endif
endif
if SEDB != "SEDBRES "
set OFFSET START
set ZSIZE2 SIZE
get SIZE2 asize MEMORY_FILE
endif
endif
next

but i always get a error while trying to unzip the .bin file if someone can help me please that will be very helpful
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-12T18:23:53+00:00
- Post Title: extracting .bin files help please

Post a screenshot of the error.
## Post #3
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-04-12T18:40:44+00:00
- Post Title: extracting .bin files help please

ok sorry i forgot to but here's the errors i get i tried 2 different scripts 

this 1 is for the script i posted


and this is the other one i just tried to use if that matters lol


im new to theses programs so sorry if im noobish
## Post #4
- Username: Nividica
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jun 28, 2012 1:48 am
- Post datetime: 2012-06-27T17:56:00+00:00
- Post Title: extracting .bin files help please

Howdy lllccc. I got this script yesterday and was also trying to pull some files out of 13-2, and ran into the same issue. Looking over the syntax, and checking the wiki, I found the problem. There are two unneeded End-Of-Lines in the text file.

Change this:

```
findloc END string

\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00
set SIZE end
```


To this:

```
findloc END string \x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00
set SIZE end
```


QuickBMS ran the script and outputted several files. Now to just figure out what to do with 'imgb' & 'trb'. I suspect imgb is a Binary Image, no idea what trb is yet.

Hope this helps ya
## Post #5
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-06-27T18:09:01+00:00
- Post Title: extracting .bin files help please

> Reply from Nividica
>
> Howdy lllccc. I got this script yesterday and was also trying to pull some files out of 13-2, and ran into the same issue. Looking over the syntax, and checking the wiki, I found the problem. There are two unneeded End-Of-Lines in the text file.

Change this:
Code: Select allgoto START
findloc END string

\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00
set SIZE end

To this:
Code: Select allgoto START
findloc END string \x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00
set SIZE end



QuickBMS ran the script and outputted several files. Now to just figure out what to do with 'imgb' & 'trb'. I suspect imgb is a Binary Image, no idea what trb is yet.

Hope this helps yai will give this a go tonight XD i really hope this will work
