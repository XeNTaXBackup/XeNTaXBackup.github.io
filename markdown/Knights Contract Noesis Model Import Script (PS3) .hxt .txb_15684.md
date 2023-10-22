## Post #1
- Username: The Chief
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-01-06T04:08:11+00:00
- Post Title: Knights Contract Noesis Model Import Script (PS3) .hxt .txb

Here is a script to import these models with textures.
If someone wants to work on the skeleton ill add support for it into the script.
Just move the texture file (.txb) in the same directory as the model (.hxt)
and it will load it if they are named the same example (chr272.hxt / chr272.txb).
## Post #2
- Username: The Chief
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-01-07T00:40:33+00:00
- Post Title: Knights Contract Noesis Model Import Script (PS3) .hxt .txb

updated script for some more fancy effects and fixed normal's. (Thanks to Mr adults for help on this)

[fmt_KnightsConract_hxt.7z](https://xentaxbackup.github.io/file/12171_fmt_KnightsConract_hxt.7z)
## Post #3
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-01-08T21:30:57+00:00
- Post Title: Knights Contract Noesis Model Import Script (PS3) .hxt .txb

thanks for this! is it possible to get bones and weights?
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-01-09T01:49:57+00:00
- Post Title: Knights Contract Noesis Model Import Script (PS3) .hxt .txb

> Reply from Tosyk
>
> thanks for this! is it possible to get bones and weights?

If someone figures out bone parenting the rest will be very easy.
## Post #5
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-01-09T07:10:29+00:00
- Post Title: Knights Contract Noesis Model Import Script (PS3) .hxt .txb

> Reply from chrrox
>
> Tosyk wrote:thanks for this! is it possible to get bones and weights?

If someone figures out bone parenting the rest will be very easy.if bones have names paranting could be done with maxscript, I mean hardcoded. I did that many times.
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-01-09T13:31:29+00:00
- Post Title: Knights Contract Noesis Model Import Script (PS3) .hxt .txb

there are no bone names.
## Post #7
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-01-09T13:37:54+00:00
- Post Title: Knights Contract Noesis Model Import Script (PS3) .hxt .txb

> Reply from chrrox
>
> there are no bone names.can bones and weights be added without parenting? at least we could parent them manualy.
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-01-09T13:41:52+00:00
- Post Title: Knights Contract Noesis Model Import Script (PS3) .hxt .txb

The skeleton is local.
I could add bones and weights but the bones are in a pile at the models feet and would need to be moved to the correct position.
That is why i needed the bone parenting to transform the bones to the correct position.
If you want to try to move the skeleton to the correct position ill add it for you it might help find what bones are what.
## Post #9
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-01-09T13:47:44+00:00
- Post Title: Knights Contract Noesis Model Import Script (PS3) .hxt .txb

> Reply from chrrox
>
> The skeleton is local.
I could add bones and weights but the bones are in a pile at the models feet and would need to be moved to the correct position.
That is why i needed the bone parenting to transform the bones to the correct position.
If you want to try to move the skeleton to the correct position ill add it for you it might help find what bones are what.if adding bones/weights it's a trivial thing at the point and you can add them today I might do that and post my researches here.
## Post #10
- Username: Tosyk
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-01-09T15:36:21+00:00
- Post Title: Knights Contract Noesis Model Import Script (PS3) .hxt .txb

Here you can try it.
[fmt_KnightsConract_hxt_bone_test.7z](https://xentaxbackup.github.io/file/12191_fmt_KnightsConract_hxt_bone_test.7z)
## Post #11
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-01-09T23:43:09+00:00
- Post Title: Knights Contract Noesis Model Import Script (PS3) .hxt .txb

> Reply from chrrox
>
> Here you can try it.thanks, I managed to raw re-map bones for chr053. here it is:


I've been surprised when I first opened model file in noesis — bones were not in the scene zero. Look at the finger bone groups for both palms — I didn't touch them, just moved in place. these groups makes me think that for bone mapping integers are used, although fractional numbers need to be used instead. I don't know where the right numbers are, maybe they rounds by some noesis function.

I have seen this before — sometimes it happened on early stage of format parsing on the mesh (when it looks too geometrical) and weights (when they are all red or out of place/order).

You should understand that math is not my best side neither the english language. I hope these thoughts helps you to find correct bone mapping.

p.s.: also bones for different models have different names. for ex: head bone name for chr053 is '22' however for chr079 this bone name is '79'.
## Post #12
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-01-10T01:59:54+00:00
- Post Title: Knights Contract Noesis Model Import Script (PS3) .hxt .txb

you should send some of the files so I can see them in max.
## Post #13
- Username: eri619
- Rank: veteran
- Number of posts: 81
- Joined date: Wed May 16, 2012 1:36 pm
- Post datetime: 2017-01-10T17:32:32+00:00
- Post Title: Knights Contract Noesis Model Import Script (PS3) .hxt .txb

could you please update your noesis scriping tutorial with images? the images are dead, you have ignored my bumps in that topic
[viewtopic.php?f=29&t=7760](http://forum.xentax.com/viewtopic.php?f=29&t=7760)

Same is the case with Very Basic model format conversion (Shaiya)

[viewtopic.php?f=29&t=3739](http://forum.xentax.com/viewtopic.php?f=29&t=3739)
## Post #14
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-01-10T18:46:24+00:00
- Post Title: Knights Contract Noesis Model Import Script (PS3) .hxt .txb

> Reply from chrrox
>
> you should send some of the files so I can see them in max.sure (max ver. 2009)
[https://dl.dropboxusercontent.com/u/9919707/chr053.7z](https://dl.dropboxusercontent.com/u/9919707/chr053.7z)
## Post #15
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2019-07-12T22:11:49+00:00
- Post Title: Knights Contract Noesis Model Import Script (PS3) .hxt .txb

Weird bone mapping/ordering indeed. I think I got it mostly working with some little hacks included  Not perfect always, but might be better than nothing. I have attached the updated script.



This script can probably be adapted to "Clash of the Titans" PS3 game too. Almost identical format.
[fmt_KnightsConract_hxt_skeleton.rar](https://xentaxbackup.github.io/file/16464_fmt_KnightsConract_hxt_skeleton.rar)
## Post #16
- Username: lkw019
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jul 18, 2011 9:22 pm
- Post datetime: 2019-09-10T08:19:06+00:00
- Post Title: Re: Knights Contract Noesis Model Import Script (PS3) .hxt .txb

Thanks for your help
