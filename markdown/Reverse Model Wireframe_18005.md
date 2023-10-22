## Post #1
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-04-20T15:15:12+00:00
- Post Title: Reverse Model Wireframe

For a long time I'd been tired of triangulate game models and I found they would be more pleasing to the eyes with clean and tidy wireframes like these:
[](https://imgur.com/ooa69EN)
[](https://imgur.com/z46CnJS)

Technically it's not very appropriate to be regarded as reversing wireframe, but merely a custom quadifying algorithm. 
I believe that the Quadify option in 3Ds Max may be based on similar principles. However sometimes it appears to perform better than 3Ds Max coz it's more conservative instead of being risky:


It's difficult to be 100% accurate unless the face buffer is ideal, but an accuracy above 90% is quite feasible. So for me the above results are quite acceptable.

Of course a 100% reversing is possible:


A simple explanation of the algorithm is available [here](http://forum.xentax.com/viewtopic.php?p=140515#p140515).

A more universal method [here](viewtopic.php?p=160497#p160497).
## Post #2
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2018-04-20T15:54:30+00:00
- Post Title: Reverse Model Wireframe

Every model is triangulated at the end anyway, so I suppose it's for esthetics only.
It looks much better that triangulated ones for sure, but only usage of this feature would be only for modelers.
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-04-21T03:26:45+00:00
- Post Title: Reverse Model Wireframe

> Reply from PredatorCZ
>
> Every model is triangulated at the end anyway
Yep I know coz that's how GPU works.

> Reply from PredatorCZ
>
> It looks much better that triangulated ones for sure
I'll take the "that" as "than" then.  

> Reply from PredatorCZ
>
> ...so I suppose it's for esthetics only.
...but only usage of this feature would be only for modelers.
I believe that there's still a difference between a game model and a so-called game art. And all game arts are quadrilateral before they're ported into the game engine, I suppose, since they need to be rigged and animated. 
I'm not some kind of obsessive of esthetics but I think it's worth a try if we can improve the model to a better stage, especially if you show no interest in modding a game.
## Post #4
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2018-04-21T08:36:19+00:00
- Post Title: Reverse Model Wireframe

> Reply from Bigchillghost
>
> 
I'll take the "that" as "than" then.
Nice catch, you got me there sir.

> Reply from Bigchillghost
>
> 
I suppose, since they need to be rigged and animated.
Rigging doesn't need quadrified meshes, riggers are working on vertex level in most cases.
They rely on soft selection, mirror, and even painter like tools, but they all works on vertex level.
Difference can be with morph targets, since the best way is to create multiple meshes and then feed them into Morphing tool.

> Reply from Bigchillghost
>
> 
especially if you show no interest in modding a game.
This, I think it's essential to have quad meshes for modding.
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-04-21T09:40:33+00:00
- Post Title: Reverse Model Wireframe

> Reply from PredatorCZ
>
> 
Rigging doesn't need quadrified meshes
Technically indeed it doesn't, coz weights affect only vertices. But I usually hear modelers complaining a lot about the troubles result from triangulate models and that's why they need good topology. Well this might not be the same thing we're talking about.

> Reply from PredatorCZ
>
> This, I think it's essential to have quad meshes for modding.
Thought you agreed that rigging doesn't need quadified meshes. Never modded a game so I have no saying on that.
## Post #6
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-04-22T06:34:57+00:00
- Post Title: Reverse Model Wireframe

I too was interested in this from first day I discovered this amazing 3D world of possibilities.
From a modeler/3D artist point of view quads are better and much more easy to work with.

The option in 3dsMax though is never accurate and very messy, in fact most of times makes a triangulated mesh worse after quadifying it.

Its a bit confusing as to what exactly are you saying with this line though.

> the Quadify option in 3Ds Max may be based on similar principles. However sometimes it appears to perform better than 3Ds Max
Your talking about same thing it seems, unless you meant to say something else your using besides the Quadify option inside 3dsMax, right?
## Post #7
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-04-22T11:14:59+00:00
- Post Title: Reverse Model Wireframe

> Reply from mono24
>
> I too was interested in this from first day I discovered this amazing 3D world of possibilities.
Good to have someone that agrees on it.

> Reply from mono24
>
> The option in 3dsMax though is never accurate and very messy, in fact most of times makes a triangulated mesh worse after quadifying it.
It depends on different objects to be dealt with. Obviously simple objects are easier to handle. Actually I don't think there'd be a perfect method for all cases as a slight unexpected modification on the wireframe could possibly affect the whole result.

> Reply from mono24
>
> 
Your talking about same thing it seems, unless you meant to say something else your using besides the Quadify option inside 3dsMax, right?
I'd been talking about my custom quadifying algorithm all the time so the "it" does not refer to the Quadify option in 3Ds Max. You'd understand what I meant if you had taken a look at the pic below that.
## Post #8
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-04-23T19:00:19+00:00
- Post Title: Reverse Model Wireframe

> Reply from Bigchillghost
>
> I'd been talking about my custom quadifying algorithm all the time so the "it" does not refer to the Quadify option in 3Ds Max. You'd understand what I meant if you had taken a look at the pic below that.
That's exactly what I understood the first time, but it was unclear also, so I think its cool that someone has a better approach and understanding at it, and actually having something to work with.
Big question though, you plan on making a Max script perhaps?
Or your keeping it for personal use, because id sure love to give it a try/test or what ever the case may be.
## Post #9
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-04-24T01:15:29+00:00
- Post Title: Reverse Model Wireframe

> Reply from mono24
>
> Big question though, you plan on making a Max script perhaps?
Nope. Not familiar with MaxScript and I'm too lazy to learn another scripting language. I implemented it in C, and placed it in every obj convertor I wrote to obtain results containing both the original triangulate game models and the quadified ones. But after I'd implemented another algorithm to 100% reverse engineering the wireframe as rendered, I just treat it as an alternative solution, thus it didn't go much further.
## Post #10
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2018-04-24T08:06:19+00:00
- Post Title: Reverse Model Wireframe

Have you tested blenders "tris to quads"?

Open model
Edit mesh
Select all
"tris to quads"

I can do a test if you have a model for me
## Post #11
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-04-24T15:07:45+00:00
- Post Title: Reverse Model Wireframe

> Reply from pixellegolas
>
> Have you tested blenders "tris to quads"?
No, I havn't. Blender is only used for format exchange purpose to me. I wouldn't even know that there's a "tris to quads" option in this software if you hadn't mentioned it. But what I need is an independent algorithm that does not rely on any 3D softwares.
## Post #12
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-04-24T15:21:44+00:00
- Post Title: Reverse Model Wireframe

> Reply from Bigchillghost
>
> I implemented it in C, and placed it in every obj convertor I wrote.
That sounds nice, anything available to try? Id love to try that convertor you speak of, or its just for your personal eyes only?
## Post #13
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-04-25T02:25:48+00:00
- Post Title: Reverse Model Wireframe

> Reply from mono24
>
> Id love to try that convertor you speak of
No need. It's already been tested and proven that it only works for a few games. But I'm not going to release the tools for these games as I don't expect to see their models everywhere. 
I'm here just to show the possibility, and inspire people with this new idea. It's not difficult at all if someone that has even a little programing knowledge is interested in this too.
So you see? The point is about the quadifying algorithm,  or related discussion, not any specific tools.
## Post #14
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-04-25T04:40:54+00:00
- Post Title: Reverse Model Wireframe

> Reply from Bigchillghost
>
> So you see? The point is about the quadifying algorithm,  or related discussion, not any specific tools.
Thank you for clarifying, and I guess who ever is a coder/programmer can take it in to consideration as a viable option.
## Post #15
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-04-27T12:23:35+00:00
- Post Title: Reverse Model Wireframe

> Reply from mono24
>
> anything available to try?
Well, I found it also works for another game I don't care much about. And the list could be expanded in the future maybe. So yes you've got something to try with now. 


 GSTDQuadifyer.rar
(7.13 KiB) Downloaded 117 times


Grab the sample files here:
[viewtopic.php?p=139489#p139489](http://forum.xentax.com/viewtopic.php?p=139489#p139489)
Same usage as the one I posted in that thread at the same page:
[viewtopic.php?p=139563#p139563](http://forum.xentax.com/viewtopic.php?p=139563#p139563)

You can create a clone of the triangulate one in 3Ds Max and use the Quadify option on it then compare it with the one quadified by my tool. Have fun!
## Post #16
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-04-28T11:07:36+00:00
- Post Title: Re: Reverse Model Wireframe

A local compare on the face:
## Post #17
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-04-29T00:34:10+00:00
- Post Title: Re: Reverse Model Wireframe

> Reply from Bigchillghost
>
> Same usage as the one I posted in that thread at the same page
Thank you for your example tool for that game only, but, it seems they both have same result:
No matter how I run: GSTDQuadifyer.exe it has same result as: GSTDConv.exe
And that is just extraction of rendermesh_0 / rendermesh_1. Nothing else.
## Post #18
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-04-29T01:00:01+00:00
- Post Title: Re: Reverse Model Wireframe

> Reply from mono24
>
> 
Thank you for your example tool for that game only
Yeah, I also want to present more.

> Reply from mono24
>
> 
No matter how I run: GSTDQuadifyer.exe it has same result as: GSTDConv.exe
And that is just extraction of rendermesh_0 / rendermesh_1. Nothing else.
What do you mean by "same result"? Did you get the obj files?
## Post #19
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-04-29T04:22:08+00:00
- Post Title: Re: Reverse Model Wireframe

> Reply from Bigchillghost
>
> Did you get the obj files?
That's what they both seem to do identically, that's what I meant, it only export obj files, nothing is quadifyed by the tool, unless I am missing something? Everything is presented in triangles.
## Post #20
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-04-29T05:05:16+00:00
- Post Title: Re: Reverse Model Wireframe

> Reply from mono24
>
> it only export obj files
Good. Then the tool worked without issues.

> Reply from mono24
>
> unless I am missing something? Everything is presented in triangles.
Have you imported the files into 3Ds Max? Or you're using other 3D softwares that doesn't support quads(like Noesis and the 3D Builder for Win10)?

The quadified meshes will be stored in the same obj file as the triangulate ones, but with the "_quadify" suffix. You'll need to filter and separate them from the original game meshes mamually in Max.
## Post #21
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-04-30T01:56:34+00:00
- Post Title: Re: Reverse Model Wireframe

Ah, got it now.
Amazing results, I hope you will consider in maybe making a universal 3dsMax Quadify selectable option same way as the built in one.
I've always wanted an accurate option as yours, if I can support this project let me know, I am very serious about it, I hope more can get on board, the results are stunning, period.

Thank you for allowing me to test, much appreciate it.
## Post #22
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-05-01T03:54:43+00:00
- Post Title: Re: Reverse Model Wireframe

> Reply from mono24
>
> I hope you will consider in maybe making a universal 3dsMax Quadify selectable option same way as the built in one.
I don't think it will be a practical idea, at least not in a short term, so don't count on me. Yeah the results might look great but don't be deceived. This algorithm relies heavily on an ideal face indices buffer, and the filter rules of determining whether two adjacent triangles should be restructured as a quadrilateral might vary from game to game, or model to model. So usually you need to figure out the proper filter rules for desired medels, and that's why I insist on using it within the extraction process. 

> Reply from mono24
>
> if I can support this project let me know, I am very serious about it
The discussion on related algorthms are open so be my guest if you're going to develop your own tool.
## Post #23
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-05-01T14:11:06+00:00
- Post Title: Re: Reverse Model Wireframe

A test on a high poly model I downloaded on the web some years ago, don't remember where exactly though:
[](https://imgur.com/6gJ4y3i)

With 3 filter rules enabled I managed to get a 100% accurate result:
[](https://imgur.com/YtYXtrN)
[](https://imgur.com/FklVw1X)
## Post #24
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-05-13T10:58:36+00:00
- Post Title: Re: Reverse Model Wireframe

Alright, time for introducing some main ideas of the algorithm.

To quadify a model, there could be a lot of potential methods, but a natural and simple one would be focusing on the face buffer.
Hence it comes the problem: how to determine which two triangles should form a new quadrangle? For convenience of explanation, let's discuss the problem with the aid of a simple image.

As you can see, in the following image, the triangle ABC (denoted by ΔABC, the same below) is surrounded by another 3 triangles: ΔADB, ΔBFC and ΔACE. The cyclic arrows represent the orientation of each triangle.



Tri4.jpg (39.71 KiB) Viewed 445 times


Let's assume that ΔABC and ΔACE should form a quadrangle, and they share the same edge AC. So for a given triangle ΔABC, whose face indices would be "a b c",
its adjacent triangle ΔACE's face indices could be "a c e", "c e a", or "e a c". 
Therefore we have 3 combinations of the actual face indices for these two triangles:

```
|a c e|		  		|c e a|		  		|e a c|

```

Say ΔACE's face indices are "a c e" for example, then all you need to do is locate to these two triangles, the combination of who's face indices meets with the form of |a b c|a c e|, and create a new quadrangle by removing the shared edge AC. Taking into account the orientations of both triangles, the indices of the quadrangle would be "a b c e". Actually the indices are the same if ΔACE's face indices are "c e a" or "e a c". These combinations are used only to filter the two trangles ΔABC and ΔACE from the face buffer, and they won't influence the orientation of the quadrangle unless they're not of the same vertex.

But what if ΔABC should form a quadrangle with ΔADB, or ΔBFC? So in total we get 9 combinations, which I call the filter rules:

```
|	adb	|	cbd	|	bdc	|	dcb	|	bad	|	cda	|	
-------------------------------------------------------------------------------------------------
|	abc	|	abc	|	abc	|
|	acd	|	dba	|	dac	|

```

This is based on the conditions that you don't need to modify the face buffer, otherwise some of them can actually be regarded as the same rule, like |abc|adb| and |abc|acd| coz they're symmetric in the horizontal direction.

Luckily the game engines usually use only a few rules listed above to break a quadrangle into two triangles, which usually are stored adjacently. 
For example, say there're two quadrangles: 

```
f 2 5 6 3

```

its triangle face indices could be 

```
f 3 4 1
f 2 5 6
f 6 3 2

```

That's what 3Ds Max usually do when you export to obj as triangles. Recreate the original quadrangles simply by dividing them into  groups per two triangles in the order of how they're stored.
If the original model contains also triangles, so long as they're not inserted between the two triangles generated from a quadrangle, usually you can ignore the side effects.

```
f 3 4 1		-->		f 1 2 3 4
f 1 4 5		-->		f 1 4 5
f 7 5 6
f 6 8 7		-->		f 7 5 6 8

```
## Post #25
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-05-13T11:52:48+00:00
- Post Title: Re: Reverse Model Wireframe

Things get more complicated when two triangles adjacent in 3D space are not stored adjacently in the face buffer.
But it isn't the dead end as long as the quadrangles are broken into triangles in strict accordance with filter rules. The less rules it uses, the more accurate the results would be, of course.
A good example would be The Witcher 3: Wild Hunt, which uses only 1 filter rule although most of the triangles were not adjacent in the buffer.

[](https://imgur.com/TSyDC73)
[](https://imgur.com/B84vBuA)
[](https://imgur.com/1LHc4o3)

However it is not so lucky for Rise of the Tomb Raider, which uses 2 filter rules(for the most common cases). I tried 4 variant methods but still havn't got a satisfied result yet.
[](https://imgur.com/LTCtqnd)[](https://imgur.com/IVo5tia)
[](https://imgur.com/MJZRvrc)[](https://imgur.com/ShCjQEa)
[](https://imgur.com/DYzEN6v)[](https://imgur.com/aeB4fnI)

Quick compare:
[](https://imgur.com/qNPyBYU)
## Post #26
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-05-17T15:46:10+00:00
- Post Title: Re: Reverse Model Wireframe

Seems I found the ultimate solution  :
[](https://imgur.com/IDYTw4h)

Also a screenshot for details of some inner parts:
[](https://imgur.com/GEWmTev)
## Post #27
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-05-18T00:19:00+00:00
- Post Title: Re: Reverse Model Wireframe

> Reply from Bigchillghost
>
> Seems I found the ultimate solution
Your being such a bad tease, I always dreamed of something like this to be done and be takes seriously, now your just making it worse, in a good way obviously.
Hundreds of people that wonder around forums like this are simply clueless as to what developers like yourself are doing, we do not understand, myself included, nor know code/programming/scripting languages etc etc etc, we simply use amazing tools that others, like yourself, are good at it and create for use.
So I hope you have thought about something as to make it work for all of us, if your really serious about it.
For example a scenario would be, you import your desired skinned mesh in 3dsMax, you know with bones/weights and all, and you just quadrangulate it as it was initially created, because from an artistic perspective quads are desired and far superior to triangles, since triangles is only needed in-game by the GPU.

I honestly hope you consider it, I hope more join in to express they're opinion, because this thing your doing is simply fantastic and I personally dream about it for a few years now, since I discovered this world of 3D possibilities.

My honest and humble opinion, thank you.
## Post #28
- Username: sfc123
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Nov 10, 2014 2:25 am
- Post datetime: 2019-01-08T06:28:41+00:00
- Post Title: Re: Reverse Model Wireframe

well done~~
## Post #29
- Username: xman2000
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Sep 26, 2019 2:23 pm
- Post datetime: 2019-09-26T20:09:12+00:00
- Post Title: Re: Reverse Model Wireframe

> Reply from Bigchillghost ↑Thu May 17, 2018 11:46 pm at Thu May 17, 2018 11:46 pm
>
> 
Seems I found the ultimate solution  :
hi i sent pm to you.
you upload this project in some place?
you can share this UltimateSolution please?
and a tutorial of complete process softwares you used and starting open the 3d model, extract wireframe and use your algorithm to Quadrangulate?
thanks.
## Post #30
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-09-27T15:06:30+00:00
- Post Title: Re: Reverse Model Wireframe

> Reply from xman2000 ↑Fri Sep 27, 2019 4:09 am at Fri Sep 27, 2019 4:09 am
>
> 
you can share this UltimateSolution please?
It's the "ultimate" solution for that specific model, which can't be compatible for every single case.

> Reply from xman2000 ↑Fri Sep 27, 2019 4:09 am at Fri Sep 27, 2019 4:09 am
>
> 
and a tutorial of complete process softwares you used and starting open the 3d model, extract wireframe and use your algorithm to Quadrangulate?
I don't think there'll be any "tutorial of complete process" since the entire project is still pretty much a rough idea. And honestly I'd prefer to inspire people with this possibility rather than to teach them how to achive it.
## Post #31
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-03-01T12:04:30+00:00
- Post Title: Re: Reverse Model Wireframe

It has been a while since the last time I posted something related to this topic. But before I post anything new, I'd like to make a simple summary of the old stuff about this topic.

As you may know, currently there're two tools I made are available in this forum that come with a quadrify feature. You can find them in the following posts in case you're interested in an attempt:

[GSTDQuadifyer](viewtopic.php?p=140100#p140100)

[A9Tool](viewtopic.php?f=16&t=18782)

Both of the quadrify method in these tools are based on a simple fact: the meshes they're dealing with have amost ideal face buffers, where almost every two triangles that should form a quadrilateral are placed in the buffer continuously. So there's even no need for a second thought about how to perform the quadrify process.

For those game models where mostly every two of these triangles are separated in discrete positions in the buffer, I came up with this 'unreliable' idea which was described in this [post](viewtopic.php?p=140515#p140515). 

This method requires you to first manually find some quads with your judgement on its topology and figure out the 'filter rules' they followed. Then try to quadrify them with these found rlues through programing. It sounds logically unreliable but it does work for some cases as shown [here](viewtopic.php?p=140194#p140194) and [there](viewtopic.php?p=140518#p140518). Maybe there do exist some kind of regular patterns if the original quads are simply split into triangles based on the orientation of the faces' vertex indices. But I can't imagine a way to mathematically prove it.   

So, I've been working on a more universal method that's built upon some actually practical rules ever since: uniform and good topology. It's a dynamic and flexible system that allows you to specify how you want these rules to be applied. By changing the available parameters it can produce different results, and so as the side effects. 

I'm not going to explain it in depth but merely to give an overall idea here. 
The main idea of this method is to quadrify starting from those triangles which are known in certain ways to form quads with their neighboring triangles. I defined 3 types of such triangles and for properly referring I'll name them as pointcut type 1, 2 and 3. All these pointcuts are chosen from the border of the mesh, as it's easier to distinguish. The quadrify process is then performed outwards the two sides of these pointcuts along the border. When the first round is done, the new border is created by ignoring the triangles that have been processed. And so on all triangles should be handled since this process is theoretically convergent. Of course the settings of the parameters could result in termination before all triangles are processed, as that's what it is capable of at its best.

To demonstrate this algorithm here's a test I've done on a head mesh from RE7. For easier observation I replaced its UVs with the positions.

First image will be the original mesh:


zoom in:


Here's the result of quadrifying with pointcut type 1 only:


The white areas are the pointcuts, which were handled firstly. The green and red areas are staggered after them. The black areas are what havn't been covered yet.

zoom in:


Here's the result of quadrifying with pointcut type 2 only:


zoom in:


And here's the result of quadrifying with pointcut type 1 mixed with type 2 at the same time for each round:


zoom in:


Here's the result of quadrifying with pointcut type 1 first, and with type 2 when no pointcuts of type 1 can be found in current state, and with type 1 again when no pointcuts of type 2 can be found an so on:


zoom in:


Here's the result of quadrifying with previous method but with also pointcut type 3 in the switching list:


The blue areas are pointcuts of type 2, and the yellow areas are pointcuts of type 3.

zoom in:


Here's the result of the quadrify option of 3DS Max:


zoom in:


To further compare the previous result with it, here's the comparison under the wireframe view (2nd image for 3DS Max):

- overall:



- zoom in:



As you can see, this new algorithm has better performance than the Quadrify option in 3DS Max in terms of these areas it has covered. Currently its parameters control how you find these pointcuts, when you use them, how you switch between different types of pointcuts, and how you determine a quad to be a 'correct' one. By changing these values, this algorithm can accordingly change its behavior, so as to produce different results. Of course there're still some issues which might be possible to be fixed later.

For instance, there're some dis-located quads that result in those red triangles which were supposed to be treated as two quads.


One possible way to fix this issue is by providing a mechanism to check all the remaining triangles after the process is finished and determine if they're supposed to be handled as quads instead of triangles, and do some patching procedure like this:



That's still just an idea and a TODO thing in the future though.
## Post #32
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-03-08T06:57:00+00:00
- Post Title: Re: Reverse Model Wireframe

Another quick test on a mesh part:
## Post #33
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2020-03-13T10:36:12+00:00
- Post Title: Re: Reverse Model Wireframe

mr.Bigchillghost could u please activate PM? ive something to ask
## Post #34
- Username: ashitaka3369
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jun 29, 2019 5:39 am
- Post datetime: 2020-03-13T11:10:16+00:00
- Post Title: Re: Reverse Model Wireframe

everyone who use Quadrangulate (maya),quadrify(max) or the blender option , is actually dreaming about that tool
congratulation amazing work
## Post #35
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2020-06-22T09:55:48+00:00
- Post Title: Re: Reverse Model Wireframe

@Bigchillghost thanks for the researches!
can you update GSTDQuadifyer to work with FBX or even make a noesis plugin?
I often use noesis console commands to easily convert models
## Post #36
- Username: behrang
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Nov 06, 2015 5:23 pm
- Post datetime: 2021-01-22T07:15:29+00:00
- Post Title: Re: Reverse Model Wireframe

> Reply from Bigchillghost ↑Sun Mar 08, 2020 2:57 pm at Sun Mar 08, 2020 2:57 pm
>
> 
Another quick test on a mesh part:

how could we have this tool in 3ds max or as a standalone exe?
## Post #37
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-01-24T11:59:41+00:00
- Post Title: Re: Reverse Model Wireframe

> Reply from behrang ↑Fri Jan 22, 2021 3:15 pm at Fri Jan 22, 2021 3:15 pm
>
> 
how could we have this tool in 3ds max or as a standalone exe?
It's not yet a tool. Everything is still experimental. And the research had been paused for a long time ever since that post was made. Though I shall return to it in the near future. Just a matter of time.
## Post #38
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-01-23T06:15:21+00:00
- Post Title: Re: Reverse Model Wireframe

Was wondering if you still consider this technique new algo you developed for quads from tris as a modifier perhaps for 3dsMax, where we could try it on any given imported triangulated geometry, would really be useful.
## Post #39
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-01-23T16:05:47+00:00
- Post Title: Re: Reverse Model Wireframe

Well, what a surprise anniversary reminder. Happy New Year mono24!  

But the project has been on hold ever since, well, a year ago, and it's too soon to ask for any tool given that I have no idea where the research might lead. Yeah a Max utility would be great but it means that I'll have to learn Max Script/Max Python and the way to implement it so no, there's no such plans.
## Post #40
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-01-23T17:04:18+00:00
- Post Title: Re: Reverse Model Wireframe

> Reply from Bigchillghost ↑Mon Jan 24, 2022 12:05 am at Mon Jan 24, 2022 12:05 am
>
> 
Well, what a surprise anniversary reminder. Happy New Year mono24!  ...
Yes indeed, I decided to do it as such, I said, well why not, so here we are 

And I am sad to hear it will not come to fruition, thank you for responding, I can now at least move on and try to find other alternatives, if any.
## Post #41
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-01-23T21:02:02+00:00
- Post Title: Re: Reverse Model Wireframe

> Reply from Bigchillghost ↑Mon Jan 24, 2022 12:05 am at Mon Jan 24, 2022 12:05 am
>
> 
Well, what a surprise anniversary reminder. Happy New Year mono24!  

But the project has been on hold ever since...
Another full year has passed, Happy New Year! Bigchillghost, hope your well.

Still hoping the project hasn't fully died out, fingers crossed.
## Post #42
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-01-25T08:30:48+00:00
- Post Title: Re: Reverse Model Wireframe

> Reply from mono24 ↑Tue Jan 24, 2023 5:02 am at Tue Jan 24, 2023 5:02 am
>
> 
Still hoping the project hasn't fully died out, fingers crossed.
It's not dead. I shall continue the research in the first half of the year, just not a top priority at the moment.
## Post #43
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-10-15T18:00:55+00:00
- Post Title: Re: Reverse Model Wireframe

> Reply from Bigchillghost ↑Wed Jan 25, 2023 4:30 pm at Wed Jan 25, 2023 4:30 pm
>
> 
It's not dead. I shall continue the research in the first half of the year, just not a top priority at the moment.
The forum will be gone in no time, is there anywhere some of us can continue to follow your progress/work at all, i sure hope there is/will be?
It is sad news for the whole community.

And on the topic at hand, has there been any work on the option to have something for triangle to quads as either standalone or3dsMax plugin or anything at all you might consider?
## Post #44
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-10-16T11:40:08+00:00
- Post Title: Re: Reverse Model Wireframe

> Reply from mono24 ↑Mon Oct 16, 2023 2:00 am at Mon Oct 16, 2023 2:00 am
>
> 
The forum will be gone in no time, is there anywhere some of us can continue to follow your progress/work at all, i sure hope there is/will be?
I havn't posted my research anywhere else other than here. But I've hosted some of my projects on [Github](https://github.com/Bigchillghost?tab=repositories) (binaries only). Will see how things go in the future.

> Reply from mono24 ↑Mon Oct 16, 2023 2:00 am at Mon Oct 16, 2023 2:00 am
>
> 
And on the topic at hand, has there been any work on the option to have something for triangle to quads as either standalone or3dsMax plugin or anything at all you might consider?
Sadly no, there's no progress since not until recently have I put it on the agenda. I don't think either a standalone or a max plugin would be an easy task but that's not the problem to worry about yet, not until there's a working solution.
## Post #45
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-10-16T18:55:15+00:00
- Post Title: Re: Reverse Model Wireframe

> Reply from Bigchillghost ↑Mon Oct 16, 2023 7:40 pm at Mon Oct 16, 2023 7:40 pm
>
> ...Sadly no, there's no progress since not until recently have I put it on the agenda. I don't think either a standalone or a max plugin would be an easy task but that's not the problem to worry about yet, not until there's a working solution.
Genuinely sad to hear that, and for what is worth, thank you for everything you've done for the community, regardless of all ups and downs the community has had and will continue to have, truly thank you.
