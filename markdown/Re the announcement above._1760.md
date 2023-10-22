## Post #1
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-03-05T14:02:03+00:00
- Post Title: Re the announcement above.

Hi Everybody, 
What Mr. Mouse said above is exactly what is planned. To further support this, already cool XeNTax site and forum, I decided to contribute something more than merely my presence. I also do that to gain some more exposure and experience in this subject matter. 

Time and my skills permiting I would attempt to assist anyone wanting to mod something in the games. It is a trial thing because we are unsure if it would fly. So if you have something you wanted to mod, try to make new 3D model, repaint the texture or just have a question - post it here.

And go on me easy and try do not shoot me down right on the start, with some time I might get at it better as we go.

Best regards 
Xela aka Polak
## Post #2
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2006-03-06T05:18:25+00:00
- Post Title: Re the announcement above.

I will definitely be visiting this section!
## Post #3
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-03-06T12:01:52+00:00
- Post Title: Re the announcement above.

The other area of my interest  is game 3D terrain. Mostly outdoor terrain for this matter, but indoor levels too. How its made in the game,  what files are responsible for it, what algorythm was used, heightmaps, bumpmaps, lightmaps, blending, multitxturing, tiled terrain with repetable tiles, photoreal terrain with contineous stream of data, how to make seamless tiles 2-way, 4-way.

What makes outdoor terain convincing, what not, sky and water, clouds and waves, new trends in making vegetation look realistic, how to make roads, urban settlements, fields and forrests etc., etc.      

Tricks and techniques, 3D engines, terrain editors, other  tools and utilities  ... all that and simillar stuff.
## Post #4
- Username: OneOneSeven
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Jul 16, 2006 1:54 pm
- Post datetime: 2006-11-11T02:04:13+00:00
- Post Title: Re the announcement above.

> Reply from Xela
>
> The other area of my interest  is game 3D terrain. Mostly outdoor terrain for this matter, but indoor levels too. How its made in the game,  what files are responsible for it, what algorythm was used, heightmaps, bumpmaps, lightmaps, blending, multitxturing, tiled terrain with repetable tiles, photoreal terrain with contineous stream of data, how to make seamless tiles 2-way, 4-way.

What makes outdoor terain convincing, what not, sky and water, clouds and waves, new trends in making vegetation look realistic, how to make roads, urban settlements, fields and forrests etc., etc.      

Tricks and techniques, 3D engines, terrain editors, other  tools and utilities  ... all that and simillar stuff.

Here's an explanation of what you were wondering about. It's long, so I blocked it out. I would reccommend having a look at the Crysis screenies, they're real beauts. 

```

-An actual model. This is probably one of the more common ways of creating interior areas, and the result can look very good with a little shader work and use of detail maps (this is the multitexturing thing at work, essentially a mini-texture is tiled all over every surface of a given material. This was used a lot in Halo 1, for example if you look at the Chief's armor/hands you'll notice little speckles.) can look pretty good.

-Heightmaps. This is really the best way of handling outdoor terrain, as they generally don't give the straight-lines look of models. Essentially what the engine will do is load an image (usually black and white, with white traditionally the maximum height and black the lowest.) and then move vertices up or down a certain amount to match the 'height' of a pixel. You may know this as displacement mapping. Generally they aren't too real-time render friendly, especially with shadowing (ick I'd hate to see my GPU try and use shadow volumes on these :cry:) Typically devs will get around this by lightmapping, or essentially having the tool they made trace a bunch of light and see where it ends up beforehand, then saves the lightness/darkness to an image file where it is then blended with the actual textures themselves. The disadvantage of this is that dynamic lights in the level really play havoc with this and makes the shadows it generates useless. The other, newer approcah is to normal map the entire thing. All of the shading, none of the cycle-hungry tangent calculations. The downside to this approach is that the terrain won't cast shadows on itself, however it will be shaded correctly. The end result still looks pretty good, take Oblivion for example.

-My solution. (I'm surprised I haven't seen anyone think of this, although it may be less practical with ultra high-detail meshes) Parallax occlusion map the entire thing. You have the advantage of normal map lighting with the (soft!) shadowing of lightmaps. Oh, did I mention that it's very possible to update those shadows in realtime?

-BSP/Octrees. These are basically a bunch of blocks, as seen in Half-Life 1/2, Quake, etc. Generally these are very limited in realism but are very friendly towards collision detection. Newer games added the ability to modify segments of these, (e.g. pull up the corner of your block) but ultimately these will probably die out with the advent of physics cards. BSP's also are pretty good at improving framerate, as they offer a sort of built-in culling system.

As for the other stuff-- Tiled things work on the same principle of seamless textures-- the edges match up. Not a whole lot to explain here. Vegetation, however, is looking a lot better with the advent of DirectX 10. You may or may not have heard of a game called Far Cry, this is probably the best foliage system out there ATM (Oblivion looks nice, yes, but Beth loses a lot of points for making each piece of grass about 20 polygons. Bad modeller! *whap*) The sequel, however, blows it out of the water. Feast your eyes:
http://www3.incrysis.com/screenshots/061111-1.jpg
http://www3.incrysis.com/screenshots/061111-2.jpg
http://www3.incrysis.com/screenshots/061111-4.jpg
http://www3.incrysis.com/screenshots/061108-3.jpg
http://www4.incrysis.com/screenshots/061003-1.jpg
http://www3.incrysis.com/screenshots/0609009-1.jpg
http://www3.incrysis.com/screenshots/crysis-hud.jpg
http://www3.incrysis.com/screenshots/crysis-jungle-korean.jpg
http://www3.incrysis.com/screenshots/061111-3.jpg

Yep, that's all ingame. Most of this is made possible through a total rewrite of DirectX, wich removes something like 50% of all total function calls. Expect things like Depth of Field, Sub-Surface Scattering, the complete redundancy of parallax mapping due to geometry shaders, and all sorts of other cool stuff. For those of you who liked the Dawn demo, you've been owned. Again.

There's also a lot of stuff I haven't covered, but all in all this should give you a pretty good idea of what you're doing. Good luck :)

```


