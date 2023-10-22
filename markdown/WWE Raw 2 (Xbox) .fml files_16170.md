## Post #1
- Username: MarioSonicU
- Rank: advanced
- Number of posts: 75
- Joined date: Fri Jun 26, 2015 6:26 am
- Post datetime: 2017-04-19T14:39:20+00:00
- Post Title: WWE Raw 2 (Xbox) .fml files

[https://mega.nz/#!Gp5wVSjB!DSZARN-Y2o5k ... xRcWCGhDNU](https://mega.nz/#!Gp5wVSjB!DSZARN-Y2o5klSYzlcXC_AyA6AF-2KU3TxRcWCGhDNU)

Are there any tools to view models? It won't work with the unfinished Noesis script for the PC version of WWF Raw.
## Post #2
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2017-04-19T20:48:40+00:00
- Post Title: WWE Raw 2 (Xbox) .fml files

Well fortunately the format is slightly less hacky than the PC version.



I need small file samples, the ones provided are too large.
## Post #3
- Username: MarioSonicU
- Rank: advanced
- Number of posts: 75
- Joined date: Fri Jun 26, 2015 6:26 am
- Post datetime: 2017-04-20T12:57:28+00:00
- Post Title: WWE Raw 2 (Xbox) .fml files

[https://mega.nz/#!npYRCALa!mWzMayvwnOv9 ... VEwA5rWBQE](https://mega.nz/#!npYRCALa!mWzMayvwnOv91kthHhfGSg2OGhTp1SM2FVEwA5rWBQE)
here they are.
## Post #4
- Username: Acewell
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2017-04-23T21:30:37+00:00
- Post Title: WWE Raw 2 (Xbox) .fml files

Ok it's done then.


[fmt_WWER2_fml.zip](https://xentaxbackup.github.io/file/12811_fmt_WWER2_fml.zip)
## Post #5
- Username: MarioSonicU
- Rank: advanced
- Number of posts: 75
- Joined date: Fri Jun 26, 2015 6:26 am
- Post datetime: 2017-04-23T22:28:15+00:00
- Post Title: WWE Raw 2 (Xbox) .fml files

The Script works! Only Problem, The faces have submeshes, and there's no way to seperate them. Any Suggestions?
## Post #6
- Username: eri619
- Rank: veteran
- Number of posts: 81
- Joined date: Wed May 16, 2012 1:36 pm
- Post datetime: 2017-06-15T08:34:42+00:00
- Post Title: WWE Raw 2 (Xbox) .fml files

Problem here is that the noesis script is treating all submeshes in the file as a singe one, could there be any adjustment made in the script to separate the submeshes?
Here are some head file samples
[https://cdn.discordapp.com/attachments/ ... /X0005.rar](https://cdn.discordapp.com/attachments/294225794253979648/324828968987394049/X0005.rar)
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-06-15T12:53:20+00:00
- Post Title: WWE Raw 2 (Xbox) .fml files

hi eri619

For the Noesis script here: there's no simple solution. You'll need to dig into the format to find the submesh borders.
You could manually add grouping lines to the obj file such like this one:
g SM_x



X0005.jpg (68.93 KiB) Viewed 180 times


Maybe some sorting of face indices could improve the result.
## Post #8
- Username: eri619
- Rank: veteran
- Number of posts: 81
- Joined date: Wed May 16, 2012 1:36 pm
- Post datetime: 2017-06-15T17:17:18+00:00
- Post Title: WWE Raw 2 (Xbox) .fml files

Thanks!
## Post #9
- Username: eri619
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2017-06-15T21:38:56+00:00
- Post Title: WWE Raw 2 (Xbox) .fml files

> Reply from eri619
>
> Problem here is that the noesis script is treating all submeshes in the file as a singe one, could there be any adjustment made in the script to separate the submeshes?

There is no such information in those files which is usable to split the meshes down. Read the python script!
## Post #10
- Username: eri619
- Rank: veteran
- Number of posts: 81
- Joined date: Wed May 16, 2012 1:36 pm
- Post datetime: 2021-03-24T17:12:12+00:00
- Post Title: WWE Raw 2 (Xbox) .fml files

These i believe are Vertex Groups/Poly groups.. What do you reckon ?
