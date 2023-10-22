## Post #1
- Username: Magilou
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Apr 06, 2021 1:17 am
- Post datetime: 2021-04-05T19:28:43+00:00
- Post Title: Help with a script for 3D models from Everybody's Golf World Tour [PS3]

Hello,
I need help making a script to import models from EGWT into blender, similar to the one made in this old thread by Szkaradek123 that worked for a different game in the same series, (also on ps3):
[viewtopic.php?t=12715](https://forum.xentax.com/viewtopic.php?t=12715)

They're using the same .xb files that need to be unpacked, and I have a few samples from an ISO that I think anyone could practise with (I assume pc_xx is standing for player character):
[https://www.mediafire.com/file/k7w7vxts ... s.rar/file](https://www.mediafire.com/file/k7w7vxtssynjz8b/Everybody%2527s_Golf_WT_Samples.rar/file)

If anyone could help and make a script to unpack the xb files and load the rigged models and animations into blender, I'd be very grateful. The first script may just need a tweak but I don't know much about coding to know what is needed x)

Thanks in advance for to anyone who helps out.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-04-05T20:39:09+00:00
- Post Title: Help with a script for 3D models from Everybody's Golf World Tour [PS3]

> Reply from Magilou ↑Tue Apr 06, 2021 3:28 am at Tue Apr 06, 2021 3:28 am
>
> 
Hello,
...
They're using the same .xb filesHello,
why do you think so? In fact they are different, compare any of the EGWT xb files to a HSGW xb:
.



HSGW_PS3_xb_header.png (10.8 KiB) Viewed 40 times


The "29000000" is a count (41 decimal for said model, used in for m in range(A[1]):)

For most EGWT xb it's 00000003 (50331648 dec.), so not a count, obviously.
Structure is different, too.
## Post #3
- Username: Magilou
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Apr 06, 2021 1:17 am
- Post datetime: 2021-04-05T21:08:16+00:00
- Post Title: Help with a script for 3D models from Everybody's Golf World Tour [PS3]

Sorry, my bad. 

Like I said, I don't know enough about code. Does that mean it can't be done?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-04-05T21:19:14+00:00
- Post Title: Help with a script for 3D models from Everybody's Golf World Tour [PS3]

> Reply from Magilou ↑Tue Apr 06, 2021 5:08 am at Tue Apr 06, 2021 5:08 am
>
> Does that mean it can't be done?At least offzip did  not work (use forum search to understand how it works).

(So you'll need someone to uncompress the .xb files.)
## Post #5
- Username: Magilou
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Apr 06, 2021 1:17 am
- Post datetime: 2021-04-05T23:07:51+00:00
- Post Title: Help with a script for 3D models from Everybody's Golf World Tour [PS3]

Thanks for taking a look for me.

If anyone could have a look at uncompressing the xb files, that'd be very helpful. If it's a lot of work I don't mind sending a donation through paypal for your effort. Just let me know first, so I know if I can afford it   Thanks!