It's been a bit since I've been around here but if anyones needs any (C++) coding advice or info on how the game engines actually *work,* feel free to send me a PM or whatever. I'm making pretty good headway on my own 3D engine, perhaps you fellas here might be able to help me design some model/texture/archive formats   I realize I don't know everything, but if you need to know about graphics, I'm your guy!
## Post #5
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2007-01-07T00:20:42+00:00
- Post Title: Re the announcement above.

OneOneSeven, 
your post was made as way back as Nov11. It took me more than a month to notice it   .Sorry. Your stuff quoted is mind bogling especially jungle scenes. The prerendered lighting  simply incredible. 
So thank you and I hope you around here to hear that. 

Actually, I have a question regarding programing of graphics , but rather related to older 8bit games. In some of them it appears that any attempt to increase the resolution of graphics by increasing size of the texture fails miserably. New strange artifacts are being introduced and the textures look scrambled. 

So my question is this: were the old graphics resolution fixed? Color deoth I understand but I thought that the size could be manipulated as long as the textures were in separate files. Do you have possibly any information about that? Game in question TAW by DiD.
## Post #6
- Username: OneOneSeven
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Jul 16, 2006 1:54 pm
- Post datetime: 2007-01-09T03:00:45+00:00
- Post Title: Re the announcement above.

No worries. My own knowledge of the subject has grown somewhat, so if anything, it may be a bit better for you ^_^
On to the solution--

This is a testament to how far games have come. You have a double conundrum on your hands here. First off, about 99.9% of these kinds of games were designed well before the dawn of the modding era, even before such action was somehow considered heresy by the developer community. It wasn't done. Nowadays such productions are very commonplace, and game devs have listened to the voice of the community and modified their work likewise. As an added side benefit, a large portion of the engine/game code is very reuseable. Consider this-- At its heart, Valve's Source engine still has pieces of Quake (yes, Quake 1) in it. Mmmmmm, chewy. Why's this important? The various functions and the like were designed to read from one *specific* texture. During development, adding new art assets would still be relatively simple as all the programmers would have to do would be shift a few numbers around. The weirdness you're experiencing sounds like the file parser kept writing into RAM past where the original should have ended. This means that pointers that relied on the memory in a specific location now have a bunch of garbage, which gets interpreted into visual weirdness. It's kind of like what happens when you use uninitialized variables, e.g. you have no idea what the hell is left in there. Try couting or printfing a character array or something that you don't set a value to.

The other consideration is that you're applying what are relatively recent concepts to older games. The nifty little auto-scale trick was introduced with DirectX/later versions of OpenGL, and, alas, it only works on 3d models with UVW coordinates. These are a pretty smart idea, as values are stored as fractions of the length and width of your texture as opposed to actual preset numbers of pixels.

