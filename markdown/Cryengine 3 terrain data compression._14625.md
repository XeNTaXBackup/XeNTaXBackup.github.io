## Post #1
- Username: Gazyi
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Feb 15, 2014 11:07 pm
- Post datetime: 2016-07-10T09:18:11+00:00
- Post Title: Cryengine 3 terrain data compression.

I want to get information of geometry entities, but unlike dynamic entites which data is not compressed (they are in mission_mission0.xml), all static entities data are in terrain.dat
I need only information about geometry entities, like their ID,Parent ID, position and rotation coordinates and maybe a material they use. Any ideas how to get it?
Here is decrypted level.pak: [https://www.dropbox.com/s/dte3mfaca8wpi ... s.zip?dl=0](https://www.dropbox.com/s/dte3mfaca8wpifo/level_lts.zip?dl=0)
## Post #2
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-07-13T12:23:53+00:00
- Post Title: Cryengine 3 terrain data compression.

Probably best to look at CryEngine's source code.

Also the files are not compressed so I'll move this to Game Archive sub-forum.
