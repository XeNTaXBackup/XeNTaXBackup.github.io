## Post #1
- Username: Trishty
- Rank: advanced
- Number of posts: 63
- Joined date: Mon Jul 05, 2010 9:37 pm
- Post datetime: 2011-08-05T10:13:17+00:00
- Post Title: WolfTeam .xfs file

[http://wolfteam.softnyx.net](http://wolfteam.softnyx.net)
[http://wolfteam.aeriagames.com](http://wolfteam.aeriagames.com)
Some image
[http://i771.photobucket.com/albums/xx35 ... 2a3979.jpg](http://i771.photobucket.com/albums/xx353/trishty/c72a3979.jpg)
[http://i771.photobucket.com/albums/xx35 ... 791c4b.jpg](http://i771.photobucket.com/albums/xx353/trishty/e3791c4b.jpg)
I have no idea how to extract the files in this wolf.xfs 700MB
Can some one help me?
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-08-05T10:42:13+00:00
- Post Title: WolfTeam .xfs file

post the first and last 10 mb of the file.
## Post #3
- Username: Trishty
- Rank: advanced
- Number of posts: 63
- Joined date: Mon Jul 05, 2010 9:37 pm
- Post datetime: 2011-08-05T18:53:59+00:00
- Post Title: WolfTeam .xfs file

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-08-05T18:58:54+00:00
- Post Title: WolfTeam .xfs file

the file is zlib compressed there must be an index file somewhere?
just use offzip to extract the files without names.
## Post #5
- Username: Trishty
- Rank: advanced
- Number of posts: 63
- Joined date: Mon Jul 05, 2010 9:37 pm
- Post datetime: 2011-08-06T03:27:08+00:00
- Post Title: WolfTeam .xfs file

thanks very much chrrox!
Have 800 files type, 6GB, it use Korea Lithtech
## Post #6
- Username: Trishty
- Rank: advanced
- Number of posts: 63
- Joined date: Mon Jul 05, 2010 9:37 pm
- Post datetime: 2011-08-06T19:25:05+00:00
- Post Title: WolfTeam .xfs file

I have a problem when extract by offzip. It extract models, textures and sounds lost information. All textures <64KB There have a lots different tex size. 256x256, 512x512, 1024x512, .... A tex big than 256x256 will lost information
Models and sounds have a same problem as tex. it lost half information.
Sample image:

I'll upload a sample file if you need
WolfTeam use the same file type as Combat Arms, Sudden Attack, CrossFire Korea Lithtech: ltb (MODEL+BONE+ANIMS), dtx (TEX), dat (MAP)
In CF dtx 256x256 have 64KB, 512x512 have 256 KB, 1024x1024 have 1MB
I extract WolfTeam by offzip and just have 64KB, not bigger. Is it lost information?
i used offzip like this: offzip.exe -a wolf.xfs wolf 0
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-08-06T19:43:02+00:00
- Post Title: WolfTeam .xfs file

they are using zlib chunks you would need to use the -1 command with offzip so it outputs one big file.
then search through that big file to extract its resources
a program like jaeder naub can do that.
## Post #8
- Username: Trishty
- Rank: advanced
- Number of posts: 63
- Joined date: Mon Jul 05, 2010 9:37 pm
- Post datetime: 2011-08-07T13:02:31+00:00
- Post Title: WolfTeam .xfs file

The contents of this post was deleted because of possible forum rules violation.
## Post #9
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-08-07T13:24:45+00:00
- Post Title: WolfTeam .xfs file

just play around with jaeder naub it can extract dds files just need to get the right settings.
## Post #10
- Username: Trishty
- Rank: advanced
- Number of posts: 63
- Joined date: Mon Jul 05, 2010 9:37 pm
- Post datetime: 2011-08-08T02:35:51+00:00
- Post Title: WolfTeam .xfs file

I think DTX, LTB files different with DDS
And jaeder naub dosen't support dtx, ltb file
I have play with jaeder naub 1 day and can't get anything. Check all in options, Scan File, ASCII Rip, RTD32 v1.01 or just check dds file type in options. Can't extract anything