If you'd like to overhaul the game, things should still be relatively easy. Most of the source code for them is freely available, and modifying things to suit your needs shouldn't pose a whole lot of a problem. That being said, it is something of a leap for a C/C++ newcomer, as some of the advanced concepts, such as classes , compiler directives , pointers and more complex data types (4-D vectors, anyone? anyone?)  can be something of a noob-eater. As you may have guessed, these are very integral parts of game programming XD

You could also go the way of Chex Trek and port classics to newer game engines  Personally I think this is one of the better solutions as there are a lot of newer technologies (such as z- or depth-buffering) that make a lot of stupid little hacks (in this case, starting the drawing of on-screen objects from the furthest from view to closest to avoid that little perspective goofiness thingy. It gets to be a headache when you consider that you have to plan your render algorithm with a model, level geometry and particle system in mind, each done in separate passes!) unnecessary. This also frees up a lot of processing time that would otherwise have been spent on, say, determining the distance for every triangle currently viewable, let alone the surface normal. This, in turn can be spent on other little gimmicks like weapons requiring reloading, AI, and ye olde standby, pretty visuals.
## Post #7
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2007-01-09T03:24:17+00:00
- Post Title: Re the announcement above.

Very interesting , but still need more passed over this reply to undertstand all. Any way mucho grazias indeed   .

About that weirdness in display of bumped texture here is the sample I should perhaps bring before. 



Notice, that only 1/4 of the texture is read no matter what and then those strange skew on the grid. My "side" theory is that that skew is on purpose to simulate sort od waves and make the sea texture (where the test was performed) more in variance from one another. On the right hand cormer is some sort of "wave" heightmap, but that is little different story. 

So I guess there is strict limitation of the buffer for texture read. Any ide if this can be adjusted without the Source?
## Post #8
- Username: OneOneSeven
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Jul 16, 2006 1:54 pm
- Post datetime: 2007-01-09T04:00:55+00:00
- Post Title: Re the announcement above.

I'd be willing to bet you're spot on with the wave idea. Cheap yet pretty effective trick, that really wouldn't have anything to do with the actual loading process as far as I can tell.

As for modification:
Depends if you have any knowledge of ASM, aka assembly language (Human-readable machine code. This is reeeeally low level, on that of issuing individual CPU hardware instructions.) You could decompile the executable, such tools do exist. Other than that, I don't think so.

Also, don't be too worried if you don't understand everything at once. I was in a very similar situation with some of the vital mathematics of 3d space, but after a day or two I found all my troubles had disappeared 

EDIT:
This is something of an afterthought, but I can pull up a really good tech presentation by ATi on doing a convincing approximation of skin. A lot of the same techniques could in theory be used to create realistic vegetation. It isn't exactly along the lines of Crysis, but it is pretty good, as well as runs on current-generation (DX9) hardware. Combine it with boatloads of instancing and you may actually end up with something playable 

