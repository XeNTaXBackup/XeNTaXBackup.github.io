## Post #1
- Username: Brody
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Dec 10, 2020 6:02 am
- Post datetime: 2022-01-14T20:56:53+00:00
- Post Title: Madoka Magica Pachislot commseed OBB file

hey everyone! i'm trying to rip the video files and assets off this pachislot madoka game that is on android, but i cant open the OBB file with 7zip or WinRar like any other android game, it comes with a weird header in said obb files

any help on ripping these files are appreciated, you can download the game's apk and obb over here in this link
[SLOT魔法少女まどか☆マギカ XAPK](https://apkpure.com/%E3%82%B0%E3%83%AA%E3%83%91%E3%83%81-slot%E9%AD%94%E6%B3%95%E5%B0%91%E5%A5%B3%E3%81%BE%E3%81%A9%E3%81%8B%E2%98%86%E3%83%9E%E3%82%AE%E3%82%AB-%E3%83%91%E3%83%81%E3%82%B9%E3%83%AD%E3%82%B2%E3%83%BC%E3%83%A0/net.commseed.gp.az117001)
cheers!
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-01-14T23:28:03+00:00
- Post Title: Madoka Magica Pachislot commseed OBB file

I don't want to download 2,3 GB game to just check the files,
but from your screenshots it seems that it contain USM Videos [http://wiki.xentax.com/index.php/USM_Video](http://wiki.xentax.com/index.php/USM_Video)

Look for "CRID" signature, it's the beginning of USM header.
## Post #3
- Username: Brody
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Dec 10, 2020 6:02 am
- Post datetime: 2022-01-15T02:30:06+00:00
- Post Title: Madoka Magica Pachislot commseed OBB file

there are a lot of Crid headers in the hex, manually having to rip these in hxd one by one seems like a big hazzle to me


i also forgot to include a screenshot of the very start of the obb file, wich i have never seen this before, hopefully this gives a clue to anyone on how to open this
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-01-15T16:26:12+00:00
- Post Title: Madoka Magica Pachislot commseed OBB file

So those OBB archives are located in /storage/emulated/0/Android/obb/net.commseed.gp.az117001 directory

There are two files there: 
- main.1.net.commseed.gp.az117001.obb
- patch.1.net.commseed.gp.az117001.obb

I was able to create two scripts for unpacking data.
[https://github.com/bartlomiejduda/Tools ... 0Pachislot](https://github.com/bartlomiejduda/Tools/tree/master/NEW%20Tools/Madoka%20Magica%20Pachislot)

First use OBB script to unpack files from OBB archive, then use USM script to get USM videos from cri.bin file.
If they are encrypted, you could try to use crid_mod.exe as described on xentax wiki.

By the way, here you can find description for both formats:
[http://wiki.xentax.com/index.php/Madoka ... hislot_BIN](http://wiki.xentax.com/index.php/Madoka_Magica_Pachislot_BIN)
[http://wiki.xentax.com/index.php/Madoka ... hislot_OBB](http://wiki.xentax.com/index.php/Madoka_Magica_Pachislot_OBB)
## Post #5
- Username: Brody
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Dec 10, 2020 6:02 am
- Post datetime: 2022-01-15T19:34:42+00:00
- Post Title: Madoka Magica Pachislot commseed OBB file

thank you so much for the help dude! i appreciate the effort
