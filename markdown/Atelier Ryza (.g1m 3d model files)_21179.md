## Post #1
- Username: nekoknight
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Oct 31, 2018 10:27 am
- Post datetime: 2019-09-27T23:26:21+00:00
- Post Title: Atelier Ryza (.g1m 3d model files)

The .g1t textures can be converted with Noesis. The elixir.gz archives can be decompressed with QuickBMS (futuremark.bms) revealing the .g1m model files.

I tried the tools below and unfortunately none of them were able to handle this file. 

- FF dissidia NT tools
- DoaTool
- gm1tools
- Steven's Gas Machine

I does look like SGM is able to get the armature by using (Dragon quest heroes Slime edition). But the Mesh output is empty. Here are some sample files from what I believe to be the main character.   [http://www.mediafire.com/file/7h7xhu8ep ... A.zip/file](http://www.mediafire.com/file/7h7xhu8ep6iz4ql/PC00A.zip/file)

Please help... I need those thighs in my life.
## Post #2
- Username: lisomn
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Feb 07, 2018 9:20 pm
- Post datetime: 2019-09-28T16:53:11+00:00
- Post Title: Atelier Ryza (.g1m 3d model files)

Because there are some strange 0×00 data interference in the data.
Delete the extra ones
 can rip them.
## Post #3
- Username: nekoknight
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Oct 31, 2018 10:27 am
- Post datetime: 2019-09-28T17:25:50+00:00
- Post Title: Atelier Ryza (.g1m 3d model files)

Wow great work Lisomn.

I am still having trouble on my side. I tried removing anything that stood out by using an g1m from a previous game as a reference. but unfortunately that did not work out. Can you please show me the strange 0×00 that you are referring to?

Also, did you use Steven's Gas Machine to rip the model afterwards? If so, what game did you pick from the drop down?
## Post #4
- Username: lisomn
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Feb 07, 2018 9:20 pm
- Post datetime: 2019-09-28T18:25:57+00:00
- Post Title: Atelier Ryza (.g1m 3d model files)

There is additional 0x00 data in the 07000100 block of the G1MG block.
07000100 block storage area index

Prompt when I use the ffsnt tool
OutOfMemoryException is abnormal.

Lol
## Post #5
- Username: nekoknight
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Oct 31, 2018 10:27 am
- Post datetime: 2019-09-28T20:11:51+00:00
- Post Title: Atelier Ryza (.g1m 3d model files)

That does not make much sense to me unfortunately. Looks like I have some reading to do.

Hopefully someone will be able to use that information to make a tool for these files.
## Post #6
- Username: lisomn
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Feb 07, 2018 9:20 pm
- Post datetime: 2019-09-28T22:13:49+00:00
- Post Title: Atelier Ryza (.g1m 3d model files)

Not just relying on tools
You need to know these files
Otherwise you will always wait for someone else to provide you with tools

Maybe my tool will be finished soon.XD
## Post #7
- Username: kurokairaku
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Aug 13, 2015 6:54 am
- Post datetime: 2019-10-16T15:17:18+00:00
- Post Title: Atelier Ryza (.g1m 3d model files)

> Reply from lisomn ↑Sun Sep 29, 2019 6:13 am at Sun Sep 29, 2019 6:13 am
>
> 
Not just relying on tools
You need to know these files
Otherwise you will always wait for someone else to provide you with tools

Maybe my tool will be finished soon.XD

Any chance I could convince you to grace us with a small little hint for the heathens who struggle to understand this stuff? Like maybe the offset to exactly where this 0x00 data we need to delete, and wether its only 1 or multiple. It would be nice for you to grace us mortals with a rock, to potentially climb to the same level as thine godhood and potentially gain understanding as a collective and end the confusions once and for all.

In layman's term, since no tool does exist I need to figure this out myself but I am rather inexperienced but maybe a thrown bone might help me get on the right track?
## Post #8
- Username: kurokairaku
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Aug 13, 2015 6:54 am
- Post datetime: 2019-10-21T16:49:02+00:00
- Post Title: Atelier Ryza (.g1m 3d model files)

> Reply from lisomn ↑Sun Sep 29, 2019 6:13 am at Sun Sep 29, 2019 6:13 am
>
> 
Not just relying on tools
You need to know these files
Otherwise you will always wait for someone else to provide you with tools

Maybe my tool will be finished soon.XD

I managed to modify an existing tool that was able to read g1ms. I mostly had to hotload skeleton part from the other g1m as a bit of a hack but the mesh itself is pretty spaghetti like. While the program appears to load in weights, and normals proper, the verts get a little stretchy and UV's seems to be messed up as well.

I ask again if you could throw a bone regarding what was supposed to "additional" data. Perhaps the exact offset of the above model and such might help. I mean it would be nice.
## Post #9
- Username: alictzelt
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 27, 2017 6:02 am
- Post datetime: 2019-10-22T06:20:51+00:00
- Post Title: Atelier Ryza (.g1m 3d model files)

> I managed to modify an existing tool that was able to read g1ms. I mostly had to hotload skeleton part from the other g1m as a bit of a hack but the mesh itself is pretty spaghetti like. While the program appears to load in weights, and normals proper, the verts get a little stretchy and UV's seems to be messed up as well.
>
> 
>
> I ask again if you could throw a bone regarding what was supposed to "additional" data. Perhaps the exact offset of the above model and such might help. I mean it would be nice.

what existing tool you use?
I try use Steven's Gas Machine, and got obj and smc file. SMC file is useless, but obj file work, also UV's seems good, Only mesh of side front hair has little damaged.
## Post #10
- Username: kurokairaku
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Aug 13, 2015 6:54 am
- Post datetime: 2019-10-22T16:36:08+00:00
- Post Title: Atelier Ryza (.g1m 3d model files)

> Reply from alictzelt ↑Tue Oct 22, 2019 2:20 pm at Tue Oct 22, 2019 2:20 pm
>
> 

I managed to modify an existing tool that was able to read g1ms. I mostly had to hotload skeleton part from the other g1m as a bit of a hack but the mesh itself is pretty spaghetti like. While the program appears to load in weights, and normals proper, the verts get a little stretchy and UV's seems to be messed up as well.

I ask again if you could throw a bone regarding what was supposed to "additional" data. Perhaps the exact offset of the above model and such might help. I mean it would be nice.


what existing tool you use?
I try use Steven's Gas Machine, and got obj and smc file. SMC file is useless, but obj file work, also UV's seems good, Only mesh of side front hair has little damaged.

I modified a private build of Ploaj's Tool which I used for FE3H. lately I've been helping make improvements but with ploaj being so busy (and my self being otherwise inexperienced) I havn't been able to get ploaj to update his tool in a while. Every fix of mine either barely works or I am a bit inexperienced to know exacrly whats going on.

which is why I was hoping to get lisomn to throw me a bone on what exactly was the extra data within the G1MG data storage. was the 07000100 the litteral hex that was before it since there is such a hex before the IndexBuffer area, if so what was the 0x00 data. As it stands as his tool builds the UV's it seems that something gets skipped or otherwise put in the wrong place since I noticed invalid numbers being inserted into the UV array.
## Post #11
- Username: alictzelt
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 27, 2017 6:02 am
- Post datetime: 2019-10-22T20:01:28+00:00
- Post Title: Atelier Ryza (.g1m 3d model files)

> which is why I was hoping to get lisomn to throw me a bone on what exactly was the extra data within the G1MG data storage. was the 07000100 the litteral hex that was before it since there is such a hex before the IndexBuffer area, if so what was the 0x00 data.
At first, I was curious about this. 
I use nekoknight's provided file. So there are 2 files .g1m (PC00A_MODEL.g1m and PC00A_MODEL_default.g1m). First I try to rip it using SGM, only one file (PC00A_MODEL.g1m) work. It only show the bones. As lisomn said "Because there are some strange 0×00 data interference in the data. Delete the extra ones can rip them." I open both file using tiny hexer to find out what is different from that file. On the first row of 0×00, I found the difference.
the header file written "_M1G7300D"  I delete the extra ones to be "_M1G7300" then i can rip it using SGM
## Post #12
- Username: kurokairaku
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Aug 13, 2015 6:54 am
- Post datetime: 2019-10-23T00:27:21+00:00
- Post Title: Atelier Ryza (.g1m 3d model files)

> Reply from alictzelt ↑Wed Oct 23, 2019 4:01 am at Wed Oct 23, 2019 4:01 am
>
> 

which is why I was hoping to get lisomn to throw me a bone on what exactly was the extra data within the G1MG data storage. was the 07000100 the litteral hex that was before it since there is such a hex before the IndexBuffer area, if so what was the 0x00 data.

At first, I was curious about this. 
I use nekoknight's provided file. So there are 2 files .g1m (PC00A_MODEL.g1m and PC00A_MODEL_default.g1m). First I try to rip it using SGM, only one file (PC00A_MODEL.g1m) work. It only show the bones. As lisomn said "Because there are some strange 0×00 data interference in the data. Delete the extra ones can rip them." I open both file using tiny hexer to find out what is different from that file. On the first row of 0×00, I found the difference.
the header file written "_M1G7300D"  I delete the extra ones to be "_M1G7300" then i can rip it using SGM

I was actually mislead by the "strange 0x00" things. I don't think your idea of it was what he meant. But the tool I used apperently actually properly gathered all data. My problem was how it was then being read into a generic mesh and skeleton which is what the tool actually exports. I am struggling with different things now but I guess I no longer need Lisomn's help. However he still figured it out far faster than me so I am nowhere near his level.

progress so far: 
.

Need to hook in my skeleton portions, properly load rigging and then I'm golden. I hope I can manage >.<. I ended up getting this far with no ones help since no one helped just yet. So to be honest, I scarely believe this would work for anything other than the PC00A model. I need to find an actual dump to try it on others.
## Post #13
- Username: alictzelt
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 27, 2017 6:02 am
- Post datetime: 2019-10-23T02:41:46+00:00
- Post Title: Atelier Ryza (.g1m 3d model files)

> My problem was how it was then being read into a generic mesh and skeleton which is what the tool actually exports.
I think we have same problem. 

I dont have experience modified ripping tool. So I just trying provided tool, but not luck to get what I want
## Post #14
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2019-10-29T12:23:51+00:00
- Post Title: Atelier Ryza (.g1m 3d model files)

bump up since this hentai game is on steam now
## Post #15
- Username: lisomn
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Feb 07, 2018 9:20 pm
- Post datetime: 2019-10-29T15:49:35+00:00
- Post Title: Atelier Ryza (.g1m 3d model files)

> Reply from kurokairaku ↑Wed Oct 23, 2019 8:27 am at Wed Oct 23, 2019 8:27 am
>
> 
alictzelt wrote: ↑Wed Oct 23, 2019 4:01 am

which is why I was hoping to get lisomn to throw me a bone on what exactly was the extra data within the G1MG data storage. was the 07000100 the litteral hex that was before it since there is such a hex before the IndexBuffer area, if so what was the 0x00 data.

At first, I was curious about this. 
I use nekoknight's provided file. So there are 2 files .g1m (PC00A_MODEL.g1m and PC00A_MODEL_default.g1m). First I try to rip it using SGM, only one file (PC00A_MODEL.g1m) work. It only show the bones. As lisomn said "Because there are some strange 0×00 data interference in the data. Delete the extra ones can rip them." I open both file using tiny hexer to find out what is different from that file. On the first row of 0×00, I found the difference.
the header file written "_M1G7300D"  I delete the extra ones to be "_M1G7300" then i can rip it using SGM


I was actually mislead by the "strange 0x00" things. I don't think your idea of it was what he meant. But the tool I used apperently actually properly gathered all data. My problem was how it was then being read into a generic mesh and skeleton which is what the tool actually exports. I am struggling with different things now but I guess I no longer need Lisomn's help. However he still figured it out far faster than me so I am nowhere near his level.

progress so far: 
.

Need to hook in my skeleton portions, properly load rigging and then I'm golden. I hope I can manage >.<. I ended up getting this far with no ones help since no one helped just yet. So to be honest, I scarely believe this would work for anything other than the PC00A model. I need to find an actual dump to try it on others.

hi kurokairaku
I read the source code of gms
Almost fully understand all the data blocks in g1m
But indexing the wrong bone when indexing the bone weight
QoQ
## Post #16
- Username: zerotaku5123
- Rank: beginner
- Number of posts: 31
- Joined date: Tue Aug 06, 2019 8:17 am
- Post datetime: 2019-10-30T04:27:26+00:00
- Post Title: Re: Atelier Ryza (.g1m 3d model files)

Will you share your model once finished?
## Post #17
- Username: Taigei
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 06, 2019 8:30 am
- Post datetime: 2019-11-06T00:32:56+00:00
- Post Title: Re: Atelier Ryza (.g1m 3d model files)

Anyone figure out how to convert the files back to g1m after your done messing with it in blender?
## Post #18
- Username: kurokairaku
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Aug 13, 2015 6:54 am
- Post datetime: 2019-11-12T17:30:59+00:00
- Post Title: Re: Atelier Ryza (.g1m 3d model files)

> Reply from zerotaku5123 ↑Wed Oct 30, 2019 12:27 pm at Wed Oct 30, 2019 12:27 pm
>
> 
Will you share your model once finished?

Bit late on the reply so maybe you already found out but yeah you can find my models through my Deviantart, just google em, or atleast my name.
## Post #19
- Username: icoee
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jan 31, 2018 3:50 pm
- Post datetime: 2019-11-17T12:39:38+00:00
- Post Title: Re: Atelier Ryza (.g1m 3d model files)

> Reply from lisomn ↑Sun Sep 29, 2019 12:53 am at Sun Sep 29, 2019 12:53 am
>
> 
Because there are some strange 0×00 data interference in the data.
Delete the extra ones
 can rip them.

Thanks very much. It works. But there are some mesher damaged. How to fix them?
[QQ图片20191117191240.png](https://xentaxbackup.github.io/file/17079_QQ图片20191117191240.png)