And as a belated Christmas/Hannukah/whatever gift, I bear more screenies, this time from a game called Alan Wake, made by the people who did Max Payne:
[http://www.alanwake.com/screenshots/scr ... e_2006_004](http://www.alanwake.com/screenshots/screenshot.php?shot=Alan_Wake_2006_004)
[http://www.alanwake.com/screenshots/scr ... e_2006_020](http://www.alanwake.com/screenshots/screenshot.php?shot=Alan_Wake_2006_020)
[http://www.alanwake.com/screenshots/scr ... e_2006_003](http://www.alanwake.com/screenshots/screenshot.php?shot=Alan_Wake_2006_003)
[http://www.alanwake.com/screenshots/scr ... e_2006_002](http://www.alanwake.com/screenshots/screenshot.php?shot=Alan_Wake_2006_002)

I believe the sound you just heard was that of Crysis crashing and burning (at least for outdoor environments, we shall find out about gameplay pretty soon.)
## Post #9
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2007-01-10T05:55:53+00:00
- Post Title: Re the announcement above.

It makes sense for it to be an engine limitation, huge size texture where unthinkable in the times where 32 or 64 mb of memory was a commodity ;)

I don't know what size texture you are trying to use thought.

depending on the tessellation the skew you speak of could be a wave effect or artifacts from affine texture mapping, that is applying a 2d surface into a 3d surface wihtout taking into account perspective
## Post #10
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2007-01-10T06:30:22+00:00
- Post Title: Re the announcement above.

One more example how those textures were mangled. Original was somethinglike 92x92 and I doubled it. Here I distinctly remember that I numbered the texture with equally spaced numbers like this:
123
567

I got only 12 and that 2 already badly deformed? 
Ugly anyway.   Wanted to make prettier.
## Post #11
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2007-01-10T06:53:41+00:00
- Post Title: Re the announcement above.

doubling a texture resolution basically adds 4 times the data, that may be why you are getting only 1/4 of the picture so the resolution is locked :(



original resolution
1(think of this as a square)

to enhance one needs to add 1 3 times to maintain the same aspect ration

12
34

3 times as big will be
123
456

so effectively you need 4 times the space just to double the resolution!
## Post #12
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2007-01-10T12:40:59+00:00
- Post Title: Re the announcement above.

> so effectively you need 4 times the space just to double the resolution!
That is obviously correct. But what throws me off here is that strange deformation of "2". I would expect to see croped texture , but with aspect ratio maintained. 
My previous mention about that "wave" displacement alpha map may have something to do with it, but still something is not right (or expected) how the program "trims" excess pixels.   

I try to make another yet example on land to see what happens then.
## Post #13
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2007-01-10T21:32:40+00:00
- Post Title: Re the announcement above.

> Reply from alera
>
> 3 times as big will be
123
456

so effectively you need 4 times the space just to double the resolution!
Pardon my intrusion, but if you triple the size of an image, it would be
123
456
789

not
123
456
## Post #14
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2007-01-10T22:03:48+00:00
- Post Title: Re the announcement above.

oops lol thanks for correcting me dinoguy
## Post #15
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2007-01-10T22:06:45+00:00
- Post Title: Re the announcement above.

Hey, don't mention it...
## Post #16
- Username: OneOneSeven
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Jul 16, 2006 1:54 pm
- Post datetime: 2007-01-10T23:09:32+00:00
- Post Title: 

> Reply from Xela
>
> so effectively you need 4 times the space just to double the resolution!
That is obviously correct. But what throws me off here is that strange deformation of "2". I would expect to see croped texture , but with aspect ratio maintained. 
My previous mention about that "wave" displacement alpha map may have something to do with it, but still something is not right (or expected) how the program "trims" excess pixels.   

I try to make another yet example on land to see what happens then.

Ima say that it just stops reading after a certain point. Essentially what happens is the program opens the file, reads the RGB values for a 64x64 texture and then just quits.
## Post #17
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2007-01-11T05:24:29+00:00
- Post Title: 

> Reply from OneOneSeven
>
> 
Ima say that it just stops reading after a certain point. Essentially what happens is the program opens the file, reads the RGB values for a 64x64 texture and then just quits.

yup, and if it doesn't and actually reads pass its pre-allocated buffer then the program would crash sooner or later


--
Sorry I didn't read your post in detail before OneOneSeven.

I just wanted to clarify something, BSP and Oct  trees are spatial subdivision schemes and are not used for rendering terrain at all

spatial subdivision is a very interesting and vast topic, it is a way for an engine to classify the data in order to proccess it efficiently and a crucial part of a game engine.

an quad tree, oct tree, bsp tree or kd-tree is basicaly a hierarchical tree with distance as it's base. The engine uses this to know with what object a moving object could potentionaly hit or for visibility determination, it is mainly used to speed up the process of picking

here is an example of a scene with spatial subdivision, lets say we want to test if object A collided with something
__________
|A......|.....B|
|C......|.......|
--------------

in the above example object A and C are in cell 1 and object B is in cell 2.
Traditionally the computer would have first tested to see if object A collides with object B and then repeat the same test with object C. but with spatial subdivision it only checks object C as B is in another cell and therefore can't possibly collide with object A.

we skipped one test :) hurray!
as scenes grow more complex, the need for quickly discarding unneeded tests becomes crucial. 

oct trees are in heavy use todays engines.
As OneOneSeven says bsp is an old method with many shortfalls
I believe it actually stands for Binary Space Partition :) and it was made for the original quake engine.

Sorry for the lengthy post :) I just thought it would be interesting.
## Post #18
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-01-11T19:00:06+00:00
- Post Title: 

What i can say?   
Really nice post, thanks
## Post #19
- Username: OneOneSeven
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Jul 16, 2006 1:54 pm
- Post datetime: 2007-01-11T21:47:00+00:00
- Post Title: 

You're correct, alera. Thanks for pointing out my error--

To clarify, a BSP tree refers to a technique involving the creation of 'blocks' and then categorizes them in to certain 'branches' and 'leaves' based on visibility. What I've primarily been referring to there are the brushes, or rectangular prisms that constitute the actual level geometry. While limited in scope, it can be used for terrain-- HL2 does a passable job at it, but they're primarily made for indoor environments. Feel free to correct me if I'm wrong, but I believe the concept was originally implemented in Quake. The simple levels and limited power of the GPU lent itself well to the system. Now that I think about it, Doom 3 uses a similar method as well, although it's been hybridized with model entities using per-polygon collision.

The collision detection thingy is pretty neat, too. Instead of checking EVERY piece of geometry (which would take quite a while!) for a collision, your area is chopped up into segments. The engine then uses a binary search pattern to determine which area you're in (I think around 8-ish standard initial divisions for octrees, likewise for quad. Once again correct me if I'm wrong.) and then progressively whittles away at the segments until it finds what you hit. Very efficient, and works along the principles of the numbers game, if you're having trouble visualizing it.

