## Post #1
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2009-06-24T06:18:12+00:00
- Post Title: nvidia model help?

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-06-24T13:05:09+00:00
- Post Title: nvidia model help?

That tutorial seems to be really good, even containing sample code.
Why don't you use that as a base?
## Post #3
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2009-06-24T13:30:24+00:00
- Post Title: nvidia model help?

> Reply from Rheini
>
> That tutorial seems to be really good, even containing sample code.
Why don't you use that as a base?

I'm really just looking for a way to extract the .obj data from the .nmb file so as load the mesh in a 3d app, but although I have thoroughly examined that tutorial 
it is of no use to my level of knowledge with reading and understanding code/hex which is level 0 at the moment. 

So any help on this would be really great.
## Post #4
- Username: gamemaster
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jul 21, 2008 8:07 am
- Post datetime: 2009-07-22T18:54:39+00:00
- Post Title: nvidia model help?

Has anyone had any luck with this?Ive been dying for an nmb converter/importer for ever!This should be a top priority for all you programmers.Dont waist time on other extractors only focus on this!

I would love to be able to have this so I can put the Adriane or luna models into unreal3 and other games!

I can program little things like a hello world program but decrypting file formats is about as complicated as rocket science.So ill just leave that up to the those who can actually do it.
## Post #5
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-07-22T18:56:59+00:00
- Post Title: nvidia model help?

So go learn programming and do it yourself.
## Post #6
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2009-07-23T14:08:48+00:00
- Post Title: nvidia model help?

[viewtopic.php?f=16&t=3108](http://forum.xentax.com/viewtopic.php?f=16&t=3108)

There is a link in this thread to a program that converts Dawn into wavefront .obj format.
## Post #7
- Username: gamemaster
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jul 21, 2008 8:07 am
- Post datetime: 2009-07-23T16:17:55+00:00
- Post Title: nvidia model help?

Im the one who posted that! It only lets you convert the dawn model. It doesnt work on any of the other ones.
## Post #8
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2009-07-26T00:39:02+00:00
- Post Title: nvidia model help?

My bad, I wasn't paying attention   ...I was looking at the Dawn model though. I think there are way too many triangles on that mesh for you to use in UT3 or any other game with current technology. I think it uses over 100000 tris. The largest modded Oblivion female bodies have around 23000 tris. Marcus Fenix from GOW (a UT3 engine game) uses 11790 tris. The Uber Reaver, which seems to be the most detailed UT3 engine character mesh that I could find on short notice, has only 45432 tris.
## Post #9
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2009-07-26T11:57:38+00:00
- Post Title: nvidia model help?

Average character model in UT3 is around 15K tris, give or take.

Having Dawn or ANY other model from nVidia, will not only slap you with a sue card from the lawyers, but also, the models will make your game chug so hard, you might as well not play it.

Seriously, you'd have an easier time asking a modeler and texturers to create this character for you.
## Post #10
- Username: gamemaster
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jul 21, 2008 8:07 am
- Post datetime: 2009-07-26T17:59:48+00:00
- Post Title: nvidia model help?

First of all I have managed to get models with even more polys than that into games like crysis and half life 2 just fine.About 20 to 30k.Its also easy to reduce the number of polys. Also its perfectly legal as long as you dont make money of it.An example would be the master chief and samus models that were put into UT3.
## Post #11
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2009-07-26T21:17:25+00:00
- Post Title: nvidia model help?

It doesn't matter if you got 20K or 30K in a game and here is why: CE2 is able to import models which weigh in as much as 1 million polygons, meaning 2 million tri's, yes I tried that.
But tell me, are you really going to stress you PC to render 1 single model when it can render dozens, even hundreds with less polycount?

And any self-respecting modeler will know this much: Automatic poly-reduction is a myth since it destroys keypoints in your model (such as joints, facial topology, and the overall silhouette of your model).

Also, funny fact, but unless a developer clearly states that their models are free-IP reign, no, you can still be slapped on with a case of being sued. A developing team some time ago were making a small mod for HL2 which was essentially a Halo-esque mod, they created everything from scratch, even the models, nothing was ripped.
However, they were sent a C&D letter at around 60% of the project in, even if everything they had was scratch made.
Same story with another mod for an RTS game, a small team was creating a Halo RTS game in DOW, yet got sent a C&D letter. Maybe it was because Halo Wars was right around the corner, but still, nothing ripped and loosely based upon Halo.

Whatever mate fills you mate, I'm just telling you that you'll have an easier time with premade characters from UT3 mods rather then trying to get this one, especially considering that many of us aren't interested in them (them being the nVidia Tech Demo's).
## Post #12
- Username: gamemaster
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jul 21, 2008 8:07 am
- Post datetime: 2009-07-27T02:41:52+00:00
- Post Title: nvidia model help?

This is a little of topic but someone managed to get a reduced poly version of the dawn model into ut2003.

[http://skincity.beyondunreal.com/index. ... fos&id=428](http://skincity.beyondunreal.com/index.php?section=models&action=show_infos&id=428)
## Post #13
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2009-07-27T14:12:45+00:00
- Post Title: nvidia model help?

ace, actually new engines dont care so much about polys, its actualy more vital with texture space now. In my engine i can import model that is 1million+ polys and walk around. But of course having low poly + normal map is the way to go anyway
## Post #14
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2009-07-27T16:57:44+00:00
- Post Title: nvidia model help?

...
...
...
...Le Sigh...seriously, le sigh...
## Post #15
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2009-07-30T19:02:45+00:00
- Post Title: nvidia model help?

even though having the nvidia models would be pointless... being there like a godzillion polygons. I'd still like to get my hands on them.. the nvidia demos are beautiful, and none of the PC rippers can phase them  very depressing.

anyone try to contact the guy who made the dawn extractor? I bet he could give us some insight with the format
## Post #16
- Username: gics
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Dec 19, 2009 4:12 pm
- Post datetime: 2009-12-19T08:46:16+00:00
- Post Title: Re: nvidia model help?

So no update for "dawn3dmodel", huh
