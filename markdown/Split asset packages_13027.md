## Post #1
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2015-07-04T14:00:27+00:00
- Post Title: Split asset packages?

Trying to get a 3D model out of the Captain America Experience app, the packages can be extracted through DisUnity, but I think it's only doing the Split0 file and every other split file is just overwriting the contents of the first. Is there a way to join all the Split parts into one file or how can I do this because all I am getting is just a mess when I try to show the 3D model with missing faces and such.
## Post #2
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2015-07-04T18:31:45+00:00
- Post Title: Split asset packages?

RunMe.bat

```
copy /b sharedassets0.assets.split0+sharedassets0.assets.split1+sharedassets0.assets.split2+sharedassets0.assets.split3+sharedassets0.assets.split4+sharedassets0.assets.split5+sharedassets0.assets.split6+sharedassets0.assets.split7+sharedassets0.assets.split8+sharedassets0.assets.split9+sharedassets0.assets.split10+sharedassets0.assets.split11+sharedassets0.assets.split12+sharedassets0.assets.split13+sharedassets0.assets.split14+sharedassets0.assets.split15+sharedassets0.assets.split16+sharedassets0.assets.split17+sharedassets0.assets.split18+sharedassets0.assets.split19+sharedassets0.assets.split20+sharedassets0.assets.split21+sharedassets0.assets.split22+sharedassets0.assets.split23+sharedassets0.assets.split24+sharedassets0.assets.split25+sharedassets0.assets.split26+sharedassets0.assets.split27+sharedassets0.assets.split28+sharedassets0.assets.split29+sharedassets0.assets.split30+sharedassets0.assets.split31+sharedassets0.assets.split32+sharedassets0.assets.split33+sharedassets0.assets.split34+sharedassets0.assets.split35+sharedassets0.assets.split36+sharedassets0.assets.split37+sharedassets0.assets.split38+sharedassets0.assets.split39+sharedassets0.assets.split40+sharedassets0.assets.split41+sharedassets0.assets.split42+sharedassets0.assets.split43+sharedassets0.assets.split44+sharedassets0.assets.split45+sharedassets0.assets.split46+sharedassets0.assets.split47+sharedassets0.assets.split48+sharedassets0.assets.split49+sharedassets0.assets.split50+sharedassets0.assets.split51+sharedassets0.assets.split52+sharedassets0.assets.split53+sharedassets0.assets.split54+sharedassets0.assets.split55+sharedassets0.assets.split56+sharedassets0.assets.split57+sharedassets0.assets.split58 sharedassets0.assets
```
## Post #3
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2015-07-04T19:53:04+00:00
- Post Title: Split asset packages?

How exactly do I use this, do I copy into DisUnity?
## Post #4
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2015-07-04T20:33:56+00:00
- Post Title: Split asset packages?

It's a command for command line (cmd) in Windows.
Or make a new Text file, paste that code into that file save it as RunMe.bat and run it.

Or another option: use [Luigi's BMS script](http://aluigi.altervista.org/papers/bms/unity.bms). It combines splitted assets into one file.
