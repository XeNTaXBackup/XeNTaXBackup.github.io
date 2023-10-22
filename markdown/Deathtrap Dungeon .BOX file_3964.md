## Post #1
- Username: StarQuake
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Aug 03, 2009 8:22 pm
- Post datetime: 2009-12-21T05:14:54+00:00
- Post Title: Deathtrap Dungeon .BOX file

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-21T10:13:25+00:00
- Post Title: Deathtrap Dungeon .BOX file

quickbms script for the big box:

```
goto OFFSET
get FILES long
for i = 1 < FILES
    get OFFSET long
    get SIZE long
    getdstring EXT 4
    set NAME string i
    string NAME += EXT
    log NAME OFFSET SIZE
next i
```
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-12-22T23:03:43+00:00
- Post Title: Deathtrap Dungeon .BOX file

```
SavePos TailOffOff 0 ;
Get TailOff Long 0 ;
GoTo TailOff 0 ;
Get FN Long 0 ;
Math FN -= 1 ;
For T = 1 To FN ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos FSO 0 ;
Get FSIZE Long 0 ;
GetDString EXT 4 0 ;
Set NAME String T ;
String NAME += EXT ;
Log NAME FO FSIZE FOO FSO ;
Next T ;

```


Or, if you want to be able to inject back altered textures or anything, use this script in MultiEx Commander. 

Go to the BMS menu and select Add BMS to MRF. Then fill in the requirements. After that, you should be able to open the .BOX files and replace files in there. It will take a while with 14000 files, but it works, I tried. 

Here's the bms:


 box.zip
(286 Bytes) Downloaded 28 times
