## Post #1
- Username: pepsiguy2
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Apr 17, 2012 10:08 am
- Post datetime: 2020-03-04T01:46:45+00:00
- Post Title: Yukes .yanm Animation Help (WWE2K)

Hello folks, lately we have cracked custom mesh support for WWE 2K games with the help of tekken57's x-rey tool. Our next hope is to crack custom animation support, and if not, at least make them extractable/dumpable.

Currently, we ARE able to splice together custom yanm files by taking parts of other files and inserting them into others via hex to create custom animations for the WWE 2K games. An example of this, was merging Undertaker and Kane's entrance into one for a Brothers of Destruction entrance. 

Our hope is to be able to either dump the yanms into an fbx or other readable format to open in MotionBuilder or 3DSmax and edit them, and be able to export them back into the game as a new yamn (which we know is possible via hex editing yanms)

Jakey from 2Kmodz provided the following writeup on the offsets in the yanm files, as well as a few samples to look at. Included is a yobj character model as well. It's openable with an included maxscript.

> YANM format and its complexities:
>
> 
>
> Offsets 0x00 - 0x03 = YANM string reference
>
> Offsets 0x04 - 0x07 = size of file in 4 bytes, up to POF0 string (eg. 00 00 0F C8). Any offsets in the file start after here.
>
> Offsets 0x08 - 0x09 = Unknown. Havok type? Always 05 00 starting with WWE 2K16, but 04 00 is also accepted.
>
> Offsets 0x0A - 0x0B = Bone count. Last gen (PS3/360) YANMs have a count of 0x3D (61 in decimal). PC is almost always 0x3F (63 in decimal). Removing one disables the last bone in the list.
>
> 
>
> Depending on the YANM format in use, there will be different size bone information.
>
> For PC/some last gen animations, offset 0x0C is the first bone.
>
> 
>
> Bone info:
>
> Offsets 0x00 - 0x03 = packed file size. To get the raw size, you take these 4 bytes and multiply them by an integer. Depending on the next few bytes will indicate whether this integer is 0x04, 0x08 or 0x14 (20 in decimal). To get the packed size, you take the raw size and divide by the integer.
>
> Offsets 0x04 - 0x05 = Unknown. These are a set of bytes that factor into the integer you multiply/divide. Here are some of the values used from what I've seen and the integers used that make up the animation of the bone:
>
> --
>
> 02 04 = 0x14
>
> 03 04 = 0x08
>
> 52 00 = 0x04
>
> 53 00 = 0x04
>
> 43 00 = 0x08
>
> 42 00 = 0x04
>
> 41 00 = 0x04 (used in move animations)
>
> 40 00 = 0x04 (used in move animations)
>
> 23 00 = 0x08
>
> 22 00 = 0x08
>
> --
>
> Offsets 0x06 - 0x07 = Size of bone part up to the next valid bone packed size. This can vary, but usually follows a sequence:
>
> --
>
> 00 10 = used if 41 00 and 40 00 are the two bytes prior
>
> 00 18 = used if 22 00, 42 00, or 02 04 are the two bytes prior
>
> 00 20 = used if 52 00 are the two bytes prior
>
> 00 30 = used if 23 00, 43 00, or 03 04 are the two bytes prior
>
> 00 38 = used if 53 00 are the two bytes prior
>
> --
>
> Offsets 0x08 - 0x0B = Bone. Last gen and PC use different bones. There is a skeletal structure for all of the 63 bones that I can include if requested.
>
> Depending on if this is a move animation or an entrance, this is either the end (signified by the 00 10 earlier) or offsets 0x0C - 0x0F = Length reference 1.
>
> Offsets 0x10 - 0x13 = Size of the previous offset (almost always 00 00 00 02).
>
> Offsets 0x14 - 0x18 = Length reference 2 (the actual data).

