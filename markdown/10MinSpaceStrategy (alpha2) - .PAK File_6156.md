## Post #1
- Username: 10Min
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Mar 01, 2011 1:54 pm
- Post datetime: 2011-03-01T06:00:39+00:00
- Post Title: 10MinSpaceStrategy (alpha2) - .PAK File

Inside this small game is a .PAK file, but MultiEx Commander can't open it. The whole game is under 25 MB, most of it being the .PAK file. Is there any way to open this file? 

Link to download the free alpha: [http://homegnome.atw.hu/downloads/10Min ... lpha2).zip](http://homegnome.atw.hu/downloads/10MinSpaceStrategy_%28alpha2%29.zip)


More info about the game: [http://www.moddb.com/games/10-min-space-strategy](http://www.moddb.com/games/10-min-space-strategy)

If you actually play the game a bit, it writes to a text document on every action, and you can see it accessing the .pak file while it does. Example:

[23:48:59] 'sfx\end_turn.ogg'
[23:49:00] 'music\04_StrayBoom_-_Glorious_Victory.ogg' 
[23:50:59] 'gfx\planets\planet_dead_v2.png'
[23:50:59] 'gfx\fight_units\spacemonster_nor_left.png'
[00:00:30] 'gfx\planeticons\planeticon_pop_growth.png
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-01T11:52:58+00:00
- Post Title: 10MinSpaceStrategy (alpha2) - .PAK File

script for [QuickBMS](http://aluigi.org/papers.htm#quickbms):

```
get DUMMY long
get FILES long
for i = 0 < FILES
    get DUMMY byte
    get NAMESZ byte
    filexor 0xaa
    getdstring NAME NAMESZ
    filexor 0
    get OFFSET long
    get SIZE long
    get DUMMY long
    get DUMMY byte
    filexor 0xaa
    log NAME OFFSET SIZE
    filexor 0
next i
```
## Post #3
- Username: HomeGnome
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Mar 03, 2011 4:37 pm
- Post datetime: 2011-03-03T08:55:18+00:00
- Post Title: 10MinSpaceStrategy (alpha2) - .PAK File

Nice job! 
Cheers, HomeGnome
