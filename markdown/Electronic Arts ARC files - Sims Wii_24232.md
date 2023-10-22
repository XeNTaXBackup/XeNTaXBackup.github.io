## Post #1
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2021-07-13T21:47:47+00:00
- Post Title: Electronic Arts ARC files - Sims Wii

Does anyone know how to unpack .arc files from The Sims 3 and The Sims Castaway on the Wii?
Samples here:
[https://mega.nz/file/fsM1UKTQ#sCOoyaHh2 ... llipX27loo](https://mega.nz/file/fsM1UKTQ#sCOoyaHh2tz5hlABeHal0yEyYi-n97s6PllipX27loo)
I tried sims2_arc.bms but it didn't work on these files.
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-07-17T23:39:57+00:00
- Post Title: Electronic Arts ARC files - Sims Wii

Hi, try this script
[https://github.com/bartlomiejduda/Tools ... script.bms](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/EA_ARC_script.bms)

Also you can find some specification here
[http://wiki.xentax.com/index.php/EA_ARC_FLSH_RNIB](http://wiki.xentax.com/index.php/EA_ARC_FLSH_RNIB)
## Post #3
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2021-07-18T01:25:31+00:00
- Post Title: Electronic Arts ARC files - Sims Wii

I was able to get files out of these Sims Wii files by adding endian big after get OFFSET long in sims2_arc.bms.
