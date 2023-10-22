## Post #1
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-10-28T23:48:21+00:00
- Post Title: Infamous First Light Tool [WIP]

A tool for extracting models and textures from the xpps archives. Skeleton/skinning support is almost done. Just needs some more testing.

Tool overview and example exported model



How to use

Load

XPPS : Loads all the meshes inside the XPPS file.
Export

NEX : Exports the model in custom binary format (.nex), intended to be loaded by Noesis. Noesis script for this format : Nex Script
GNF : Exports all the textures in GNF format. Can also be loaded using Noesis.
Note  : Models and textures will be exported into the folder Export.
Download : [https://www.mediafire.com/file/972qkecj ... r.zip/file](https://www.mediafire.com/file/972qkecjn37fipq/InfFLViewer.zip/file)

[WIP] Skeleton/Weights
## Post #2
- Username: esreveR
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Sep 28, 2016 11:52 pm
- Post datetime: 2020-03-26T00:22:31+00:00
- Post Title: Infamous First Light Tool [WIP]

I know this is semi old but please keep me updated, I'm trying to rip infamous second son and they use this exact file format.
## Post #3
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2020-03-27T06:15:39+00:00
- Post Title: Infamous First Light Tool [WIP]

Hi, thank you for the tool, works good, but I want ask how you view the model with textures in the preview?
## Post #4
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-03-27T09:19:51+00:00
- Post Title: Infamous First Light Tool [WIP]

> Reply from esreveR ↑Thu Mar 26, 2020 8:22 am at Thu Mar 26, 2020 8:22 am
>
> 
please keep me updated, I'm trying to rip infamous second son and they use this exact file format.

You can already download the tool. Do you mean keep you updated on skeleton support? I was working on it, but it seemed like there isn't any interest for this, so it is on hold for now.

> Reply from fil1969 ↑Fri Mar 27, 2020 2:15 pm at Fri Mar 27, 2020 2:15 pm
>
> 
I want ask how you view the model with textures in the preview?

Unfortunately you can't. I applied those materials manually in Unity. That is why it looks like the preview.
## Post #5
- Username: esreveR
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Sep 28, 2016 11:52 pm
- Post datetime: 2020-03-29T19:06:59+00:00
- Post Title: Infamous First Light Tool [WIP]

Yeah I meant the skeleton so thats sucks, no worries though.
## Post #6
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2020-03-31T17:25:30+00:00
- Post Title: Infamous First Light Tool [WIP]

I have been waiting ages for this thank you!
i will keep an eye on this thread
## Post #7
- Username: jfmherokiller
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 08, 2011 5:07 am
- Post datetime: 2020-06-18T04:54:30+00:00
- Post Title: Infamous First Light Tool [WIP]

I am joining in to say this tool is cool but can you please also share the actual format of the xpp archives?

As far as my own research has gone ive speculated its a kind of tar format. (info based on visual existence of a possible header footer combo)
## Post #8
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-06-18T06:45:32+00:00
- Post Title: Infamous First Light Tool [WIP]

> Reply from jfmherokiller ↑Thu Jun 18, 2020 12:54 pm at Thu Jun 18, 2020 12:54 pm
>
> 
can you please also share the actual format of the xpp archives?
I haven't researched that. Just used some magic/pattern bytes to find model related sections in the file. So I don't know how the archive can be parsed properly.
## Post #9
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2020-06-18T18:47:41+00:00
- Post Title: Infamous First Light Tool [WIP]

Any news on the tool?
## Post #10
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-06-18T20:36:56+00:00
- Post Title: Infamous First Light Tool [WIP]

> Reply from Faithfullfaun ↑Fri Jun 19, 2020 2:47 am at Fri Jun 19, 2020 2:47 am
>
> 
Any news on the tool?

Nah, still on hold atm  I have plans to return to it. At least to release the skeleton support. Has to wait until July though.
## Post #11
- Username: riccochet
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Aug 11, 2014 9:55 pm
- Post datetime: 2020-11-18T16:06:41+00:00
- Post Title: Infamous First Light Tool [WIP]

> Reply from akderebur ↑Fri Jun 19, 2020 4:36 am at Fri Jun 19, 2020 4:36 am
>
> 
Nah, still on hold atm  I have plans to return to it. At least to release the skeleton support. Has to wait until July though.

Just wondering if you still remember this tool, and if you would release the skeleton support version?
Thanks for all your contributions as always
## Post #12
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-11-18T16:21:43+00:00
- Post Title: Infamous First Light Tool [WIP]

> Reply from riccochet ↑Thu Nov 19, 2020 12:06 am at Thu Nov 19, 2020 12:06 am
>
> 
Just wondering if you still remember this tool, and if you would release the skeleton support version?

Have you tried daemon's tool? [viewtopic.php?f=16&t=22868](https://forum.xentax.com/viewtopic.php?f=16&t=22868)
## Post #13
- Username: riccochet
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Aug 11, 2014 9:55 pm
- Post datetime: 2020-11-25T06:30:58+00:00
- Post Title: Infamous First Light Tool [WIP]

I completely missed that. thanks!
