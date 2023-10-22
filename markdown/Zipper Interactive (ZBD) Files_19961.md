## Post #1
- Username: Cosmas47
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Apr 08, 2019 7:18 am
- Post datetime: 2019-04-08T20:50:32+00:00
- Post Title: Zipper Interactive (ZBD) Files

Hey all,
Piggy-backing off of this thread: [https://forum.xentax.com/viewtopic.php?p=150718#p150718](https://forum.xentax.com/viewtopic.php?p=150718#p150718)
I'm looking to find out how to read/write ZBD files. It seems compressed as it has a 2byte lead, but beyond that I can't tell much about it.
Very new to reverse engineering. Any suggestions?

Company also produced Mech Warrior 3 around the same time. Maybe the formats are similar?
[interp.zip](https://xentaxbackup.github.io/file/16009_interp.zip)
## Post #2
- Username: IronArthur
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Aug 05, 2015 9:25 pm
- Post datetime: 2019-04-09T09:40:39+00:00
- Post Title: Zipper Interactive (ZBD) Files

I tried to reverse some of the ZBD files.

interp.zbd it´s a really easy "pak" file, uncompressed and unencrypted.
interpZBD.PNG

The structure is first a definition/index array of files and an offset of the same file, in this case the file is like a hash of words or actions to take like an script language:  "GameZReadZBDFile: %MissionZBDFile%"

But it seems like this is only one type of zbd file, the are other type of zbd files with similar but different structure to pak files like textures or whatever. they seem to be nor compressed nor encrypted.

bye,
## Post #3
- Username: Cosmas47
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Apr 08, 2019 7:18 am
- Post datetime: 2022-10-10T18:31:46+00:00
- Post Title: Zipper Interactive (ZBD) Files

Resurrecting this as some headway has been made but I'm still a little perplexed.

This time I'm trying to crack the gamez.zbd format. This particular archive concerns the terrain files for the game which I'm trying to extract for analysis. See the spec breakdown for findings.

Where I'm getting lost is in the polygon data. Like most formats, you expect to see a list of Vec3s for vertices then following that you'd get a list of vertex indices that make up each polygon. Unfortunately I'm hitting just another address of some unknown data. Open to suggestions.

[Specification breakdown](https://docs.google.com/document/d/1ZMOEsqTWuE37HQb4SyxRsSCMloKkKBDCmz0zPLRoINo/edit?usp=sharing)
Sample [gamez.zbd](https://drive.google.com/file/d/1vM_GJVc2Wlk8rRNQ6x9kVuBtxHVLGGB-/view?usp=sharing) file.
## Post #4
- Username: thedaemonsultan
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Apr 16, 2022 1:49 am
- Post datetime: 2022-12-08T15:05:08+00:00
- Post Title: Zipper Interactive (ZBD) Files

hi there I see you are working on trying to extract .zbd files from Zipper Interactive's games i.e. Recoil and MW3.
we have discord [https://discord.gg/fmRUYGBE ](https://discord.gg/fmRUYGBE)in which we are actively trying to reverse engineer .zbd files.
What we have been able to extract [download/file.php?id=22221](download/file.php?id=22221)
my post regarding the same [viewtopic.php?f=16&t=25256&p=184472&hilit=zbd#p184472](viewtopic.php?f=16&t=25256&p=184472&hilit=zbd#p184472)
we are using a tool called Mech3ax [https://github.com/TerranMechworks/mech3ax](https://github.com/TerranMechworks/mech3ax)

we would love to have you there, where you can bounce off ideas and work together.

Regards,
TheDaemonSultan
