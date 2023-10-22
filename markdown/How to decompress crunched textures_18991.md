## Post #1
- Username: YouDude
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Apr 09, 2017 5:55 am
- Post datetime: 2018-10-28T12:47:19+00:00
- Post Title: How to decompress crunched textures

Hi everyone, I was browsing files from a mobile Unity game on Unity Studio. Some of the textures could not be previewed and If I tried to export them in any format the result would have been a glitchy colorful pixels mess. According to Unity Studio, the file format is "ETC2_RGBA8Crunched", so I googled it and found out that the "crunch" is a type of texture compression for Unity. I've tried several softwares I have, like PVR and Noesis but there seems to be no way to convert it. Do you have any suggestion?
## Post #2
- Username: BAcw
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Oct 28, 2018 11:14 pm
- Post datetime: 2018-10-28T15:18:41+00:00
- Post Title: How to decompress crunched textures

Same issue and haven't found a solution
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-10-28T17:11:26+00:00
- Post Title: How to decompress crunched textures

Just wrap your image into a ktx format and unpack it.
[https://github.com/BinomialLLC/crunch/tree/master/bin](https://github.com/BinomialLLC/crunch/tree/master/bin)
