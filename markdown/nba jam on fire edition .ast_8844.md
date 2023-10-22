## Post #1
- Username: sdot
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Apr 19, 2012 7:30 am
- Post datetime: 2012-04-27T16:41:56+00:00
- Post Title: nba jam on fire edition .ast

Hey guys, Im attempting to extract the textures from nba jam ofe to port them to another version of the game. I've extracted the ps3 .pkg file and end up with a handful of .ast files. I did a search here and found a topic with a script, but it didn't work for me. Stuck, what do i do? Help.
## Post #2
- Username: sdot
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Apr 19, 2012 7:30 am
- Post datetime: 2012-05-02T02:42:01+00:00
- Post Title: nba jam on fire edition .ast

push.
anybody?
## Post #3
- Username: flowersongs
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Feb 03, 2016 2:40 am
- Post datetime: 2016-02-04T10:18:11+00:00
- Post Title: nba jam on fire edition .ast

Hi, I know this was a few years ago you posted, but now I am starting on an NBA Jam texture project and would like any user suggestions. I extracted the AST files contents with the OPenBMS script from aluigi user on here. It worked to extract all the texture files - I have the files, file name is correct for players, file size seems correct for textures, but there is NO extension. I have no idea what type of file these are. Importing into photoshop with various popular extensions has not worked so far. Anyone figure these texture files or any NBA Jam files out yet?

edit: perhaps they are DIF files? For example, a file title will say:  CHANUCEY_BILLUPS_HOME_HEAD_DIF 
Electronic Arts - EA - does have a DIF file type according to this link: [http://eblong.com/zarf/blorb/iff.html](http://eblong.com/zarf/blorb/iff.html)
but that says DIF files are for databasing and not imaging.. something along the lines of an IFF would most likely be an image. Anyone know conversion methods for a DIF, DIFF, or IFF?
edit 2: FWIW, Tried an IFF file converter and it did not recognize any of the files as graphic files. Could they be DIFF database files with multiple images packed inside? not impossible i guess. anyone? 
I am going search threw the graphic file sections on here manually, and perhaps post some of my findings there as well.. 
I already did plenty of xentax site searching on NBA jam, ast, etc.
## Post #4
- Username: flowersongs
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Feb 03, 2016 2:40 am
- Post datetime: 2016-02-08T23:19:15+00:00
- Post Title: nba jam on fire edition .ast

Does Anybody have any suggestions on graphic file types for NBA Jams on this forum? ANY insight is greatly appreciated, thank you.
## Post #5
- Username: flowersongs
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Feb 03, 2016 2:40 am
- Post datetime: 2016-02-18T02:32:02+00:00
- Post Title: nba jam on fire edition .ast

Okay, I have opened textures from NBA Jam on fire edition in photoshop. used xbox sdk kit to finally extract the tga files, and then bundle them back together to xpr2. This makes an xpr2 file with the same name, etc. I tried placing all the files, but the game freezes when loading a match an looking for the textures, it appears it WANTs the .AST file. 
NOW, I can someone please help me run this NBA extraction script in reverse to make an ast?  I tried running itin quickbms with the Reimport batch, but it errored saying expected BGFA, this file is XPR2. The script worked to Extract the files, now I need to inject them or re-import them to .ast ... Please help me run this script in reverse and my project is complete. 

```
# script for QuickBMS http://quickbms.aluigi.org

idstring "BGFA"
getdstring VER 4
get DUMMY long
get FILES long
get OFFSET long
goto OFFSET
getdstring DUMMY 12
for i = 0 < FILES
    getdstring DUMMY 10
    get OFFSET long
    get ZSIZE threebyte
    get SIZE threebyte
    getdstring NAME 0x2a
    math OFFSET *= 8
    if SIZE == 0
        log NAME OFFSET ZSIZE
    else
        math SIZE += ZSIZE
        clog NAME OFFSET ZSIZE SIZE
    endif
next i
```
## Post #6
- Username: flowersongs
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Feb 03, 2016 2:40 am
- Post datetime: 2016-02-18T02:48:27+00:00
- Post Title: nba jam on fire edition .ast

Okay, I have opened textures from NBA Jam on fire edition in photoshop. used xbox sdk kit to finally extract the tga files, and then bundle them back together to xpr2. This makes an xpr2 file with the same name, etc. I tried placing all the files, but the game freezes when loading a match an looking for the textures, it appears it WANTs the .AST file. 
NOW, I can someone please help me run this NBA extraction script in reverse to make an ast?  I tried running itin quickbms with the Reimport batch, but it errored saying expected BGFA, this file is XPR2. The script worked to Extract the files, now I need to inject them or re-import them to .ast ... Please help me run this script in reverse and my project is complete. 

```
# script for QuickBMS http://quickbms.aluigi.org

idstring "BGFA"
getdstring VER 4
get DUMMY long
get FILES long
get OFFSET long
goto OFFSET
getdstring DUMMY 12
for i = 0 < FILES
    getdstring DUMMY 10
    get OFFSET long
    get ZSIZE threebyte
    get SIZE threebyte
    getdstring NAME 0x2a
    math OFFSET *= 8
    if SIZE == 0
        log NAME OFFSET ZSIZE
    else
        math SIZE += ZSIZE
        clog NAME OFFSET ZSIZE SIZE
    endif
next i
```
