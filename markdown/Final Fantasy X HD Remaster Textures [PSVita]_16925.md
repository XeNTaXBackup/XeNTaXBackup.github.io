## Post #1
- Username: szczuru
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Sep 26, 2015 5:38 am
- Post datetime: 2017-08-25T12:19:10+00:00
- Post Title: Final Fantasy X HD Remaster Textures [PSVita]

Hi, does anyone know do ho properly convert textures from FFXHD (PSVita) to DDS? (And convert it back?). There are a lot of tools for FFX/FFXHD but nothing works with PSVita edition  DDS seems to be still DDS5 but swizzled and i don't have any idea how properly extract it 

Few samples (fonts):

[http://www73.zippyshare.com/v/ap7pn27r/file.html](http://www73.zippyshare.com/v/ap7pn27r/file.html)
[http://www73.zippyshare.com/v/SMQwT397/file.html](http://www73.zippyshare.com/v/SMQwT397/file.html)
## Post #2
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2017-08-25T12:49:28+00:00
- Post Title: Final Fantasy X HD Remaster Textures [PSVita]

FFX/X2 HD DDS.phyre format described here:
[http://forums.qhimm.com/index.php?topic ... #msg240958](http://forums.qhimm.com/index.php?topic=16943.msg240958#msg240958)

Software for texture manipulation was made by someone outside Qhimm and probably here. There's the link:
[http://steamcommunity.com/app/359870/di ... 007524857/](http://steamcommunity.com/app/359870/discussions/0/364041517007524857/)
## Post #3
- Username: szczuru
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Sep 26, 2015 5:38 am
- Post datetime: 2017-08-25T12:58:07+00:00
- Post Title: Final Fantasy X HD Remaster Textures [PSVita]

Thanks  But i know that topic and still any tool/script for FFX HD PC version doesn't seems to work with Vita version
## Post #4
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2017-08-25T13:08:12+00:00
- Post Title: Final Fantasy X HD Remaster Textures [PSVita]

Okay, your example:
DXT5 header at 0xC11
Filename at 0xB4E

Data difference:
PC - B2
PSVita - C3

I don't have tools with me now, sorry
Did you try FFX HD PS3 tools?
## Post #5
- Username: szczuru
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Sep 26, 2015 5:38 am
- Post datetime: 2017-08-25T13:31:05+00:00
- Post Title: Final Fantasy X HD Remaster Textures [PSVita]

No, i've tested only tools/script for PC version. For PC version - everything seems to works fine but for Vita - nothing for gfx works. Even texture finder doesn't find textures (or it finds but all textures seems to be swizzled). I'm trying to port Polish fan-made translation from PC version to Vita version. Text files format seems to be the same but tuxteres (eg fonts) are diffrent :/
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-08-26T01:01:33+00:00
- Post Title: Final Fantasy X HD Remaster Textures [PSVita]

use this bms script to extract the gxt file from your samples and open it with Noesis 

```

get NAME basename
idstring "RYHP"
get SIZE asize
findloc OFFSET string "GXT"
goto OFFSET
math SIZE - OFFSET
string NAME - ".dds"
string NAME + ".gxt"
print "Open these *.gxt files with Noesis!"
log NAME OFFSET SIZE
```
## Post #7
- Username: szczuru
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Sep 26, 2015 5:38 am
- Post datetime: 2017-08-26T08:46:19+00:00
- Post Title: Final Fantasy X HD Remaster Textures [PSVita]

> Reply from AceWell
>
> use this bms script to extract the gxt file from your samples and open it with Noesis 
Code: Select all# script for QuickBMS http://aluigi.org/papers.htm#quickbms

get NAME basename
idstring "RYHP"
get SIZE asize
findloc OFFSET string "GXT"
goto OFFSET
math SIZE - OFFSET
string NAME - ".dds"
string NAME + ".gxt"
print "Open these *.gxt files with Noesis!"
log NAME OFFSET SIZE

It works!  How export edited texture back to phyre format? This is lat thing i need to port fan-made translation  This script only trimmed "header"? (everything before GXT) am i right?
## Post #8
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-08-26T22:16:25+00:00
- Post Title: Final Fantasy X HD Remaster Textures [PSVita]

> Reply from szczuru
>
> This script only trimmed "header"? (everything before GXT) am i right?
well yes, but i think gxt format has some bit shifting and i don't know how you would export this data back to its original state.