There are other nifty methods of testing, such as axis-aligned bounding boxes (the potential movements of the objects are checked against lines in three different perspectives, theoretically could be implemented/optimized to use two) and bounding spheres (Is the object's center within this distance of our origin? It is? Boot it.) You can also use planes, which is essentially a simplified version of a-abb.

Speaking of interesting search algorithms, I read a fascinating article on the AI of F.E.A.R. It uses an A* search algorithm that constantly determines the most efficient way of killing you, the player, based on conditions like cover, current status, ammunition, player facing, etc. Other enemies can and do actively work together to bring you down. Absolute genius, wondering if I can somehow improve upon the process. If you haven't checked out the game, do so (be advised that you need a reasonably capable computer!) as the AI, storytelling and atmosphere is top-notch. Beats out Halo overall in my opinion, and coming from a Halo fan, this means something (Bonus points if you already knew this. If you don't know what I'm referring to then don't bother.)

EDIT: Whoops, didn't see you already posted the Quake thingy XD.

And yes, BSP stands for Binary Space Partition. In plain English, it keeps halving the divisions(partitions) of space.

EDIT 2:

> Reply from alera
>
> doubling a texture resolution basically adds 4 times the data, that may be why you are getting only 1/4 of the picture so the resolution is locked 



original resolution
1(think of this as a square)

to enhance one needs to add 1 3 times to maintain the same aspect ration

12
34

3 times as big will be
123
456

so effectively you need 4 times the space just to double the resolution!

FYI it's exponential. 2^n
## Post #20
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2007-01-13T03:01:54+00:00
- Post Title: 

> Reply from OneOneSeven
>
> 
Speaking of interesting search algorithms, I read a fascinating article on the AI of F.E.A.R. It uses an A* search algorithm that constantly determines the most efficient way of killing you, the player, based on conditions like cover, current status, ammunition, player facing, etc. Other enemies can and do actively work together to bring you down. Absolute genius, wondering if I can somehow improve upon the process. If you haven't checked out the game, do so (be advised that you need a reasonably capable computer!) as the AI, storytelling and atmosphere is top-notch. Beats out Halo overall in my opinion, and coming from a Halo fan, this means something (Bonus points if you already knew this. If you don't know what I'm referring to then don't bother.)

lol I remember halo :) quite repetitive but the ai was something fun :D!

I don't remember what was the name of the toughest difficulty but the friendly ai was horrible >.< I gave up on finishing the game at top difficulty because of it :( jumping around like a rabbit trying to have an overview of what was happening while trying to get the captain out of the ship wasn't fun at all

I heard of F.E.A.R but I am much more inclined towards prey, maybe because portal engines have always intrigued me, not as much for it's 0 overdraw but because of the illusion it can create :) oh and the "useless" interactivity that I love so much

however my pc is currently only a work station and I played neither :P bleh

> Reply from Savage
>
> 
What i can say?
Really nice post, thanks
cool :)

--
LOL when I search the internet to check if wolfenstain was spelled correctly I came across something rather amusing [http://en.wikipedia.org/wiki/Castle_Wolfenstein](http://en.wikipedia.org/wiki/Castle_Wolfenstein)

look at the graphics improvements the commodore 64 had!(I seriously thought Wow!)

and it is game programmed mostly in underpants! haha
