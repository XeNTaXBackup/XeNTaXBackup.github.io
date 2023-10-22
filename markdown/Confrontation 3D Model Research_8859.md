## Post #1
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-04-29T20:31:34+00:00
- Post Title: Confrontation 3D Model Research

Hi guys, I bought a game today from Cyanide [http://www.cyanide-studio.com/](http://www.cyanide-studio.com/)

I added a skin file ( 3D Model ) of the Jackal Hunter, it is of an unknown format to me, so I need some help here :/

.cef extension

the textures are in plain .dds format 

If no-one would like to help, at least tell me how I would start to figure it out myself.

Thnx

T.
[JackalHunter.rar](https://xentaxbackup.github.io/file/5374_JackalHunter.rar)
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-29T21:59:53+00:00
- Post Title: Confrontation 3D Model Research

It's just 3 structs, probably vertbuff + index buff + whatever "blend weight" refers to.

At offset 191 that probably tells you how many structs to follow, and the type of struct. Each of them comes with a count after the name. And then you start reading the structs.

Then there's another struct after.