Samples: [https://www39.zippyshare.com/v/wzZ9uUIv/file.html](https://www39.zippyshare.com/v/wzZ9uUIv/file.html)
## Post #2
- Username: pepsiguy2
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Apr 17, 2012 10:08 am
- Post datetime: 2020-03-12T01:15:19+00:00
- Post Title: Yukes .yanm Animation Help (WWE2K)

Bumping to offer a bounty of there's interest
## Post #3
- Username: pepsiguy2
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Apr 17, 2012 10:08 am
- Post datetime: 2020-05-10T02:08:05+00:00
- Post Title: Yukes .yanm Animation Help (WWE2K)

Just wanna bump and say the 2KModz community is offering 300+$ for anyone who wants to help. We're working on a new writeup to post here with bone offsets and what we suspect are co-ordinates etc.

Also going to be including xbox360/ps3 samples of the older yanm format as well.

We're currently looking for someone who can dump it to fbx.
## Post #4
- Username: sillirion
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 09, 2016 11:21 pm
- Post datetime: 2020-05-10T20:08:33+00:00
- Post Title: Yukes .yanm Animation Help (WWE2K)

Better to download wwe mobile games, extract assets with Asset studio gui then convert them with motionbuilder.
## Post #5
- Username: pepsiguy2
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Apr 17, 2012 10:08 am
- Post datetime: 2020-05-12T09:33:53+00:00
- Post Title: Yukes .yanm Animation Help (WWE2K)

> Reply from sillirion ↑Mon May 11, 2020 4:08 am at Mon May 11, 2020 4:08 am
>
> 
Better to download wwe mobile games, extract assets with Asset studio gui then convert them with motionbuilder.

Not sure I get the idea. 2K PC is a propretiary format and the mobile games are unity. It's two different engines.
## Post #6
- Username: jakeypearce
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jul 05, 2015 1:25 am
- Post datetime: 2020-05-12T09:38:42+00:00
- Post Title: Yukes .yanm Animation Help (WWE2K)

Not to mention WWE 2K for mobile isn't developed by Yukes, but Visual Concepts and n-Space.
## Post #7
- Username: pepsiguy2
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Apr 17, 2012 10:08 am
- Post datetime: 2020-07-29T09:10:54+00:00
- Post Title: Yukes .yanm Animation Help (WWE2K)

Hey friends. Long time no talk.

Here is our 300$ bounty. [https://www.upwork.com/jobs/~0107c3a478675ff38f](https://www.upwork.com/jobs/~0107c3a478675ff38f)

Let us know if anyone is willing to take the job.
## Post #8
- Username: ShazamAbdou
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Aug 05, 2020 12:14 pm
- Post datetime: 2020-09-16T20:23:39+00:00
- Post Title: Yukes .yanm Animation Help (WWE2K)

Any updates on the project?
## Post #9
- Username: Tinted100
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Oct 27, 2022 10:50 am
- Post datetime: 2022-10-27T02:57:18+00:00
- Post Title: Yukes .yanm Animation Help (WWE2K)

Why can't we just be able to edit parts of an entrance,taunts,movements,and moves?or was this explained already?
## Post #10
- Username: WCG847
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jul 23, 2021 8:48 pm
- Post datetime: 2023-02-01T17:58:32+00:00
- Post Title: Yukes .yanm Animation Help (WWE2K)

It looks to be a custom FBX file. Yukes being using a custom version of the FBX file since 2006 which, iconically was also the year when FBX was developed
## Post #11
- Username: WCG847
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jul 23, 2021 8:48 pm
- Post datetime: 2023-02-20T17:28:50+00:00
- Post Title: Yukes .yanm Animation Help (WWE2K)

Also, I have figured out that YANM is a container that contains a big endian version of .Anim files (NOT 2K22’s version but SVR 11 and under) which means, if you have a tool that converts little endian to big, then you might can actually inject these chunks using the references Jakey shared. We might even convert YANM chunks into little endian for use under SVR 11. To get them into FBX, we need to convert the chunks into floats, so we can parse it into FBX. This writeup is based off Last gen.
## Post #12
- Username: roswell
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Apr 02, 2019 8:00 am
- Post datetime: 2023-03-04T01:22:59+00:00
- Post Title: Yukes .yanm Animation Help (WWE2K)

Maybe someone could reupload samples. Links above are expired.
## Post #13
- Username: WCG847
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jul 23, 2021 8:48 pm
- Post datetime: 2023-04-10T09:30:25+00:00
- Post Title: Yukes .yanm Animation Help (WWE2K)

Coming back on this, I don’t think Yuke’s use FBX. I think they use a binary version of Biovision Hierarchy (BVH)
## Post #14
- Username: RRXX23
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Apr 17, 2023 5:49 pm
- Post datetime: 2023-04-17T10:32:51+00:00
- Post Title: Yukes .yanm Animation Help (WWE2K)

Hello so...it's 2023 any updates here?
## Post #15
- Username: dannydickens
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Apr 26, 2023 5:38 pm
- Post datetime: 2023-04-26T09:43:17+00:00
- Post Title: Yukes .yanm Animation Help (WWE2K)

Is version 1.0.0 the latest version?


[cuphead](https://cuphead9.com)
